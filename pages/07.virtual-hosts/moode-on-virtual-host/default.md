---
title: 'Moodle on virtual host'
visible: true
---

 <p style="font-family:Courier; color:white; background-color:black;">
sudo mkdir /var/www/html/vdsbasic.xyz <br>
sudo mkdir /var/www/html/vdsbasic.xyz/moodle <br>
</p>

<p style="font-family:Courier; color:white; background-color:black;">
sudo chown -R www-data:www-data /var/www/vdsbasic.xyz/moodle<br>
sudo chmod -R 755 /var/www/vdsbasic.xyz/moodle<br>
</p>

<p style="font-family:Courier; color:white; background-color:black;">
sudo nano /var/www/vdsbasic.xyz/index.html
</p>


<kbd>
<html><br>
    <head><br>
        <title>vdsbasic.xyz placeholder</title><br>
    </head><br>
    <body><br>
        <h1>Success! vdsbasic.xyz placeholder is ready!</h1><br>
    </body><br>
</html><br>
</kbd>    
  
