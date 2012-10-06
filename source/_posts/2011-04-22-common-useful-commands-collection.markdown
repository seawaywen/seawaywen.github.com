---
layout: post
title: "Common useful commands collection"
date: 2011-04-22 14:49
comments: true
categories: [tips, linux]

---

* Copy remote single file to local  
```
scp username@host:/Users/xx/copyFile ./localDir
```
* Copy remote directory to local  
```
scp -R username@host:/Users/xx/copyFile ./localDir
```
* Delete all .svn folders recursively in current directory (Include the files in folders)  
```
find ./ -name ".svn" -type d -exec rm -rf {} \;
```
* Delete all dep file  
```
find . -name *.dep -type f -exec rm -f {} \;
```
* Restart apache in Mac  
```
sudo apachectl restart
```

