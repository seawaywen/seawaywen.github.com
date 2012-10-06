---
layout: post
title: "how to use the SSH in the proxy env"
date: 2012-04-14 11:22
comments: true
categories: [tips, ssh]

---

Sometimes you are working in the coperation dev environemnt and you found you stay behind the firewall, some ports are blocked, such as 22, and you have to access internet via corperation proxy server, but you do need to use ssh to connect some site outside of office. This post will provide you a solution to use SSH in the proxy environment.

**This post imagin that you work with Mac env**


#####1. Install [corkscrew](http://www.agroman.net/corkscrew/):
	./configure -host=apple
	make
	make install
it will be installed in /usr/local/corkscrew by default.  

#####2. Config proxy information In *System preference*

#####3. 	Setup the SSH config info  
	echo 'ProxyCommand /usr/local/bin/corkscrew your.proxy.server 8080 %h %p' >> ~/.ssh/config

#####4. Test with  
	ssh xx@xxx.com

Done.