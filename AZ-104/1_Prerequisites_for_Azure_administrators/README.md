[Study guide](https://learn.microsoft.com/en-us/certifications/exams/az-104#two-ways-to-prepare)

## Azure Cloud Shell
- Azure Cloud Shell is an interactive, browser-accessible shell for managing Azure resources.
- Runs on a temporary host provided on a per-session, per-user basis.
- Requires a resource group, storage account, and Azure File share.
- Persists $HOME using a 5-GB image held in your file share.

## Azure CLI
Azure CLI lets you control nearly every aspect of every Azure resource. You can work with resource groups, storage, VMs, Azure Active Directory (Azure AD), containers, machine learning, and so on.

## Create resource groups
Resource Groups are at their simplest a logical collection of resources. There are a few rules for resource groups.
- Resources can only exist in one resource group.
- Resource Groups cannot be renamed.
- Resource Groups can have resources of many different types (services).
- Resource Groups can have resources from many different regions.

## Use tagging to organize resources
- A resource can have up to 50 tags. 
- The name value is limited to 512 characters for all types of resources except storage accounts, which have a limit of 128 characters. 
- The tag value is limited to 256 characters for all types of resources. 
- Tags aren't inherited from parent resources. 
- Not all resource types support tags, and you can't apply tags to classic resources.
- You can use Azure Policy to automatically add or enforce tags for resources your organization creates based on policy conditions that you define. For example, you could require that a value for the Department tag is entered when someone in your organization creates a virtual network in a specific resource group.

## Role-based access control
RBAC provides fine-grained access management for Azure resources, enabling you to grant users the specific rights they need to perform their jobs. RBAC is considered a core service and is included with all subscription levels at no cost.

## Azure Resource Manager
- Azure Resource Manager templates are written in JSON, which allows you to express data stored as an object (such as a virtual machine) in text. 
- A JSON document is essentially a collection of key-value pairs.
