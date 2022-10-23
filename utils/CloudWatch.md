# CloudWatch
- monitoring and log service
- can setup alarms
- can stop, terminate, reboot and recover ec2 instances
- can trigger lambda or event bridge

## Cloudwatch Metrics
- metrics for every service in AWS
- bucketet by namespaces
- a metric can has up to 10 attributes
- metrics can have timestamps
- can create dashboard
- can create custom metrics

### Cloudwatch metrics streams
- continually stream cloudwatch metrics to 
- Kindesis Firehouse
- 3rd party providers
- option to filter metrics, to just send a subset

## Cloudwatch Logs
- Log groups (application name)
- log steam (log files, instances whitin on app, containers)
- can define log expiration days
### Targets
- can send logs to
- s3
- kinesis data streams
- kinesis data firehouse
- Lambda
- elasticsearch
### How to send Logs
- SDK
- Cloudwatchj Logs Angent
- Cloudwatch unified agent
- Elastic Beanstalk, collection of logs from applciation
- ecs collection from containers
- aws lambda collection from function logs
- vpc flow logs
- api gateway
- cloudtrail based on filter
- route 53 dns requests

### Filter 
- look for ip 
- look for string
- can trigger cloudwatch alarmas
### Insights
- query logs for dashboard
#### Container Insights
- collect and aggregate logs from containers
- ecs
- eks
- ec2 kubernetis
- fargate
- used containerized version of the container agent

#### Lambda Insights
- metircs for labmda functions
- is provided via lambda layer

#### Contributer Insights
- Top N Contributers to Network traffic
- identify bad hosts

#### Application Insights
- automated dashboard with monitored applications
- suport only select techstack on ec2 (java, iis, databases)
- can use additional ressources (RDS, S3, SNS ...)
- Powered by Sage maker
- reduce time to troubleshoot
- alters and findigs are sent to eventbride and SSM OpsCenter

### Export
-  to s3 up to 12 hours
- api call is createexporttask
- use log sbursciptions for real tiome

### Log subscriptions
- Uses a filter
- send to destination (e.g. Lambda )

### Multi account
- use one  central kinesis and subscriptions

## Cloudwatch Agent
- software on ec2
- needs correct permission

### Logs Agent
- old version 
- only send to cloudwatch logs
### Unified Agent
- collects system level metrics such as RAM processes etc
- collect logs to send to cloudwatch logs
- configuration via SSM Parameter Store

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
- ec2 instance actions (stop, terminate, reboot, revocer)
- trigger ASG
- SNS

### Composite Alrams
- multiple alarms combined (multi metric alaram)
- And or OR conditions

### EC2 Instance recovery
- Status Check
- start recovery (move host but keep ips, metadata and placement groups)