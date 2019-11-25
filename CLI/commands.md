# Useful CLI commands
**Resource Groups**

* Creating
    * az group create --name <enter-name> --location <location>
    * az account list-locations 
* Set default location
    * az configure --defaults location=uksouth
* Set default resource group
    * az configure --defaults group=<enter-rgroup-name>
* List resource groups
    * All - az group list
    * Detailed - az group show --name <enter-name>
* Deleting
  * az group delete --name <enter-name>
  * options --yes (skips confirmation), --no-wait (terminal doesn't wait)
  
**Virtual Networks**
* Creating: basic
    * az network vnet create --resource-group <rgroup> --name <name>
* Creating: Address prefix
    * Address range for virtual network
    * CIDR notation: default = 10.0.0.0/16
    * --address-prefixes <enter CIDR>
* Creating: subnet
    * --subnet-name <name> --subnet-prefix <enter CIDR>
    * subnet CIDR must be within VNet CIDR e.g. 10.0.0.0/24 is within 10.0.0.0/16
* Deleting az network vnet delete --resource-group <name> --name <VNet name>

**Subnets**
