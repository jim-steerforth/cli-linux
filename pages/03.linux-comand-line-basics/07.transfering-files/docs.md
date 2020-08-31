---
title: 'Transfering files'
taxonomy:
    category:
        - docs
---

<p>FTP is usually the best choice for transferring files to a remote computer but sometimes for a single file or folder, scp is an alternative. Use this command.</p>
<code>
scp myfolder.zip jimmy@vdsbasic.xyz:/home/jimmy/transfer
</code>
<p>Once it is in place we can unzip it:</p>
<code>
unzip myfolder.zip
<code>
<p>It will create a directory structure but the tree will be under ~/transfer. We need to move it while preserving the file structure. The easiest way is to use rsync with the r ( recursive function)</p>

First:<br>
<code>
sudo mkdir /var/www/html/myfolder
rsync -r ~/transfer/ /var/www/html/myfolder
</code>
<p>The command copies all the files to the new directory.</p>
<p>
Becoming familiar with these commands is very useful when working in Linux. Don't worry about remembering the syntax - I often google and copy. What is important is knowing which command to use.</p>

