---
layout: post
title: "MySQLdb missing image error from PyCharm IDE when django sync"
date: 2011-07-25 11:48
comments: true
categories: [django, pycharm]

---

### Solution:
You can set the environment used by launchd (and, by extension, anything started from Spotlight) with launchctl setenv. 

For example to set the path:


    launchctl setenv PATH /opt/local/bin:/opt/local/sbin:/usr/bin:/bin:/usr/sbin:/sbin

Or if you want to set up your path in .bashrc or similar, then have it mirrored in launchd:

    PATH=/opt/local/bin:/opt/local/sbin:/usr/bin:/bin:/usr/sbin:/sbin

	launchctl setenv PATH $PATH

There's no need to reboot (though you will need to restart an app if you want it to pick up the changed environment.)


