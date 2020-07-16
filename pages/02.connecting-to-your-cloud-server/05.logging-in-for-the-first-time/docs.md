---
title: ' Logging in for the first time'
taxonomy:
    category:
        - docs
---

Go to your welcome email and find your username and password. <br>
<p>In Termux enter <b>ssh username@domain</b>. For example, the username sent to me was ubuntu and my domain is vdsbasic.xyz so my command is <br></p>
<div style="background-color:black;color:white;padding:20px;">
    ssh ubuntu@vdsbasic.xyz
</div>

<p>If you get the message ssh command not found in Termux, install openssh<br></p>
<p>
</p>
<div style="background-color:black;color:white;padding:20px;">
    apt install openssh
</div>
<p></p>
<p>As the first login. it will tell you the authenticity host can not be verified, Continue connecting (yes)</p>
<div style="background-color:black;color:white;padding:20px;">

    <p>ssh ubuntu@yourserver.xyz<br>The authenticity of host 'yourserver.xyz (44.156.23.97)' can't be established.<br>ECDSA key fingerprint is SHA256:+g1ilXCbm......./wEOvzRG31EsTNP292IE52gfQBI.<br>Are you sure you want to continue connecting (yes/no)? yes
        <br>Warning: Permanently added 'vdsbasic.xyz,44.156.23.97' (ECDSA) to the list of known hosts.<br>Please login as the user "ubuntu" rather than the user "root".<br>ubuntu@vdsbasic.xyz's password: :<br>Welcome to Ubuntu 18.04.4 LTS (GNU/Linux 4.15.0-88-generic
        x86_64)
        <br><br>* Documentation: https://help.ubuntu.com<br>* Management: https://landscape.canonical.com<br>* Support: https://ubuntu.com/advantage<br><br> System information as of Tue Jul 7 11:05:34 UTC 2020<br><br> System load: 0.0 Processes: 85
        <br> Usage of /: 13.9% of 9.52GB Users logged in: 0<br> Memory usage: 17% IP address for ens3: 44.156.23.97
        <br> Swap usage: 0%<br><br><br>124 packages can be updated.<br>75 updates are security updates.<br><br>ubuntu@vdsbasic:~$ <br></p>
</div>

<p>.</p>
<p>You are now on the command line of your new Linux machine. Next step is to create a sudo user and if  ypu haven't used Linux before, learn the basic commands.</p>