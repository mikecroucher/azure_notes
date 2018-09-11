# azure notes
My notes on how to do stuff in Azure

**Install the az CLI client on the WSL**

https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-apt?view=azure-cli-latest

**Install PowerShell cmdlets**

https://docs.microsoft.com/en-us/powershell/azure/install-azurerm-ps?view=azurermps-6.8.1

**Install cloud-init on Ubuntu**
```
sudo apt-get install cloud-init
```

**Sign in to Azure from a PowerShell Session**
```
# Import the module into the PowerShell session
Import-Module AzureRM
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

**List locations**
```
az account list-locations
```

**Create a resource group**
```
az group create --name myResourceGroupSecureWeb2 --location westus2
```

**List all running VMs**
az vm list --show-details --query "[?powerState=='VM running'].{Name:name}" -o table
