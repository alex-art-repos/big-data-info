Time Series DB
==============

1.OpenTSDB
- based on HBase

2.Whisper (Graphite)
- data on disk on Whisper format (RRD style)
- each timeseries is stored in a separate file

3.InfluxDB
- distributed storage cluster

https://docs.influxdata.com/influxdb/v1.8/concepts/insights_tradeoffs/

- For the time series use case, we assume that if the same data is sent multiple times, it is the exact same data that a 
  client just sent several times.

  Pro: Simplified conflict resolution increases write performance.
  Con: Cannot store duplicate data; may overwrite data in rare circumstances.

- Deletes are a rare occurrence. When they do occur it is almost always against large ranges of old data that are cold for 
  writes.

  Pro: Restricting access to deletes allows for increased query and write performance.
  Con: Delete functionality is significantly restricted.

- Updates to existing data are a rare occurrence and contentious updates never happen. Time series data is predominantly 
  new data that is never updated.

  Pro: Restricting access to updates allows for increased query and write performance.
  Con: Update functionality is significantly restricted.

- The vast majority of writes are for data with very recent timestamps and the data is added in time ascending order.

  Pro: Adding data in time ascending order is significantly more performant.
  Con: Writing points with random times or with time not in ascending order is significantly less performant.

- Scale is critical. The database must be able to handle a high volume of reads and writes.

  Pro: The database can handle a high volume of reads and writes.
  Con: The InfluxDB development team was forced to make tradeoffs to increase performance.

- Being able to write and query the data is more important than having a strongly consistent view.

  Pro: Writing and querying the database can be done by multiple clients and at high loads.
  Con: Query returns may not include the most recent points if database is under heavy load.

- Many time series are ephemeral. There are often time series that appear only for a few hours and then go away, e.g. a 
  new host that gets started and reports for a while and then gets shut down.

  Pro: InfluxDB is good at managing discontinuous data.
  Con: Schema-less design means that some database functions are not supported e.g. there are no cross table joins.

- No one point is too important.

  Pro: InfluxDB has very powerful tools to deal with aggregate data and large data sets.
  Con: Points don’t have IDs in the traditional sense, they are differentiated by timestamp and series.

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