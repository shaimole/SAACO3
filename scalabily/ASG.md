![[Pasted image 20221101113842.png]]
# Auto Scaling Group

## TLDR
A Group of [[EC2]] Instances scaled horizontally, can use an [[ELB]] or work without it if there is no incomming traffic. Can use [[ELB]] or [[EC2]] health checks.

- scale horizontaly
- scale out and in
- ensure maximum and minimum ec2s
- automaticly register EC2 with load balancer
- if instance is unhealthy it will be terminated and recreated
- set desired capacity

## launch template
- similar to launch config
- specifies same stuff
- allows for multiple versions of a template
- can mix on demand and spot instances

## launch configuration
- defines instace configuration (size etc)
- AMI
- instance Type
- key pair
- [[SecurityGroup]]
- block device mapping
- can not be modified but must be swaped if already in use

## Instance States

### Standby
- used for maintance
- wont be terminated if health check fails
- wont recieve traffic

## Termination Order
1. Cost (Spot vs on-demand)
2. oldest launch configuration
3. oldest launch template
4. closest to next billig hour
