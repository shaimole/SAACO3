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
- automatic failover to standby database
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