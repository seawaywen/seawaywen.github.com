---
layout: post
title: "How to setup a HTTPS site"
date: 2012-09-03 18:29
comments: true
categories: [host, site] 

---

Recently I am going to use SSL on my site. Some important steps were record here for your information.


#### Generate CSR (Certificate Signing Request)

	openssl genrsa -out domain.key 2048
	openssl req -new -key domain.key -out domain.csr

**To be continue**...