# Elastic Compute Cloud

## Virtual Maschines (EC2)

### Configuration
- OS (Win, Linux, MacOs)
- CPU
- RAM
- Stoarge Space Network attached (EBS & EFS)
- Hardware attached (EC2 Instace Store)
- Network Card (Speed, Ip)
- Firewall (Security Group)
- Bootstrap Script (ec2-user Data)

### User Data
- script is run once at instance first start
- installing updates
- installing software
- Download files from the internet

### Security Groups
- only allow rules
- refrence ip or other sg
- essential a firewall
- access to ports
- autherized ip ranges
- inbound and outbound
- one group to many instances
- vpc and region bound
- is not on the ec2 but before
- use seperate sg for ssh access
- time out usually means sg issue
- connection refused application or server error
- default all inbound is blocked all outbound allowed


### Instance Types

#### Convention
- ClassGeneration.Size

#### Families
##### General Purpose
- Balance between, computing, memory, network
##### Compute Optimized
- ML
- Media Transcoding 
- ...
##### Memory Optimized
- process large data sets in memory
- non relational Databases
- cache stores
- In memory Databases 
- Real time proccessing of big unstructured data

##### Storage Optimzied
- Alot of Datasets in local storage
- High frequency online transaction processing systems
- Databases
- Cache for in mem databases (redis)
- Distributed file Systems
- Data warehouse applications

## Virtual Drives (EBS)

## Distributing Load Accross Mashines (ELB) 

## Scale Mashines (ASG)

## Purcharsing Options
### On Demand
- price by second
- use for short workload
### Reserved
#### Default
- 1 Year OR 3 Years 
- cheaper than on demand
- Need to specify Type OS, Region, Tenacy
- cheaper if payed upfornt
- Scope reserve in Zone and AZ
- You can sell peer to peer in marketplace
#### Convertiable
- more expensive than default
- can change instance  type , os, region, tenacy

### Savings Plans
- 1 Year OR 3 Years
- up to same discaunt das default ri
- commit to an amound of usage
- beyond commit is billed on dempand price
- locked to instance family and region
- can change os, tenancy, and instance size
### Spot Instances
- short workload
- cheapest
- define max price
- can lose instance
- suited for resiliant jobs
- distributed workloads
### Dedicated Hosts
- entire physical server, control placement
- complicance
- server bound software licence 
- can use on demand or reserved 
- most expensive 
### Dedicated Instances
- no customer will share the hardware
- hardeware may be shared within same account
- no control over instance placement (hardware might be moved)
### Capacity Reservations
- Reserve a capacity in a AZ for duration (on demaand instance)
- no time commitment
- no billig discount
- Combine with Saving plan and Reserved Instances for same AZ to save
- Charged on demand even if instance is not running
- short term uninterrupted workload in a specific az
