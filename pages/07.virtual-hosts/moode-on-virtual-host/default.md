---
title: 'Moodle on virtual host'
visible: true
---

    
<p>With a virtual host, a LetsEncrypt certificate can be set up to allow HTTPS connections. It protects student data,  looks more professional, and  Moodle uses <a href="https://webrtc.org/">WebRTC</a> for recording audio and video and that requires encryption. Setting up HTTPS now will save time and trouble later.</p>


<p>First create a moodle subdirectory under the domain name. </p>

 

<p style="font-family:Courier; color:white; background-color:black;">
sudo mkdir /var/www/moodle <br>
</p>


<p>Change the ownership of the folder to the web user www-data and the permissions to 755</p>


<p style="font-family:Courier; color:white; background-color:black;">
sudo chown -R www-data:www-data /var/www/moodle<br>
sudo chmod -R 755 /var/www/moodle<br>
</p>


<p>Create a test page</p>


<p style="font-family:Courier; color:white; background-color:black;">
sudo nano /var/www/moodle/index.html
</p>

 

<pre>
&lt;html&gt;&lt;br&gt;
    &lt;head&gt;&lt;br&gt;
        &lt;title&gt; Moodle placeholder&lt;/title&gt;&lt;br&gt;
    &lt;/head&gt;&lt;br&gt;
    &lt;body&gt;&lt;br&gt;
        &lt;h1&gt;Success! Moodle placeholder is ready!&lt;/h1&gt;&lt;br&gt;
    &lt;/body&gt;&lt;br&gt;
&lt;/html&gt;&lt;br&gt;
</pre>    

<p>Set up a config file.</p>


<p style="font-family:Courier; color:white; background-color:black;">
sudo nano /etc/apache2/sites-available/vdsbasic.xyz.conf
</p>


<p><pre>
&lt;VirtualHost *:80&gt;
    ServerAdmin webmaster@vdsbasic.xyz
    ServerName vdsbasic.xyz
    ServerAlias www.vdsbasic.xyz
    DocumentRoot /var/www/moodle
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
&lt;/VirtualHost&gt;
</pre></p>


<p>Apache will be using the etc/apache2/sites-available/000-default.conf file. We are replacing this file with our own. 
</p>

<p>sudo a2dissite 000-default.conf</p>


<p>
Set up the config file.</p>



<p>sudo a2ensite vdsbasic.xyz.conf</p>


<p><pre>
jimmy@vds2:/var/www$ sudo a2ensite vdsbasic.xyz.conf
Enabling site vdsbasic.xyz.
To activate the new configuration, you need to run:
  systemctl reload apache2
 </pre> </p>


<p><pre>
jimmy@vds2:/var/www$ sudo a2dissite 000-default.conf
Site 000-default disabled.
To activate the new configuration, you need to run:
  systemctl reload apache2

Config test
jimmy@vds2:/var/www$ sudo apache2ctl configtest
Syntax OK
</pre> </p>

<p>sudo systemctl restart apache2</p>