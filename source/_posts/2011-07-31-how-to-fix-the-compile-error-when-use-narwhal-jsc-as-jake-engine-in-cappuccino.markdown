---
layout: post
title: "How to fix the compile error when use narwhal-jsc as Jake Engine in Cappuccino"
date: 2011-07-31 11:09
comments: true
categories: [cappuccino, javascript]

---

When you use the narwhal-jsc as your jake Engine, compile with the following errors:  

    Making all in examples
	Make[3]: *** No rule to make target `../src/libedit.la', needed by `tc1'. Stop.
	make[2]: *** [all-recursive] Error 1
	make[1]: *** [all] Error 2
	make: *** [deps/libedit-20100424-3.0/src/.libs/libedit.dylib] Error 2
	
###Solution to fix:
```
1.tusk install narwhal-jsc
2.go to narwhal/packages/narwhal-jsc
3.go to deps/libedit20100424-3.0(may be different from this version number)
4.sudo autoreconf --force --install
5. ./configure
6. sudo make (with compile error, don't care about it)
7. go back to narwhal/packages/narwhal-jsc
8. make webkit (compile successfully)
9. ln -s narwhal/packages/narwhal-jsc/bin/narwhial-jsc narwhal/bin
10. export NARWHAL_ENGINE=jsc (add to ~/.profile)
11. source ~/.profile
12. open a new terminal and run jake (it works)
```
