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
</pre>   </p>
 
 