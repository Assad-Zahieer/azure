# Azure

## What?
* Microsoft's cloud computing platform which provides compute power, storage, and services over the internet using a pay-as-you-go pricing model
* Similar infrastructure to aws (regions, availability zones etc.)
* Uses virtulisation in data centers via:
    * **Hypervisor** - Emulates computer functionality (CPU, storage, RAM etc.) in a VM. Each Azure server has a HV which can run many VMs
    * **Fabric controller** - Creates a VM, one server in each rack has a FC
    * **Orchestrator** - Responsible for all actions in Azure. Packages user requests and passes them to a FC on the best server rack
    
    ![Diagram](https://github.com/Assad-Zahieer/BobsProject/blob/master/Azure-compute-node.jpg)

## Azure Services
8 main categories
   1. Compute services
   2. Cloud storage
   3. Networking
   4. Databases
   5. AI & big data
   6. Internet of things
   7. Web
   8. Security
### 1. Compute Services
* Azure provides a range of options for hosting services and applications, calculations etc. such as:
      * Azure virtual machines
      * Azure container instances
      * Azure functions (serverless)
      * Azure kubernetes service 
      * Azure batch    
### 2. Cloud Storage
1. Azure **blob** storage - for very large objects
2. Azure **file** storage - file sharing
3. Azure **queue** storage - data store for queueing and delivering messages between apps
4. Azure **table** storage - NoSQL store
* All the above are elastically scalable
5. Azure **disk** storage - disks attatched to VMs
### 3. Networking
* link compute resources and managing access of apps and services
#### 3.1 Azure virtual network (VNet)
* Isolated netowrk on azure (similar to AWS vpc)
* Segment into subnets for security and organisation
* **VPN Gateway** provides secure connection between on-premise location and Azure VNet 
      * e.g. Data stored on-premise but app hosted on Azure
#### 3.2 Network security group (NSG)
* NSG manages network traffic to Azure resources (allow/deny)
      * cloud level firewall
#### 3.3 Azure load balancer
* Load balancer is used to manage traffic
* Azure load balancer manages traffic for you
      * no need to maintain VM load balancers
      * high availability
#### 3.4 Azure traffic manager
* Reduces latency by routing users to closest endpoint
* **latency** - time for data to travel over a network
* **bandwidth** - max. data amount on a connection
### 4. Databases
* Azure SQL database
* Azure Cosmos db
### 5. AI & big Data
* Machine learning - Cloud AI service (not azure specific)
   * Analyse data to forecast future bahaviours
* Big data - large volumes of data (e.g stock exchange, jet engines etc)
* Services offered:
      * Azure machine learning service
      * Azure SQL data warehouse
### 6. Internet of things
* Dashboard to control IoT assets (sensors, devices etc.)
### 7. Web
* Azure app service
* Azure search
* Azure API management
### 8. Security
* Identity management - who has access to what
      * RBAC - Role Based Access Control
* Azure active directory
* Azure security center
* Azure key-vault
