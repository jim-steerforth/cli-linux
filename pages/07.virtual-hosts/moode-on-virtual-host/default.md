---
title: 'Moodle on virtual host'
visible: true
---

<p style="font-family:Courier; color:white; background-color:black;">sudo mkdir /var/www/html/vdsbasic.xyz
sudo mkdir /var/www/html/vdsbasic.xyz/moodle
</p>

<p style="font-family:Courier; color:white; background-color:black;">sudo chown -R www-data:www-data /var/www/vdsbasic.xyz/
</p>



jimmy@vds2:/var/www$ sudo a2ensite vdsbasic.xyz.conf
Enabling site vdsbasic.xyz.
To activate the new configuration, you need to run:
  systemctl reload apache2
  
  sudo a2dissite 000-default.conf

jimmy@vds2:/var/www$ sudo a2dissite 000-default.conf
Site 000-default disabled.
To activate the new configuration, you need to run:
  systemctl reload apache2

Config test
jimmy@vds2:/var/www$ sudo apache2ctl configtest
Syntax OK

sudo systemctl restart apache2

<VirtualHost *:80>
    ServerAdmin webmaster@vdsbasic.xyz
    ServerName vdsbasic.xyz
    ServerAlias www.vdsbasic.xyz
    DocumentRoot /var/www/vdsbasic.xyz/moodle
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>



sudo a2dissite vdsbasic.xyz.conf
