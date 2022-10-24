# Elastic Container Service
- use docker images
- run and scale docker applications
## EC2 Based
- need to have a running ec2 as target for host
- billed for ec2
- instace must run ecs agent
## Fargate Based
- serverless
- billed for cpu and memory

## Roles
### Instance Profile
- only for ec2
- used to create and run image on ec2
### Task Role
- permissons for the code running in the container

## Autoscaling
- scale on cpu, mem or alb count per target
- fargate is easier
- combine ecs cluster capacity prover paired with asg
### Modes
- target tracking
- step caling
- scheduld scaling

## Advanced Use Cases
- use event bride or SQS Que to launch container, process tasks and shut down container afterwards