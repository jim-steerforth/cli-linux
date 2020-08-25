---
title: 'Create a config file for MySQL   '
---

The config file allows the database to be backed up without using a password. More secure and more convenient.  The file is a hidden file under the home directory.

<pre><code>
nano ~/.my.cnf

[mysqldump]
user = mysqluser
password = secret

chmod 600 ~/.my.cnf
    
</code></pre>