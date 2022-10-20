# Simple Queue Service
- message queue
- aws managed
- async systems
- decouplein
- message delay up to 15 min
- dynamicly add concurrency/ read throughput
- track ack/fail 
- set visibilty timeout for ack/fail
- scale transparently
- buffer requests
## Types
- cannot convert between types, ressouce needs to be recared
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
