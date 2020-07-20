---
title: 'Moodle on virtual host'
visible: true
---

 First create a moodle subdirectory under the domain name. 
 
 [presentation="presentations/"]<p style="font-family:Courier; color:white; background-color:black;">
sudo mkdir /var/www/html/vdsbasic.xyz <br>
sudo mkdir /var/www/html/vdsbasic.xyz/moodle <br>
</p>

Change the ownership of the folder to the web user www-data and the permissions to 755

<p style="font-family:Courier; color:white; background-color:black;">
sudo chown -R www-data:www-data /var/www/vdsbasic.xyz/moodle<br>
sudo chmod -R 755 /var/www/vdsbasic.xyz/moodle<br>
</p>

Create a test page

<p style="font-family:Courier; color:white; background-color:black;">
sudo nano /var/www/vdsbasic.xyz/moodle/index.html
</p>


<pre>
&lt;html&gt;&lt;br&gt;
    &lt;head&gt;&lt;br&gt;
        &lt;title&gt;vdsbasic.xyz Moodle placeholder&lt;/title&gt;&lt;br&gt;
    &lt;/head&gt;&lt;br&gt;
    &lt;body&gt;&lt;br&gt;
        &lt;h1&gt;Success! vdsbasic.xyz Moodle placeholder is ready!&lt;/h1&gt;&lt;br&gt;
    &lt;/body&gt;&lt;br&gt;
&lt;/html&gt;&lt;br&gt;
</pre>    

Set up a config file.

<p style="font-family:Courier; color:white; background-color:black;">
sudo nano /etc/apache2/sites-available/vdsbasic.xyz.conf
</p>

<pre>
&lt;VirtualHost *:80&gt;
    ServerAdmin webmaster@vdsbasic.xyz
    ServerName vdsbasic.xyz
    ServerAlias www.vdsbasic.xyz/moodle
    DocumentRoot /var/www/vdsbasic.xyz/moodle
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
&lt;/VirtualHost&gt;
</pre>

sudo a2dissite 000-default.conf

Set up thee config file.
  
sudo a2ensite vdsbasic.xyz.conf

jimmy@vds2:/var/www$ sudo a2ensite vdsbasic.xyz.conf
Enabling site vdsbasic.xyz.
To activate the new configuration, you need to run:
  systemctl reload apache2
  
  



jimmy@vds2:/var/www$ sudo a2dissite 000-default.conf
Site 000-default disabled.
To activate the new configuration, you need to run:
  systemctl reload apache2

Config test
jimmy@vds2:/var/www$ sudo apache2ctl configtest
Syntax OK

sudo systemctl restart apache2



