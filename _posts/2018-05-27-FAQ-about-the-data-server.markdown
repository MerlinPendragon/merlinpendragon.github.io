---
layout: post
title:  "FAQ | 大容量存储服务器(THANOS)常见问题及解答 (持续更新中)"
date:   2018-05-27 16:49:01 +0800
categories: faq update research
---

1. **如何下载广州超算的数据？**
  * pku_bqiao_1 账户

		{% highlight bash %}
		rsync -avzhe ssh --progress  gzcs:/WORK/pku_bqiao_1/lxb/epoch-xb/epoch2d/ .
		{% endhighlight %}

   关于 rsync 的更多用法可以查阅[这个链接](https://www.tecmint.com/rsync-local-remote-file-synchronization-commands/)

  * NSFC 账户

		{% highlight bash %}
		rsync -avzhe ssh --progress  nsfc:/NSFCGZ/nsfc2015_8/xuxr/ .
		{% endhighlight %}

2. **如何用两台工作站跑小模拟**

    以 1d 为例

		{% highlight bash %}
		echo data | mpirun -n 64 -host master,slave /home/work/workspace/epoch-4.10.1/epoch1d/bin/epoch1d
		{% endhighlight %}




