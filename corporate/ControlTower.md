# AWS Control Towert
- multi account AWS Env setup
- uses AWS Organisations
## Benefits
- automate setup of orgas
- automate policy managed using guard rails
- detect policy viloations
- monitor compliance through dashboard

## Guardrails

### Preventive Guardrail
- uses SCPs
- e.g. restrict regions across all accounts
### Detective Guiardrail
- uses AWS Config
- e.g. identify untagged ressources

## Integration
- SNS