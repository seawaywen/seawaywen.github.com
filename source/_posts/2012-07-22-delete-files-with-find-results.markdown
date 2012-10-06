---
layout: post
title: "Delete files with find results"
date: 2012-07-22 12:48
comments: true
categories: [command, tips] 

---


When you tried to delete all files with the name abc.txt under the folder /home/kelvin, try the following commands(one of them works):

	find /home/kelvin -name abc.txt | xargs rm -rf
	find /home//kelvin -name abc.txt -exec rm -fv {} \;


Refer the doc: <http://www.linuxsir.org/main/?q=node/137>

Done.