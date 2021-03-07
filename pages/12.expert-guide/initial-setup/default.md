---
title: 'Initial Setup'
---

#### Create a sudo user 
sudo adduser jimmy  
sudo usermod -aG sudo jimmy  
su jimmy  
[Why create a sudo user?] <a id="#sudo1"></a>

#### Update packages
sudo apt update 
sudo apt upgrade


#### Allocate swap space
sudo swapon --show
sudo fallocate -l 1G /swapfile 
sudo chmod 600 /swapfile
sudo mkswap /swapfile 

#### Virtual hosts
sudo add-apt-repository ppa:certbot/certbot 
sudo apt install python-certbot-apache 
sudo certbot --apache -d mysite.com -d www.mysite.com

#### Install apache and set up the firewall
sudo apt install apache2
sudo ufw allow 22/tcp
sudo ufw enable


sudo apt install mysql-client mysql-server php libapache2-mod-php
sudo service mysql start


sudo mysql_secure_installation 
sudo mysql -u root -p 
CREATE DATABASE moodle DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
create user 'moodledude'@'localhost' IDENTIFIED BY 'passwordformoodledude';
GRANT SELECT,INSERT,UPDATE,DELETE,CREATE,CREATE TEMPORARY TABLES,DROP,INDEX,ALTER ON moodle.* TO moodledude@localhost IDENTIFIED BY 'passwordformoodledude';
quit;


sudo add-apt-repository ppa:certbot/certbot 
sudo apt install python-certbot-apache 
cat /etc/apache2/sites-available/vdsbasic.xyz.conf 
sudo certbot --apache -d vdsbasic.xyz -d www.vdsbasic.xyz

sudo mkdir /var/www/moodle 
sudo chown -R www-data:www-data /var/www/moodle
sudo chmod -R 755 /var/www/moodle
sudo nano /var/www/moodle/index.html
<html><br>
    <head><br>
        <title> Moodle placeholder</title><br>
    </head><br>
    <body><br>
        <h1>Success! Moodle placeholder is ready!</h1><br>
    </body><br>
</html><br>
sudo systemctl restart apache2 

sudo rm -ir /var/www/moodle 
cd /var/www/html
sudo git clone git://git.moodle.org/moodle.git 
cd moodle 
sudo git branch -a 
sudo git branch --track MOODLE_39_STABLE origin/MOODLE_39_STABLE
sudo git checkout MOODLE_39_STABLE 
sudo mkdir /var/moodledata
sudo chown -R www-data /var/moodledata
sudo chmod -R 777 /var/moodledata
sudo chmod -R 0755 /var/www/moodle 

#### What is sudo user? <a id="sudo"></a>
Safer than user root.
