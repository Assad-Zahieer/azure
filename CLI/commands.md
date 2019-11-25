# Useful CLI commands
**Resource Groups**
* Every Azure resource needs to be associated with a resource group - VNets, VMs etc.
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
* Your own isolated azure network which you can add resources to (similar to aws VPC)
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
* Creating
      * az network vnet subnet create --resource-group <r-grp> --name <name> --address-prefixes <CIDR>
* Deleting
      * az network vnet subnet delete --resource-group <r-grp> --vnet-name <vnet> --name <name>

**NSGs**
* Firewalls which Can be applied to network interfaces or subnets
* Creating
      * az network nsg create --resource-group <r-grp> --name <name>
* Deleting
      * az network nsg delete --resource-group <r-grp> --name <name>
* Rules
   * Allow traffic (port, priority), if no rule - traffic denied by default
   * default port = 80
   * priority 100 - 4096, 100 is highest
   * az network nsg rule create --resource-group <r-grp> --name <name> --priority <number> --nsg-name <nsg> --destination-port-ranges <number>
   
**Public IP Addresses**
* Creating
   * az network public-ip create --resourse-group <r-grp> --name <name>
* Create with DNS name
   * --dns-name <unique-dns-name>
* Make static
   * --allocation-method Static
* Deleting
   * az netwrok public-ip dlete --resource-group <r-grp> --name <name>
   
**Network Interface**
* Like ethernet port or wireless adapter for VMs
* Allow VM to communicate over networks (including internet)
* Creating
   * Required parameters - Resource group, VNet and subnet
   * az network nic create --resource-group <r-grp> --name <name> --vnet-name <vnet> --subnet <subnet>
* Creating with NSG
   * --network-security-group <NSG>
* Creating with public IP
   * --public-ip-address <name>
* Deleting
   * az network nic delete --resource-group <r-grp> --name <name>
   
**VMs**
* Creating   
   * az vm create --resource-group <r-grp> --name <name> --image <OS image>
   * az vm image list -o table
* Creating with network interface
   * All nsg rules applied to network interface will be applied to the VM
   * --nics <network-interface>
* Deleting
   * az vm delete --resource-group <r-grp> --name <name>
