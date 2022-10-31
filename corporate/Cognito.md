![[Pasted image 20221031091542.png]]
# Amazon Cognito

## TLDR
Cognito is a Server which grants and manager access to your applications running in AWS. This is archived by granting an authenticated user temporary [[IAM]] credentials.

## Sub Services

## User Pools
- Is a User directory
- You can use AWS build in user managment or use external (google, twitter facebook)
- You can use the SDK to access directory profile
- Easy sign up and sign in
- Comes with a customizable web UI
- Can use any SAML 2.0 identity providers
- MFA support
- Comes with a credentials check option (have ive been pwnd?)
- Comes with account takeover protection
- Phone or email verification
- Can define custom workflows
- Supports user migration
- Can also run [[Lambda]] triggers

## Identity Pools
- Maps an identify or a group to aws credentials
- Provied aws credentials to grant access to aws ressources
- Use user pool to authenticate, then use identify pools for granular access rights
