---
layout: post
title: "show hidden files in Finder"
date: 2011-02-16 12:27
comments: true
categories: [mac, tips]

---

### Enable showing hidden files in finder

    defaults write com.apple.finder AppleShowAllFiles -	bool true
	
	KillAll Finder
	
### disable showing hidden files in finder

    defaults write com.apple.finder AppleShowAllFiles -	bool false
	
	KillAll Finder
	