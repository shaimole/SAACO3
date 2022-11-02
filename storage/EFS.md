![[Pasted image 20221101130307.png]]
# Eastic File System

## TLDR 
High performance network file system which is pay per gb use and can attach to multiple services in multiple AZs.

## Features
- multi AZ
- high avalilable, scalable and expensive
- pay per use
- uses [[SecurityGroup]]

## Uses cases
- Content Management, web serving, data sharing
- NFSv4.1 protocol
- Only compatible with linux
- encyption at rest with [[KMS]]
- posix file system

## Performance
- 1000s of clients 10GBs throughput
- Can handle petabyte scale data

### Performances Modes
- set at creation time

#### General purpose
- web server, cms
- latency sensitive

#### Max IO
- higher latency and throughput
- paralell
- big data, media processing

### Throughput modes

#### bursting
- 1 tb = 50mbs + burst of up to 100mbs

#### provisioned
- set throughput regardless of size
- use when data created is small but performance needs to be high

## Storage classes

### Storage Tiers
- livecycle managemet for cost savings
- uses livecycle policies

#### Standard 
- frequently access files

#### Infrequent access
- cost to retrieve files but lower storage costs

## Availablity

### Standard 
- multi AZ

### One Zone
- one AZ
- good for dev
- compatible with infrequent acess ( for up to 90% in savings)
- backup enabled by default

