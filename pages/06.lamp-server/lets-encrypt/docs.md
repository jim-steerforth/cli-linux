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


<p>The virtual host file for my server was set up here. Subsitute your domain and check the servername line.<br>
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
sudo certbot --apache -d <i>vdsbasic.xyz</i> -d <i>www.vdsbasic.xyz</i>
 </p> 


You should 
<ul>
  <li>Enter your email (certicates may need renewal)</li>
  <li>Agree to the Terms of Service</li>
  <li>Optional to share your email address with the Electronic Frontier Foundation</li>
  <li>Redirect HTTP traffic to HTTPS, removing HTTP access with option 2</li>
   
</ul>

This will create 
<ul>
  <li>a new Certificate: /etc/apache2/sites-available/vdsbasic.xyz-le-ssl.conf</li>
  <li>a new available site: /etc/apache2/sites-available/vdsbasic.xyz-le-ssl.conf</li>
</ul>

<p>If you go to your domain, it now redirects to https://vdsbasic.xyz/</p>


 <pre>
$ sudo certbot --apache -d vdsbasic.xyz -d www.vdsbasic.xyz
[sudo] password for jimmy: 
Saving debug log to /var/log/letsencrypt/letsencrypt.log
Plugins selected: Authenticator apache, Installer apache
Enter email address (used for urgent renewal and security notices) (Enter 'c' to
cancel):<i><u>myaddress@email.com
</u></i>
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Please read the Terms of Service at
https://letsencrypt.org/documents/LE-SA-v1.2-November-15-2017.pdf. You must
agree in order to register with the ACME server at
https://acme-v02.api.letsencrypt.org/directory
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
(A)gree/(C)ancel: A

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Would you be willing to share your email address with the Electronic Frontier
Foundation, a founding partner of the Let's Encrypt project and the non-profit
organization that develops Certbot? We'd like to send you email about our work
encrypting the web, EFF news, campaigns, and ways to support digital freedom.
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
(Y)es/(N)o: Y
Obtaining a new certificate
Performing the following challenges:
http-01 challenge for vdsbasic.xyz
http-01 challenge for www.vdsbasic.xyz
Enabled Apache rewrite module
Waiting for verification...
Cleaning up challenges
Created an SSL vhost at /etc/apache2/sites-available/vdsbasic.xyz-le-ssl.conf
Enabled Apache socache_shmcb module
Enabled Apache ssl module
Deploying Certificate to VirtualHost /etc/apache2/sites-available/vdsbasic.xyz-le-ssl.conf
Enabling available site: /etc/apache2/sites-available/vdsbasic.xyz-le-ssl.conf
Deploying Certificate to VirtualHost /etc/apache2/sites-available/vdsbasic.xyz-le-ssl.conf

Please choose whether or not to redirect HTTP traffic to HTTPS, removing HTTP access.
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
1: No redirect - Make no further changes to the webserver configuration.
2: Redirect - Make all requests redirect to secure HTTPS access. Choose this for
new sites, or if you're confident your site works on HTTPS. You can undo this
change by editing your web server's configuration.
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Select the appropriate number [1-2] then [enter] (press 'c' to cancel): 2
Enabled Apache rewrite module
Redirecting vhost in /etc/apache2/sites-enabled/vdsbasic.xyz.conf to ssl vhost in /etc/apache2/sites-available/vdsbasic.xyz-le-ssl.conf

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Congratulations! You have successfully enabled https://vdsbasic.xyz and
https://www.vdsbasic.xyz

You should test your configuration at:
https://www.ssllabs.com/ssltest/analyze.html?d=vdsbasic.xyz
https://www.ssllabs.com/ssltest/analyze.html?d=www.vdsbasic.xyz
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

IMPORTANT NOTES:
 - Congratulations! Your certificate and chain have been saved at:
   /etc/letsencrypt/live/vdsbasic.xyz/fullchain.pem
   Your key file has been saved at:
   /etc/letsencrypt/live/vdsbasic.xyz/privkey.pem
   Your cert will expire on 2020-10-20. To obtain a new or tweaked
   version of this certificate in the future, simply run certbot again
   with the "certonly" option. To non-interactively renew *all* of
   your certificates, run "certbot renew"
 - Your account credentials have been saved in your Certbot
   configuration directory at /etc/letsencrypt. You should make a
   secure backup of this folder now. This configuration directory will
   also contain certificates and private keys obtained by Certbot so
   making regular backups of this folder is ideal.
 - If you like Certbot, please consider supporting our work by:

   Donating to ISRG / Let's Encrypt:   https://letsencrypt.org/donate
   Donating to EFF:                    https://eff.org/donate-le

 </pre>
 
 <h3>Additional Reading</h3>
<p><a href="(https://www.digitalocean.com/community/tutorials/an-introduction-to-let-s-encrypt](An Introduction to Let's Encrypt">An Introduction to Let's Encrypt</a></p>

<p><a href="https://www.digitalocean.com/community/tutorials/how-to-secure-apache-with-let-s-encrypt-on-ubuntu-18-04">How To Secure Apache with Let's Encrypt on Ubuntu 18.04</a></p>

      