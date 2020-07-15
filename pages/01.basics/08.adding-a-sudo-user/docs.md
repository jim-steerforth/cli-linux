---
title: 'Adding a sudo user'
taxonomy:
    category:
        - docs
---

<p>We are adding a new user called jimmy. Our new server has already given us a sudo user but some Linux distributions may log you in as root. This command assumes you have logged in as ubuntu, a sudo user. <br></p>
<div style="background-color:black;color:white;padding:20px;">
    sudo adduser jimmy

    <p>Set password prompts:<br> Enter new UNIX password:<br> Retype new UNIX password:<br> passwd: password updated successfully<br></p>
</div>
<p>
    Password is entered twice. Make sure it is strong. The other details can be folled in or skiped.</p>
<p></p>
<div style="background-color:black;color:white;padding:20px;">

    User information prompts:<br> Changing the user information for username<br> Enter the new value, or press ENTER for the default<br> Full Name []:<br> Room Number []:<br> Work Phone []:<br> Home Phone []:<br> Other []:<br> Is the information correct?
    [Y/n] Y<br>
    <p></p>

    sudo usermod -aG sudo jimmy
</div>
<p><br>

</p>
<p>In Ubuntu the logging on as root is strongly discouraged. We are creating a new user (jimmy). The user ubuntu is not root so we add sudo before the command, The user jimmy is then given sudo privileges. <br></p>
<p><b>From now on, never log in as root. Always use your new user and sudo to carry out any admin procedures.</b><br></p>