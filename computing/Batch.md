![[Pasted image 20221030223211.png]]
# AWS Batch

## TLDR
AWS Batch is used to simplify big batch jobs at scale. It handles to provisioning of computing, orchisation and storage power at a higher level.

## Features
- Fully managed batch processing at any scale
- Run 100ks  of batch jobs
- Batch job has an start or end
- Dynamicly launch [[EC2]] on-demand instances or spot instances
- Can also use Fargate [[ECS]]
- Helpful for cost optimisations
- No infrastructure to manage
- Not serverless
- No time limit
- Any runtime
- Can use [[EBS]] or Instance store for diskspace

## Batch vs [[Lambda]]
- [[Lambda]] has a time Limit
- [[Lambda]] has limited runtimes options
- [[Lambda]] is serveress
- [[Lambda]] has limited disk space