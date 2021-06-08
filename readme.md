# Terraform Bundle Binary

For Terraform Enterprise to run in an airgapped environment it needs to be provided with Terraform provider binaries at run time since they can not be fetched over the internet.

There are several ways to accomplish this, but a common solution is to bundle the provider versions with Terraform core binary. This is accomplished with the `terraform-bundle` tool which today is located in the Terraform repo. <https://github.com/hashicorp/terraform/tree/v0.15.5/tools/terraform-bundle>

`terraform-bundle` is being removed from Terraform Core and the will replaced in the future Terraform Provider support inside the Private Module Registry. However until this is released and users are able to upgrade to a supported version of TFE there is still a requirement for this tool.

This repo will use GitHub actions to build `terraform-bundle` for Linux, MacOS, & Windows for the latest patch version of Terraform 0.12 and 0.15 as there are differences in how the providers are structured between these versions.

`terraform-bundle` can be downloaded from the releases section of this repo or via cli, 

```sh
version="0.1.0"
curl -L -o terraform-bundle "https://github.com/hashicorp-services/terraform-bundle-binary/releases/download/${version}/terraform_bundle_linux_amd64_v0.15.5"
chmod +x terraform-bundle
```

## .github

Contains the GitHub Actions which will build the terraform-bundle binaries

## Using Terraform Bundle for Terraform Enterprise

If building a bundle for TFE, the command and arguments to use is `terraform-bundle -os=linux -arch=amd64`
For more detailed usage instructions <https://github.com/hashicorp/terraform/tree/v0.15.5/tools/terraform-bundle#usage>

## Community Support

Support for this tool is provided on a best-effort basis, and it comes with no guarantee or service level agreement. Bugs and feature requests should be entered as GitHub issues. If an existing issue matches your requirements, please add a +1 reaction to bump it up our priority list.
Pull requests are welcome! We encourage you to fork this repository and send back a PR with any improvements.
