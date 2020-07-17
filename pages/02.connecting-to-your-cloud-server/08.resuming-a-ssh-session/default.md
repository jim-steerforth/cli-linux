---
title: 'Resuming a SSH Session'
published: false
---

One of the frustration you ma have is the ssh session terminates and you need to log in again. Terminating the SSH session may also terniante the process running in the window.
Run this command to open a terminal multiplexer.
jimmy@vds2:~$ screen
Now if you are logged out, when you log enter:

jimmy@vds2:~$ screen -ls
There is a screen on:
	1554.pts-2.vds2	(07/17/20 06:00:42)	(Detached)
1 Socket in /run/screen/S-jimmy.
jimmy@vds2:~$ screen -r 1554


The screen -ls command lists the windows openm one with number 1554. screen -r 1554 opens the previous window which has continued to run in tteh background.



[More details are here.](https://www.howtogeek.com/662422/how-to-use-linuxs-screen-command/)