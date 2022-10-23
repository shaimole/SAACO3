# Kinesis
- real time data streaming service
- gigabytes of data per second
- 100ks of sources
- 2MBs/shard default shared between all consumers of kinesis streaam
- use enhanced fan out to support multiple consumers, each consumer gets the 2mbs/shard
- 1mbs input per shard 
- shards need to be provioned ahead of time
- consume records up to 7 days later
- multi applications consume the same stream
- keep order of records
- routing related records to the same consumer

## Firehouse
- load steaming data into data stores/ lakes and analytic tools
- scales to data throughput
- aws managed
- batch
- transform
- encrypt
### Targets
- S3
- Redshift
- Elasticsearch
- Splunk

## Data Analytics for SQL Application
- serverless
- pay per consumption rate
- read from Data Streams or Firehouse
- use SQL Statements while refrencing s3
- send againt to another Kinesis Stream or Firehouse
### Usage
- Real Time anaytics

## Data Anaytics for Appache Flink
- Use Flink (Java, Scala or SQL) to process or analyse streaming data
- provison compute ressources
- parallel computing
- automatic scaling
- backups
- any apache flink feature
- uses aws manged cluster behind the scenes
## Sources
- Kinesis Data Steams
- MSK
## Usage
- more powerful queries
- run complex queries
- 
