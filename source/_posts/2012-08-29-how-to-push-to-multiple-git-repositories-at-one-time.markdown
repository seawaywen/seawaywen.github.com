---
layout: post
title: "How to push to multiple git repositories at one time"
date: 2012-08-29 14:10
comments: true
categories: [git]

---

I have 2 different repositories now on the different server, now I want one of them to be the backup. Two solutions are in my mind.

1. Sync the repository periodically
2. Each time when push the changes, both of the repositoy should be pushed

Here you can follow this handy trick to keep your updates on each your GIT server with one push:

**In .git/config file:** 

	[remote "all"]
	url = kelvin@git.xxx.com:sample.git
	url = kelvin@git.yyy.com::sample.git

	[remote "origin"]
	fetch = +refs/heads/*:refs/remotes/origin/*
	url = kelvin@git.xxx.com:sample.git

	[remote "github"]
	fetch = +refs/heads/*:refs/remotes/github/*
	url = kelvin@git.yyy.com::sample.git


Done.


