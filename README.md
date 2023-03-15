# Nutanix-Inventory-with-Nutanix-ansible-collection
## Nutanix Inventory 
This series of Ansible playbooks perform an inventory of resources managed by Nutanix Prism including:
   * Cluster
   * Cluster nodes
   * Subnets
   * VMs 
   * VM's disks
   * VM's NIC
   


Ansible playbooks will generate CSV files as output from the inventory 


## Configuration
Use the nutanix Ansible github(https://github.com/nutanix/nutanix.ansible) to download the collection and configure the environment 

## Environment Variables
 - export ANSIBLE_LIBRARY=/location-where-ansible-collections-are-installed/nutanix/ncp/plugins/modules/
 - export ANSIBLE_MODULE_UTILS=/location-where-ansible-collections-are-installed/nutanix/ncp/plugins/module_utils

## Workflow
The flow for playbooks is as follow:
* nutanix-inventory.yml    |---> cluster-sub-inventory.yml 

                           |---> subnet-sub-inventory.yml

                           |---> node-sub-inventory.yml

                           |---> vm-sub-inventory.yml

* vm-sub-inventory.yml

   |---> vm-disk-sub-inventory.yml

   |---> vm-nic-sub-inventory.yml



## To run playbook
Edit the nutanix-inventory.yml to specify address and credentials for connection to prism

````
ansible-playbook nutanix-inventory.yml  
````

Enjoy!



