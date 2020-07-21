---
title: Firewall
---

A firewall is a network security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules/

We will use uf w which should already be installed.

Check status
 <p style="font-family:Courier; color:white; background-color:black;">
$ sudo ufw status<br>
Status: inactive<br>
   </p>

**It is important to allow 22/tcp as your SSH connection needs it.**
<p style="font-family:Courier; color:white; background-color:black;">
    <pre>
$ sudo ufw allow 22/tcp
$ sudo ufw enable
Command may disrupt existing ssh connections. Proceed with operation (y|n)? y
Firewall is active and enabled on system startup
</pre>
</p>

Check status again.
<p style="font-family:Courier; color:white; background-color:black;">
    <pre>
$ sudo ufw status
Status: active

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW       Anywhere                  
22/tcp (v6)                ALLOW       Anywhere (v6)  

</pre>
</p>

We are allowing only SSH. First ser up some default rules:



<p style="font-family:Courier; color:white; background-color:black;">
    <pre>
sudo ufw default deny incoming
sudo ufw default allow outgoing


</pre>
</p>

Then allow www and  Apache Full which will be for our webserver.

<p style="font-family:Courier; color:white; background-color:black;">
    <pre>
sudo ufw allow www
sudo ufw allow 'Apache Full'
</pre>
</p>


Checks status again:

<p style="font-family:Courier; color:white; background-color:black;">
    <pre>
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

</pre>
</p>

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