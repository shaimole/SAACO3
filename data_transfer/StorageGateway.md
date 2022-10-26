# Storage Gateway
- hybrid Cloud
- bride cloud and on premise
## Usage
- long migrations
- security
- complicance
- it strat
- tiered storage
- backup and restore
- disater recovery
## Types
### S3 File Gateway
- NFS or SMB Protocol
- translates request to Http request to S3
- most recently used data is cached in file gateway
### FSx File Gatway
- native access to FSx for Windows File Server
- local cache for frequently accessed data
- windows native compatiblity (SMB, NTFS, AD)
- group file shares and home directories
### Volume Gateway
- Block Storage
- Backed by EBS snapshots
#### Cached volumes
- low latency access to most recent data
#### Stored volumes
- dataset in on premise, backups are schedules to s3
#### Tape Gateway
- uses Virtual Tape libray
- for backup processes using physical Tapes
## Hardware appliance
- can buy from amazon.com
- is harware which will be your gateway