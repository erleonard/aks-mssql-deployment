<img src="logo.jpg" width="64" />

# :walking: Getting Started

- An Azure Subscription
    - You must have sufficient permissions to deploy resources
- Visual Studio Code **OR** the Azure Cloud Shell

## Install the Azure CLI
The Azure CLI team maintains a script to run all installation commands in one step. This script is downloaded via curl and piped directly to bash to install the CLI.

*If you wish to inspect the contents of the script yourself before executing, simply download the script first using curl and inspect it in your favorite text editor.*

```console
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
```
[Reference](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux?pivots=apt#option-1-install-with-one-command)

## Next Step
:arrow_forward: [aks-deployment](./aks-deployment.md)