## What is infrastructure as code?
### Infrastructure as code can help you better understand the state of your cloud resources:

- Audit trail: This audit trail means that you can review the details of each change, who made the change, and when the change was made.
- Documentation
- Unified system: When you use a common system, your organization can better understand the relationship between your applications and your infrastructure.
- Better understanding of cloud infrastructure: When you use the Azure portal to provision resources, many of the processes are abstracted from view. When you deploy the same virtual machine by using infrastructure as code, you have complete control over all resources that are created.

### Imperative and declarative code
- imperative: you execute a sequence of commands, in a specific order, to reach an end configuration.
	- Bash
	- Azure PowerShell
- declarative: you specify only the end configuration.
	- JSON
	- Bicep
	- Ansible, bu RedHat
	- Terraform, by HashiCorp

## What is Azure Resource Manager?

There are two types of ARM template files: JSON and Bicep.
- JavaScript Object Notation (JSON) is an open-standard file format that multiple languages can use.
- Bicep is a new domain-specific language that was recently developed for authoring ARM templates by using an easier syntax.

### Operations: Control plane and data plane
- control plane operations: Use the control plane to manage the resources in your subscription.
- data plane operations: Use the data plane to access features that are exposed by a resource.
- For example: you use a control plane operation to create a virtual machine, but you use a data plane operation to connect to the virtual machine by using Remote Desktop Protocol (RDP).

## What is Bicep?
Example
```bash
param location string = resourceGroup().location
param namePrefix string = 'storage'

var storageAccountName = '${namePrefix}${uniqueString(resourceGroup().id)}'
var storageAccountSku = 'Standard_RAGRS'

resource storageAccount 'Microsoft.Storage/storageAccounts@2022-05-01' = {
  name: storageAccountName
  location: location
  kind: 'StorageV2'
  sku: {
    name: storageAccountSku
  }
  properties: {
    accessTier: 'Hot'
    supportsHttpsTrafficOnly: true
  }
}

output storageAccountId string = storageAccount.id
```

## How Bicep works
### Bicep deployment
When you deploy a resource or series of resources to Azure, you submit the Bicep template to Resource Manager, which *still requires JSON templates*. The tooling that's built into Bicep converts your Bicep template into a JSON template. This process is known as *transpilation*, which essentially treats the ARM template as an intermediate language.

Example:
```bash
az deployment group create \
  --template-file main.bicep \
  --resource-group storage-resource-group
```
You can view the JSON template that's submitted to Resource Manager by using the `bicep build` command.
```bash
bicep build main.bicep
```

## When to use Bicep
- For Azure deployments, Bicep has some advantages, but Bicep doesn't work as a language for other cloud providers.
- Easy transition from JSON: You can use the Bicep CLI to decompile any ARM JSON template into a Bicep template by using the `bicep decompile` command.

## Summary
Imagine how much time it would take to deploy new environments manually by using only the Azure portal. You must deploy each resource one by one, making sure to keep configurations identical. When you want to add a new resource or change an existing resource, you must manually create the resource for each environment. Infrastructure as code can help you define your resources in a single place and then apply the same configuration to all your environments.





















