# IAM (Identity and Access Mangment)

## General 
- Global Service
### Best Practices
- Dont use Root account for other things than account setup
- One physical user = one AWS User
- Assign users to groups and assign permissions to groups
- Use PW Policy
- Use and enforce MFA
- Use Roles for services
- Use Access Keys for accessing services 
- Audit permissons with IAM Cred Report 
- Never share keys or user

## Users
- Actual Persons
- Can have multiple or no Groups
## Groups
- Collection of Users
- One Group can have multiple Users
## Roles
- intended to be used by AWS Services
- can be used to access cross account ressources

## Policies
- Handles Permissions
- Attached to group as json doc.
- Should use least privilege principle
- If a user has multiple groups, his permissions will be the composition of all group policies
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

###  Password Policy
- minimum length
- include uppercase
- include lowercase
- include non alphanumeric
- numbers
- deny or allow pw change by user himself
- expiration date
- prevent reuse

### MFA

#### Virtual MFA Device
- Google Auth
- Authy

#### U2F (Universal 2nd Factor Security Key)
- 3rd Party device
- support multiple users for one device

#### Hardware Key FOB MFA Device
- 3rd Party

#### Hardware Key FOB MFA Device for US Gov Cloud
- 3rd Party

### IAM Security Tools

#### IAM Credentials Report
- Report of all  Accounts Users and credential status (pw, accesskeys, mfa etc)

#### IAM Access Advisor
- for a single user or ressource get the info of all service permissions and when that service was lastly accessed
- can be used to revise policies and roles
