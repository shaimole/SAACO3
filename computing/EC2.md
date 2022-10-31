![[Pasted image 20221030223457.png]]
# Elastic Compute Cloud

## TLDR
EC2 is a the combination of a virtual mashine and hardware capacity attached to that vm in AWS. It is one of the oldest services and well integrated into most other services.

## Virtual Machines (EC2)

### Configuration Options
- OS (Win, Linux, MacOs)
- CPU
- RAM
- Network attached storage ([[EBS]] & [[EFS]])
- Hardware attached ([[InstanceStore]])
- Network Card (Speed, Ip)
- Firewall ([[SecurityGroup]])
- Bootstrap script (User Data)

### User Data
- Is a script is run once on the first start of the instance
- Script is run using root privileges

### Use Cases
- Installing updates
- Installing software
- Download files from the internet

### Instance Types

#### Type Definition
- Split by family
- In family types are defined by Class.Generation.Size 

#### Families

##### General Purpose
- Balance between, computing, memory and network speed

##### Compute Optimized
- High cpu power

###### Use Cases
- Ml
- Media Transcoding 
-  ...

##### Memory Optimized
- High amount of RAM/Memory

###### Use Cases
- Process large data sets in memory
- Non relational databases
- Cache stores
- In memory databases 
- Real time proccessing of big unstructured data

##### Storage Optimzied
- High amount of Disk IOPs

###### Use Cases
- Alot of Datasets in local storage
- High frequency online transaction processing systems
- Databases
- Cache for in mem databases (e.g. redis)
- Distributed file systems
- Data warehouse applications

## Purcharsing Options

### On Demand
- Price by second
- Use for short workload

### Reserved

#### Default
- 1 Year OR 3 Years 
- Cheaper than on demand
- Need to specify type os, region, tenacy
- Cheaper if payed upfront
- Scope reserve in zone and AZ
- You can sell peer to peer in marketplace

#### Convertiable
- More expensive than default
- Can change instance type, os, region, tenacy

### [[SavingsPlans]]
- 1 Year OR 3 Years
- Up to same discount as default reserved instance
- Commit to an amount of usage (cpu, mem, disk)
- Beyond commit is billed on demand price
- Locked to instance family and region
- Can change os, tenancy, and instance size

### Spot Instances
- Cheapest
- Can lose instance
- Define max price you are willing to pay, if you are overbid your instance is gone

#### Use Cases
- Short workloads
- Suited for resiliant jobs
- Distributed workloads (these are resiliant by definition)

### Dedicated Hosts
- Rent an entire physical server, control placement of that server
- can use on demand or reserved 
- most expensive 

#### Use Cases
- Complicance
- Server bound software licences

### Dedicated Instances
- No other customer will share the hardware used by you
- Hardeware may be shared within same account
- No control over instance placement (hardware might be moved)

### Capacity Reservations
- Reserve a capacity in a AZ for duration (on demand instance)
- No time commitment
- No billig discount
- Combine with Saving plan and Reserved Instances for same AZ to save money
- Charged on demand price if instance is not running

  #### Use Cases
- short term uninterrupted workload in a specific az

## Spot Instance
- Request for an instance and the instance running itself is diffrent
- If you terminate your instance but not the request the instance will be relaunched
- If you cancel your request your instance will still be running

### Fleet
- Define multiple options for instance type , region etc
- Define a budget and target capacity

#### Strategies
- Lowest price, launch from lowest price pool
- Diversified, launch from all pools (resiliance)
- Capacity optimized, launch from pool with strongest capacity settings

## Elastic Ip
- A static ip which can be attached to Elastic Network Interfaces and other services
- Used to mask a fail by keeping ip but changing mashine
- Up to 5 per account
- Can request more than 5 from aws

## Placement Groups
Placement strategy for a group ec2 instances

### Spread
- Multi AZ 
- Diffrent hardware
- Limited to 7 instances per AZ per placement group
- Use for critical apps and high availability

### Cluster
- Same rack
- Fast internal connection from ec2 to ec2 
- Used for low latency and big data jobs with deadline
- Rack fail -> all EC2s fail

### Partition
- Multi AZ
- Multi rack but same rack per partition

#### Use Case
-  big data application which are partition aware

## ENI Elastic Network Interfaces
- Virtual Network Card
- Can be used not only for ec2
- Eth0 = primary ENI
- Primary private ip
- Can add multiple for multiple private ips
- Can attach elastic ip
- Can attach mac adress
- Can attach and detach from instance
- Bound by AZ

## EC2 Hibernate
- Standby for EC2, ram is saved
- Faster startup
- Root [[EBS]] must be encrypted
- Used for breaks in very long running tasks or if an instances takes very long to startup
- Can last no longer than 60 days