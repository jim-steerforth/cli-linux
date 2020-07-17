---
title: ' Install Apache'
taxonomy:
    category:
        - docs
visible: true
---

jimmy@vdsbasic:~$ sudo apt update<br></div>
jimmy@vdsbasic:~$ sudo apt install apache2<br</div>
Reading package lists... Done<br>
Building dependency tree <br>
Reading state information... Done<br>
The following additional packages will be installed:<br> 
apache2-bin apache2-data apache2-utils libapr1<br> libaprutil1 libaprutil1-dbd-sqlite3 libaprutil1-ldap<br> liblua5.2-0 ssl-cert<br>
............................................<br>
jimmy@vdsbasic:~$ sudo ufw app list<br>
Available applications:<br> 
Apache<br> 
Apache Full<br> 
Apache Secure<br> 
OpenSSH<br>
jimmy@vdsbasic:~$ sudo ufw app info "Apache Full"<br>
Profile: Apache Full<br>
Title: Web Server (HTTP,HTTPS)<br>
Description:<br>
Apache v2 is the next generation of the omnipresent Apache web server.<br>
<br>
Ports:<br> 
80,443/tcp<br>
<br>
<br>
Check Apache is installed by going to your server address. The file is located at<tt>/var/www/html/index.html and provides us with </tt><tt><tt>start and stop instructions: <br></tt></tt><br>


    <ul>
        <li><tt><tt>etc/init.d/apache2</tt> or <tt>apache2ctl</tt> </tt>
        </li>
    </ul>


    <ul>
        <li><tt> the layout of the configuration files under /etc/apache2<br></tt></li>
    </ul>

<tt><pre>/etc/apache2/
|-- apache2.conf
|       `--  ports.conf
|-- mods-enabled
|       |-- *.load
|       `-- *.conf
|-- conf-enabled
|       `-- *.conf
|-- sites-enabled
|       `-- *.conf</pre>Now lets replace this page</tt>
<tt><tt>sudo rm <tt><tt>/var/www/html/index.html</tt></tt>
    </tt><br></tt>
<p>    
Test your configuration.    </p>


<tt>sudo nano <tt><tt>/var/www/html/index.html</tt></tt><br></tt>

<tt><br></tt>
<tt>&lt;html&gt;<br> &lt;body&gt;<br> Hello world! <br> &lt;/body&gt;<br>&lt;/html&gt;<br></tt>
