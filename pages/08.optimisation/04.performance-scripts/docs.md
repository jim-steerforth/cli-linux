---
title: 'Performance Scripts'
published: true
taxonomy:
    category:
        - docs
---

Your page content goes here.<p> 
To run the Performance Tuning Scripts start with a clean install of a LAMP stack. The XS test will run on 1 CPU and 1gB of RAM with 
a 1gB swap file but you will need more grunt for a S or M test. I used the DigitalOCcean marketplace to 
load a fresh LAMP. Don't install Moodle.</p>
<p> I haven't worried too much about security here as this is a Droplet I am setting up and deleting within days.</p>

Swap File first. Simple rule is same amount as your RAM.<br>
<code>
<pre>
sudo fallocate -l 1G /swapfile 
sudo chmod 600 /swapfile 
sudo mkswap /swapfile 
sudo swapon /swapfile 
sudo swapon --show
</pre>
</code>

<p>Write to your fstab table if you want to reboot and still have a swap file.<br>
</p>

Your LAMP should have php installed but add the bits and pieces Moodle needs. Check your php version first (php -version) as this installs the 7.4 version<br>
<br>

<code>
<pre>
sudo apt install graphviz aspell ghostscript clamav php7.4-pspell php7.4-curl php7.4-gd php7.4-intl php7.4-mysql php7.4-xml php7.4-xmlrpc php7.4-ldap php7.4-zip php7.4-soap php7.4-mbstring
</pre>
</code>

Create a database user with all privileges. There is no need to create a database.<br>
<code>
<pre>
sudo mysql -u root

create user 'mpc'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON * . * TO 'mpc'@'localhost';
FLUSH PRIVILEGES;
exit;
</pre>
</code>

Set up the wwwroot. In Debian based distros the wwwroot is /www/var/html but the Moodle Performance Scripts assume the root is in /var/www
Adjust the wwwroot by changing the DocumentRoot to /var/www/html to/var/www<br>
<code>
<pre>
  sudo nano /etc/apache2/sites-available/000-default.conf  
</pre>
</code>

Restart Apache.<br>
<code>
<pre>
sudo service apache2 restart
</pre>
</code>

Now create the dataroot and back up directory.<br>
<code>
<pre>
sudo mkdir /var/moodledata
sudo chmod -R 777 /var/moodledata
mkdir /home/jimmy/backup
</pre>
</code>

Now we have to install Java.<br>
<code>
<pre>
sudo apt update
sudo apt install default-jre
</pre>
</code>
Then Jmeter.<br>
<code>
<pre>
cd /opt
sudo wget https://downloads.apache.org//jmeter/binaries/apache-jmeter-5.3.tgz
sha512sum apache-jmeter-5.3.tgz 
</pre>
</code>
Check the SHA512 sum matches.
<code>
<pre>
sudo tar xvf apache-jmeter-5.3.tgz 
</pre>
</code>
Now install Moodle Performance Scripts.<br>
<code>
<pre>
cd /var/www
sudo git clone git://github.com/moodlehq/moodle-performance-comparison.git moodle-performance-comparison
cd moodle-performance-comparison
cp webserver_config.properties.dist webserver_config.properties
cp jmeter_config.properties.dist jmeter_config.properties
</pre>
</code>
