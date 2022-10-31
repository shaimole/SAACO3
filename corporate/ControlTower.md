![[Pasted image 20221031092405.png]]
# AWS Control Tower

## TLDR
Control Tower is often used in conjunction with [[AWSOrganisations]]
to manage and configure a multi account setup.

## Benefits
- Automate setup of [[AWSOrganisations]]
- Automate policy management using guard rails
- Detect policy viloations
- Monitor compliance through dashboard
- Streamline account creation in [[AWSOrganisations]]

## Guardrails

### Preventive Guardrail
- uses [[AWSOrganisations]] SCP
- e.g. restrict regions across all accounts

### Detective Guiardrail
- uses [[AWSConfig]]
- e.g. identify untagged ressources

## Further Integration
- [[SNS]]