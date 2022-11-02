![[Pasted image 20221102200252.png]]
# AWS Network Firewall

## TLDR
Firewall for a [[VPC]]

## Features
- 1000s of rules
- protocol rules
- stateful domain list group (e.g. only allow traffic to *.google.com)
- general pattern matching using regex
- send logs to [[S3]], [[CloudWatch]] , or [[Kinesis]] firehouse

## Filter
- Alow
- Drop
- Alert

## Active flow inspection
- intrusion preventions (Managed by AWS)