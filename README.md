# Vagrant Box LEMP Stack

This is a LEMP debian based box. Use it for a Magento 1.x CE simi-production Stack.

## Requirements

- virtualbox 5.x
- vagrant >1.8.4
- (in case of error of shared folder mount errors) vagrant vagrant-vbguest plugin (install with the command `vagrant plugin install vagrant-vbguest`)

## How to use

1) download https://github.com/gmdotnet/Vagrant-LEMP-Magento/archive/master.zip

2) unzip on your favorite work folder

3) rename `config/config.yaml.sample` in `config/config.yaml`

4) change settings in `config/config.yaml`

5) run `vagrant up` on folder where is `Vagrantfile`

6) (optional) make your configuration on vagrant machine entering by run `vagrant ssh`

7) have fun and happy coding!

## OS and base box

- debian/jessie64  8.5.1
- default private network ip: 192.168.251.10

## Software Installed

- [composer](https://getcomposer.org/)  1.2.0
- curl
- git
- htop
- jpegoptim 1.4.1
- mailutils
- [mailhog](https://github.com/mailhog/MailHog)  0.2.0
- mc-dbg (midnight commander)
- mysql percona 5.6
- mysqltuner 1.6.0
- mytop
- nginx 1.6.2
- optipng 0.7.5
- phpmyadmin 4.6.3 - all languages (accessible via *http://phpmyadmin.vagrant* on your file host with the same ip of vagrant machine)
- postfix
- redis server 2.8.17

- Magento Utils:
    - [modman](https://github.com/colinmollenhour/modman) 1.12
    - [n98-magerun](https://github.com/netz98/n98-magerun)  1.97.22

- PHP
  - php5-fpm  5.6.22
  - php5-cli
  - php5-curl
  - php5-gd
  - php5-intl
  - php5-mcrypt
  - php5-mysql

### MySQL Percona server

- created an user called `local` (password `local`) with root privilegies
- root password is `vagrant`

### PHP-FPM

- listen on 127.0.0.1:9000
- daemon user is `vagrant`

### Nginx server

- daemon user is `vagrant`
- configuration sample for magento

### Redis Server

- no password required
- listen on `127.0.0.1`

### SMTP and EMAIL with postfix and MailHog

- postfix is configured as satellite system with 127.0.0.1:1025
- mailhog do not start automatically. Just open a shell and type `mailhog`
    - web interface is set on `<vagrant ip>:8025`
- all emails are not sent outside the machine
- to test:
    - start mailhog
    - send a test email with `echo "this is a test email | mail -s "subject test email" fake@fake.mail`
    - check on your browser `<vagrant ip>:8025` the email sent
- you can use mailhog as SMTP server, just configure your application to send email at 127.0.0.1 with port 1025

### Vagrant Provision script

- `backup_database.sh`: the script makes a backup of all databases into /home/backup/database/ folder

### Other info

- root password is `vagrant` but you can simply run `sudo su` from vagrant user
- if you can't find a configuration in this file before, it means is used the default value

### Credits

Giuseppe Morelli - [giuseppemorelli.net](http://www.giuseppemorelli.net)