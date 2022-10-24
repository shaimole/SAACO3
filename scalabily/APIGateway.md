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
- any AWS API (Step function, SQS, ...)

## Endpoint Types
### Edge Optimized
- routed through cloudfront
- used for global clients
### Regional
- clients within the same region
- manually combine with cloudfront for more control
### Private
- only from within your vpc
- can use ressource policy
## Authentification
- IAM Roles (for internal Application)
- Cognito for External Users
- Custom Autherized (using Lamba and own code)
### Custom Domanin  name HTTP Secuirty
- use ACM 
- ACM cert must be in us east 1 for Edge Optimized
- must use route 53