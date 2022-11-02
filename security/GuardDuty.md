![[Pasted image 20221102195508.png]]
# Amazon Guard Duty

## TLDR
Ml based continues monitoring and thread detection service. Helps for Crypto exploits

## Features
- thread detection 
- continously monitor AWS Accounts, workload and data stored in [[S3]]
- integrates with thread intelligence (known bad ips)
- uses ML to give insight
- protection against crypto currency attack

## Source to Analyse
- [[CloudTrail]] Managment Events
- [[CloudTrail]] [[S3]] Data events
- [[VPC]] Flow Logs
- DNS Logs
- [[EKS]] Audit Logs

## Findings
- [[CloudWatch]] Event Rules to [[Lambda]] or [[SNS]]
- If you disabled the service it will reset the service and delete all data collected