---
layout: post
title:  "Tips | How to start an afp server for file sharing and time machine backup on Ubuntu"
date:   2018-06-04 23:09:01 +0800
categories: tips afp timemachine  
---

The one thing after we set up our data server is to remotely access the file directory on the data server. Originally, I used samba service on the workstation, but today I wanna try something new. AFP, a.k.a. Apple Filing Protocol, is a file sharing protocal developed by Apple. Since Yao and I use Mac, why not try it out? Also, nfs protocol is extremely slow for read/write on Mac, idk why. 

First, we need netatalk and avahi. For, install all the dependency packages. Follow the instruction on the [official website](http://netatalk.sourceforge.net/3.1/htmldocs/installation.html). Note that you can only get 2.x version of netatalk if you use apt. So the best way is to obtain the latest release from the official website.

Second, config netatalk. Edit this file `sudo vim /usr/local/etc/afp.conf`. The format is quite same as smb.conf. You can set User and default path for each entry.

Third, start `avahi-daemon` service first and then start `afpd`.

Bang! You can now mount the shared volume by going to finder, `cmd+k`, enter `afp://[ip address]`. And, done. 

After that, I thought, why not try to use the data server as a time machine back up for my Mac. The setting is quite easy. Just set `time machine = yes` in the entry. All the parameter is explained on the [manual page](http://netatalk.sourceforge.net/3.0/htmldocs/afp.conf.5.html) 





