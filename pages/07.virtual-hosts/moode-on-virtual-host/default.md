---
title: 'Moodle on virtual host'
visible: true
---

 <p style="font-family:Courier; color:white; background-color:black;">
sudo mkdir /var/www/html/vdsbasic.xyz <br>
sudo mkdir /var/www/html/vdsbasic.xyz/moodle <br>
</p>

<p style="font-family:Courier; color:white; background-color:black;">
sudo chown -R www-data:www-data /var/www/vdsbasic.xyz/moodle<br>
sudo chmod -R 755 /var/www/vdsbasic.xyz/moodle<br>
</p>

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
  
  
