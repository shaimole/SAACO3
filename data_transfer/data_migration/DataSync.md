# AWS Data Sync
- online data transfer service
- use for one time transfers of data which no longer need to be in other location synced
- accelerates copying large amounts of data between on-premises and aws
- encrypted
## Sources
- on premise
- edge
- other clouds
## Targets
- s3
- efs
- FSx for Windows file server
- FSx for Lustre
- FSX for OpenZFS
- NetApp ONTAP

## Data Sync Agent
- run as a vm on premises
## S3 Outpost
- runs on EC2 on the outpost
## Snowcone
- Agent comes pre installed on physical device

## Route
- Onpremise File System -> On premise Data Sync Agent -> AWS Direct Connect Connection or Internet -> AWS Datasync service -> Cloud storage 