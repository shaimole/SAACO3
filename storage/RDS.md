# RDS
- scaling capacity (up to set maximum storage, every 6h max, 5 mins needs to be low storage which is less than 10% remaining)
- os patching
- no ssh
- monitoring dashboards
- multi az
- scaling capability

## Read replicas
- up to 5 read replicas
- eventually async replication
- can be promoted to their own database
- no cross az network cost
- cross region cost per network traffic
- can be multi AZ
## Multi AZ
- can be upgraded without downtime
- one dns name
- automatic failover to standby database by switching target ip of dns name
- sync replication
- one db will be standby
- deactive automation mode and take snapshot before modify
## RDS Custom
- only for oracle and mssql
- access to underlying database and os
- ssh possible
## Security
- if you need encrpt in transit use ssl/tls by launching the client with the --ssl_ca flag
- can use KMS to encrypt data at rest
### Option

#### RDS Custom for Oracle
- alllows customisation to host and os

## Backups
- daily full backup during maintence window
- transactions logs are backed up by rds every 5 mins

- restory any point in time (5 mins aago)
- 1 to 35 daus of retention
### Manual Snapshot
- manual trigger
- retention aas log as you want

### Savings
- take snapshot and delete database
- if you want rds back just restore with snapshot

### restore
- restorre mysql rds database from s3

### Cloning
- create a new aurora cluster from a existing one
- faster than snapshot & restore
- cost effective
- usful to create staging

## Security
- encrypt at rest with KMS, must be defined at launch time
- if master is not encrypted, reaad replicas can not be encryypted
- to change from and to encypt use snapshot
- encrypt in flight with tls root certificates client side
- can use iam roles to connect to database instead of username and pw
- can use security groups
- audit logs can be enabled and be send to cloudwatch


## RDS Proxy
- fully manged database proxy 
- allows apps to pool and share connection established with the database which allows less connections to database
- improves database performance
- severless
- autoscalling
- high available (multi az)
- reduces rds and aurora failover time by 66%
- enforces iam auth for db and store creds in aws secrets manager
- RDS Proxy is never public and can only be used from within the vpc
