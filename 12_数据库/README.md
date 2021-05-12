# 数据库

对于数据库方向，重点就是两种数据库，一种是以 SQL 为代表的关系型数据库，另一种是以非 SQL 为代表的 NoSQL 数据库。关系型数据库主要有三个：Oracle、MySQL 和 Postgres。

在这里，我们只讨论越来越主流的 MySQL 数据库。首先，我们要了解数据库的一些实现原理和内存的一些细节，然后我们要知道数据的高可用和数据复制这些比较重要的话题，了解一下关系型数据库的一些实践和难点。然后，我们会进入到 NoSQL 数据库的学习。

NoSQL 数据库千奇百怪，其主要是解决了关系型数据库中的各种问题。第一个大问题就是数据的 Schema 非常多，用关系型数据库来表示不同的 Data Schema 是非常笨拙的，所以要有不同的数据库（如时序型、键值对型、搜索型、文档型、图结构型等）。另一个大问题是，关系型数据库的 ACID 是一件很讨厌的事，这极大地影响了数据库的性能和扩展性，所以 NoSQL 在这上面做了相应的妥协以解决大规模伸缩的问题。

对于一个程序员，你可能觉得数据库的事都是 DBA 的事，然而我想告诉你你错了，这些事才真正是程序员的事。因为程序是需要和数据打交道的，所以程序员或架构师不仅需要设计数据模型，还要保证整体系统的稳定性和可用性，数据是整个系统中关键中的关键。所以，作为一个架构师或程序员，你必须了解最重要的数据存储——数据库。

## 关系型数据库

今天，关系型数据库最主要的两个代表是闭源的 Oracle 和开源的 MySQL。当然，还有很多了，比如微软的 SQL Server，IBM 的 DB2 等，还有开源的 PostgreSQL。关系型数据库的世界中有好多好多产品。当然，还是 Oracle 和 MySQL 是比较主流的。所以，这里主要介绍更为开放和主流的 MySQL。

如果你要玩 Oracle，我这里只推荐一本书《[Oracle Database 9i/10g/11g 编程艺术](https://book.douban.com/subject/5402711/)》，无论是开发人员还是 DBA，它都是必读的书。这本书的作者是 Oracle 公司的技术副总裁托马斯·凯特（Thomas Kyte），他也是世界顶级的 Oracle 专家。

这本书中深入分析了 Oracle 数据库体系结构，包括文件、内存结构以及构成 Oracle 数据库和实例的底层进程，利用具体示例讨论了一些重要的数据库主题，如锁定、并发控制、事务等。同时分析了数据库中的物理结构，如表、索引和数据类型，并介绍采用哪些技术能最优地使用这些物理结构。

* 学习 MySQL，首先一定是要看[MySQL 官方手册](https://dev.mysql.com/doc/)。

* 然后，官方还有几个 PPT 也要学习一下。

  * [How to Analyze and Tune MySQL Queries for Better Performance](https://www.mysql.com/cn/why-mysql/presentations/tune-mysql-queries-performance/)
  * [MySQL Performance Tuning 101](https://www.mysql.com/cn/why-mysql/presentations/mysql-performance-tuning101/)

  * [MySQL Performance Schema & Sys Schema](https://www.mysql.com/cn/why-mysql/presentations/mysql-performance-sys-schema/)
  * [MySQL Performance: Demystified Tuning & Best Practices](https://www.mysql.com/cn/why-mysql/presentations/mysql-performance-tuning-best-practices/)
  * [MySQL Security Best Practices](https://www.mysql.com/cn/why-mysql/presentations/mysql-security-best-practices/)
  * [MySQL Cluster Deployment Best Practices](https://www.mysql.com/cn/why-mysql/presentations/mysql-cluster-deployment-best-practices/)
  * [MySQL High Availability with InnoDB Cluster](https://www.mysql.com/cn/why-mysql/presentations/mysql-high-availability-innodb-cluster/)

* 然后推荐《[高性能 MySQL](https://book.douban.com/subject/23008813/)》，这本书是 MySQL 领域的经典之作，拥有广泛的影响力。不但适合数据库管理员（DBA）阅读，也适合开发人员参考学习。不管是数据库新手还是专家，都能从本书中有所收获。

* 如果你对 MySQL 的内部原理有兴趣的话，可以看一下这本书《[MySQL 技术内幕：InnoDB 存储引擎](https://book.douban.com/subject/24708143/)》。当然，还有官网的[MySQL Internals Manual](https://dev.mysql.com/doc/internals/en/) 。

* 数据库的索引设计和优化也是非常关键的，这里还有一本书《[数据库的索引设计与优化](https://book.douban.com/subject/26419771/)》也是很不错的。虽然不是讲 MySQL 的，但是原理都是相通的。这也是上面推荐过的《高性能 MySQL》在其索引部分推荐的一本好书。你千万不要觉得只有做数据库你才需要学习这种索引技术。不是的！在系统架构上，在分布式架构中，索引技术也是非常重要的。这本书对于索引性能进行了非常清楚的估算，不像其它书中只是模糊的描述，你一定会收获很多。

下面还有一些不错的和 MySQL 相关的文章。

* [MySQL 索引背后的数据结构及算法原理](http://blog.codinglabs.org/articles/theory-of-mysql-index.html)
* [Some study on database storage internals](https://kousiknath.medium.com/data-structures-database-storage-internals-1f5ed3619d43)
* [Sharding Pinterest: How we scaled our MySQL fleet](https://medium.com/pinterest-engineering/sharding-pinterest-how-we-scaled-our-mysql-fleet-3f341e96ca6f)
* [Guide to MySQL High Availability](https://www.mysql.com/cn/why-mysql/white-papers/mysql-guide-to-high-availability-solutions/)
* [Choosing MySQL High Availability Solutions](https://dzone.com/articles/choosing-mysql-high-availability-solutions)
* [High availability with MariaDB TX: The definitive guide](https://mariadb.com/wp-content/uploads/2019/04/mariadb-platform-high-availability-guide_whitepaper_1001.pdf)

最后，还有一个 MySQL 的资源列表 [Awesome MySQL](https://shlomi-noach.github.io/awesome-mysql/)，这个列表中有很多的工具和开发资源，可以帮助你做很多事。

MySQL 有两个比较有名的分支，一个是 Percona，另一个是 MariaDB，其官网上的 Resources 页面中有很多不错的资源和文档，可以经常看看。 [Percona Resources](https://www.percona.com/resources)、[MariaDB Resources](https://mariadb.com/resources/) ，以及它们的开发博客中也有很多不错的文章，分别为 [Percona Blog](https://www.percona.com/blog/) 和 [MariaDB Blog](https://mariadb.com/resources/blog/)。

然后是关于 MySQL 的一些相关经验型的文章。

* [Booking.com: Evolution of MySQL System Design](https://www.percona.com/live/mysql-conference-2015) ，Booking.com 的 MySQL 数据库使用的演化，其中有很多不错的经验分享，我相信也是很多公司会遇到的的问题。

* [Tracking the Money - Scaling Financial Reporting at Airbnb](https://medium.com/airbnb-engineering/tracking-the-money-scaling-financial-reporting-at-airbnb-6d742b80f040) ，Airbnb 的数据库扩展的经验分享。

* [Why Uber Engineering Switched from Postgres to MySQL](https://eng.uber.com/postgres-to-mysql-migration/) ，无意比较两个数据库谁好谁不好，推荐这篇 Uber 的长文，主要是想让你从中学习到一些经验和技术细节，这是一篇很不错的文章。

关于 MySQL 的集群复制，下面有这些文章供你学习一下，都是很不错的实践性比较强的文章。

* [Monitoring Delayed Replication, With A Focus On MySQL](https://engineering.imvu.com/2013/01/09/monitoring-delayed-replication-with-a-focus-on-mysql/)
* [Mitigating replication lag and reducing read load with freno](https://github.blog/2017-10-13-mitigating-replication-lag-and-reducing-read-load-with-freno/)

另外，Booking.com 给了一系列的文章，你可以看看：

* [Better Parallel Replication for MySQL](https://medium.com/booking-com-infrastructure/better-parallel-replication-for-mysql-14e2d7857813)

* [Evaluating MySQL Parallel Replication Part 2: Slave Group Commit](https://medium.com/booking-com-infrastructure/evaluating-mysql-parallel-replication-part-2-slave-group-commit-459026a141d2)

* [Evaluating MySQL Parallel Replication Part 3: Benchmarks in Production](https://medium.com/booking-com-infrastructure/evaluating-mysql-parallel-replication-part-3-benchmarks-in-production-db5811058d74)

* [Evaluating MySQL Parallel Replication Part 4: More Benchmarks in Production](https://medium.com/booking-com-infrastructure/evaluating-mysql-parallel-replication-part-4-more-benchmarks-in-production-49ee255043ab) 

* [Evaluating MySQL Parallel Replication Part 4, Annex: Under the Hood](https://medium.com/booking-com-infrastructure/evaluating-mysql-parallel-replication-part-4-annex-under-the-hood-eb456cf8b2fb)

对于 MySQL 的数据分区来说，还有下面几篇文章你可以看看。

* [StackOverflow: MySQL sharding approaches?](https://stackoverflow.com/questions/5541421/mysql-sharding-approaches)

* [Why you don’t want to shard](https://www.percona.com/blog/2009/08/06/why-you-dont-want-to-shard/)

* [How to Scale Big Data Applications](https://www.percona.com/sites/default/files/presentations/How%20to%20Scale%20Big%20Data%20Applications.pdf)

* [MySQL Sharding with ProxySQL](https://www.percona.com/blog/2016/08/30/mysql-sharding-with-proxysql/)

然后，再看看各个公司做 MySQL Sharding 的一些经验分享。

* [MailChimp: Using Shards to Accommodate Millions of Users](https://mailchimp.com/developer/) 

* [Uber: Code Migration in Production: Rewriting the Sharding Layer of Uber’s Schemaless Datastore](https://eng.uber.com/schemaless-rewrite/)

* [Sharding & IDs at Instagram](https://instagram-engineering.com/sharding-ids-at-instagram-1cf5a71e5a5c)

* [Airbnb: How We Partitioned Airbnb’s Main Database in Two Weeks](https://medium.com/airbnb-engineering/how-we-partitioned-airbnb-s-main-database-in-two-weeks-55f7e006ff21)

## NoSQL 数据库

关于 NoSQL 数据库，其最初目的就是解决大数据的问题。然而，也有人把其直接用来替换掉关系型数据库。所以在学习这个技术之前，我们需要对这个技术的一些概念和初衷有一定的了解。下面是一些推荐资料。

* Martin Fowler 在 YouTube 上分享的 NoSQL 介绍 [Introduction To NoSQL](https://www.youtube.com/watch?v=qI_g07C_Q5I)， 以及他参与编写的 [NoSQL Distilled - NoSQL 精粹](https://book.douban.com/subject/25662138/)，这本书才 100 多页，是本难得的关于 NoSQL 的书，很不错，非常易读。

* [NoSQL Databases: a Survey and Decision Guidance](https://medium.baqend.com/nosql-databases-a-survey-and-decision-guidance-ea7823a822d#.nhzop4d23)，这篇文章可以带你自上而下地从 CAP 原理到开始了解 NoSQL 的种种技术，是一篇非常不错的文章。

* [Distribution, Data, Deployment: Software Architecture Convergence in Big Data Systems](https://resources.sei.cmu.edu/asset_files/WhitePaper/2014_019_001_90915.pdf)，这是卡内基·梅隆大学的一篇讲分布式大数据系统的论文。其中主要讨论了在大数据时代下的软件工程中的一些关键点，也说到了 NoSQL 数据库。

* [No Relation: The Mixed Blessings of Non-Relational Databases](http://ianvarley.com/UT/MR/Varley_MastersReport_Full_2009-08-07.pdf)，这篇论文虽然有点年代久远。但这篇论文是 HBase 的基础，你花上一点时间来读读，就可以了解到，对各种非关系型数据存储优缺点的一个很好的比较。

* [NoSQL Data Modeling Techniques](https://highlyscalable.wordpress.com/2012/03/01/nosql-data-modeling-techniques/) ，NoSQL 建模技术。这篇文章我曾经翻译在了 CoolShell 上，标题为 [NoSQL 数据建模技术](https://coolshell.cn/articles/7270.htm)，供你参考。
  * [MongoDB - Data Modeling Introduction](https://docs.mongodb.com/manual/core/data-modeling-introduction/) ，虽然这是 MongoDB 的数据建模介绍，但是其很多观点可以用于其它的 NoSQL 数据库。
  * [Firebase - Structure Your Database](https://firebase.google.com/docs/database/android/structure-data) ，Google 的 Firebase 数据库使用 JSON 建模的一些最佳实践。

* 因为 CAP 原理，所以当你需要选择一个 NoSQL 数据库的时候，你应该看看这篇文档 [Visual Guide to NoSQL Systems](https://blog.nahurst.com/visual-guide-to-nosql-systems)。

选 SQL 还是 NoSQL，这里有两篇文章，值得你看看。

* [SQL vs. NoSQL Databases: What’s the Difference?](https://www.upwork.com/resources/sql-vs-nosql-databases-whats-the-difference)

* [Salesforce: SQL or NoSQL](https://engineering.salesforce.com/sql-or-nosql-9eaf1d92545b) 

## 各种 NoSQL 数据库

学习使用 NoSQL 数据库其实并不是一件很难的事，只要你把官方的文档仔细地读一下，是很容易上手的，而且大多数 NoSQL 数据库都是开源的，所以，也可以通过代码自己解决问题。下面我主要给出一些典型的 NoSQL 数据库的一些经验型的文章，供你参考。

### 列数据库 Column Database

* Cassandra 相关
  * 沃尔玛实验室有两篇文章值得一读。
    * [Avoid Pitfalls in Scaling Cassandra Cluster at Walmart](https://medium.com/walmartglobaltech/avoid-pitfalls-in-scaling-your-cassandra-cluster-lessons-and-remedies-a71ca01f8c04)
    * [Storing Images in Cassandra at Walmart](https://medium.com/walmartglobaltech/building-object-store-storing-images-in-cassandra-walmart-scale-a6b9c02af593)
  * [Yelp: How We Scaled Our Ad Analytics with Apache Cassandra](https://engineeringblog.yelp.com/2016/08/how-we-scaled-our-ad-analytics-with-cassandra.html) ，Yelp 的这篇博客也有一些相关的经验和教训。
  * [Discord: How Discord Stores Billions of Messages](https://blog.discord.com/how-discord-stores-billions-of-messages-7fa6ec7ee4c7) ，Discord 公司分享的一个如何存储十亿级消息的技术文章。
  * [Cassandra at Instagram](https://www.slideshare.net/DataStax/cassandra-at-instagram-2016) ，Instagram 的一个 PPT，其中介绍了 Instagram 中是怎么使用 Cassandra 的。
  * [Netflix: Benchmarking Cassandra Scalability on AWS - Over a million writes per second](https://netflixtechblog.com/benchmarking-cassandra-scalability-on-aws-over-a-million-writes-per-second-39f45f066c9e) ，Netflix 公司在 AWS 上给 Cassandra 做的一个 Benchmark。

* HBase 相关
  * [Imgur Notification: From MySQL to HBASE](https://medium.com/imgur-engineering/imgur-notifications-from-mysql-to-hbase-9dba6fc44183)
  * [Pinterest: Improving HBase Backup Efficiency](https://medium.com/pinterest-engineering/improving-hbase-backup-efficiency-at-pinterest-86159da4b954)
  * [IBM : Tuning HBase performance](https://www.ibm.com/docs/en/error?originalUrl=SSPT3X_2.1.2/com.ibm.swg.im.infosphere.biginsights.analyze.doc/doc/bigsql_TuneHbase.html)
  * [HBase File Locality in HDFS](http://www.larsgeorge.com/2010/05/hbase-file-locality-in-hdfs.html)
  * [Apache Hadoop Goes Realtime at Facebook](http://borthakur.com/ftp/RealtimeHadoopSigmod2011.pdf)
  * [Storage Infrastructure Behind Facebook Messages: Using HBase at Scale](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.294.8459&rep=rep1&type=pdf)
  * [GitHub: Awesome HBase](https://github.com/rayokota/awesome-hbase)

针对于 HBase 有两本书你可以考虑一下。

* 首先，先推荐两本书，一本是偏实践的《[HBase 实战](https://book.douban.com/subject/25706541/)》，另一本是偏大而全的手册型的《[HBase 权威指南](https://book.douban.com/subject/10748460/)》。
* 当然，你也可以看看官方的 [The Apache HBase™ Reference Guide](http://hbase.apache.org/book.html#book)
* 另外两个列数据库：
  * [ClickHouse](https://clickhouse.tech/) - Open Source Distributed Column Database at Yandex
  * [Scaling Redshift without Scaling Costs at GIPHY](https://engineering.giphy.com/scaling-redshift-without-scaling-costs/)

### 文档数据库 Document Database - MongoDB, SimpleDB, CouchDB

* [Data Points - What the Heck Are Document Databases?](https://docs.microsoft.com/en-us/archive/msdn-magazine/2011/november/data-points-what-the-heck-are-document-databases)
* [eBay: Building Mission-Critical Multi-Data Center Applications with MongoDB](https://www.mongodb.com/blog/post/ebay-building-mission-critical-multi-data-center-applications-with-mongodb)
* [The AWS and MongoDB Infrastructure of Parse: Lessons Learned](https://medium.baqend.com/parse-is-gone-a-few-secrets-about-their-infrastructure-91b3ab2fcf71)
* [Migrating Mountains of Mongo Data](https://medium.com/build-addepar/migrating-mountains-of-mongo-data-63e530539952)
* [Couchbase Ecosystem at LinkedIn](https://engineering.linkedin.com/blog/2017/12/couchbase-ecosystem-at-linkedin)
* [SimpleDB at Zendesk](https://medium.com/zendesk-engineering/resurrecting-amazon-simpledb-9404034ec506)
* [Github: Awesome MongoDB](https://github.com/ramnes/awesome-mongodb)

### 数据结构数据库 Data structure Database - Redis

* [Learn Redis the hard way (in production) at Trivago](https://tech.trivago.com/2017/01/25/learn-redis-the-hard-way-in-production/)
* [Twitter: How Twitter Uses Redis To Scale - 105TB RAM, 39MM QPS, 10,000+ Instances](http://highscalability.com/blog/2014/9/8/how-twitter-uses-redis-to-scale-105tb-ram-39mm-qps-10000-ins.html) 
* [Slack: Scaling Slack’s Job Queue - Robustly Handling Billions of Tasks in Milliseconds Using Kafka and Redis](https://slack.engineering/scaling-slacks-job-queue/)
* [GitHub: Moving persistent data out of Redis at GitHub](https://github.blog/2017-01-10-moving-persistent-data-out-of-redis/)
* [Instagram: Storing Hundreds of Millions of Simple Key-Value Pairs in Redis](https://instagram-engineering.com/storing-hundreds-of-millions-of-simple-key-value-pairs-in-redis-1091ae80f74c)
* [Redis in Chat Architecture of Twitch (from 27:22)](https://www.infoq.com/presentations/twitch-pokemon/)
* [Deliveroo: Optimizing Session Key Storage in Redis](https://deliveroo.engineering/2016/10/07/optimising-session-key-storage.html)
* [Deliveroo: Optimizing Redis Storage](https://deliveroo.engineering/2017/01/19/optimising-membership-queries.html)
* [GitHub: Awesome Redis](https://github.com/JamzyWang/awesome-redis)

### 时序数据库 Time-Series Database

* [What is Time-Series Data & Why We Need a Time-Series Database](https://blog.timescale.com/blog/what-the-heck-is-time-series-data-and-why-do-i-need-a-time-series-database-dcf3b1b18563/)
* [Time Series Data: Why and How to Use a Relational Database instead of NoSQL](https://blog.timescale.com/blog/time-series-data-why-and-how-to-use-a-relational-database-instead-of-nosql-d0cd6975e87c/)
* [Beringei: High-performance Time Series Storage Engine @Facebook](https://engineering.fb.com/2017/02/03/core-data/beringei-a-high-performance-time-series-storage-engine/)
* [Introducing Atlas: Netflix’s Primary Telemetry Platform @Netflix](https://netflixtechblog.com/introducing-atlas-netflixs-primary-telemetry-platform-bd31f4d8ed9a)
* [Building a Scalable Time Series Database on PostgreSQL](https://blog.timescale.com/blog/when-boring-is-awesome-building-a-scalable-time-series-database-on-postgresql-2900ea453ee2/)
* [Scaling Time Series Data Storage - Part I @Netflix](https://netflixtechblog.com/scaling-time-series-data-storage-part-i-ec2b6d44ba39)
* [Design of a Cost Efficient Time Series Store for Big Data](https://leventov.medium.com/design-of-a-cost-efficient-time-series-store-for-big-data-88c5dc41af8e)
* [GitHub: Awesome Time-Series Database](https://github.com/xephonhq/awesome-time-series-database)

### 图数据库 - Graph Platform

* 首先是 IBM Devloperworks 上的两个简介性的 PPT。
  * [Intro to graph databases, Part 1, Graph databases and the CRUD operations](https://www.ibm.com/developerworks/library/cl-graph-database-1/cl-graph-database-1-pdf.pdf)
  * [Intro to graph databases, Part 2, Building a recommendation engine with a graph database](https://www.ibm.com/developerworks/library/cl-graph-database-2/cl-graph-database-2-pdf.pdf)

* 然后是一本免费的电子书《[Graph Database](https://graphdatabases.com/)》。

* 接下来是一些图数据库的介绍文章。
  * [Handling Billions of Edges in a Graph Database](https://www.infoq.com/presentations/graph-database-scalability/)
  * [Neo4j case studies with Walmart, eBay, AirBnB, NASA, etc](https://neo4j.com/customers/)
  * [FlockDB: Distributed Graph Database for Storing Adjacency Lists at Twitter](https://blog.twitter.com/engineering/en_us/a/2010/introducing-flockdb.html)
  * [JanusGraph: Scalable Graph Database backed by Google, IBM and Hortonworks](https://architecht.io/google-ibm-back-new-open-source-graph-database-project-janusgraph-1d74fb78db6b)
  * [Amazon Neptune](https://aws.amazon.com/cn/neptune/)

### 搜索数据库 - ElasticSearch

* [Elasticsearch: The Definitive Guide](https://www.elastic.co/guide/en/elasticsearch/guide/master/index.html) 这是官网方的 ElasticSearch 的学习资料，基本上来说，看这个就够了。

* 接下来是 4 篇和性能调优相关的工程实践。
  * [Elasticsearch Performance Tuning Practice at eBay](https://tech.ebayinc.com/engineering/elasticsearch-performance-tuning-practice-at-ebay/)
  * [Elasticsearch at Kickstarter](https://kickstarter.engineering/elasticsearch-at-kickstarter-db3c487887fc)
  * [9 tips on ElasticSearch configuration for high performance](https://www.loggly.com/blog/nine-tips-configuring-elasticsearch-for-high-performance/)
  * [Elasticsearch In Production - Deployment Best Practices](https://medium.com/@abhidrona/elasticsearch-deployment-best-practices-d6c1323b25d7)

* 最后是 GitHub 上的资源列表 [GitHub: Awesome ElasticSearch](https://github.com/dzharii/awesome-elasticsearch) 。

## 小结

好了，总结一下今天分享的内容。虽然有人会认为数据库与程序员无关，是 DBA 的事儿。但我坚信，数据库才真正是程序员的事儿。因为程序是需要和数据打交道的，所以程序员或架构师不仅需要设计数据模型，还要保证整体系统的稳定性和可用性，数据是整个系统中关键中的关键。

对于数据库方向，重点就是两种数据库，一种是以 SQL 为代表的关系型数据库，另一种是以非 SQL 为代表的 NoSQL 数据库。因而，在这篇文章中，我给出了 MySQL 和各种开源 NoSQL 的一些相关的有价值的文章和导读，主要是让你对这些数据库的内在有一定的了解，但又不会太深。同时给出了一些知名企业使用数据库的工程实践，这对于了解各种数据库的优劣非常有帮助，值得认真读读。

从下篇文章开始，我们将进入分布式系统架构方面的内容，里面不仅涵盖了大量的理论知识，更有丰富的入门指导和大量的工程实践。敬请期待。