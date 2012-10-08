---
layout: post
title: "Python env issue on Mac (Mountain Lion)"
date: 2012-09-16 20:51
comments: true
categories: [python, mac]

---

Today I have python issue after upgrading to the Moutain Lion. I want to create a new virtual python evironment with virtualenv, but I got this error:  

	Traceback (most recent call last): File "/Library/Python/2.7/site-packages/pip-1.2-py2.7.egg/pip/
	basecommand.py", line 106, in main status = self.run(options, args) File "/Library/Python/2.7/
	site-packages/pip-1.2-py2.7.egg/pip/commands/install.py", line 248, in run import setuptools
	ImportError: No module named setuptools
	
	
After google the issue, I got the solution, the root cause is that Apple remove the source code of Python in Mountain Lion, and some libs depend on the .py files.

Try this: 

```
curl -O http://python-distribute.org/distribute_setup.py 
/usr/bin/python2.7 distribute_setup.py	
sudo pip install pip --upgrade
```	
	
Done.	
