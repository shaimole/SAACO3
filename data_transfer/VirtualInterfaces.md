![[Pasted image 20221031105916.png]]
## TLDR
These Interfaces are used to route traffic into your [[VPC]] inside of AWS.

## Versions

### Public Virtual Interface
- connect to ressources with public ips (eg. [[S3]])
- scope is region

### Private virtual Interface
- connect to private vpc ressources
- scope is [[VPC]]
- private ip

### Transit virtual Interface
- connect to multiple ressources in different vpcs
- scope is region and multi account
