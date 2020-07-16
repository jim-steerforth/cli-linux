---
title: ' Install Apache'
taxonomy:
    category:
        - docs
visible: true
---

jimmy@vdsbasic:~$ sudo apt update
jimmy@vdsbasic:~$ sudo apt install apache2
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following additional packages will be installed:
  apache2-bin apache2-data apache2-utils libapr1
  libaprutil1 libaprutil1-dbd-sqlite3 libaprutil1-ldap
  liblua5.2-0 ssl-cert
............................................
jimmy@vdsbasic:~$ sudo ufw app list
Available applications:
  Apache
  Apache Full
  Apache Secure
  OpenSSH
jimmy@vdsbasic:~$ sudo ufw app info "Apache Full"
Profile: Apache Full
Title: Web Server (HTTP,HTTPS)
Description: Apache v2 is the next generation of the omnipresent Apache web
server.

Ports:
  80,443/tcp


Check Apache is installed by going to your server address. The file is located at /var/www/html/index.html and provides us  with start and stop instructions:

    etc/init.d/apache2 or apache2ctl 

    the layout of the configuration files under /etc/apache2

/etc/apache2/
|-- apache2.conf
|       `--  ports.conf
|-- mods-enabled
|       |-- *.load
|       `-- *.conf
|-- conf-enabled
|       `-- *.conf
|-- sites-enabled
|       `-- *.conf

Now lets replace this page
sudo rm /var/www/html/index.html
sudo nano /var/www/html/index.html

<html>
  <body>
    Hello world! 
  </body>
</html>.