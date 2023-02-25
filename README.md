# terraform-with-azure

## Overview

In this mini project, I deploy a development environment to Microsoft Azure using Terraform. This includes a resource group, network interface and a Linux virtual machine (VM) with Docker installed. One can ssh into the development environment's VM using information dynamically entered into the ssh `config` file (depending on the OS system, which has valid options of `mac` and `windows`).

This Resume Foundations project was designed by Derek Morgan at More than Certified and is accessible at [More than Certified](https://courses.morethancertified.com/p/rfp-terraform-azure). It is free to enroll in, as of February 25th, 2023.

I've made a single addition to the course by adding [Terraform pre-commit git hooks](https://github.com/antonbabenko/pre-commit-terraform) to my repo. The instructions to set this up are detailed in the section below.

## Set up the `pre-commit` hooks.

The following instructions are valid for MacOS.

Firstly, install the dependencies:
```
brew install pre-commit terraform-docs tflint tfsec checkov terrascan infracost tfupdate minamijoyo/hcledit/hcledit jq
```

Initialize `pre-commit`:
```
DIR=~/.git-template
git config --global init.templateDir ${DIR}
pre-commit init-templatedir -t pre-commit ${DIR}
```

To run on all files, use the following command:
```
pre-commit run -a
```

# terraform.tfvars

In order for this project to run correctly, you will need to add a `terraform.tfvars` file to your project. The file itself requires a variable called `host_os`, which has valid options of `mac` or `windows`.
