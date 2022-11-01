# Amazon Guard Duty
- thread detection 
- continously monitor AWS Accounts, workload and data stored in S3
- integrates with thread intelligence (known bad ips)
- uses ML to give insight
- protection against crypto currency attack

## Source to Analyse
- Cloud Trail Managment Events
- Cloud Trail S3 Data events
- VPC Flow Logs
- DNS Logs
- Kubernetis Audit Logs

## Findings
- Cloud Watch Event Rules to Lambda or SNS
- If you disabled the service it will reset the service and delete all data collected