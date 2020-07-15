---
title: 'rm rmdir man'
media_order: man.jpg
taxonomy:
    category:
        - docs
---

We start with two sub-directories play and play2 in the home directory each containing one text file. How can we get rid of them?
<div style="background-color:black;color:white;padding:20px;">$ cd ~<br> $ rm play/file2.txt<br> $ rmdir play<br> $ rmdir play2<br> rmdir: failed to remove 'play2': Directory not empty<br></div>


<p><br></p>
<p>From the home directory we can delete the file in the sub-directory and then remove the empty directory. The directory play2 is not empty and can't be removed with rmdir.</p>
<p>
</p>
<div style="background-color:black;color:white;padding:20px;">$ rm -r play2<br> $ cd play2<br> bash: cd: play2: No such file or directory</div><br>
<p></p>
<p>
</p>
<div style="background-color:black;color:white;padding:20px;">rm -r</div> does it though. The -r stands for recursive which means it will delete all files and sub=directories. <b>Caution - deleting directories by mistake can do a lot of damage! There is a better way</b>
<p></p>
<p>

</p>
<div style="background-color:black;color:white;padding:20px;">&gt;$ rm -ir play<br> rm: descend into directory 'play'? y<br> rm: remove regular empty file 'play/file1.txt'? y<br> rm: remove directory 'play'? y<br></div>
<p></p>
<div>

    The -i flag means interactive so&nbsp; each deletion is confirmed. Note we can use rm with no flags or several flags such as i or r after the dash to alter the behaviour of the command.</div>
<div><br></div>

<p>How to remember all these codes? You get help by using the <kbd>man</kbd> command.<br>
</p>
<div style="background-color:black;color:white;padding:20px;"> man rm</div><br> Scroll up and down with the arrow keys and the letter <kbd>q</kbd> exits.
<p></p>

![](man.jpg)

