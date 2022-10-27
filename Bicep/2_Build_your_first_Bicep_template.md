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

## Parameters and variables
- Paramneter: lets you bring in values from outside the template file
  - Types of parameters: `string`. `int`, `bool`, `array`, `object`
- Variable: defined and set within the template
- Expression: a powerful feature that helps you to discover values when the template runs

### Declare a parameter with a default value
```bash
param appServiceAppName string = 'toy-product-launch-1'

resource appServiceApp 'Microsoft.Web/sites@2022-03-01' = {
  name: appServiceAppName
  location: 'westus3'
  properties: {
    serverFarmId: appServicePlan.id
    httpsOnly: true
  }
}
```

### Declare a variable
```bash
var appServicePlanName = 'toy-product-launch-plan'
```

### Declare a parameter using an expression
```bash
param location string = resourceGroup().location

resource appServiceApp 'Microsoft.Web/sites@2022-03-01' = {
  name: appServiceAppName
  location: location
  properties: {
    serverFarmId: appServicePlan.id
    httpsOnly: true
  }
}
```
> Note: Some resources in Azure can be deployed only into certain locations. You might need separate parameters to set the locations of these resources.


### Create a unique resource name using function `uniqueString()`
```
param storageAccountName string = uniqueString(resourceGroup().id)
param storageAccountName string = 'toylaunch${uniqueString(resourceGroup().id)}'
```
> Note: `uniqueString()` returns the *same value* for the *same seed*.

### Condition using `?`
```
@allowed([
  'nonprod'
  'prod'
])
param environmentType string

var storageAccountSkuName = (environmentType == 'prod') ? 'Standard_GRS' : 'Standard_LRS'
var appServicePlanSkuName = (environmentType == 'prod') ? 'P2V3' : 'F1'
```
> Note: Syntax for `?` is `condition ? if true: if false`

Deploy an Bicep template with a condition parameter
```bash
az deployment group create \
  --template-file main.bicep \
  --parameters environmentType=nonprod
```

## Group resources with Modules
Modules are also a way to make Bicep code even more reusable. You can have a single Bicep module that lots of Bicep templates use. Any Bicep template can be used as a module by another template.

### Outputs
Declare an output
```bash
output appServiceAppName string = appServiceAppName
```
Example: output value set to the fully qualified domain name (FQDN) of a public IP address resource
```bash
output ipFqdn string = publicIPAddress.properties.dnsSettings.fqdn
```

### Define a module
```bash
module myModule 'modules/mymodule.bicep' = {
  name: 'MyModule'
  params: {
    location: location
  }
}
```

### Module example
main.bicep
```bash
param location string = 'westus3'
param storageAccountName string = 'toylaunch${uniqueString(resourceGroup().id)}'
param appServiceAppName string = 'toylaunch${uniqueString(resourceGroup().id)}'

@allowed([
  'nonprod'
  'prod'
])
param environmentType string

var storageAccountSkuName = (environmentType == 'prod') ? 'Standard_GRS' : 'Standard_LRS'

resource storageAccount 'Microsoft.Storage/storageAccounts@2022-05-01' = {
  name: storageAccountName
  location: location
  sku: {
    name: storageAccountSkuName
  }
  kind: 'StorageV2'
  properties: {
    accessTier: 'Hot'
  }
}

module appService 'modules/appService.bicep' = {
  name: 'appService'
  params: {
    location: location
    appServiceAppName: appServiceAppName
    environmentType: environmentType
  }
}

output appServiceAppHostName string = appService.outputs.appServiceAppHostName
```
appService.bicep
```bash
param location string
param appServiceAppName string

@allowed([
  'nonprod'
  'prod'
])
param environmentType string

var appServicePlanName = 'toy-product-launch-plan'
var appServicePlanSkuName = (environmentType == 'prod') ? 'P2v3' : 'F1'

resource appServicePlan 'Microsoft.Web/serverFarms@2022-03-01' = {
  name: appServicePlanName
  location: location
  sku: {
    name: appServicePlanSkuName
  }
}

resource appServiceApp 'Microsoft.Web/sites@2022-03-01' = {
  name: appServiceAppName
  location: location
  properties: {
    serverFarmId: appServicePlan.id
    httpsOnly: true
  }
}

output appServiceAppHostName string = appServiceApp.properties.defaultHostName
```
Deploy command
```bash
az deployment group create \
  --template-file main.bicep \
  --parameters environmentType=nonprod
```











