---
title: 'Termux Apache'
taxonomy:
    category:
        - docs
---

 <p>  <pre>
   apt update
   apt upgrade 
   apt install php-apache
   apt install nano  
   nano /data/data/com.termux/files/usr/etc/apache2/httpd.conf   
   

LoadModule php7_module /data/data/com.termux/files/usr/libexec/apache2/libphp7.so


&lt;FilesMatch \.php$&gt;
  SetHandler application/x-httpd-php
&lt;/FilesMatch&gt;
   
&lt;IfModule dir_module&gt;
  DirectoryIndex index.php
&lt;/IfModule&gt;

nano   /data/data/com.termux/files/usr/share/apache2/default-site/htdocs/index.php

&lt;?php
phpinfo();

apachectl start

localhost:8080/index.php


comment
#LoadModule mpm_worker_module libexec/apache2/mod_mpm_worker.so
uncomment
LoadModule mpm_prefork_module libexec/apache2/mod_mpm_prefork.so



</pre>   </p>
new

apt install graphviz aspell ghostscript clamav php7.2-pspell php7.2-curl php7.2-gd php7.2-intl php7.2-mysql php7.2-xml php7.2-xmlrpc php7.2-ldap php7.2-zip php7.2-soap php7.2-mbstring