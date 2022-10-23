# Amazon Managed Streaming
- alternative to Kinesis
- Fully managed apache Kafka on AWS
- cluster
## MSK Serverless
- no provisioning
- automatic scaling

## Diffrence to Kinesis
- Kinesis 1 MB limit per mssg, msk 10 mb
- kinesis shard, kafka topics
- kafka doesnt enforce ssl
- kafka can only add partions to a topic

## Consumers
- Apps (EC2, ECs, EKS)
- Kinesis Data ANalytics
- GLUE
- Lambda