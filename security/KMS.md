# AWS Key Managed Service
- create and manage cryptographic keys
- control use of keys
- FIPS 140-2 valid
- used for ebs encryption
- integrated with iam for auth
- Can audit use of keys via CloudTrail
- 3 cent per 10000 api calls
- scoped per region
## Key Types

### Symetric
- AES256 keys
- single key to encrypt and decrypt
- AWS services which use KMS use this
- you can only get this key via api call

### Asymetric
- public key (encrypt)
- private key (decrypt)
- can download public key
- private key only api
- use case: encryption outside of aws which access to api

### Free
- aws managed
### Customer Manged Key (CMK)
- 1 dollar a month
- created or imported in kms

## Key Rotation

### AWS Manged key
- automatic every 1 year

### CMK
- must be enabled
- automatic very uear
- if importet only manual rotation with use of alias

## Key Policies
- similar to s3 policies
- controll access to kms
- default = everyone in this account can use the key
- use for cross account

## Multi Region Keys
- keys are replicated with same id into diffrent region
- encrypt and decypt in other keys
- use case to encrypt global services (auroa global, dynamo global tables)