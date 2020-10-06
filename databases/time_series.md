Time Series DB
==============

1.OpenTSDB
- based on HBase

2.Whisper (Graphite)
- data on disk on Whisper format (RRD style)
- each timeseries is stored in a separate file

3.InfluxDB
- distributed storage cluster

4.Gorilla (Facebook)
- in-memory TSDB

Tuomas Pelkonen, Scott Franklin, Justin Teller, Paul Cavallaro, Qi Huang, Justin Meza, Kaushik Veeraraghavan
Gorilla: A Fast, Scalable, In-Memory Time Series Database
http://www.vldb.org/pvldb/vol8/p1816-teller.pdf

4.TimescaleDB
- postgres (11,12) extension
- compression
- converts fresh row-based data to columnar (by time) 
- https://blog.timescale.com/blog/building-columnar-compression-in-a-row-oriented-database/