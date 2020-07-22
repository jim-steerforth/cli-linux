---
title: 'Let''s Encrypt'
taxonomy:
    category:
        - docs
visible: true
---

<p>Begin by adding a new repository. </p>

<p style="font-family:Courier; color:white; background-color:black;">
sudo add-apt-repository ppa:certbot/certbot
</p>
 
 
    

<p><pre>$ sudo add-apt-repository ppa:certbot/certbot<br>
This is the PPA for packages prepared by Debian 
Let's Encrypt Team and backported for Ubuntu.


Note: Packages are only provided for currently supported Ubuntu releases
 More info: https://launchpad.net/~certbot/+archive/ubuntu/certbot
Press [ENTER] to continue or Ctrl-c to cancel adding it.
</pre>
  </p>
  
<p>Install the certificate </p>

 <p style="font-family:Courier; color:white; background-color:black;">
sudo apt install python-certbot-apache
</p>

<h3>Additional Reading</h3>
<p><a href="(https://www.digitalocean.com/community/tutorials/an-introduction-to-let-s-encrypt](An Introduction to Let's Encrypt">An Introduction to Let's Encrypt</a></p>

<p><a href="https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-18-04">How To Secure Apache with Let's Encrypt on Ubuntu 18.04</a></p>

<p>The virtual host file for my server was set up here. Subsiture your domain and check the servername line.<br>
It should reference your domain name.
</p>

<p style="font-family:Courier; color:white; background-color:black;">
$ cat /etc/apache2/sites-available/vdsbasic.xyz.conf
</p>

<pre>
<VirtualHost *:80>
    ServerAdmin webmaster@vdsbasic.xyz
    ServerName vdsbasic.xyz
    ServerAlias www.vdsbasic.xyz
    DocumentRoot /var/www/moodle
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
</pre>

Run this command, with your domain.
<p style="font-family:Courier; color:white; background-color:black;">
sudo certbot --apache -d <i>vdsbasic.xyz</i> -d <i>www.vdsbasic,xyz</i>
 </p> 