![[Pasted image 20221101125233.png]]
# Simple Queue Service

## TLDR
AWS standard queue service. Has ton of features like fifo and multi consumer. Scales indefinetly.

## Features
- aws managed
- async systems
- decouplein
- message delay up to 15 min
- unlimited throughput 
- unlimited numer of messages
- default retention 4 days, max 14 days
- max size 256kbs
- dynamicly add concurrency/ read throughput
- track ack/fail 
- set visibilty timeout for ack/fail
- scale transparently
- buffer requests
- can have duplicate messages

## Producers
- needs to use sdk/api

## Consumers
- [[EC2]] Instances, [[Lambda]] ..
- polls queue, recieves up to 10 msg at a time
- after processing use sdk/api to send delete msg command to [[SQS]]

## Types
- cannot convert between types, ressouce needs to be recreated

### Standard
- max throughput
- best efford ordering
- at least once delivery

### Fifo
- first in first out
- needs to end with .fifo
- delivered exactly once
- max 3k per second with batching
- max 300 per second withut batching

## Security
- https api 
- at rest encryption with kms keys
- client side encryption also possible
- iAm to control access to queue

### SQS Access policies
- resource based permissions
- cross account
- other services without iam role

## Visibilty Timeout
- after polled msg becomes invisible
- set to process time to stop being processed twices
- if process time takes longer can use SQS API to increase visibilty timeout for this message

## Long Poling
- Queue gets polled for longer time to wait if queue is empty
- decrease the number of api calls
- between 1 and 20 seconds
- can be configured at queue level or in api request