# Data Migiration Service
- seamlessly migrate
- full set
- resilient
- self healing
- data change capture
- no code needed
- replication instaces for scaling workloads
- support continous repication
- uses an ec2 instance to run dms software
## Sources
- on premise anfd ec2 instaces
- azure
- S3
- Aurora
- RDS
## Targets
- on premise and ec2 instances
- relational Databases
- elasticsearch
- dynamo db
- document db
- Data Warehouses
- Streaming Platforms
- Kinesis Data Streams
- Amazon Manged Streaming of Kafka (MSK)
- Redshift
- S3
## Limitations
- aws service to aws service sometimes needs to be in the same region and same account

## Basic Schema copy
- create tables and pls
- heterogenus migration ( Orcale to MySQL e.g.)
## Schema conversion tool
- transfer db from one schema to another
- move stored procedures

## RDS to Aurora mysql
### option 1
- DB Snapshot from RDS restore as aurora
### option 2
- Create an aurora read replaicaa from rds, when replication laag is 0 promote the replica to  own db cluster
### option 3 external to aws
- use percona xtrabackup and upload to s3
- creaate aurora from s3
### option4 external to aws
- create aurora
- us mysqldump to  migraate into aurora (slower than s3 method)
### option 5 use dms

