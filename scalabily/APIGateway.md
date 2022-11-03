# Api Gateway
- fronted for api
- can thrrottle request unsing token bucket algorithm
- set a limit on steady-state rate and a burst of request
- use lambda for no infrastructe
- support websocket protocol
- handle api versioning
- swagger/open api support
- transform and validate request
- cache responses

## API Gateway Keys
- used to track a consumers usage accross your api

## Targets
- Lambda for REST
- any HTTP endpoint
- any AWS API ([[StepFunction]], [[SQS]], ...)

## Endpoint Types


### Edge Optimized
- routed through [[Cloudfront]]
- used for global clients

### Regional
- clients within the same region
- manually combine with [[Cloudfront]] for more control

### Private
- only from within your vpc
- can use ressource policy

## Authentification
- [[IAM]] Roles (for internal Application)
- [[Cognito]] for External Users
- Custom Autherized (using [[Lambda]] and own code)

### Custom Domanin  name HTTP Secuirty
- use [[utils/ACM]] 
- [[utils/ACM]] cert must be in us east 1 for Edge Optimized
- must use  [[Route53]]