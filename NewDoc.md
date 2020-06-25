
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
> 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkyMDExNjAxNCw1MjgxMTI1NDgsLTEyNj
UyNjc4NDAsLTY4NDY0ODg5MCwxNjE0Mjc1NzMyLDEwMDc0Mzc5
ODAsMjA1MjMzNzA2NywyMDYzNzk2NjNdfQ==
-->