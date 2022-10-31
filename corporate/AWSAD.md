![[Pasted image 20221031085227.png]]
# Directory Service

## TLDR
A collection of sub services which allows companies to leverage directory authentification within AWS. Supports Microsoft Active Directoy.

## Versions

### AWS Manged Active Directory
- The Active Directory is manged on aws side.
- Can also be used on premise, a 2 side trust connection is established between aws AD and on prem AD

## AD Connector
- Can use on prem ad auth in aws, by proxying to the ad domain controller on premise
- AD is managed on premise

## Simple AD
- Create a new AD managed in AWS 
- No on prem AD required but can be joined