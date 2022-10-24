# DynamoDB
- NoSQL
- serverless
- milisec latency
- key value doc db
- single digit milisecond performance
- multi az
- fully manged
- multi master
- backup and restore
- in memory caching
- transaction capabilty
##  Capacity Modes
- provisoned capacity with optional autoscaling
- on demand capacity
## Use cases
- can replace elasticache (stroing session data with ttl feature)
 - serverless apps
 - rapdily evolve schemas
 - small documents 100bs
 - distributed serverless cache
## DAX cluster
- read cache 
- in memory
- microsecond read latency
## Auth
- Iam
## Dynamo DB STream
- event processing
- invoke lambda or send to kinesis
- 24 hour retention 
- limited number of consumers
## Dynamo DB Kinesis Data Steams
- 1 year retention
- all features of kineis
## Global Tables
- active active setup for multi region
- two way replication
- must enable Streams as prerequiste
## Backups
- automated backups up to 35 days with PITR to restore to new table
- on demand backups
## Export
- export import to S3