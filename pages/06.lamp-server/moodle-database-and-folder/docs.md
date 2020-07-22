---
title: 'Moodle Database and Folder'
published: true
taxonomy:
    category:
        - docs
visible: true
---

<p>This section sets up the database for Moodle. This will be done on the MySql command line. The password ypu enter is the password for user root as set in securing MySql.
</p>

    
<p style="font-family:Courier; color:white; background-color:black;">
$ sudo mysql -u root -p
</p>   

The first password us for the Linux sudo user, the second for the mysql root user.

    
<pre>
$ sudo mysql -u root -p 
[sudo] password for jimmy: 
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 10
Server version: 5.7.30-0ubuntu0.18.04.1 (Ubuntu)

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> 
 </pre>
 
<p>You are now in the mysql program as shown by the mysql prompt. Copy these commands, replace 'moodledude' with a name and 'passwordformoodledude' bya suitably strong password. You will need this username and password when you install Moodle.</p>


<p style="font-family:Courier; color:black; background-color:gainsboro;">
CREATE DATABASE moodle DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;<br>

create user 'moodledude'@'localhost' IDENTIFIED BY 'passwordformoodledude';<br>

GRANT SELECT,INSERT,UPDATE,DELETE,CREATE,CREATE TEMPORARY TABLES,DROP,INDEX,ALTER ON moodle.* TO moodledude@localhost IDENTIFIED BY 'passwordformoodledude';<br>

quit;<br>
</p>
