![[Pasted image 20221030213328.png]]
# Identity and Access Mangment

## TLDR
AWS IAM is a global service. Its used in nearly all other services to control permissions and interaction boundaries in regards to resources and services in your account. Its also required to manage users in your AWS Account or [[AWSOrganisations]]. Permissions come in the form of groups, role and policies.

### Best Practices
- Dont use your root account for anything but account setup
- One physical users should also be one AWS user
- Assign users to groups and assign permissions to groups
- Use a password policy to prevent weak passwords
- Use and enforce MFA
- Use roles for services
- Use access keys for accessing services 
- Audit permissons with IAM Credential Report
- Never share keys or user 
- Use least privilege principle

## Users
- Real persons
- Can have multiple or no groups
## Groups
- Collection of users
- One group can have multiple users
## Roles
- intended to be used by AWS Services
- can be used to access cross account ressources

## Permission Boundary
- maximum permission employees can grant to other entities
- uses managed policies
- is attached to principal (which is the AWS Account)
- can only be set on users and roles

## Policies
- Handles permissions
- Attached to group, user or role as a json document.
- Should use least privilege principle
- If a user has multiple groups his permissions will be the composition of all policies of all groups
- Deny always overwrites any alow
```json
{
    "Version":"date", //required
    "Id":"string", //optional
    "Statement": [ // atleast 1 required
        {
            "Sid": "", // statement id optional
            "Effect" : "", // Allow | Deny
            "Principal" : "", // which account/user/role this should be applied to (only if used to attach to a ressource)
            "Action": [ // list of actions to deny or allow 
                "s3:putObject"
            ],
            "Ressource":["mybucket/*"], // list of ressource for which the actions are applied to
            "Condition": []//list of conditions for when this policy is applied, optional
        }
    ]
}
```
### IAM Policy Conditions
```json
"Condition": { "NumericLessThanEquals": {"aws:MultiFactorAuthAge": "3600"} }
```
- restrict by client IP
- restrict by target region
- restrict by tag(user and ressouce)
- force mfa
- account org
### Trust Policy
- Defines/Limits which ressource an asume the IAM role

## Password Policy

### Password limitations
- minimum length
- include uppercase
- include lowercase
- include non alphanumeric
- numbers
- no reuse
### Other Features
- deny or allow pw change by user himself
- expiration date 

## MFA

### Virtual MFA Device
- Google Auth
- Authy

### U2F (Universal 2nd Factor Security Key)
- 3rd Party device
- support multiple users for one device

### Hardware Key FOB MFA Device
- 3rd Party

### Hardware Key FOB MFA Device for US Gov Cloud
- 3rd Party

## IAM Security Tools

### IAM Credentials Report
- Report of all  Accounts Users and credential status (pw, accesskeys, mfa etc)

### IAM Access Advisor
- target a single user or ressource and get the info of all service permissions and when that service was lastly accessed
- can be used to revise policies and roles

## Roles vs Ressource Based Policies
- when you assume a role, you give up all previous persmissions
- Ressource based if a Iam entity needs to do multiple things on diffrent accounts

### [[EventBride]]
- when [[EventBride]] runs any task it needs access for the target service
- some service support iam some use ressource based policies

### Cross Account
- attach policy to a resouce ([[S3]])
- use a role as a proxy (give role access)