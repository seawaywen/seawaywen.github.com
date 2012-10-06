---
layout: post
title: "Setup Postgres on Ubuntu"
date: 2012-08-05 15:46
comments: true
categories: [db, postgres, ubuntu]

---

#####1. Change the pg_hda.conf  

    /etc/postgresql/9.1/main/pg_hba.conf
	host all all 172.22.2.0/24 md5


#####2.Change the `/etc/postgresql/9.1/main/postgresql.conf`
    listen_addresses = '*'

#####3.Change the postgres user's password
    sudo su postgres -c psql template1
	ALTER USER postgres WITH PASSWORD ' <***password***> ';

#####4.sudo passwd postgres

#####5.Restart the db server
	sudo /etc/init.d/

#####6.Create the database
	su postgres
	createdb mydb


refer to:<https://help.ubuntu.com/11.04/serverguide/postgresql.html>

Done.
