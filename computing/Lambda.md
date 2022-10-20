# AWS Lambda
- run code serverless
- pay per compute time
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