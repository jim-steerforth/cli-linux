---
title: tesr
---

<p>With a virtual host, a LetsEncrypt certificate can be set up to allow HTTPS connections. It protects student data,  looks more professional, and  Moodle uses <a href="https://webrtc.org/">WebRTC</a> for recording audio and video and that requires encryption. Setting up HTTPS now will save time and trouble later.</p>


<p>First create a moodle subdirectory under the domain name. </p>

<p style="font-family:Courier; color:white; background-color:black;">
sudo mkdir /var/www/moodle <br>
</p>

<p>Change the ownership of the folder to the web user www-data and the permissions to 755</p>

<p style="font-family:Courier; color:white; background-color:black;">
sudo chown -R www-data:www-data /var/www/moodle<br>
sudo chmod -R 755 /var/www/moodle<br>
</p>
