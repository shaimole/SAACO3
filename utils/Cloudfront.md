# CloudFront
- CDN
- data, videos, application and apis delivery
- global
- regional edge cachhes
- only http based requests

## Customization at Edge
- serverless
- customize a cdn endpoint
- pay per use
### Use cases
- Website security and privacy
- seo
- intelligent route
- bot mitigation
- real time image transform
- a/b testing
- Dynmaic Web Apps at Edge
- User prio
- tracking ad analytics
- user auth 
### Clloudfront Edge function
- code attached to cloudfront distributions
- runs closer to users for min latency
- lightweight written in js
- high scale latency senstive cns customisations
- sub ms startuptimes
- managed in cloudfront
- millions of request per second
#### Price
- Free tier available
- 1/5 of Lambda @Edge
#### Use cases
- cache key normalisation (transform request attributes)
- header manipulation
- url rewrites and rediect
- validate jwt tokens
### Lambda at Edge
- nodeJs or python
- 1ks of request per second
- can change every part of the request (viewer and origin)
#### Price
- no free tier
#### Use cases
- loner exec time
- adjustible cpu memory
- code depends on 3rd party (AWS CLI)
- Network access
- File System Access
- Http Body Access