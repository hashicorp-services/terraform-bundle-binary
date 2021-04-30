# Terraform Bundler

For Terraform Enterprise to run in an airgapped environment it needs to be provided with Terraform provider binaries at run time since they can not be fetched over the internet.

There are several ways to accomplish this, but a common solution is to bundle the provider versions with Terraform core binary.

## .github

Contains the GitHub Action which will compile the terraform-bundle binaries
