---
title: 'LiteSpeed Webserver'
taxonomy:
    category:
        - docs
---

A lot of buzz around this one and many claims it is faster than Apache. Installation is not difficult.
First add the repository
sudo wget -O - http://rpms.litespeedtech.com/debian/enable_lst_debian_repo.sh | sudo bash
Then update your system and install
sudo apt update
sudo apt install openlitespeed


sudo apt install lsphp72

sudo apt install graphviz aspell ghostscript clamav php7.2-pspell php7.2-curl php7.2-gd php7.2-intl php7.2-mysql php7.2-xml php7.2-xmlrpc php7.2-ldap php7.2-zip php7.2-soap php7.2-mbstring



Then enable php support - you will need to check the php version on your server. Ubuntu 18.04 is still back in 7.2

sudo ln -sf /usr/local/lsws/lsphp72/bin/lsphp /usr/local/lsws/fcgi-bin/lsphp5



