---
title: 'Mega Storage !!Under Development!!'
---

 <p>   Dropbox wih 2 gB of storage not enough? Mega offers 50 gB, more obviously but may not be as reliable as Dropbox. Nothing to stop you from using both, that is your production server, and two copies each night on separate servers.</p>
<p>    Mega can sync to your home computer but this will mean downloads every night over your internet connection. Perhaps best to just use Megatools and send your updates straight from your productions server to the Mega account.</p>
<p>The latest version will be at https://megatools.megous.com/builds/experimental/<br>
You may have to adjust the version number.</p>
<code><pre>
cd ~/bin
wget    https://megatools.megous.com/builds/experimental/megatools-1.11.0-git-20200503-linux-i686.tar.gz
tar xvf megatools-1.11.0-git-20200503-linux-i686.tar.gz
</pre></code>

 <p>   Dropbox wih 2 gB of storage not enough? Mega offers 50 gB, more obviously but may not be as reliable as Dropbox. Nothing to stop you from using both, that is your production server, and two copies each night on separate servers.</p>
<p>    Mega can sync to your home computer but this will mean downloads every night over your internet connection. Perhaps best to just use Megatools and send your updates straight from your productions server to the Mega account.</p>
<p>The latest version will be at https://megatools.megous.com/builds/experimental/<br>
You may have to adjust the version number.</p>
<code><pre>
cd ~/bin
wget    https://megatools.megous.com/builds/experimental/megatools-1.11.0-git-20200503-linux-i686.tar.gz
tar xvf megatools-1.11.0-git-20200503-linux-i686.tar.gz
</pre></code>

<p>This produces a directory structure with the tools in the megatools subdirectory.</p>

<p>megatools-1.11.0-git-20200503-linux-i686/<br>
megatools-1.11.0-git-20200503-linux-i686/megatools
</p>
<code>
cd megatools-1.11.0-git-20200503-linux-i686/megatools 
</code>
<p>
This page describes the process of <a href="https://megatools.megous.com/man/megatools-reg.html">Megatool Registration</a>
</p>



 <p>   Dropbox wih 2 gB of storage not enough? Mega offers 50 gB, more obviously but may not be as reliable as Dropbox. Nothing to stop you from using both, that is your production server, and two copies each night on separate servers.</p>

<p>    Mega can sync to your home computer but this will mean downloads every night over your internet 
</pre></code>

<p>This produces a directory structure with the tools in the megatools subdirectory.</p>

<p>megatools-1.11.0-git-20200503-linux-i686/</p>
 
So move the folder to a simpler name.<br>
 <code>
 mv megatools-1.11.0-git-20200503-linux-i686 megatools1.11.0
</code>                                                
                                                
<p>
This page describes the process of <a href="https://megatools.megous.com/man/megatools-reg.html">Megatool Registration</a>
</p>

cd ~/bin/megatools1.11.0

First step is<br>
megatools reg [--scripted] --register --email <email> --name <realname> --password <password>

Like this:
<code>
./megatools reg  --register --email myname@email.com --name Patrick --password mypassword
</code>   
    
This comes back:
    
<p>
Registration email was sent to yourname@email.com. To complete registration, you must run:<br>

  megatools reg --verify VzwR4EHWlSszpICYHkVcgg==:04ejblahblahblahblah73AJg==:VA64x90TvUY @LINK@<br>

(Where @LINK@ is registration link from the 'MEGA Signup' email)<br>
<p>
Go to your emailand ignore the tempting Accept button. Instead copy the link starting with https and replace the @LINK@</p>

<code>      
megatools reg --verify VzwR4EHWlSszpICYHkVcgg==:04ejblahblahblahblah73AJg==:VA64x90TvUY https://mega.nz/#confirmblahblahnlah
</code>     
    <p>
        Account registered successfully!
    </p>
<p>
Next step is to add the new directory to our path so we can call the tools from anywhere.
</p>  
<p>
Megatools need the user name and password in commands. Rather than passing it through every comnand, create a config file.
    </p>
    
<code>
    nano ~/.megarc
 </code>  
    
Add three lines.  
 
     <code> 
[Login]
Username = your [at] email
Password = yourpassword
  </code>    
    



