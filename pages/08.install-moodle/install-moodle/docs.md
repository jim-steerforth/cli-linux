---
title: 'Install Moodle'
media_order: 'server.jpg,configphp.jpg'
taxonomy:
    category:
        - docs
visible: true
---

    
   <p>  First step is to remove our placeholder /var/www/moodle' direectory using the interactive and recursive flags.</p>

<p style="font-family:Courier; color:white; background-color:black;">
sudo rm -ir /var/www/moodle
</p>


<p><pre>$ sudo rm -ir /var/www/moodle rm: descend into directory '/var/www/moodle'? y 
rm: remove regular file '/var/www/moodle/index.html'? y 
rm: remove directory '/var/www/moodle'? y</pre></p>

<p>
Change to the /var/www directory</p>

<p style="font-family:Courier; color:white; background-color:black;">
cd /var/www
</p>



<p style="font-family:Courier; color:white; background-color:black;">
sudo git clone git://git.moodle.org/moodle.git
</p>

<p><pre>$ sudo git clone git://git.moodle.org/moodle.git 
Cloning into 'moodle'...
remote: Counting objects: 1167105, done.
remote: Compressing objects: 100% (262652/262652), done.
remote: Total 1167105 (delta 869241), reused 1166956 (delta 869092)
Receiving objects: 100% (1167105/1167105), 394.79 MiB | 12.67 MiB/s, done.
Resolving deltas: 100% (869241/869241), done.
Checking out files: 100% (21144/21144), done.</pre></p>

<p>Change to the newly created directory</p>



<p style="font-family:Courier; color:white; background-color:black;">
cd moodle
</p>


<p style="font-family:Courier; color:white; background-color:black;">
sudo git branch -a 
</p>



verty slow...
<p style="font-family:Courier; color:white; background-color:black;">
sudo git branch --track MOODLE_39_STABLE origin/MOODLE_39_STABLE
</p>




<p><pre>sudo git branch --track MOODLE_39_STABLE origin/MOODLE_39_STABLE
[sudo] password for jimmy: 
Branch 'MOODLE_39_STABLE' set up to track remote branch 'MOODLE_39_STABLE' from 'origin'.</pre></p>

<p style="font-family:Courier; color:white; background-color:black;">
sudo git checkout MOODLE_39_STABLE
</p>


<p><pre>
$ sudo git checkout MOODLE_39_STABLE
Switched to branch 'MOODLE_39_STABLE'
Your branch is up to date with 'origin/MOODLE_39_STABLE'.</pre></p>
<p>
Set up ownership and permissions on the directories required by Moodle.</p>


<p style="font-family:Courier; color:white; background-color:black;">
sudo mkdir /var/moodledata <br>
sudo chown -R www-data /var/moodledata <br>
sudo chmod -R 777 /var/moodledata <br>
sudo chmod -R 0755 /var/www/moodle <br>
</p>


<p>Now go to your web page and complete the install. My web address https://vdsbasic.xyz </p>

Check the foldrer locatioms are
<ul>
  <li>Moodle directory /var/www/moodle </li>
  <li>Data directory /var/moodledata</li>
</ul>
<p>
You willl neede to enter Moodle database user and password.</p>

![](server.jpg)

All our requirements should be met.

![](configphp.jpg)
