---
title: "Distributed Search Engine"
collection: COURSE PROJECT FOR CIS 555 INTERNET & WEB SYSTEMS @PENN
type: "This is a class project for CIS 555 Internet & Web Systems (Spring 2021) at University of Pennsylvania."
permalink: /teaching/2024-spring
venue: "University Of Pennsylvania, CIS"
date: 2021-01-01
location: "Philadelphia, PA"
---

My team built a distributed search engine, with 4 components:
Crawler
======

 Crawler is built with StormLite, a lightweight version of Apache Storm, and runs on EC2. It crawls webpages given a seed URL, maintains the frontier using SQS queue, respects protocols provided by domain specific robots.txt and store content in S3 buckets. With three EC2 instances, the crawler can crawl 2-3 documents per second. For this project, we crawled 600k+ documents total.

Indexer
======
Indexer is built with a MapReduce job implemented in Apache Storm, and runs on EC2. It reads document contents stored in S3 by the crawler and create an inverted index to be used by the search engine. The indexer processes each document into terms, and stores the inverted index on a table in DynamoDB for fast retrieval. The inverted index table provides term frequency (TF) and document frequency (DF) information for document ranking. With two EC2 instances, the indexer can index crawl 2 documents per second. For this project, we indexed 200k documents total.

PageRank
======
PageRank is built with Apache Spark and run on EMR cluster. It ranks the importance of each web page (or “document”) by constructing graphs from incoming and outgoing links.


Search engine & UI
======
Search engine & UI is built with React.js for the front-end, Spark Java for the back-end. Given a query, the search engine retrieves documents all query terms appear in from the inverted index table, and rank them using TF-IDF and PageRank score to be displayed as the results page.

---

excerpt: "Short description of portfolio item number 1<br/><img src='/images/CIS555.png'>"

This is an item in your portfolio. It can be have images or nice text. If you name the file .md, it will be parsed as markdown. If you name the file .html, it will be parsed as HTML. 
