# Auto Scaling Group
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
- instace Type
- key pair
- SGs
- block device mapping
- can not be modified but must be swaped if already in use