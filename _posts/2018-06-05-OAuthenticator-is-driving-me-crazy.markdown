---
layout: post
title:  "OAuthenticator is driving me crazy!!"
date:   2018-06-04 23:09:01 +0800
categories: jupyter jupyterhub OAuthenticator
---

OK, about the data server, we want to add multi-user support for jupyter notebook, but we don't want to add system user for each one. So I find jupyterhub might be the solution. One particular good thing about jupyterhub is that it can use GitHub account for authentication. BUT, I can't get it done! After I log in to my GitHub account, it cannot be redirected back to our ip address. 404, dunno why... 
