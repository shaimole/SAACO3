![[Pasted image 20221101162633.png]]
# CloudWatch

## TLDR
Central service for all logs and metrics in AWS.

## Features
- can setup alarms
- can stop, terminate, reboot and recover [[EC2]] instances
- can trigger [[Lambda]] or [[EventBride]]

## Cloudwatch Metrics
- metrics for every service in AWS
- bucketet by namespaces
- a metric can has up to 10 attributes
- metrics can have timestamps
- can create dashboard
- can create custom metrics

### Cloudwatch metrics streams
- continually stream cloudwatch metrics to 
- [[Kinesis]] Firehouse
- 3rd party providers
- option to filter metrics, to just send a subset

## Cloudwatch Logs
- Log groups (application name)
- log steam (log files, instances whitin on app, containers)
- can define log expiration days

### Targets To Send Logs To
- [[S3]]
- [[Kinesis]] data streams
- [[Kinesis]] data firehouse
- [[Lambda]]
- elasticsearch

### How to send Logs
- SDK
- Cloudwatch Logs Angent
- Cloudwatch unified agent
- [[ElasticBeanstalk]], collection of logs from applciation
- [[ECS]] collection from containers
- aws [[Lambda]] collection from function logs
- [[VPC]] flow logs
- [[APIGateway]]
- [[CloudTrail]] based on filter
- [[Route53]] dns requests

### Filter 
- look for ip 
- look for string
- can trigger cloudwatch alarmas

### Insights
- query logs for dashboard

#### Container Insights
- collect and aggregate logs from containers
- [[ECS]]
- [[EKS]]
- [[EKS]]
- [[ECS]] Fargate
- used containerized version of the container agent

#### Lambda Insights
- metircs for [[Lambda]] functions
- is provided via [[Lambda]] layer

#### Contributer Insights
- Top N Contributers to Network traffic
- identify bad hosts

#### Application Insights
- automated dashboard with monitored applications
- suport only select techstack on ec2 (java, iis, databases)
- can use additional ressources ([[RDS]], [[S3]], [[SNS]] ...)
- Powered by Sage maker
- reduce time to troubleshoot
- alters and findigs are sent to [[EventBride]] and [[SSM]] OpsCenter

### Export
-  to s3 up to 12 hours
- api call is createexporttask
- use log sbursciptions for real tiome

### Log subscriptions
- Uses a filter
- send to destination (e.g. [[Lambda]] )

### Multi account
- use one  central kinesis and subscriptions

## Cloudwatch Agent
- software on ec2
- needs correct permission

### Logs Agent
- old version 
- only send to [[CloudWatch]] logs

### Unified Agent
- collects system level metrics such as RAM processes etc
- collect logs to send to [[CloudWatch]] logs
- configuration via [[SSMParameterStore]] 

### Metrics
- CPU
- DISK (io remianing)
- RAM
- NetStat
- processes
- swap space

## Cloudwatch Alarams
- trigger notifications from any metric

### Stages
- OK
- Inssufficent Data
- Alarm

### Period
- length of time to evaluate the metric

### Targets
- [[EC2]] instance actions (stop, terminate, reboot, revocer)
- trigger [[ASG]]
- [[SNS]]

### Composite Alrams
- multiple alarms combined (multi metric alaram)
- And or OR conditions

### [[EC2]] Instance recovery
- Status Check
- start recovery (move host but keep ips, metadata and placement groups)