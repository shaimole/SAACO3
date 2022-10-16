# Eastic File System
- Network file system that can be mounted to multiple instances
- multi AZ
- high avalilable, scalable and expensive
- pay per use

## Uses cases
- Content Management, web serving, data sharing
- NFSv4.1 protocol
- uses SGs
- Only compatible with linux
- encyption at rest with kms
- posix file system
- scales automaticly, pay per use

## Performance
- 1000s of clients 10GBs throughput
- Can handle petabyte scale data
### performances Modes
- set at efs creation time
#### General purpose
- web server, cms
- latency sensitive
#### Max IO
- higher latency and throughput
- paralell
- big data, media processing

### throughput modes

#### bursting
- 1 tb = 50mbs + burst of up to 100mbs

#### provisioned
- set throughput regardless of size

## Storage classes

### Storage Tiers
- livecycle managemed for cost savings
- uses livecycle policies
#### Standard 
- frequently access files
#### Ifrequent access
- cost to retrieve files but lower storage costs

## Availablity

### Standard 
- multi AZ
### One Zone
- one AZ
- good for dev
- compatible with infrequent acess ( for up to 90% in savings)
- backup enabled by default

