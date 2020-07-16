---
title: 'Installing WSL'
published: true
---

<p>Windows 10 has a Linux subsystem. If you are running Windows build 16215 or later, here is how you can access this windows feature. You can check your Windows build number by opening a command prompt (Right click on Start menu &gt; Run &gt; Type <kbd>cmd</kbd>)
    and then type
</p>


<p><kbd>
wmic os get BuildNumber
</kbd></p>


I get BuildNumber 17134 so I am good to go. [Instructions from Microsoft are here.](https://docs.microsoft.com/en-us/windows/wsl/install-win10)


<p>First you must open Windows PowerShell (from the start menu) as Administrator and run <br><b> Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux</b><br> Then restart your computer when prompted.</p>


<p>After the restart: <br> Open the Microsoft store and find the latest version of Ubuntu LTS (18.04 at the time of writing) as this is stable and up-to-date.<br> Select "Get" to download.<br> Now initialize it by launching from your Start menu.<br></p>


<p>What you should see is a command window saying Installing, this may take a few minutes. Be prepared to wait a few minutes.</p>


<p>First you are asked to enter a new UNIX username and a password. This is the "sudo user" so write down the username and password. When you add new programs or modify settings you log on as the sudo user.</p>
<p>Like Termux, this isn't "real" Linix but an emulation. <br></p>