---
title: ' Install Apache'
taxonomy:
    category:
        - docs
visible: true
---

<div>jimmy@vdsbasic:~$ sudo apt update<br></div>
<div>jimmy@vdsbasic:~$ sudo apt install apache2</div>Reading package lists... Done<br>Building dependency tree&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;<br>Reading state information... Done<br>The following additional packages will be installed:<br>&nbsp; apache2-bin
apache2-data apache2-utils libapr1<br>&nbsp; libaprutil1 libaprutil1-dbd-sqlite3 libaprutil1-ldap<br>&nbsp; liblua5.2-0 ssl-cert
<div>............................................</div>
<div>jimmy@vdsbasic:~$ sudo ufw app list</div>Available applications:<br>&nbsp; Apache<br>&nbsp; Apache Full<br>&nbsp; Apache Secure<br>&nbsp; OpenSSH<br>jimmy@vdsbasic:~$ sudo ufw app info "Apache Full"<br>Profile: Apache Full<br>Title: Web Server (HTTP,HTTPS)<br>Description:
Apache v2 is the next generation of the omnipresent Apache web<br>server.<br><br>Ports:<br>&nbsp; 80,443/tcp<br>
<div><br></div>
<div><br></div>
<div>Check Apache is installed by going to your server address. The file is located at&nbsp;<tt>/var/www/html/index.html and provides us&nbsp; with </tt><tt><tt>start and stop instructions: <br></tt></tt>
</div>
<div>
    <ul>
        <li><tt><tt>etc/init.d/apache2</tt> or <tt>apache2ctl</tt> </tt>
        </li>
    </ul>
</div>
<div>
    <ul>
        <li><tt> the layout of the configuration files under /etc/apache2<br></tt></li>
    </ul>
</div>
<div><tt><pre>/etc/apache2/
|-- apache2.conf
|       `--  ports.conf
|-- mods-enabled
|       |-- *.load
|       `-- *.conf
|-- conf-enabled
|       `-- *.conf
|-- sites-enabled
|       `-- *.conf</pre>Now lets replace this page</tt></div>
<div><tt><tt>sudo rm <tt><tt>/var/www/html/index.html</tt></tt>
    </tt><br></tt>
</div>
<div><tt>sudo nano <tt><tt>/var/www/html/index.html</tt></tt><br></tt>
</div>
<div><tt><br></tt></div>
<div><tt>&lt;html&gt;<br>&nbsp; &lt;body&gt;<br>&nbsp;&nbsp;&nbsp; Hello world!&nbsp; <br>&nbsp; &lt;/body&gt;<br>&lt;/html&gt;<br></tt></div>
