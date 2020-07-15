---
title: 'touch cd mv cp'
media_order: termux2a.png
taxonomy:
    category:
        - docs
---

![](termux2a.png)
<p>The command<kbd>
 touch
</kbd> creates an empty file. We have started in the home directory so the new file will be one level down.</p>

<p><kbd>
cd folder1
</kbd> takes us to the folder and ls shows the new file.</p>
<p><kbd>mv file1.txt ~/folder2
</kbd> moves the folder to another subdirectory of the home folder. ls shows the file has moved. Another use of mv is to rename a file. For example <br>
    <kbd>mv file1.txt file2.txt</kbd><br> will rename the file to file2.txt.</p>
<p>cd takes us to folder2 and we confirm the file is there. Copying the file is done like this:<br>
    <kbd>cp file1.txt ~/folder1</kbd>. Here the<br><kbd> ~/folder1</kbd><br> is an absolute reference to /home/folder1</p>

<p><kbd>
ls
</kbd> shows the file is in both directories</p><br>