---
title: 'Create Swap space'
taxonomy:
    category:
        - docs
visible: true
---

<p>Swap is disk space that is used when the amount of physical RAM memory is full. Inactive pages are moved from the RAM to the swap space. With a RAM of only 1G, creating swap space is recommended.</p>

<p>Check if swap is enabled. No swap shows as a blank line.</p>

 <p style="font-family:Courier; color:white; background-color:black;">
 sudo swapon --show
</p>   
 <p>This will add a 1G swap file. This is about right for doubling our RAM.</p>
<p> 
Create a file to be used for swap</p>
 <p style="font-family:Courier; color:white; background-color:black;">
 sudo fallocate -l 1G /swapfile
</p>   

<p>Set file permissions only for root.</p>

 <p style="font-family:Courier; color:white; background-color:black;">
 sudo chmod 600 /swapfile
</p>   

 <p>Set up a Linux swap area.</p>
 
 <p style="font-family:Courier; color:white; background-color:black;">
 sudo mkswap /swapfile
</p>   
 <p><pre>$ sudo mkswap /swapfile
Setting up swapspace version 1, size = 1024 MiB (1073737728 bytes)
no label, UUID=c83cd3a3-08e4-4997-ad46-6e8113528c16</pre></p>

<p>Activate</p>

 <p style="font-family:Courier; color:white; background-color:black;">
sudo swapon /swapfile
</p> 


<p>Check your new swap space.</p>

 <p style="font-family:Courier; color:white; background-color:black;">
sudo swapon --show
</p> 
 
 
<p><pre> 
 $  sudo swapon --show
NAME      TYPE  SIZE USED PRIO
/swapfile file 1024M   0B   -2
</pre></p>

<p>Edit the available disk partition on the file systems table.</p>

 <p style="font-family:Courier; color:white; background-color:black;">
sudo nano /etc/fstab
</p> 


<p> Paste the following line at the end of the file. This will retain the swap after a reboot.</p>

 <p style="font-family:Courier; color:white; background-color:black;">
/swapfile swap swap defaults 0 0
</p> 

<p>My fstab looks like this:<br>
<pre>
LABEL=cloudimg-rootfs   /        ext4   defaults        0 0
LABEL=UEFI      /boot/efi       vfat    defaults        0 0
/swapfile swap swap defaults 0 0
</pre>
</p>

 
<h3>Additional Reading </h3>  
    <a href="https://linuxize.com/post/how-to-add-swap-space-on-ubuntu-18-04/">How to Add Swap Space on Ubuntu 18.04</a>











