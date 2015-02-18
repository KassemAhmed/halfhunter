## Phuse VPS Setup

### Create deployer group and add deployer

    sudo addgroup deployer
    sudo adduser deploy deployer

### Add public ssh key to deploy user

    cat ~/.ssh/id_deploy_phuse.pub | ssh deploy@staging.thephuse.com "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"

### Install Ajenti

    wget -O- https://raw.github.com/Eugeny/ajenti/master/scripts/install-ubuntu.sh | sudo sh

Installed Ajenti-V
    
    sudo apt-get install ajenti-v ajenti-v-nginx ajenti-v-mysql ajenti-v-php-fpm php5-mysql

Installed D-bus for PHP-FPM service communication with Ajenti-V

    sudo apt-get install dbus
    sudo service ajenti restart

### Install LAMP

    sudo apt-get install lamp-server^

- Set root mysql password within setup

- enable rewrite

        sudo a2enmod rewrite


### Chang SSH port number

    4607

### Lock down /var/www to root:deployer

    sudo chown root:deployer /var/www
    sudo chmod 755 /var/www
    sudo chmod g+s /var/www

### Setup www-data ssh key for git hook deployments
    
    sudo mkdir /var/www/.ssh
    sudo chown www-data:deployer /var/www/.ssh
    sudo chmod -R 700 .ssh
    sudo -u www-data ssh-keygen

### Install Node.js and npm

    sudo apt-get install nodejs && sudo apt-get install npm

### Install Pip for python and Python dev packages
  
    sudo apt-get install python-pip
    sudo apt-get install build-essential python-dev

### Install MongoDB

Import public key for package management system

    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10

Create list file for MongoDB

    echo 'deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' | sudo tee /etc/apt/sources.list.d/mongodb.list

Reload package database

    sudo apt-get update

Install latest stable version of MongoDB

    sudo apt-get install -y mongodb-org

Pin versions of MongoDB so they are not updated accidentally

    echo "mongodb-org hold" | sudo dpkg --set-selections
    echo "mongodb-org-server hold" | sudo dpkg --set-selections
    echo "mongodb-org-shell hold" | sudo dpkg --set-selections
    echo "mongodb-org-mongos hold" | sudo dpkg --set-selections
    echo "mongodb-org-tools hold" | sudo dpkg --set-selections

Install pymongo for Ajenti management

    pip install pymongo

### Install rbenv and ruby

Install rbenv

    sudo apt-get install rbenv

Install ruby-build to install ruby versions through rbenv

    git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build

Install version 2.1.4 of ruby (use verbose because it takes awhile)

    rbenv install --verbose 2.1.4
