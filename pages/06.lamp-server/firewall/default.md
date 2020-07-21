---
title: Firewall
visible: true
---

A firewall is a network security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules/

We will use uf w which should already be installed.

Check status

$ sudo ufw status
Status: inactive

**It is important to allow 22/tcp as your SSH connection needs it.**

$sudo ufw allow 22/tcp
$ sudo ufw enable
Command may disrupt existing ssh connections. Proceed with operation (y|n)? y
Firewall is active and enabled on system startup

Check status again.

$ sudo ufw status
Status: active

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW       Anywhere                  
22/tcp (v6)                ALLOW       Anywhere (v6)  

We are allowing only SSH. First ser up some default rules:

sudo ufw default deny incoming
sudo ufw default allow outgoing

Then allow www and  Apache Full which will be for our webserver.

sudo ufw allow www
sudo ufw allow 'Apache Full'


Checks status again:

jimmy@vds2:/var/www/moodle$ sudo ufw status
Status: active

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW       Anywhere                  
80/tcp                     ALLOW       Anywhere                  
Apache Full                ALLOW       Anywhere                  
22/tcp (v6)                ALLOW       Anywhere (v6)             
80/tcp (v6)                ALLOW       Anywhere (v6)             
Apache Full (v6)           ALLOW       Anywhere (v6)    


jimmy@vds2:/var/www/moodle$ sudo ufw default allow outgoing
Default outgoing policy changed to 'allow'
(be sure to update your rules accordingly)
jimmy@vds2:/var/www/moodle$ sudo ufw allow www
Rule added
Rule added (v6)
jimmy@vds2:/var/www/moodle$ sudo ufw status
Status: active

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW       Anywhere                  
80/tcp                     ALLOW       Anywhere                  
22/tcp (v6)                ALLOW       Anywhere (v6)             
80/tcp (v6)                ALLOW       Anywhere (v6) 