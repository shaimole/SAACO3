# VPN
## Design
- use non overlapping ip ranges for each network

### Options

#### AWS Managed VPN
- over internet
- aws manged
- use this to take advantage of aws manged services for failover and redundency
- one Virtual Private gateway to multiple Customer Gateways

##### Pro
- reuses existing vpn equipment
- reuses exisiting internet connection
- highly available
- Static routes, Border Gateway Protocol, peering and routing policies
##### Con
- Network latency
- variablity
- depending on internet
- Customer managed enpoints need to implement failover manually
- Customer device needs single hop BGP
#### AWS Transit Gateway + VPN
- over internet
- aws managed
- regional router distributes traffic to diffrent vpcs
- vpc need to be in the same region
- multiple customer gatways for one AWS Transit Gateway
##### Pro
- Same as AWS Managed VPN
- additional high availabilty and scalabity 
- up to 5k attachments for the transit gateway
##### Cons
- same as AWS Manged VPN
#### AWS Direct Connect
- Dedicated network connection over private lines
- VIF = Vitrual Interface
- need multiple aws direct connect connections to support multiple customer entrypoints, but only one virtual private gateway on AWS side
- higher bandwidth
- using private ip
- 1 to 10 Gbps
- can use link aggregation group
- Use direct connect Gateway to connect to multiple regions or accounts or vpcs

##### Pros
- More predictable Network performance
- Reduced bandwidth costs
- Support BGP peering and routing policies
##### Cons
- Requires additional telecom infrastructre
#### AWS Transit Gateway + AWS Direct Connect
- dedicated private network connection to region router which distributes the traffic to multiple vpcs
##### Pros
- Same as AWS Direct Connect
- additional high availabilty and scalabity 
- up to 5k attachments for the transit gateway
##### Cons
- Same as AWS Direct Connect
#### AWS Direct Connect + VPN
- Ipsec VPN connection over private Lines
##### Pros and Cons
- all Pros aand cons of AWS Mangend VPN and AWS Direct Connect
#### AWS Direct Connect + VPN + Transit Gatway
- Same as AWS Direct COnnect + VPN but for up to 5k targets
#### AWS VPN Cloud Hub
- Connect remote branch offices in a hub-and-spoke model for primary or backup connectivity
- connect remote to remote not remote to vpn
##### Pros
- Reusus exsiting internet connection and AWS VPN connections
- AWS managed and highly available
- Supports BGP for exchaning routes and routing policies
##### Cons 
- Network letency
- variablility and avialabilty are dependend on internet
- User managed branch office endpoints are responsible for failover implementation
#### Softeware Site to Site VPN
- Software applicance-based VPN connection over the internet
##### Pros
- supports wider range of VPN vendors, products and protocols
- Fully customer manged solution
##### Cons
- customer is responsible for implementing high availabilty for all endpoints

## IPSec
- also known as Site to Site VPN
- connect to a vpc from on premise/remote
### Virtual Private Gateway
-  also known as VPN Gateway
- entrypoint to AWS VPC side of your VPN Connection
### VPN Tunnel
- encryted link where data can pass from the customer networkt to or from aws
### Customer Gatway
- An AWS Ressource that provides Information to AWS about your Customer Gateway device
### Customer Gateway Device
- Physical or Software
- on customer side (on premise/remote) to establish VPN connection
