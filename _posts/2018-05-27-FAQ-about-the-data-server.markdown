---
layout: post
title:  "FAQ | 大容量存储服务器(THANOS)常见问题及解答 (持续更新中)"
date:   2018-06-05 16:49:01 +0800
categories: faq update research
---

### 2019.08.27 更新

1. 近期 vpn 出现问题，导致连不上广超，请各位通过自己的电脑连接。
2. slurm作业调度系统已安装，请使用slurm来提交小模拟
以 1d 为例

{% highlight bash %}
echo data | srun -p debug -N 1 -n 需要的核数 /epoch的路径/
{% endhighlight %}

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

### **如何用两台工作站跑小模拟？**
以 1d 为例

{% highlight bash %}
echo data | mpirun -n 64 -host master,slave /home/work/workspace/epoch-4.10.1/epoch1d/bin/epoch1d
{% endhighlight %}

注意`-host master,slave`分别是两台工作站的主机名。

### **如何远程处理数据？**

#### 使用 Jupyter Notebook

用浏览器打开 [https://162.105.227.116](https://162.105.227.116) 。可以看到一个登陆界面，我根据 `workspace` 下面大家各自的文件夹名字给大家建立了账号，例如：iridium sxf leiz 等，初始密码为 123456。使用账号密码登陆后即可使用 Jupyter Notebook 处理数据。

请大家采用如下命令及时修改密码

{% highlight bash %}
sudo passwd 用户名
{% endhighlight %}

#### Jupyter 快速上手

参考 `/home/work/workspace/tutorial.ipynb` 的内容。




