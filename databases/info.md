Databases
=========

1.PostgreSQL
- Postgres internals http://www.interdb.jp/pg/pgsql02.html

Ibrar Ahmed
Parallelism in PostgreSQL
https://www.percona.com/blog/2019/07/30/parallelism-in-postgresql/

PostgreSQL Time-Series Data Case: Automatic Compression over Time
https://www.alibabacloud.com/blog/postgresql-time-series-data-case-automatic-compression-over-time_594813

1.2.Compression in postgresql
- postgres on ZFS 
  https://www.citusdata.com/blog/2013/04/30/zfs-compression/
  https://www.2ndquadrant.com/en/blog/pg-phriday-postgres-zfs/
  https://medium.com/@lk.snatch/postgresql-compression-854a4647ee43 (Auto-compression TOAST-able data, Postgres Pro compression / encryption, 
  Cstore_fdw columnar store extension, ZSON extension for jsonb format, Compression file systems (like ZFS or Btrfs), TimeScaleDB for time-series data)  
  
Aleksander Alekseev, Anastasia Lubennikova
In-core compression:how to shrink your databasesize in several times  
https://afiskon.github.io/static/2017/postgresql-in-core-compression-pgconf2017.pdf

- field compression
http://blog.cleverelephant.ca/2019/11/pgsql-gzip.html
https://github.com/postgrespro/zson

Aya Iwata, Fujitsu Limited
Data compression in PostgreSQL and its future
https://www.postgresql.eu/events/pgconfeu2019/sessions/session/2671/slides/263/Data_Compression_in_PostgreSQL_and_its_future_noscript.pdf

1.3.Postgres-based DB
- Postgres­XC
- GridSQL https://wiki.postgresql.org/wiki/GridSQL 
- Stado https://wiki.postgresql.org/wiki/Stado 

2.Greenplum
- MPP, postgres-based, newer version based on postgres 9.4
- https://habr.com/ru/company/tinkoff/blog/267733/

3."Эволюция структур данных в Яндекс.метрике", clickhouse
- https://habr.com/company/yandex/blog/273305/
- Clickhouse benchmarks with popular DBs https://clickhouse.tech/benchmark.html

4.Hadoop based
- HBase (column store, key-value)
- Cloudera Impala (MPP, C++, metadata in Hive Metastore)
- Hive (MapReduce)
- Apache Phoenix (компилирует SQL-запросы в собственные запросы API HBase)
- Apache Accumulo (sorted, distributed key/value store, Apache HDFS to store its data, Apache ZooKeeper for consensus)

- Apache Kudu (column store, C++)

Todd Lipcon, David Alves, Dan Burkert, Jean-Daniel Cryans, Adar Dembo, Mike Percy, Silvius Rus, Dave Wang, Matteo Bertozzi, Colin Patrick McCabe, Andrew Wang, Cloudera, inc
Kudu:  Storage for Fast Analytics on Fast Data
https://kudu.apache.org/kudu.pdf

5.PrestoDB
- invented at Facebook
- open source distributed SQL query engine for running interactive analytic queries against data sources of all sizes
- https://prestodb.io/ 

6.Apache Drill
- MPP
- open source, inspired by Dremel
- Schema-free SQL Query Engine for Hadoop, NoSQL and Cloud Storage
- https://drill.apache.org/

7.TokuDB 
- storage engine for MySQL and MariaDB, scalable, ACID and MVCC compliant
- https://www.percona.com/software/mysql-database/percona-tokudb

8.HP Vertica
- hp_vertica_description.pdf

Andrew Lamb, Matt Fuller, Ramakrishna VaradarajanNga Tran, Ben Vandiver, Lyric Doshi, Chuck Bear
The Vertica Analytic Database: C-Store 7 Years Later
http://vldb.org/pvldb/vol5/p1790_andrewlamb_vldb2012.pdf

9.Oracle Exadata
- exadata_x4_hardware_overview.pdf
- exadata_tests.pdf

10.Google BigQuery (service)
- Dremel

Sergey Melnik, Andrey Gubarev, Jing Jing Long, Geoffrey Romer,Shiva Shivakumar, Matt Tolton, Theo Vassilakis Google, Inc
Dremel: Interactive Analysis of Web-Scale Datasets
https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/36632.pdf

11.Google BigTable
- proprietary
- GFS

Fay Chang, Jeffrey Dean,Sanjay Ghemawat,Wilson C.Hsieh, Deborah A.Wallach, Mike Burrows, Tushar Chandra, Andrew Fikes, Robert E.Gruber
Bigtable:A Distributed Storage System for Structured Data
https://storage.googleapis.com/pub-tools-public-publication-data/pdf/68a74a85e1662fe02ff3967497f31fda7f32225c.pdf

12.Amazon Redshift

13.IBM Netezza 
- uses FPGAs
- proprietary AMPP (Asymmetric Massively Parallel Processing) architecture
- black box from IBM

14.Teradata
- physical distributed memory
- https://habr.com/ru/post/209078/
- https://habr.com/en/company/teradata/blog/160821/ 

15.https://dbdb.io/

Comparisons 
-----------

Justin Ellingwood
Hadoop, Storm, Samza, Spark, and Flink: Big Data Frameworks Compared
https://www.digitalocean.com/community/tutorials/hadoop-storm-samza-spark-and-flink-big-data-frameworks-compared

Compression
-----------

Zip, deflate
https://m.habr.com/ru/company/mailru/blog/490790/

ZFS Compression - A Win-Win
https://blogs.oracle.com/solaris/zfs-compression-a-win-win-v2

Zstandard
https://facebook.github.io/zstd/

Data formats
------------

1. Column-based
- Apache ORC (Optimized Row Columnar)
- RCFIle (row group with separated columns)
- Parquet

2. Row-based, line-oriented 
- plain text, CSV, JSON
- compressed CSV, JSON with LZO, bzip2
- Apache Avro
- Sequence

Books
-----

Butch Quinto
Next-Generation Big Data: A Practical Guide to Apache Kudu, Impala, and Spark

Editors: Zhan, Jianfeng, Han, Rui, Weng, Chuliang (Eds.) 
Big Data Benchmarks, Performance Optimization, and Emerging Hardware
4th and 5th Workshops, BPOE 2014, Salt Lake City, USA, March 1, 2014 and Hangzhou, China, September 5, 2014, Revised Selected Papers