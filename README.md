# Vagrant Box LEMP Stack

This is a LEMP debian based box. Use it for a Magento 1 simi-production Stack.

## Requirements

- virtualbox 5.x
- vagrant >1.8.4
- (in case of error of shared folder mount errors) vagrant vagrant-vbguest plugin (install with the command `vagrant plugin install vagrant-vbguest`)

## How to use

1) download https://github.com/gmdotnet/Vagrant-LEMP-Magento/archive/master.zip

2) unzip on your favorite work folder

3) change Vagrantfile - section config.vm.synced_folder to sync your project folder

4) run 'vagrant up'

5) make your configuration on vagrant machine entering by run 'vagrant ssh'

6) have fun!

## OS and base box

- debian/jessie64  8.5.1
- private network ip: 192.168.251.10

## Software Installed

- htop
- mytop
- git
- nginx 1.6.2
- php5-fpm  5.6.22
- php5-curl
- php5-gd
- php5-mcrypt
- php5-mysql
- php5-cli
- php5-intl
- phpmyadmin 4.6.3 - all languages (accessible via *http://phpmyadmin.vagrant* on your file host with the same ip of vagrant machine)
- mysql percona 5.6
- curl
- mc-dbg (midnight commander)
- composer 1.1.3
- n98-magerun 1.97.22
- modman 1.12
- optipng 0.7.5
- jpegoptim 1.4.1
- mysqltuner 1.6.0
- redis server 2.8.17

### MySQL Percona server

- created an user called 'local' with root privilegies
- root password is 'vagrant'

### PHP-FPM

- listen on 127.0.0.1:9000
- daemon user is 'www-data'

### Nginx server

- daemon user is 'www-data'
- configuration sample for magento

### Redis Server

- no password required

### Vagrant Provision script

- the script makes a backup of all databases into /home/backup/database/ folder

### Other info

- root password is 'vagrant' but you can simply run 'sudo su' from vagrant user
- if you can't find a configuration in this file before, it means is used the default value
