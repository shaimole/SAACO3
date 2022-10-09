# IAM (Identity and Access Mangment)

## General 
- Global Service

## Users
- Actual Persons
- Can have multiple or no Groups
## Groups
- Collection of Users
- One Group can have multiple Users
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