# Vagrant Box LEMP Stack

This is a LEMP debian based box. Use it for a Magento simi-production Stack.

## Requirements

- virtualbox 5.x
- vagrant >1.8.4
- (in case of error of shared folder mount errors) vagrant vagrant-vbguest plugin (install with the command `vagrant plugin install vagrant-vbguest`)

## How to use

1) download

2) unzip on your favorite work folder

3) change Vagrantfile - section config.vm.synced_folder to sync your project folder

4) run 'vagrant up'

5) make your configuration on vagrant machine entering by run 'vagrant ssh'

6) have fun!

## OS and base box

- debian/jessie64  8.5.1
- private network ip: 192.168.251.10

## Software Installed



### MySQL Percona server

- created an user called 'local' with root privilegies
- root password is 'vagrant'

### Nginx server

- daemon user is 'www-data'

### Vagrant Provision script

- the script makes a backup of all databases into /home/backup/database/ folder

### Other info

- root password is 'vagrant' but you can simply run 'sudo su' from vagrant user
- if you can't find a configuration in this file before, it means is used the default value
