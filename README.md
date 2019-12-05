# azure notes
My notes on how to do stuff in Azure

## New account on a new laptop

Start off with a new conda environment
```
conda create -n azure Python=3.7
conda activate azure
```
Install the azure cli and log on to the azure account
```
## This may take a while
pip install azure-cli
## Opens up a browser window where you put your credentials in
az login 
```

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
```
az vm list --show-details --query "[?powerState=='VM running'].{Name:name}" -o table
```

**List them all with their IP address**
```
az vm list --show-details --query "[?powerState=='VM running'].{Name:name,IP:publicIps}" -o table
```

**Delete a VM**
```
az vm delete -g resource_groupname -n VMName --yes
```
