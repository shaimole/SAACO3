# Cubernetis

## Manged Node Groups
- creates ec2 instances for you
- ASG managed by eks
- support on demand and spot instaces

## Self manghed
- EC2 are created by the user and registered to the cluster
- can use prebuild eks optimized AMI
- on demand or spot instaces
## Fargate
- no nodes or maintence required

## Data volumes
- need to specify storage class
- EBS
- EFS (works with fargate)
- FSx for Lustre
- FSx for NetApp ONETAP