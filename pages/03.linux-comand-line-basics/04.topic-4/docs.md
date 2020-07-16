---
title: 'Keyboard Tricks'
media_order: termux4a.png
taxonomy:
    category:
        - docs
---

<b>Auto complete</b>
<p>This is standard on all Linux and a great time saver. <br></p>

<p style="font-family:Courier; color:white; background-color:black;">
cd ~<br>
mkdir verylongandhardtoremberdirectoryname1</p>



<p>Now push the arrow key for UP. The last command is shown.Backspace the last character of 1 and replace it with a 2.</p>

<p style="font-family:Courier; color:white; background-color:black;">
cd ~<br>
mkdir verylongandhardtoremberdirectoryname2<br>
cd v[TAB] 
</p> 
<p>Here tab is shown by the arrow keys.</p>
<p>The shell autocompletes the file up to the point where the two files differ.</p>


<p>You can also move the Termux keyboard to the left so you have the standard Android keyboard with auto-complete.</p>

<p>This next step uses what we have learned.</p>


<p style="font-family:Courier; color:white; background-color:black;">
mkdir ~/.termux
</p>

<p>This creates a directory under the home directory.The leading . means it is a hidden directory for configuration files.</p>

<p style="font-family:Courier; color:white; background-color:black;">
nano ~/.termux/termux.properties</p>This opens up a nano editing session. Copy the new section into nano.
</p>



<p style="font-family:Courier; color:white; background-color:black;">
extra-keys = [['ESC','/','HOME','UP','END','PGUP'],['TAB','CTRL','ALT','LEFT','DOWN','RIGHT','PGDN']]
</p>



<p>
    Select CTRL-X to exit, select y when asked to save and comfirm the filename.</p>

    ![](termux4a.png)
    <p style="font-family:Courier; color:white; background-color:black;"cat ~/.termux/termux.properties will show you the contents of the file.</p>


<p style="font-family:Courier; color:white; background-color:black;">
termux-reload-settings</p> This final step will set up your Termux to have extra keys for moving left and right.</p>

![](termux4a.png)