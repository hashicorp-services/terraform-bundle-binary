# Terraform Bundle Binary

For Terraform Enterprise to run in an airgapped environment it needs to be provided with Terraform provider binaries at run time since they can not be fetched over the internet.

There are several ways to accomplish this, but a common solution is to bundle the provider versions with Terraform core binary. This is accomplished with the `terraform-bundle` tool which today is located in the Terraform repo. <https://github.com/hashicorp/terraform/tree/v0.15.1/tools/terraform-bundle>

`terraform-bundle` is being removed from Terraform Core and the will replaced in the future Terraform Provider support inside the Private Module Registry. However until this is released and users are able to upgrade to a supported version of TFE there is still a requirement for this tool.

This repo will use GitHub actions to build `terraform-bundle` for Linux, MacOS, & Windows for the latest patch version of Terraform 0.12 and 0.15 as there are differences in how the providers are structured between these versions.

## .github

Contains the GitHub Action which will build the terraform-bundle binaries

## Using Terraform Bundle for Terraform Enterprise

If building a bundle for TFE, the command and arguments to use is `terraform-bundle -os=linux -arch=amd64`
For more detailed usage instructions <https://github.com/hashicorp/terraform/tree/v0.15.1/tools/terraform-bundle#usage>
