![[Pasted image 20221031103135.png]]
# AWS Data Sync

## TLDR
Data Sync is used for a secure one time transfer of data via the internet from a source into AWS.

## Features
- accelerates copying large amounts of data between a source and aws
- encrypted

## Use Cases
- one time transfers of data which no longer need to be in other location synced

## Sources
- On premise
- Edge
- Other clouds

## Targets
- [[S3]]
- [[EFS]]
- [[FSxWindowsFileServer]]
- [[FSxLustre]]
- FSX for OpenZFS
- NetApp ONTAP

## Data Sync Agent
- Runs as a vm on premises

## S3 Outpost
- Runs on EC2 on the outpost

## Snowcone
- Agent comes pre installed on physical device

## Route
- Onpremise File System -> On premise Data Sync Agent -> AWS [[DirectConnect]] or Internet -> AWS [[DataSync]] service -> Cloud storage 