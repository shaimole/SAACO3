# AWS Snow Family
- collect and process data at the edge
- or migrate data in and out of aws
## Data migration
- used when network lines are not fast enough (TBS and PBS)
- request from aws
- install ops software on your servers
- use the client and hardware
- ship back
- snownall is wiped
### Snowcone
- smaller Snowball
- 8TBs of storage
- fits on top of a drone
- can transfer other network aswell (collect offline transfer online)
### Snowball Edge
- big box to move tb or pbs of data in and out of aws
- pay per job
- provide block or s3 compatible storage
- cluster up to 15 devices (like 1 PB)
#### Storage optimized
- 80 TB
#### Compute optimized
- 42 TB 
### Snowmobile
- truck to transfer data
- 100PB of data
- high security
- use when transfering more than 10 PB
## Edge Computing
- process on edge
- no internet access
- preprocess
### Snowcone
- 2cpus, 4gb on memory
### Snowball Edge
- runs ec2s or lambda functions
#### compute optimzed
- 52vCpus 208GiB Ram
- optional GB
- 42 astorage
#### storage optimized
- up to 40 vCpus, 80GiB of Ram

### Ops Hub
- GUI Software to connect to snow devices
- edge computing 
- store data for transfer