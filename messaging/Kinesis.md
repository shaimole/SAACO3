![[Pasted image 20221101120425.png]]
# Kinesis

## TLDR
Kinesis is a set of services for streaming real time or next to real time data in AWS. Its generaly more expensive and more difficult to setup than [[SQS]] but offers more features and higher performance.


## Features
- region scoped
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

## Kineis Data Streams Detail
- shards which split data and computing power

### Record
- entry in kinesis
- parition key which targets the shard
- data blob (up to 1mb)
- Producers can set 1mbs and 1000msg per sec per SHARD

#### Consumer
- recieves partion key, seceqnce number and blog
- thoughput 2mbs per sec shared for all consumers
- enhances 2mb per sec per consumer
- apps using sdk
- [[Lambda]]
- kinesis firehouse
- kinesis data analytics

### Retention
- between 1 and 365 days
- can replay data
- immutabilty

### Modes

#### Provisoned Mode 
- choose numer of shards, scale manualy
- 1mbs in 2 mbs sec out per shard
- pay per shard per hour

#### On demand
- default capacity provisoned (4mbs)
- scales on throughput peak observed within the last 30 days
- pay per hour and data in out per GB

### Security
- [[KMS]] at rest
- https in flight
- [[IAM]] for access
- can also use client side encryption
- [[VPC]] endpoint for access from [[VPC]]
- monitor with [[CloudTrail]]

## Kinesis Streams vs Firehouse
- Streams to capture data in real time, and ingest at scale
- Firehouse to load streaming into aws data stores
- Firehouse is not real time
- Firehouse has close ended consumer options
- Firehouse has a single target

## Firehouse
- load steaming data into data stores/ lakes and analytic tools
- serverless
- scales to data throughput
- aws managed
- batch
- transform
- encrypt
- SINGLE consumer

### Cost
- pay per Data send
- near real time (60 sec minimum)

### Producers
- Clients
- Apps
- SDK
- Kinesis Agent
- AWS IOT
- [[CloudWatch]] logs and events
- kinesis data streams

### Targets
- [[S3]]
- [[Redshift]]
- Elasticsearch
- Splunk
- custom http endpoints

## Data Analytics for SQL Application
- serverless
- pay per consumption rate
- read from Data Streams or Firehouse
- use SQL Statements while refrencing [[S3]]
- send againt to another Kinesis Stream or Firehouse
- stores data

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
-  [[MSK]]

## Usage
- more powerful queries
- run complex queries

## Data Ordering in SQS vs Kinesis
- kinesis your producers need to use the same partition/shard key for related data
- in [[SQS]] there is no ordering
- in [[SQS]] FIFO there is only one consumer and order stays the same
- in [[SQS]] FIFO queue if you want to send related data to diffrent consumers you use a group id, which works then similar to kinesis

### [[SQS]] VS [[SNS]] VS [[Kinesis]]

#### [[SQS]] 
- pull data then delete message via api call from consumer
- Message is processed by exacly one consumer (hopefully)
- as many workers at you want
- scales indefiently
- need fifo for order

#### [[SNS]]
- push same data to multiple subscribers
- data is not persistent
- fan out to combine with SQS

#### Kinesis
- standard 2mb per shard pull data
- consumers can consume data concurrently
- enhanced fan ut 2mb per shard per consumer , push data
- limited amount of consumers (by shard)
- replay data
- ment for real time big data
- ordering at shard level
- data will expire after x days