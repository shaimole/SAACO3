# Elastic Load Balancer
- Server which forwands traffic to ec2s
- spread load
- expose single dns access to whole clustered application
- seamlessly handle failures
- health checks
- provides https to instances
- enforce stickyness with cookies
- high availabliy across zones
- separate public traffic from private traffic
- can be setup as internal or external
## General
- managed by aws

## compatible services
- EC2
- EC2 ASG
- ECS
- AWS Certificate Manager
- Cloud Watch
- Route 53
- AWS WAAF
- AWS Global Accelerator

## Health checks
- port and route

## Classic Load Balancer
- htt, https (layer 7), tcp (layer 4), ssl
- deprecated
- health checks tcp or http based
- fixed hostname
## Application Load Balancer
- http, https , websocket (layer 7)
- need target groups
- can use to target diffrent containers on same mashine
- good for ecs and docker
- port mapping feature
- fixed hostname
- app servers dont see the clients ip directly

### Target groups
- EC2 Instances
- ECS Tasks
- Lambda functions
- Private IP Adresses

### Routing
- based on path
- based on hostname
- based on query

## Network Load Balancer
- TCP, TLS, UDP (Layer 4)
- high performance, millions of requests per second
- less latency
- one static ip per AZ
- support elastic IP
- health checks with tcp, http or https
### Target Groups
- EC2 Instances
- Private Ip Adresses
- Application Load Balancer

## Gateway Load Balacher
- IP Protocol (layer 3, networkt)
- Deploy scale and manage a fleed of 3rd party netwurk viurual aplicaneces
- Examples, Firewals, Instrusion Detection, Deep Packet Inspection, payload manipulations
- GENEVE Protocol on port 6081

### Functions
- Transparent Network Gateway, single entry exit for all trafic
- Load Balancer distributes to your check mashienes

### Target Groups
- Ec2 Instances
- Private Ips


## Security
- uses Security Groups