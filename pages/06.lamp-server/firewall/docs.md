---
title: Firewall
published: true
taxonomy:
    category:
        - docs
visible: true
---

A firewall is a network security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules/

We will use uf w which should already be installed.

Check status
 <p style="font-family:Courier; color:white; background-color:black;">
$ sudo ufw status<br>
Status: inactive<br>
   </p>

**It is important to allow 22/tcp as your SSH connection needs it.**
<p style="font-family:Courier; color:white; background-color:black;">$ sudo ufw allow 22/tcp<br>
$ sudo ufw enable<br>
Command may disrupt existing ssh connections. Proceed with operation (y|n)? y<br>
Firewall is active and enabled on system startus</p>



Check status again.

<p style="font-family:Courier; color:white; background-color:black;">
    
$ sudo ufw status
  </p>  
<pre>   
Status: active<br>

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW       Anywhere                  
22/tcp (v6)                ALLOW       Anywhere (v6)  
</pre>



We are allowing only SSH. First set up some default rules:



<p style="font-family:Courier; color:white; background-color:black;">   
sudo ufw default deny incoming<br>
sudo ufw default allow outgoing<br>
</p>

Then allow www and  Apache Full which will be for our webserver.

<p style="font-family:Courier; color:white; background-color:black;">   
sudo ufw allow www<br>
sudo ufw allow 'Apache Full'<br>
</p>


Checks status again:

<p style="font-family:Courier; color:white; background-color:black;">   
jimmy@vds2:/var/www/moodle$ sudo ufw status
   </p>  

<pre>
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

