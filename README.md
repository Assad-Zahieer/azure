# Azure

## What?
* Microsoft's cloud computing platform which provides compute power, storage, and services over the internet using a pay-as-you-go pricing model
* Similar infrastructure to aws (regions, availability zones etc.)
* Uses virtulisation in data centers via:
    * **Hypervisor** - Emulates computer functionality (CPU, storage, RAM etc.) in a VM. Each Azure server has a HV which can run many VMs
    * **Fabric controller** - Creates a VM, one server in each rack has a FC
    * **Orchestrator** - Responsible for all actions in Azure. Packages user requests and passes them to a FC on the best server rack
    
    ![Diagram](https://github.com/Assad-Zahieer/BobsProject/blob/master/Azure-compute-node.jpg)
