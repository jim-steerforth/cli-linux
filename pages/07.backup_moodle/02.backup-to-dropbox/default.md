---
title: 'Backup to Dropbox'
published: true
---

You could back up your Moodle to your home computer but there are a couple of reasons why not.
* Your home computer needs to be on and connected to the internet 
* Connections to your home run on lower grade connections.

A better solution is to use somewhere in the cloud. A Dropbox account with a 2 gb limit may be all you need to have at least a couple of days of course and database backups completely independent of your hosting provider. 

First you need a script called Dropbox-Uploader. 


mkdir ~/bin
cd ~/bin
sudo git clone https://github.com/andreafabrizi/Dropbox-Uploader.git<br>
cd Dropbox-Uploader<br>
sudo chmod +x dropbox_uploader.sh<br>

This adds a script to the ~/bin directory and makes it executable.
Next Dropbox needs to be set up, by going to the https://www.dropbox.com/developers/apps page and clickong on the "Create Apps" page to go to the "Create a new app on the DBX Platform" page.
In "Choose an API" choose "Legacy", choose "Full Dropbox" under access and give it a name (I just called it wonk) before agreeeing to the conditions and clicking the "Create an App" button.

When you come back to the first page,  find “Generated access token”, set Access token expiration to never   and click the “Generate” button and copy the access token. 

Come back to your own server and run the dropbox uploader script for the first time.

~/bin/Dropbox-Uploader/dropbox_uploader.sh

It should ask you for the token. Now you can test creating folders, uploading and deleting files from the command line to Dropbox.


touch ~/upload1.txt
~/bin/Dropbox-Uploader/dropbox_uploader.sh upload ~/upload1.txt /
 > Uploading "/home/grantm/upload1.txt" to "/upload1.txt"... DONE
grantm@ThinkPad-T420:~$ ~/bin/Dropbox-Uploader/dropbox_uploader.sh list
 > Listing "/"... DONE
 [F] 240     Get Started with Dropbox Paper.url
 [F] 1102331 Get Started with Dropbox.pdf
 [F] 0       upload1.txt

~/bin/Dropbox-Uploader/dropbox_uploader.sh list
 > Listing "/"... DONE
 [F] 240     Get Started with Dropbox Paper.url
 [F] 1102331 Get Started with Dropbox.pdf
 [F] 0       upload1.txt
 
 ~/bin/Dropbox-Uploader/dropbox_uploader.sh list
 > Listing "/"... DONE
 [F] 240     Get Started with Dropbox Paper.url
 [F] 1102331 Get Started with Dropbox.pdf
 [F] 0       upload1.txt









