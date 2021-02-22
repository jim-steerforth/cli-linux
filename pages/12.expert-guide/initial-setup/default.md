---
title: 'Initial Setup'
---

#### Create a sudo user
sudo adduser jimmy  

sudo usermod -aG sudo jimmy  

su jimmy  

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