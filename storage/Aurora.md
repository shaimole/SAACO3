# Amazon Aurora
- not open source
- MySQL and Postgre
- global
- self healing
- fault tolerant
- autoscaling up to 64 TB per instance
- is a cluster
- multi az
- each az has a copy of the cluster
- 5x faster than mysql
- 3x fast than postgre
- up to 15 replicas
- faster replication
- 20% more cost than rds
- restore to any point in time
## Primary DB
- read and write
- only one per cluster
- if fails a replica will be promoted
## Aurora Replica
- same storage as primary
- multiple per az possible
- only read
- reader endpoint does load balancing