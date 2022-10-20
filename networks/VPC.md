# VPC Virtual Private Cloud

## Console Wizard

### Options

#### VPC with public subnet
- single puyblic subnet
- internet gateway
- recommended for simple public facing application
#### VPC withg public and private subnets
- public subnet
- private subnet
- internet gateway
- recommended for 2 tier application
#### VPC with public, private subnets and AWS Site-to-Site VPN
- public subnet
- private subnet
- virtual private gatway
- internet gateway
- recommended to extend network into the cloud and some ressource are internet facing
#### VPC with private subnet and AWS Site-to-Site VPN
- private subnet
- virtual private gateway
- recommended to extend private network into the cloud

## VPC Endpoint
- privatly connect a VPC to supported services 
- does not require an internet gateway, NAT, VPN or DirectConnect
- instances dont require public ip adresses
- uses AWS Private Link as connection Line
- data does not leave AWS while communicatiing
### Interface Endpoint
- eni with private ip adress in the target subnet
### Gateway Endpoint
- only for S3 and Dynamo DB
- gateway which you set as a route target 

## VPC Peering
- connection between 2 VPCs using private adresses
- not transitive

### Transit Gatway
- hub for multiple peering connections
- attach options are, vpc, direct connect gateway or another transit gateway either as peering or vpn
- MTU = max package size
- MTU 85kbs if direct connect or peering vpc
- MTU 15kbs if VPN
- has a route table
- route propagation
- gives douple throughput of virtual private gateway

## VPC Sharing
- share one or more subnets within other accounts beloning to the same organisation
- every account can only work with the ressources they created

