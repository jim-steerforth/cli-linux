---
title: Benchmarking
media_order: Bencnm.png
taxonomy:
    category:
        - docs
---

This used a Moodle plugin called Moodle Benchmarking to give an indicatioon of weaknesses in your system.
Dashboard -> Site administration -> Plugins -> Install plugins
Installing failed because of being unable to write to /var/www/html/moodle/report so this is fixed by a temporary change to permissions. Mine is set up to drwxr-xr-x which is 755 meaning the directory is unable to be written to
sudo chmod 777 /var/www/html/moodle/report
Then run the benchnark plugin again and
sudo chmod 755 /var/www/html/moodle/report
After a few checks, upgrade your database.
Dashboard -> Site administration -> Reports -> Benchmark

![](Bencnm.png)

This is a Hostvds 1 CPU and 1gB of Ram, 1 gB Swap space with newly installed Moodle on Ubutnu 18.04. Database and PHP with extensins were installed and config files were at default.



