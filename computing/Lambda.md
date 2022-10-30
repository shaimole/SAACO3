![[Pasted image 20221030233208.png]]
# AWS Lambda

## TLDR
AWS Lambda means you dont care about any infrastructure, you just upload a function to aws. You can than use that function from other services like  [[APIGateway]], [[SNS]] or even [[CLI]]. You upload Lambda code as a zip.

## Features
- Run code serverless
- Pay per compute time
- Scaling is automated
- No charge if not running
- Operates from AWS owned[[VPC]]
- By default only public traffic
- You can enable function [[VPC]] access if you need private ressources from your [[VPC]]
- Scale up based on request amount
- Can set custom function timeout
- Can be packaged and deployed as container images

## Drawbacks
- Limited by time SHORT EXECUTIONS
- if you need both private and public ressources, you will have to enable [[VPC]] access and use a nat gateway to access the internet

## Security

### Lambda authorizer
- Send additonal info based of bearer token or request context
- Is useful because you can skip having too lookup users inside of your function  (you pass the user data)
- Dont pass credentials! (Though you could)

## Compute Power
- Relative to memory allocation which can be manually set

## Lambda Layer
- Zip archive which contains librarties, custom runtime and other dependecies
- A single function can use up to 5 layers
- Can use self created layers or already published ones
- Unzipped size cannot exeed 250mb for a function and all layers which it depends on

## Container Image
- If using an image the image must implement the  [[Lambda]] runtime api
- [[ECS]] and Fargate are prefered for this use case

## Price
- Pay per call first 1 mill are free
- 0.20 cent per one million request after
- Pay per duration 400000GB-Seconds per month free
- Price scales up after that depending on gbseconds (more will be cheaper per gbsecond)

## Limits Per Region

### Memory 
- 128MB to 10GB in 1mb increments

### Max Exec Time
- 900 seconds/ 15 mins

### ENV vars
- 4kb for all vars together

### Disk
- 512MB to 10GB

### Concurrency
- 1000 but can be increased

### Deployment

#### Zip Size
- 50 MB

#### Uncompressed With Dependencies
- 250 MB

#### TMP
- can use /tmp to load other files after/on startup

