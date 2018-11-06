# Liatrio AWS Terraform

This repository contains the Terraform configurations needed to manage a multi-account AWS organization and the various roles that will be used within the accounts.

At Liatrio, we used this as the foundation for our accounts. We created a private fork that contains the actual users and resources used in our accounts. Be sure to modify `shared.tfvars` to customize for your organization.

## Prerequisites

- [Terraform](https://www.terraform.io/)
- [Terragrunt](https://github.com/gruntwork-io/terragrunt)
- [Keybase](https://keybase.io) account (only required during initialization to get a secret key for the initial admin user)

## Initialization

See the [init](init) folder for initial setup instructions the first time the organization is being created.

## Post-Initialization

Future Terraform runs must be run by an IAM user in the Infosec account with the appropriate group assignment for the target account:

- Infosec account: `InfosecAdmins` group
- Prod account: `ProdAdmins` group
- Non-Prod account: `NonProdAdmins` group