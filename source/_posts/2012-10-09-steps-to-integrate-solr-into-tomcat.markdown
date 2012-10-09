---
layout: post
title: "Steps to integrate Solr into Tomcat"
date: 2012-10-09 11:27
comments: true
categories: solr

---

Recently I am using the Solr as the full text search enginee in the project. The project is django based, an amazing framework [HayStack](http://haystacksearch.org/) was imported as the django search modular. It provides some useful APIs and Commonds that are quite handy.

For Solr, by default it can be ran `java -jar start.jar` in Solr dir, but in need of the project, we need to host the Solr by Tomcat.
I record some important steps here:

## The example Solr version is **3.6**

## Install Solr instance(s)
1. Extact the apache-solr-3.6.0.zip.

2. Copy the `apache-solr-3.6.0/example/solr` directory to the installation directory `/Users/Kelvin/Services/SolrSearchEngines/solr1`.  

3. Copy dist/apache-solr-*.war into `/Users/Kelvin/Services/SolrSearchEngines/solr` as solr.war.  

4. Open `/Users/Kelvin/Services/SolrSearchEngines/conf/solrconfig.xml`    
Specify the full path of dataDir for the index data:
```
<dataDir>${solr.data.dir:/Users/Kelvin/Services/SolrSearchEngines/solr1/data}</dataDir>
```
<!-- more -->

## Generate Solr schema file with Haystack module in Django

1. Install the hayStack in your Django application. 
2. run the command to generate the schema file:

```
python manage.py build_solr_schema > schema.xml
```

Replace the existed schema in the Solr's example

```
mv /Users/Kelvin/Services/SolrSearchEngines/solr1/conf/schema.xml /Users/Kelvin/Services/SolrSearchEngines/solr1/conf/schema.xml.origin    

cp schema.xml /Users/Kelvin/Services/SolrSearchEngines/solr1/conf

cd /Users/Kelvin/Services/SolrSearchEngines/solr1/conf

cp stopwords.txt stopwords_en.txt
```


## Create solr1.xml file 
Go in `tomcat-installer-dir/conf/Catalina/localhost` create a xml file call solr1.xml with the content:

```
<?xml version="1.0" encoding="utf-8"?>
<Context docbase="/Users/Kelvin/Services/solr.war" debug="0" crosscontext="true">
  <Environment name="solr/home" type="java.lang.String" value="/Users/Kelvin/Services/SolrSearchE\
ngines/solr1" override="true" />
</Context>
```


## Deploy the solr admin site
Put the *solr.war* to `tomcat-installer-dir/webapp`, once the tomcat startup, it will extract to a folder call `solr`, rename it to `solr1`


## Have multiple instances and have a try

Repeat the above steps with different installation directories to run multiple instances of Solr side-by-side.

If Tomcat is not already running, start it with service tomcat6 start or $CATALINA_HOME/bin/startup.sh run. 

The Solr admin should be available at http://localhost:8080/solr1.



