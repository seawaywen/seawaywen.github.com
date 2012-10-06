---
layout: post
title: "Install PIL on Ubuntu"
date: 2012-08-16 22:59
comments: true
categories: [python, ubuntu]

---

Install the build dependencies:  
	sudo apt-get build-dep python-imaging

Symlink the libraries:  
	sudo ln -s /usr/lib/`uname -i`-linux-gnu/libfreetype.so /usr/lib/
	sudo ln -s /usr/lib/`uname -i`-linux-gnu/libjpeg.so /usr/lib/
	sudo ln -s /usr/lib/`uname -i`-linux-gnu/libz.so /usr/lib/

Install:
	pip install PIL
	
	
Done.