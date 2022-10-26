# Amazon Simple Notification Service
- subscriber async model
- one producer multiple consumers/subscribers
- up to 12 million subscribtions per topic
- up to 100k topics
## Sources
- Cloudwatcg alarms
- ASG Notifications
- AWS Budgets
- Lambda
- Dynamo DB
- Cloudformation
...
## Targets
- Kinesis Data Firehouse
- SQS
- Lambda
- HTTP
- EMail
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
- at rest using kms
- client side optional
- iam for access control
- sns access policies, ressource based for cross account or other services
## Fifo
- same as SQS

## Filtering
- json policies on a subscriber 
- will only recive msg which match the filter
- can be used with fan out to split sns msgs to multiple deticated sqs queues