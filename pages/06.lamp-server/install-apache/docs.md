---
title: ' Install Apache'
media_order: Apache.jpg
taxonomy:
    category:
        - docs
visible: true
---

To install Apache, first update the system, then use apt to install Apache 2.

 <p style="font-family:Courier; color:white; background-color:black;">
jimmy@vdsbasic:~$ sudo apt update<br>
jimmy@vdsbasic:~$ sudo apt install apache2<br
Reading package lists... Done<br>
Building dependency tree <br>
Reading state information... Done<br>
The following additional packages will be installed:<br> 
apache2-bin apache2-data apache2-utils libapr1<br> libaprutil1 libaprutil1-dbd-sqlite3 libaprutil1-ldap<br> liblua5.2-0 ssl-cert<br>
......
</p>
<p>
ufw app list shows we have Apache installed and it is able to be accessed through the firewall.</p>

 <p style="font-family:Courier; color:white; background-color:black;">
jimmy@vdsbasic:~$ sudo ufw app list<br>
Available applications:<br> 
Apache<br> 
Apache Full<br> 
Apache Secure<br> 
OpenSSH<br>
</p>
<p>ufw can also be used to check ports are open.</p>

 <p style="font-family:Courier; color:white; background-color:black;">
jimmy@vdsbasic:~$ sudo ufw app info "Apache Full"<br>
Profile: Apache Full<br>
Title: Web Server (HTTP,HTTPS)<br>
Description:<br>
Apache v2 is the next generation of the omnipresent Apache web server.<br>
<br>
Ports:<br> 
80,443/tcp<br>
</p>

<p>Check Apache is installed by going to your server address.Mine is a vdsbasic.xyz</p>
![](Apache.jpg)  
    
<p>    The file is located at /var/www/html/index.html and provides us with start and stop instructions:</p>
 
<p>Create your own index.html file.</p>

<p style="font-family:Courier; color:white; background-color:black;">
sudo nano /var/www/html/index.html
</p>

<tt>&lt;html&gt;<br> &lt;body&gt;<br> Hello world! <br> &lt;/body&gt;<br>&lt;/html&gt;<br></tt>
