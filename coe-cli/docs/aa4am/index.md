# ALM Accelerator for Advanced Makers

The [ALM Accelerator for Advanced Makers](https://github.com/microsoft/coe-starter-kit/tree/main/ALMAcceleratorForAdvancedMakers) (AA4AM) command allows you to manage common tasks for Advanced Makers. 

Not sure what AA4AM is and how it can help? The main GitHub project [README](https://github.com/microsoft/coe-starter-kit/blob/main/ALMAcceleratorForAdvancedMakers/README.md) provides further context and examples of usage.

The diagram below provides an overview of the key components required and permissions required.

![ALM Accelerator for Advanced Makers Overview](../../images/aa4am-overview.jpg)

## Sample Install

The following recording shows a sample generating a install configuration file and installing AA4AM using the config file using a [Demo Deployment](./scenarios.md#demonstration-deployment).

![Example](./install.svg)

## Install Overview

1. Review the [Before You Start](./before-you-start.md) to ensure you have the required Power Platform environments and Azure DevOps organizations created

2. As an administrator complete the [Admin Install](./admin-install.md)

3. Have Advanced Makers create [Development Environments](./development-environments.md)

4. Use [Maker Setup](./maker-setup.md) to create and setup environment and solution branches in the Azure DevOps repository.

## Maker First Solution

Once the environment has been setup and your development environment created and registered as a service connection in Azure DevOps you can use the following steps to create your first source control managed solution.

1. Switch to Developer Environment
1. Create new solution e.g. NewSolution1
1. Add items to the solution. For example
   a. Select Solution
   b. Add Canvas Application
   c. Add Button
   d. Save Application and Close
1. Create Solution branch using the following CLI command

```bash
coe aa4am branch -o https://dev.azure.com/dev12345 -p alm-sandbox -d MySolution1
```

1. Open ALM Accelerator for Advanced Maker Application
1. Select Push change to Git
   a. Create New Branch e.g. MySolution1-WIP
   b. From existing Solution Branch created above e.g. MySolution1
   c. Add a comment e.g. Initial version
1. Click on Latest Push Status 
   a. Permit permissions for pipeline to run (Variable Group, Service Connection, Pipeline)

Notes:
1. If this is your first build pipeline you will need to set Pipeline Variables for your environment. At a minimum you will need to set **ServiceConnection** variable to your environment you have setup for validation, test and production.

## Read Next

- [Command Reference](./command-reference.md)
- [ALM Accelerator for Advanced Makers](https://github.com/microsoft/coe-starter-kit/tree/main/ALMAcceleratorForAdvancedMakers) - Overview for AA4AM
- [Scenarios](./scenarios.md) - Discusses different install scenarios for AA4AM from Demo Installs to Enterprise Deployments
- Manual Setup - Understand the key steps that the CLI is automating
  - [Foundational Setup](https://github.com/microsoft/coe-starter-kit/blob/main/ALMAcceleratorForAdvancedMakers/SETUPGUIDE.md#foundational-setup) - Foundational Setup for Manual steps automated by the CLI install command
  - [Development Project Setup](https://github.com/microsoft/coe-starter-kit/blob/main/ALMAcceleratorForAdvancedMakers/SETUPGUIDE.md#development-project-setup) - Documents the Manual steps that are automated by the CLI install command
  - [Solution Setup](https://github.com/microsoft/coe-starter-kit/blob/main/ALMAcceleratorForAdvancedMakers/SETUPGUIDE.md#solution-setup) - Documents the manual steps to setup Azure DevOps that are by the CLI install command
  - [Importing Solution](https://github.com/microsoft/coe-starter-kit/blob/main/ALMAcceleratorForAdvancedMakers/SETUPGUIDE.md#importing-the-solution-and-configuring-the-app) - Documents the manual steps to import the managed solution that are by the CLI install command