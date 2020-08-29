---
title: 'Create a config file for MySQL   '
---

The config file allows the database to be backed up without using a password. More secure and more convenient.  The file is a hidden file under the home directory.

<pre><code>
nano ~/.my.cnf

[mysql]
user = mysqluser
password = secret

[mysqldump]
user = mysqluser
password = secret
</code></pre>

Set the config file permissions. <br>


<pre><code>
chmod 600 ~/.my.cnf
    
</code></pre>