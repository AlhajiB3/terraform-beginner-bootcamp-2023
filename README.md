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



## Refactoring into Bash Scripts 

While fixing the Terraform CLI gpg depreciation issues we notice that bash scripts steps were a considerable amount more code.  So we decided to create a bash script to install the Terraform CLI


This bash script is located here: [./bin/install-terraform](./bin/install-terraform)

- The will keep the Gitpod Task File ([.gitpod.yml](.gitpod.yml)) tidy.
- Ths allow us an easier to debug and execute manually Terraform CLI install
- This will allow better portability for other projects that need to install Terraform CLI.

## Shebang

A shebang (Pronounced Sha-bang) tells the bash script what program that will interpet the script. eg. #!/bin/bash

Chapt GPT recommended this format for bash: #!/usr/bin/env bash

- for portability for different OS distributions
- will search the user's PATH for the bash eexcutable

When executing the bash script we can use the `./` shortahnd to execute the bash script.

https://en.wikipedia.org/wiki/Shebang_(Unix)


## Linux Permissions Considerations

