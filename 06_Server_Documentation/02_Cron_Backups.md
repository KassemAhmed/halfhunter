## Utilization
Phuse VPS is currently backing up databases and uploads via a cron job.

All cron scripts are stored in a [bitbucket repo](https://bitbucket.org/thephuseteam/vps-cron-scipts) and are `git pull` from `/home/deploy/vps-cron-scipts`.

### Backup Database Script help

    ------------------------
     Backup Database Script
    ------------------------
    Example:
      /home/deploy/vps-cron-scipts/backup-database.v1.sh -s [sitename] -d [dbname]

    Backup Script Options:
      -s Site name [required]
      -d Database name [defaults to sitename if no parameter is provided]
      -t Database type (mysql/mongo) [defaults to mysql]
      -f Backup filepath (/var/www/sitename/wp-content/uploads)
      -m Max backups that are kept [defaults to 30]
      -h Help

### Current cron job for phuse.ca

    0 23 * * * /home/deploy/vps-cron-scipts/backup-database.v1.sh -s phuseca -f /var/www/phuseca/wp-content/uploads

`0`  Minute
`23` Hour
`*`  Day
`*`  Month
`*`  DoW (day of the week)

`*` means all


### Add a new cron backup job for a site

- Log into [ajenti](https://staging.thephuse.com:8000/).
- Click on Cron tab.
- Select `deploy` from user list and click select.
- Change the frequency job (most likely something like `1 23 * * *`).
- Paste in path to shell script `/home/deploy/vps-cron-scipts/backup-database.v1.sh`
- Add after script path the needed parameters
  - Site name `-s mysitename` - __Required__
  - Database name `-d mydatabasename`
  - Database type if not mysql `-t mongo`
  - Backup file path `-f /var/www/sitename/backupthis`
  - Max backups that are kept on the server `-m 30`

You can also add cron jobs via the CLI.

SSH info server

    ssh deploy@phuse.ca

Enter cron editor

    crontab -e

Add job on new line

    1 23 * * * /home/deploy/vps-cron-scipts/backup-database.v1.sh -s phuseca