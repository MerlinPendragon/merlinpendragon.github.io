---
layout: post
title:  "FAQ | 大容量存储服务器(THANOS)常见问题及解答 (持续更新中)"
date:   2018-05-27 16:49:01 +0800
categories: faq update research
---

### **如何下载广州超算的数据？**
#### pku_bqiao_1 账户

{% highlight bash %}
rsync -avzhe ssh --progress  gzcs:/WORK/pku_bqiao_1/远程路径 /本地路径
{% endhighlight %}

关于`rsync`的更多用法可以查阅[这个链接](https://www.tecmint.com/rsync-local-remote-file-synchronization-commands/)。
使用`rsync`的好处是如果下载断了，下次可以接着下。除了`rsync`之外，还可以使用`sftp`等命令。

#### NSFC 账户

{% highlight bash %}
rsync -avzhe ssh --progress  nsfc:/NSFCGZ/nsfc2015_8/远程路径 /本地路径
{% endhighlight %}

### **如何用两台工作站跑小模拟**
以 1d 为例

{% highlight bash %}
echo data | mpirun -n 64 -host master,slave /home/work/workspace/epoch-4.10.1/epoch1d/bin/epoch1d
{% endhighlight %}

注意`-host master,slave`分别是两台工作站的主机名。




