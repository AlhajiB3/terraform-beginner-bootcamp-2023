# Terraform Beginner Bootcamp 2023

## Semantic Versioning :mage:

The project is going to ultilize semantic versioning its tagging. 
[semver.org](https://semver.org/) 

The general format:

**MAJOR.MINOR.PATCH**, eg. `1.0.1`

- **MAJOR** version when you make incompatible API changes
- **MINOR** version when you add functionality in a backward compatible manner
- **PATCH** version when you make backward compatible bug fixes

## Install the Terraform CLI

The terraform CLI installation instructions have changed due to gg keyring changes. So the orginial gitpod.yml So we needed to refer to the latest install CLI instructions via Terraform Documentation and change the scripting for install.

[Install Terraform CLI] (https://developer.hashicorp.com/terraform/downloads)



## Considerations for Linux Distribution 

This Project is built against Ubuntu

## Refactoring into Bash Scripts 

While fixing the Terraform CLI gpg depreciation issues we notice that bash scripts steps were a considerable amount more code.  So we decided to create a bash script to install the Terraform CLI

Example of running os:

cat /etc/os-release

PRETTY_NAME="Ubuntu 22.04.3 LTS"
NAME="Ubuntu"
VERSION_ID="22.04"
VERSION="22.04.3 LTS (Jammy Jellyfish)"
VERSION_CODENAME=jammy
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=jammy


This bash script is located here: [./bin/install-terraform](./bin/install-terraform)

- The will keep the Gitpod Task File ([.gitpod.yml](.gitpod.yml)) tidy.
- Ths allow us an easier to debug and execute manually Terraform CLI install
- This will allow better portability for other projects that need to install Terraform CLI.

## Shebang

A shebang (Pronounced Sha-bang) tells the bash script what program that will interpet the script. eg. #!/bin/bash

Chapt GPT recommended this format for bash: #!/usr/bin/env bash

- for portability for different OS distributions
- will search the user's PATH for the bash executable

When executing the bash script we can use the `./` shortahnd to execute the bash script.

https://en.wikipedia.org/wiki/Shebang_(Unix)


## Execeutable Consirations 

When executing the bash `./` shortahnd notiation 

````sh
chmod u+x ./bin/install-terraform-cli

akternatively:

```sh
chmod u+x ./bin/install-terraform-cli

#### Linux Permissions Considerations

In order to make our bash scripts we need to change linux permission for the fix t be exectuable at the user mode.


## Github Lifecycle (Before, Init, Command)

We need to be careful when using the Init because it will not rerun if we restart an exisitng workspace

https://www.gitpod.io/docs/configure/workspaces/tasks