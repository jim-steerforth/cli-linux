---
title: 'Let''s Encrypt'
visible: true
---

sudo add-apt-repository ppa:certbot/certbot

jimmy@vds2:/var/www/moodle$ sudo add-apt-repository ppa:certbot/certbot
 This is the PPA for packages prepared by Debian Let's Encrypt Team and backported for Ubuntu.

Note: Packages are only provided for currently supported Ubuntu releases.
 More info: https://launchpad.net/~certbot/+archive/ubuntu/certbot
Press [ENTER] to continue or Ctrl-c to cancel adding it.

sudo apt install python-certbot-apache


sudo ufw allow 22/tcp
jimmy@vds2:/var/www/moodle$ sudo ufw enable
Command may disrupt existing ssh connections. Proceed with operation (y|n)? y
Firewall is active and enabled on system startup


jimmy@vds2:/var/www/moodle$ sudo ufw status
Status: active

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW       Anywhere                  
22/tcp (v6)                ALLOW       Anywhere (v6)   

sudo ufw default deny incoming

sudo ufw default allow outgoing

/etc/apache2/sites-available/your_domain.com.conf with the ServerName directive already set appropriately.

jimmy@vds2:/var/www/moodle$ sudo apache2ctl configtest
Syntax OK

