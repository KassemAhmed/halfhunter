Monit is a small Open Source utility for managing and monitoring Unix systems. Monit conducts automatic maintenance and repair and can execute meaningful causal actions in error situations.

Find out more info at [mmonit.com](http://mmonit.com/monit/).

--------------
## Utilization
Phuse is currently using Monit to monitor phuse.ca vps services. If one of the listed services becomes unavailable it is then killed and restarted by monit.

## Currently Monitored

- System
- Processes
  - mysqld
  - mongodb
  - crond
  - apache
- File
  - mysql_bin
  - mysql_rc
  - cron_bin
  - cron_rc
  - apache_bin
  - apache_rc
- Directory
  - cron_spool
- Host
  - phuse [phuse.ca:80]
  - handbook.phuse [handbook.phuse.ca:80 status 500]
  - staging.phuse [staging.phuse.ca:80]

## Check status of services with monit

You can access the status through the command line from ssh

    sudo monit status

or you can access the [web interface](http://107.155.108.65:2812/) in your browser

## Add a new service to monit

Add new service config file to the config directory

    sudo vim /etc/monit/monitrc.d/

Then symbolic link it

    sudo ln -s /etc/monit/monitrc.d/[config-file] /etc/monit/conf.d/[config-file]

Reload monit

    sudo monit reload

or add new monitor

    sudo monit monitor [service name]

## Send Notification to Slack #monit
    
Anything that is monitored can have the notifications pushed to the #monit channel in Slack. All that needs to be added is this after a check

    if failed
      then exec /opt/monit/slack-check.rb

Example for checking a url

    check host phuse with address phuse.ca
      if failed
         port 80
         protocol http
         request "/"
         timeout 10 seconds
         then exec /opt/monit/slack-check.rb