---
title: 'MySql and PHP'
---

<p> MySql and php  is next for an install</p>

 
 <p style="font-family:Courier; color:white; background-color:black;">sudo apt install mysql-client mysql-server php libapache2-mod-php</p>
 
<p> To start the service</p>

 
<p style="font-family:Courier; color:white; background-color:black;"> sudo service mysql start</p>
<p> 
 Other commands are </p>

 <p style="font-family:Courier; color:white; background-color:black;">
 sudo service mysql start<br>
 sudo service mysql stop<br>
 sudo service mysql status<br>
 sudo service mysql restart<br>
 </p>
 
 <p>  The next bit is very  important.</p>

  <p style="font-family:Courier; color:white; background-color:black;"> 
  sudo mysql_secure_installation
 </p>
 
 This secures the MySql service. MySql must be running and this command must be run by the sudo user.<br>
        <ul>
        <li>When asked  "<i>Would you like to setup VALIDATE PASSWORD plugin?</i>"Choose "N" </li>
      <li>Now set the Mysql root user (<b>IMPORTANT do not forget that password! Write it down</b>)</li>
      <li>Answer Y to <i>"Remove anonymous users?", "Disallow root login remotely?", "Remove test database and access to it?", "Reload privilege tables now?</i>"</li>
    </ul>
    
Check your PHP version with:<br> 

 <p style="font-family:Courier; color:white; background-color:black;"> php -v </p>

Mine returns PHP 7.2.19-0ubuntu0.18.04.1. If the command returns a version of 7.3 or higher, change the version number in the following command:<br> 
    <<p style="font-family:Courier; color:white; background-color:black;"e>
sudo apt install graphviz aspell ghostscript clamav php7.2-pspell php7.2-curl php7.2-gd php7.2-intl php7.2-mysql php7.2-xml php7.2-xmlrpc php7.2-ldap php7.2-zip php7.2-soap php7.2-mbstring
</p>
Restart Apache webserver. <br>
<p style="font-family:Courier; color:white; background-color:black;">
    sudo service apache2 restart
</p>

<p>    You may see <i>Failed to enable APR_TCP_DEFER_ACCEPT </i> so run</p>
    
<p style="font-family:Courier; color:white; background-color:black;">
    sudo service apache2 status 
</p>
<p>    You should see Apache2 is running.</p>
 