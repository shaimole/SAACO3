# AWS Lambda
- run code serverless
- pay per compute time
- limited by time SHORT EXECUTIONS
- scaling is automated
- no charge if not running
- Operates from AWS owned VPC
- by default only public traffic
- you can enable function vpc access if you need private ressources
- if you need both private and public res, you will have to enable vpc access and use a nat gateway
- scale up based on request amount
- can set custom function timeout
- can be packaged and deployed as container images

## Security

### Lambda authorizer
- send additonal info based of bearer token or request context
- skip having too lookup users
- dont pass credentials!
## compute power
- relative to memory allocation
## Lambda Layer
- zip archive which contains librarties, custom runtime and other dependecies
- a single function can use up to 5 layers
- can use own layers or already published ones
- unzipped size cannot exed 250mb for function and all layers
## Container Image
- image must implement lambda runtime api
- ecs and fargate is prefered

## Price
- pay per call first 1 mill are free
- 0.20 cent per one million request after
- pay per duration 400000GB Seconds per month free
- scales up after that depending on gbseconds

## Limits per region

### Memory 
- 128MB to 10GB in 1mb increments
### Time
- 900 seconds/ 15 mins
### ENv vars
- 4kb
### Disk
- 512MB to 10GB
### Concurrency
- 1000 but can be increased
### Deployment
#### zip size
- 50 MB
#### uncompressed with dependencies
- 250 MB
#### tmp
- can use /tmp to load other files after/on startup
#### env vars
- 4kb max

