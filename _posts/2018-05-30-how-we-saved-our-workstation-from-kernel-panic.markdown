---
layout: post
title:  "Tips | How we saved a workstation from `kernal panic`"
date:   2018-05-30 15:29:01 +0800
categories: tips update 
---

Yesterday, CL consulted me about Chinese input mathod not working. BTW, he's using Ubuntu 16.04 on a Dell workstation. I 
checked the language support and found that Chinese option greyed out. The first thing came to my mind is to reinstall the 
Chinese language pack, but it didn't work. Howard suggested we upgrade to Ubuntu 18.04.

So I googled how to update 18.04 from 16.04 and found an answer on DigitalOcean community. The command is 

{% highlight bash %}
sudo do-release-upgrade -d
{% endhighlight %}

After like two hours of downloading and a lot of times inputting -y. CL claimed it's finished and nothing happened, so he 
chose to reboot the workstation. However, he cannot normally login. It said: "Kernel panic. Root fs cannot be mounted". 
Something like that. 

Ok, so we *entered the recovery mode and loaded the old kernel Linux 4.04*, and successfully entered the login page. Weird, 
still cannot access the desktop after entering correct password. Fortuantely, we can enter the terminal. Yeah! The first thing 
we did was to backup all the files in `/home/` directory to our data server. 

Today, I check the official site of Ubuntu and found that Ubuntu 16.04 can be upgrade to 18.04 in the late July... Anyway, I 
tried to run `update-manager -c` in the terminal and rebooted the workstation. BANG! Everything works now. The workstation is 
in Ubuntu 18.04 and no `kernel panic` error occurs. Hurray.



