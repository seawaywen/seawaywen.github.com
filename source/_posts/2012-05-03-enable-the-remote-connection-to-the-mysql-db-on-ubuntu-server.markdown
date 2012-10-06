---
layout: post
title: "Enable the remote connection to the MySQL DB on Ubuntu Server"
date: 2012-05-03 17:51
comments: true
categories: [db, mysql, ubuntu]

---


1. Create a MySQL user  
`mysql> GRANT ALL PRIVILEGES ON remote.* TO remote@"%" IDENTIFIED BY "remotepwd";`

2. Change the /etc/mysql/my.cnf  
`disable the bind-address = 127.0.0.1`

3. Restart the DB  
`sudo /etc/init.d/mysql restart`


Done.