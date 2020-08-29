---
title: 'Moodle Backup'
visible: true
---

If you have students on your Moodle site, you have the responsibility to keep their work safe. Some time ago, while using a cheap VPS, I found my site had simply disappeared. The server was never seen again. Luckily I had course backups manually created and downloaded to my desktop. There were a couple of days old so an embarrassing situation but not critical.

So how should you back up? Automatically, at least daily and  with a copy stored in an offsite location. Here is how I do it:

First an automatic course back up. I set this up for around midnight, a time when mos students are finished. The backup creates a .mbz file can be used to restore a course on a different Moodle server. Set this up in:

Site administration -> Courses -> Backups -> Automated backup setup.

Set the schedule to daily, execute time can be left to default ( midnight), and specify the directory to /home/user/backup. You may have to first create this folder manually in Linux.

<pre><code>
cd ~
mkdir backup
</code></pre>


(The command cd ~ is a shortcut to your home directory ie /home/jimmy/)

Next step is a database dump. You can use the instructions from Moodle docs but there are a few problems with their instructions.

<pre><code>
cd /my/backup/directory
mv moodle-database.sql.gz moodle-database-old.sql.gz
mysqldump -h example.com -u myusername --password=mypassword -C -Q -e --create-options mydatabasename > moodle-database.sql
gzip moodle-database.sql
</code></pre>


First, the password is exposed in the script, not the best for security. Second, the database backups only go back one day. Finally, the backups are stored on the same server Moodle is running on so failure on the server could wipe Moodle and the backups. I want to suggest a better way - storing up to a week of database dumps, a daily back up offsite, and a daily delete of old files. Here is how to do it.