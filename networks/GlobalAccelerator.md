# AWS Global Accelerator
- network layer service
- distribute traffic to optimal endpoints over AWS Network
- two static anycast ip adresses as fixed entrypoints
- global service
- can use weights to distribute portion of traffic
- good fit for non http use cases
## Targets
- ALB
- NLB
- Elastic IP
- EC2
## Health Checks
- failover less than 1 min unhealty
- good disater recovery
## Security
- only 2 external ips need to be whitelisted

