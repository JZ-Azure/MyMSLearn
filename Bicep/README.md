## az bicep command group
[CLI references](https://learn.microsoft.com/en-us/cli/azure/bicep?view=azure-cli-latest)

|Command|Action|
|:---|:---|
|az bicep build | Build a Bicep file.|
|az bicep decompile | Attempt to decompile an ARM template file to a Bicep file.|
|az bicep generate-params | Generate parameters file for a Bicep file.|
|az bicep install | Install Bicep CLI.|
|az bicep list-versions | List out all available versions of Bicep CLI.|
|az bicep publish | Publish a bicep file to a remote module registry.|
|az bicep restore | Restore external modules for a bicep file.|
|az bicep uninstall | Uninstall Bicep CLI.|
|az bicep upgrade | Upgrade Bicep CLI to the latest version.|
|az bicep version | Show the installed version of Bicep CLI.|

## Install bicep and sign in to Azure
```bash
az bicep install && az bicep upgrade
az login
az account set --subscription YOUR_SUB_NAME
```

## Deploy a Bicep template to Azure
```bash
az deployment group create --template-file FILE_NAME.bicep
```
