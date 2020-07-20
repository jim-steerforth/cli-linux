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
/var/www/your_domain/index.html</div><pre class="code-pre "><code>&lt;html&gt;
    &lt;head&gt;
        &lt;title&gt;Welcome to <span class="highlight">Your_domain</span>!&lt;/title&gt;
    &lt;/head&gt;
    &lt;body&gt;
        &lt;h1&gt;Success!  The <span class="highlight">your_domain</span> virtual host is working!&lt;/h1&gt;
    &lt;/body&gt;
&lt;/html&gt;
</kbd>    
  
