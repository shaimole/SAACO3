![[Pasted image 20221101163353.png]]
# Amazon Simple Notification Service

## TLDR
Message queue with a subscriber model. It can send the same message to alot of diffrent services at once. Scales good but not indefinetly.

## Features
- subscriber async model
- one producer multiple consumers/subscribers
- up to 12 million subscribtions per topic
- up to 100k topics

## Sources
- [[CloudWatch]] alarms
- [[ASG]] Notifications
- AWS Budgets [[AWSBilling]]
- [[Lambda]]
- [[DynamoDB]]
- Cloudformation
- ...

## Targets
- [[Kinesis]] Data Firehouse
- [[SQS]]
- [[Lambda]]
- HTTP
- E-Mail
- push
- sms

## Topic Publish
- create a topic
- add subscriptions to topic
- publish to the topic

## Direct Publish
- for mobile apps
- create platform app
- create platform endpoint
- publish to endpoint
- Google GCM
- Apple APNS
- Amazon ADM ...

## Security
- https by default
- at rest using [[KMS]]
- client side optional
- iam for access control
- sns access policies, ressource based for cross account or other services

## Fifo
- same as [[SQS]] Fifo

## Filtering
- json policies on a subscriber 
- will only recive msg which match the filter
- can be used with fan out to split sns msgs to multiple deticated [[SQS]] queues