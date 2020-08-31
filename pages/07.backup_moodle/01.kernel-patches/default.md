---
title: 'Kernel Patches'
published: true
---

Personal users of Ubuntu can subscribe three machines (laptop, server or cloud) free of charge.  This service will apply critical kernel patches without rebooting. This keeps your server safe from a weakness found in the kernel,
First, create an account on [UbutuOne](https://login.ubuntu.com/). Then go to [LivePatch](https://ubuntu.com/livepatch)  to get your token.

The first two lines copied from the LivePatch site install the patch. The next line shows the status of my system with the kernel automatially patched.

<pre>
    
sudo snap install canonical-livepatch
sudo snap install canonical-livepatch <token>    
   
    
sudo canonical-livepatch  status
last check: 49 minutes ago
kernel: 4.15.0-112.113-generic
server check-in: succeeded
patch state: ✓ no livepatches needed for this kernel yet
</pre>


