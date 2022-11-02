![[Pasted image 20221030231124.png]]
# Elastic Container Service

## TLDR
ECS is AWS Docker Service. You can launch and modify containers as tasks in multiple ways depending on your application and scale.

## [[EC2]] Based
- Need to have a running [[EC2]] as the host for your containers
- You are billed for depending on the [[EC2]]
- The [[EC2]] Instance must be running  the ecs agent

## Fargate Based
- Serverless
- Billed for cpu and memory used
- by default 20gb of free block storage

## Roles

### Instance Profile
- Only used for host [[EC2]]
- Used to create and run image on [[EC2]] 

### Task Role
- Defines Permissons for the code running in the container (access to other services)

## Autoscaling
- Scale on CPU, Mem or [[ELB]] traffic per target
- Scaling Fargate is easier
- Combine ecs cluster capacity prover paired with Auto Scaling group

### Modes
- Target tracking
- Step caling
- Scheduld scaling

## Advanced Use Cases
- Use [[EventBride]] or [[SQS]] to launch container, process tasks and shut down container afterwards