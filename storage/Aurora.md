# Amazon Aurora
- MySQL and Postgre
- global
- self healing
- fault tolerant
- autoscaling up to 64 TB per instance
- is a cluster
- multi az
- each az has a copy of the cluster

## Primary DB
- read and write
- only one per cluster
- if fails a replica will be promoted
## Aurora Replica
- same storage as primary
- multiple per az possible
- only read