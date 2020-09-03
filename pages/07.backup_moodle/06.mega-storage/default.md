---
title: 'Mega Storage'
---

 <p>   Dropbox wih 2 gB of storage not enough? </p>
    
 <p>Mega is an alternative which offers 50 gB of free storage. But there is a <a href="https://www.cloudstorageoptions.com/mega/">catch</a> . The amount you can upload is limited and subject to change. As  August 2020 it is around 1 gB every six hours. Free won't be perfect but if your backups and dumps are less than a Gig a day, Mega is an option. You coold use more than one free service, that is your production server, and two copies each night on separate servers.</p>
<p>    Mega can sync to your home computer but this will mean downloads every night over your internet connection. Perhaps best to just use Megatools and send your updates straight from your productions server to the Mega account.</p>
<p>The latest version will be at  <a href="https://megatools.megous.com/builds/experimental/">https://megatools.megous.com/builds/experimental/</a> <br>
You may have to adjust the version number, at 1.11.0 at the time of writing.</p>
<code><pre>
cd ~/bin
wget    https://megatools.megous.com/builds/experimental/megatools-1.11.0-git-20200503-linux-i686.tar.gz
tar xvf megatools-1.11.0-git-20200503-linux-i686.tar.gz
</pre></code>

<p>This produces a directory structure with the tools in the megatools subdirectory.</p>

<p>megatools-1.11.0-git-20200503-linux-i686/<br>
</p>

 
So move the folder to a simpler name.<br>
 <code>
 mv megatools-1.11.0-git-20200503-linux-i686 megatools1.11.0
</code>   

Next step is to create a soft link to a directory in our path. A link is a shortcut and will allow the megatools script to be called from anywhere in the file system.
    </p>
 <code>   
      sudo   ln -s ~/bin/megatools1.11.0/megatools /usr/sbin/megatools<br>
    </code>   
                                                
<p>
This page describes the process of <a href="https://megatools.megous.com/man/megatools-reg.html">Megatool Registration</a>
</p>


First step is<br>
megatools reg [--scripted] --register --email <email> --name <realname> --password <password><br>

Like this:<br>
<code>
megatools reg  --register --email myname@email.com --name Jimmy --password mypassword
</code>   
    
This comes back:<br>
    
<p>
Registration email was sent to yourname@email.com. To complete registration, you must run:<br>
<br>
  megatools reg --verify VzwR4EHWlSszpICYHkVcgg==:04ejblahblahblahblah73AJg==:VA64x90TvUY @LINK@<br>
<br>
(Where @LINK@ is registration link from the 'MEGA Signup' email)<br>
<p>
Go to your emailand ignore the tempting "Accept" button. Instead copy the link starting with https and replace the @LINK@</p>

<code>      
megatools reg --verify VzwR4EHWlSszpICYHkVcgg==:04ejblahblahblahblah73AJg==:VA64x90TvUY https://mega.nz/#confirmblahblahnlah<br>
</code>     
    <p>
        Account registered successfully! 
    </p>
    
<p>
Megatools need the user name and password in commands. Rather than passing it through every comnand, create a config file.
    </p>
    
<code>
    cd ~/bin/megatools1.11.0 <br>
    nano .megarc <br>
 </code>  
    
Uncomnent (remove leding hash)  and edit the three lines.  <br>
 
     <code> 
[Login]<br>
Username = your [at] email<br>
Password = yourpassword<br>
  </code>    
<p>    

Now try a command to check free space.<br>
 <code>    
$megatools  df
     </code> 
    
    The result:<br>
Total: 53687091200<br>
Used:  0<br>
Free:  53687091200<br>
  
    
<p>
Now test by creating a folder on Mega,copy over the docs dirctory and delete the folder.
    </p>
    
<code><pre>    
$ megatools mkdir /Root/NewFolder
$ megatools ls /Root
/Root
/Root/NewFolder
    
megatools copy --local docs --remote /Root/NewFolder
    
/Root/NewFolder/.megarc
/Root/NewFolder/docbook-xsl.css
/Root/NewFolder/megarc.html
/Root/NewFolder/megatools-copy.html
/Root/NewFolder/megatools-df.html
    
$ megatools rm /Root/NewFolder
$ megatools ls /Root 
/Root
 </pre> </code> 
    <p>
    So we can create folders, copy and delete.
    </p>
    Script 2 sends only course backups to Dropbox. 
    

    
    


    


    



