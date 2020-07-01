
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

## Description

A time series database (TSDB) is a database optimized for time-stamped or time series data. Time series data are simply measurements or events that are tracked, monitored, down sampled, and aggregated over time. This could be server metrics, application performance monitoring, network data, sensor data, events, clicks, trades in a market, and many other types of analytics data.

## Performance

A time series database is built specifically for handling metrics and events or measurements that are time stamped. A TSDB is optimized for measuring change over time. Properties that make time series data very different than other data workloads are data lifecycle management, summarization, and large range scans of many records.

## Advantages

- Scalability

- It balance the ACID/BASE relationship by offering principles that suit time series data.

- Usability

- Trade-offs: Database architecture is about trade-offs and priorities.

## Data features:

- Data is appended in sequence.

- Data can be multi-dimensional correlated.

- Hot data is typically accessed at high frequencies.

- Cold data needs to be reduced in dimension and archived.

- Data mainly covers values, states, and events.

## Databases

 - InfluxDB
   Kdb+
   Prometheus
   Graphite
   RRDTool
   TimescaleDB
   OpenTSDB
   Druid
   
   FaunaDB
   
   KairosDB
   
   DolphinDB
   
   GridDB
   
   eXtremeDB
   
   Amazon Timestream
   
   Alibaba Cloud TSDB

References:

[https://www.influxdata.com/time-series-database/](https://www.influxdata.com/time-series-database/)

[https://medium.com/datadriveninvestor/what-are-time-series-databases-a3e847608f91](https://medium.com/datadriveninvestor/what-are-time-series-databases-a3e847608f91)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY3OTk0MDQ4NCwtODE2NjMwNTE5LDM0Mz
M3Njc1OCwtNzUxODI5ODIwLC05MjAxMTYwMTQsNTI4MTEyNTQ4
LC0xMjY1MjY3ODQwLC02ODQ2NDg4OTAsMTYxNDI3NTczMiwxMD
A3NDM3OTgwLDIwNTIzMzcwNjcsMjA2Mzc5NjYzXX0=
-->