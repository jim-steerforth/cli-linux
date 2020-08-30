---
title: 'Dropbox script'
published: true
taxonomy:
    category:
        - docs
---

<!DOCTYPE html>

<!-- Created on 30 Aug 2020, 4:14:25 pm -->

<html lang="en">
  <head>
    <meta charset=utf-8 />
    <title>
      Enter a title here
    </title>
    <meta name="GENERATOR" content="Arachnophilia 5.5" />
    <meta name="FORMATTER" content="Arachnophilia 5.5" />
  </head>
  
  <body>
<pre>
    #!/bin/bash

# Created on Oct 26, 2019, 8:37:00 PM


#Author = JamesSteerforth
#Version 1.0


#START

TODAY=`date +"%Y%m%d"`

count=2   # How many days of backup do you want to keep?
# This will depend on how big your backup files are and how much space you have on dropbox
# Check available space on dropbox after a few days of running


EXPIRYDATE=$( echo `date -d "${TODAY} -${count} days" +"%Y%m%d"`)

# create this directory if it doesn't already exist ie mkdir ~/backup
BACKUPDIR=~/backup


#define databaseName 
DATABASENAME=$BACKUPDIR/moodle-database-$TODAY.sql.gz

COURSEBACKUP=$BACKUPDIR/backup-moodle2-course-2-sept19-$TODAY-2353.mbz
# this course backup is created by Moodle. You need to match the name in this area.
# My file is called backup-moodle2-course-2-sept19-20200222-2353.mbz
# The string 20200222 is the date string "today" created by this script. 
# You need to match all the rest


# Command to dump and zip the database. You need to create the .my.cnf file for user moodledump file to avoid the password 
mysqldump -h localhost  -u moodledump  -C -Q -e --create-options moodle | gzip > $DATABASENAME

# The files are stored in the root directory of Dropbox. Ypu may need to adjust.
OLDDATABASENAME=/moodle-database-$EXPIRYDATE.sql.gz
OLDCOURSEBACKUP=/backup-moodle2-course-2-sept19-$EXPIRYDATE-2353.mbz


#Add the latest backups
~/bin/Dropbox-Uploader/dropbox_uploader.sh upload $DATABASENAME /
~/bin/Dropbox-Uploader/dropbox_uploader.sh upload $COURSEBACKUP /

#Delete the old to save space
~/bin/Dropbox-Uploader/dropbox_uploader.sh delete  $OLDDATABASENAME /
~/bin/Dropbox-Uploader/dropbox_uploader.sh delete  $OLDCOURSEBACKUP /

#Delete  from our backup directory  after 5 days. More space than on Dropbox so can afford to keep them longer.
find $BACKUPDIR/ -type f -name '*.mbz' -mtime +5 -exec rm {} \;
find $BACKUPDIR/ -type f -name '*.sql.gz' -mtime +5 -exec rm {} \;

#echo $BACKUPDIR
#echo $DATABASENAME
#echo $OLDDATABASENAME
#echo $COURSEBACKUP
#echo $OLDCOURSEBACKUP

#rm  $OLDDATABASENAME
#rm  $OLDCOURSEBACKUP

#end 
</pre>   
  </body>
</html>