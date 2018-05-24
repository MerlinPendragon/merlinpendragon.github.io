---
layout: post
title:  "Tips | How to connect 2 workstations"
date:   2018-05-24 14:41:01 +0800
categories: tips update research
---

Recently, my boss bought 2 Dell Precision-Tower workstations. We have been using
those workstations ever since. But we want to have these 2 workstations
connected with each other, so we can double the computing power.

Basically, we followed the steps from [this][https://stackoverflow.com/questions/15903408/specify-the-machines-running-program-using-mpi] StackOverflow answer.

The first step is to create new users with the same usernames on both machines,
which is quite easy. Then we need to set up `ssh` connection using ssh keys,
which is simple too. The problem we encountered is that the slave machine cannot connect back
to master machine. It turned out that we should add hostname and corresponding
ip to `/etc/hosts`.

After that, just keep the `MPICH` version the same on both machine. And

{% highlight bash %}
mpirun -n 64 -host master,slave ./bin/xxx
{% endhighlight %}

Everything works now!

