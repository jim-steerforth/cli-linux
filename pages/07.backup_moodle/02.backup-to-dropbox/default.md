---
title: 'Backup to Dropbox'
published: true
---

You could back up your Moodle to your home computer but there are a couple of reasons why not.
* Your home computer needs to be on and connected to the internet 
* Connections to your home run on lower grade connections.
A better solution is to use somewhere in the cloud. A Dropbox account with a 10 gb limit may be all you need to have at least a couple of days of course and database backups completely independent of your hosting provider. 
First you need a script called Dropbox-Uploader. 

cd /opt
git clone https://github.com/andreafabrizi/Dropbox-Uploader.git
cd Dropbox-Uploader
chmod +x dropbox_uploader.sh

This adds a script to the /opt directory and makes it executable.
Next Dropbox needs to be set up, by going to the https://www.dropbox.com/developers/apps page and clickong on the "Create Apps" page to go to the "Create a new app on the DBX Platform" page.
In "Choose an API" choose "Scoped Access", choose "Full Dropbox" under access and give it a name before clicking the "Create an App" button.
When you come back to the first page, find “Generated access token” and click the “Generate” button and copy the access token.
Run the script for the first time.
/opt/Dropbox-Uploader//dropbox_uploader.sh
It should ask you for the token.




