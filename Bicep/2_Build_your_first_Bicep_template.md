## What is Bicep? 
Bicep is a language for declaratively deploying Azure resources.

### How is Bicep related to ARM templates?
When you submit a Bicep template to Resource Manager, the Bicep tooling converts your template to a JSON format in a process called *transpilation*.

## Define resources
Example: creates a storage account named *toylaunchstorage*
```bash
resource storageAccount 'Microsoft.Storage/storageAccounts@2022-05-01' = {
  name: 'toylaunchstorage'
  location: 'westus3'
  sku: {
    name: 'Standard_LRS'
  }
  kind: 'StorageV2'
  properties: {
    accessTier: 'Hot'
  }
}
```
>Note: Every storage account needs a globally unique name, and `toylaunchstorage` needs to be changed.

### Dependencies
Example: Declare an app service that depends on an App Servier Plan
```bash
resource appServicePlan 'Microsoft.Web/serverFarms@2022-03-01' = {
  name: 'toy-product-launch-plan'
  location: 'westus3'
  sku: {
    name: 'F1'
  }
}

resource appServiceApp 'Microsoft.Web/sites@2022-03-01' = {
  name: 'toy-product-launch-1'
  location: 'westus3'
  properties: {
    serverFarmId: appServicePlan.id
    httpsOnly: true
  }
}
```

