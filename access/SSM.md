![[Pasted image 20221030220736.png]]
# Systems Manager Session Manager

## TLDR
Instead of using SSH or [[EC2InstanceConnect]] you can use the Session Manager to access your [[EC2]] Instances. Also simplifies access to machines in private subnets.

- Allows to start shell on [[EC2]] and on premise servers
- No SSH port opening needed
- No bastion host needed
- No SSH keys needed
- Runs on linux, win or mac 
- Send session log data to [[S3]] or [[CloudWatch]] 
- Shell is open from SSM to [[EC2]] and is herby locked within AWS