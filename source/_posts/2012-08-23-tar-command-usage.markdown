---
layout: post
title: "Tar command usage"
date: 2012-08-23 22:02
comments: true
categories: [tips, linux, command]

---

Create the tar file  

	tar -czvp -f archive.tar.gz foo bar # Create archive.tar.gz from files foo and bar with the preserved permission,
	tar -cjvp -f archive.tar.bz2 foo bar 


How to split the file:

	split -b 4000k archive.tar.gz archive.20120829.tar.gz. -verbose

	creating file 'archive.20120829.tar.gz.aa'
	creating file 'archive.20120829.tar.gz.ab'
	creating file 'archive.20120829.tar.gz.ac'
	...

We can merge above 2 commands as one with the pipe | as following:

	tar -czvp -f -- archive.tar.gz foo bar |split -b 4000k -- archive.tar.gz archive.20120829.tar.gz. -verbose

	tar -tvf archive.tar # List all files in archive.tar verbosely.

How to exact the split tar files?

	cat archive.20120829.tar.gz.a* > archive.20120829.tar.gz
	
	cat archive.20120829.tar.gz.a* |tar -zxv


**Strange ISSUE**:

Under Mac OS, when you `tar cfv xx.tar xx`, you have some strange extra files start with ._xxx generated.
