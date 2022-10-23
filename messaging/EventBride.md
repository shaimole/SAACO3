# EventBride
- schedule (cron jobs)
- event pattern (email when root user logs in)
- json format
- can archive events
- replay archived events
- event json is typed, can be nice for custom code/lambda
## Sources
- EC2
- Code Build
- S3
- Trusted Advisor
- CloudTrail (ani API call)
- schedule
## Targets
- lambda
- batch
- ecs
- sqs
- sns
- step functions
- pipelines
- kinesis
- ssm
-...
## Event Bus
- supports resource based policies
- can allow events from other accounts
### Default
- AWS Services
### Parnter Event bus
- supported 3rd party events
### Custom Event Bus
- for custom apps
