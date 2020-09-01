---
title: 'Transfering files'
published: true
taxonomy:
    category:
        - docs
---

<p>FTP is usually the best choice for transferring files to a remote computer but sometimes for a single file or folder, scp is an alternative. Use this command to send a zipped folder from the current folder to a folder on the remote computer.</p>
<code>
scp myfolder.zip jimmy@vdsbasic.xyz:/home/jimmy/transfer
</code>
<p>Once it is in place we can unzip it:</p>
<code>
unzip myfolder.zip
</code>
<p>It will create a directory structure but the tree will be under ~/transfer. We need to move it while preserving the file structure. The easiest way is to use rsync with the r ( recursive function)</p>

First:<br>
<code>
sudo mkdir /var/www/html/myfolder <br>
rsync -r ~/transfer/ /var/www/html/myfolder <br>
</code>
<p>The command copies all the files to the new directory.</p>
<p>
Becoming familiar with these commands is very useful when working in Linux. Don't worry about remembering the syntax - I often google and copy. What is important is knowing which command to use.</p>
<p>
The rsync command is a very useful one and can also be used to transfer folders from one computer to another. This [page](https://www.digitalocean.com/community/tutorials/how-to-use-rsync-to-sync-local-and-remote-directories-on-a-vps) goes into detail for this command. </p>

