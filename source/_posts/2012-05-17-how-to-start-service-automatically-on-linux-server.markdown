---
layout: post
title: "Start service automatically on linux server"
date: 2012-05-17 14:52
comments: true
categories: [linux, tips]

---

###Add the service as automatically startup
1. copy the startup script to `/etc/init.d`
2. `sudo chmod 755 /etc/init.d/your_script`
3. run the following commonds  
```
cd /etc/init.d
sudo upate-rc.d your_script defaults xx(xx is the start sequence number)
```


###Remove the startup service
```
cd /etc/init.d
sudo update-rc.d -f your_script remove
```

