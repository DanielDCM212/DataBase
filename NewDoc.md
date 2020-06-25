
# Team:
 - [Jeorval Cano](https://github.com/JeorvalCM)
 - [Andres Hernandez](https://github.com/AndresHdez2000)
 - [Daniel Cuevas](https://github.com/DanielDCM212)

## COLUMN-ORIENTED DATABASE

### Description

Traditional relational databases are row-oriented, with each row having a row-id and each field within the row stored together in a table. 
Every time you look something up in a row-oriented database, every row is scanned, regardless of which columns you require. 


#### Performance

Columnar systems generally outperform relationship systems in almost all circumstances, but the range can vary widely. Queries that include calculations or individual access to records can be as slow or slower than a properly indexed relational system.

#### Structural limitations
Columnar databases use different techniques to imitate a relational structure. Some require the same main key in all tables, that is, the database hierarchy is limited to two levels. 



#### Benefits
> + High performance on aggregation queries (like COUNT, SUM, AVG, MIN, MAX)  
> + Highly efficient data compression and/or partitioning  
> + True scalability and fast data loading for Big Data  
> + Accessible by many 3rd party BI analytic tools  
> + Fairly simple systems administration

#### Advantages for certain types of systems
> + Data Warehouses and Business Intelligence  
> + Customer Relationship Management (CRM)  
> + Library Card Catalogs  
> + Ad hoc query systems

#### Disadvantages
> + Transactions are to be avoided or just not supported
> + Queries with table joins can reduce high performance 
> + Record updates and deletes reduce storage efficiency 
> + Effective partitioning/indexing schemes can be difficult to design



#### DB
> + [SAP Sybase IQ](https://www.sap.com/index.html)
> + [Infobright](http://www.ignitetech.com/solutions/information-technology/infobrightdb)
> + [Vertica (HP)](https://www.vertica.com/)
> + [ParAccel](https://www.actian.com/)
> + [Microsoft SQL Server](https://www.microsoft.com/)
> + [Apache Cassandra](https://cassandra.apache.org/)
> + [Vertica](https://www.vertica.com/)
> + [Apache HBase](https://hbase.apache.org/)
> + [ClickHouse](https://clickhouse.tech/)

|                	| [Apache Cassandra](https://cassandra.apache.org/)                                                                                                                                                                                                                                                            	| [Apache HBase](https://hbase.apache.org/)                                                                                                                                                                                                                                                                                                                                                                                                                                                       	| [ClickHouse](https://clickhouse.tech/)                                                                                                                                                                                                                                                                                                                      	|
|:--------------:	|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| Description    	| A column store designed to maximize scalability, availability, and performance.                                                                                                                                                                                                                              	| A distributed database that supports structured storage for large amounts of data and is designed to work with the Hadoop software library.                                                                                                                                                                                                                                                                                                                                                     	| A fault tolerant DBMS that supports real time generation of analytical data and SQL queries.                                                                                                                                                                                                                                                                	|
| FAULT TOLERANT 	| Data is automatically replicated to multiple nodes for fault-tolerance.<br>Replication across multiple data centers is supported. Failed nodes can be replaced with no downtime.                                                                                                                             	| Automatic and configurable sharding of tables                                                                                                                                                                                                                                                                                                                                                                                                                                                   	| ClickHouse supports multi-master asynchronous replication and can be deployed across multiple datacenters.<br>All nodes are equal, which allows avoiding having single points of failure.<br>Downtime of a single node or the whole datacenter won't affect the system's availability for both reads and writes.                                            	|
| PROVEN         	| + CERN<br>+ Comcast<br>+ eBay<br>+ GitHub<br>+ GoDaddy<br>+ Hulu<br>+ Instagram<br>+ Intuit<br>+ Netflix<br>+ Reddit                                                                                                                                                                                         	| + 23andMe<br>+ Adobe<br>+ Airbnb<br>+ Amadeus IT Group<br>+ Bloomberg<br>+ Facebook<br>+ Ráfaga                                                                                                                                                                                                                                                                                                                                                                                                 	| + Spotify<br>+ Geniee<br>+ ContentSquare<br>+ Cloudflare                                                                                                                                                                                                                                                                                                    	|
| Performance    	| Cassandra consistently outperforms popular NoSQL alternatives in benchmarks and real applications,<br>primarily because of fundamental architectural choices.                                                                                                                                                	| In any production environment, HBase is running with a cluster of more than 5000 nodes, only Hmaster acts as the master to all the slaves Region servers.<br>If Hmaster goes down, it can be only be recovered after a long time.<br>Even though the client is able to connect region server. Having another master is possible but only one will be active.<br>It will take a long time to activate the second Hmaster if the main Hmaster goes down. So, Hmaster is a performance bottleneck. 	| ClickHouse uses all available hardware to its full potential to process each query as fast as possible.<br>Peak processing performance for a single query stands at more than 2 terabytes per second (after decompression, only used columns).<br>In distributed setup reads are automatically balanced among healthy replicas to avoid increasing latency. 	|
| SCALABLE       	| Some of the largest production deployments include Apple's,<br>with over 75,000 nodes storing over 10 PB of data, Netflix (2,500 nodes, 420 TB, over 1 trillion requests per day),<br>Chinese search engine Easou (270 nodes, 300 TB, over 800 million requests per day), and eBay (over 100 nodes, 250 TB). 	| The hallmarks of HBase are extreme scalability , high reliability, and the schema flexibility you get from a column-oriented database.                                                                                                                                                                                                                                                                                                                                                          	| ClickHouse scales well both vertically and horizontally.<br>ClickHouse is easily adaptable to perform either on a cluster with hundreds or thousands of nodes or on a single server or even on a tiny virtual machine.<br>Currently, there are installations with more multiple trillion rows or hundreds of terabytes of data per single node.             	|
| Pricing | Open-source | Open-source | Open-source |
| Publisher | [Apache Software Foundation](https://www.apache.org/) | [Apache Software Foundation](https://www.apache.org/) | [ClickHouse](https://clickhouse.tech/) |
| Website | https://cassandra.apache.org/ | https://hbase.apache.org/ | https://clickhouse.tech/ |

## SEARCH DATABASE

### Description

The primary aim of the search is to retrieve the most relevant matches to the user’s queries, excluding other general content from the website.
The system should be able to narrow down the search by using ranges (price, dates, sizes, etc.), sorting (by popularity, date, price) and filtering (including only desirable parameters). When we talk about web apps where information changes dynamically (prices, description details, availability of goods), it is extremely important to have near real-time updates; for example, in eCommerce or booking engines to show goods and services available in stock, engines can provide recommendations when looking up for the most interesting products or information, to improve the user experience.

#### Performance

When the database grows, it becomes more difficult to look up. Search Database scales up while your DB gets bigger, so the search speed does not slow down, can be used not only as an indexer, but also as a data storage. Nevertheless, we would not recommend using it as your primary storage, and we still keep data in the main DB for better security and reliability, using Search Engines only to index data and store logs

#### Structural Limitations 

Multi get and multi term vectors API throw IndexNotFoundException when trying to access non existing indices that the user is not authorized for. By doing that they leak information regarding the fact that the index doesn’t exist, while the user is not authorized to know anything about those indices.

#### Benefits

 * full-text search (by simple words and phrases or multiple forms of a word or phrase)
 * Multifield search
 * Highlighting (visual indicator of the searched words)
 * Search by synonyms
 * Autocomplete suggestions
 * faceted search (opperations of counting)
 * fuzzy search(algorithms such as levestain algorithm, to detect typos or misspellings)
 * geospacial search(an object such as location according to its latitude an longitude)

#### Advantages

 1. Near real-time
 2. High scalability
 3. Not only indexer but used as a database
 4. Visualization of the Data
 5. Machine Learning for anomaly detection and outlier detection 
 6. Fast search 

#### Disadvantages

* The configuration of the system is not very intuitive
* Many updates in the database might affect the retrival of results
* It is needed to review the date converge, many problem matching for recen databases 

#### DB
* [ELASTIC SEARCH](https://www.elastic.co/)  
* [SOLR](https://lucene.apache.org/solr/)
* [SPLUNK](https://www.splunk.com/)  
* [SPHINX](http://sphinxsearch.com/)


### Matrix comparisson

|  |Elastic Search  |Solr| Splunk |
|Description|A distributed, RESTful modern search and analytics engine based on Apache Lucene|A widely used distributed, scalable search engine based on Apache Lucene|Analytics Platform for Big Data|
|Primary database model|Search engine|Search engine|Search engine|
|Secondary database models|Document store|--|--|
|Developer|Elastic|Apache Software Foundation|Splunk Inc.|
|Initial release|2010|2006|2003|
|Current release|7.7.0, May 2020|8.5.2, May 2020|--|
|License|Open Source|Open Source|Commercial|
|DBaaS offerings|Elasticsearch Service on Elastic Cloud: Try out the official hosted Elasticsearch and Kibana offering available on AWS, GCP and Azure that's powered by the creators of Elasticsearch.|--|--|
|Implementation language|Java|Java|--|
|Server operating systems|All OS with a Java VM|All OS with a Java VM|Linux, OS X, Solaris, Windows|
|Data scheme|schema-free info|Yes|Yes|
|XML support|No|Yes|Yes|
|SQL|SQL-like query language|Solr Parallel SQL Interface|No|
|APIs and other access methods|Java API, RESTful HTTP/JSON API|Java API, RESTful HTTP/JSON API|HTTP REST|
|Supported programming languages|.Net<br>Groovy<br>Community Contributed Clients<br>Java<br>JavaScript<br>Perl<br>PHP<br>Python<br>Ruby|.Net<br>Erlang<br>Java<br>JavaScript<br>any language that supports sockets and either XML or JSON<br>Perl<br>PHP<br>Python<br>Ruby<br>Scala|C#<br>Java<br>JavaScript<br>PHP<br>Python<br>Ruby|
|MapReduce|ES-Hadoop Connector|spark-solr|Yes|
|In-memory capabilities|Memcached and Redis integration|Yes|No|
|WebSite|[ELASTIC SEARCH](https://www.elastic.co/)|[SOLR](https://lucene.apache.org/solr/)|[SPLUNK](https://www.splunk.com/)|
### References
 
 
[greenice](https://greenice.net/elasticsearch-vs-solr-vs-sphinx-best-open-source-search-platform-comparison/)

[mcmaster](https://fhs.mcmaster.ca/neru/documents/limitationsofsearchdatabases.pdf)

[DB_compare](https://db-engines.com/en/system/Elasticsearch%3BSolr%3BSplunk)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgxNjYzMDUxOSwzNDMzNzY3NTgsLTc1MT
gyOTgyMCwtOTIwMTE2MDE0LDUyODExMjU0OCwtMTI2NTI2Nzg0
MCwtNjg0NjQ4ODkwLDE2MTQyNzU3MzIsMTAwNzQzNzk4MCwyMD
UyMzM3MDY3LDIwNjM3OTY2M119
-->
