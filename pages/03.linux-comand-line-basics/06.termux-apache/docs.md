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
   &lsaquo;FilesMatch \.php$&rsaquo;
  SetHandler application/x-httpd-php
&lsaquo;/FilesMatch&rsaquo;
   
&lsaquo;IfModule dir_module&rsaquo;
  DirectoryIndex index.php
&lsaquo;/IfModule&rsaquo;
</pre>   </p>
