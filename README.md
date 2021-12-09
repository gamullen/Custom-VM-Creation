# Azure Marketplace VM with uiFormDefinition

[![Deploy To Azure](https://github.com/gamullen/Moore/blob/master/Moore/assets/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fgamullen%2FCustom-VM-Creation%2Fmaster%2Fazuredeploy.json%3F/uiFormDefinitionUri/https%3A%2F%2Fraw.githubusercontent.com%2Fgamullen%2FCustom-VM-Creation%2Fmaster%2FuiFormDefinition.json%3F)

This template allows deploying a Windows VM using an existing resource for the Virtual Network.
The VM has no Public IP Address.

The admin password is retrieved from Azure Key Vault.

A PowerShell script is pulled from a storage account container and executed 
upon VM creation using the CustomScriptExtension.
The storage account access key is securely retrieved from Key Vault.

uiFormDefinition.json is also included.

Before submitting to Marketplace, the following steps will need to be performed

- Rename ```azuredeploy.json``` to ```mainTemplate.json```
- Remove ```azuredeploy.parameters.json``` from the list of files to be submitted
- Update the GUID in ```mainTemplate.json``` for Customer Usage Attribution
  - https://docs.microsoft.com/en-us/azure/marketplace/marketplace-solution-templates
- Create a zip package of all the dependencies including the templates files, scripts, UI definition etc
  - https://docs.microsoft.com/en-us/azure/marketplace/cloud-partner-portal/azure-applications/cpp-skus-tab#package-details-for-solution-template