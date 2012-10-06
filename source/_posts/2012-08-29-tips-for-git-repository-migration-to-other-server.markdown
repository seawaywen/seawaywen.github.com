---
layout: post
title: "Tips for git repository migration to other server"
date: 2012-08-29 14:40
comments: true
categories: [git, tips]

---

Recently I am going to use the private git repository that hosting on the [webfaction](http://www.webfaction.com) from my own server. During the migration I met some issues, here are some tips should be noticed.


When create the new repository, don't forget:  
    git config http.receivepack true


If you are using the SSL on the GIT server without certificate signed by CA, you **SHOULD** do these in your local box:
	export GIT_SSL_NO_VERIFY=true
	git clone https://demo@your_git_site_url/project.git


Then, disable SSL certificate verification for the repository to enable push and pull operations:
	switch to the repository directory
	git config http.sslVerify false

And of course when you get error:   

`SSL certificate problem, verify that the CA cert is OK.` `Details: error:14090086:SSL`   	
`routines:SSL3_GET_SERVER_CERTIFICATE:certificate verify failed while accessing`
	
You can config gloablly:
	git config --global http.sslVerify false

<!-- more -->

When you clone the repository from the server, and you got the following error message:  

`./objects/pack/._pack-de7d2e641423ddac38ff369dae6afad9f02d4397.idx is too small`    

`error: index file /home/joe/site/.git/objects/pack/._pack-de7d2e641423ddac38ff369dae6afad9f02d4397.idx is too small`  


What you should do is run the following commands in your local repository:  
	git config repack.usedeltabaseoffset false
	git repack -a -d


If you have Error:   

`RPC failed; result=22, HTTP code = 411`  

do as following:
	git config http.postBuffer 524288000 #Permit pushes up to 500 megabytes

