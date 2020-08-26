# Overview

This is a built-in module to environment [pip-templates-env-master](https://github.com/pip-templates/pip-templates-env-master). 
This module stores scripts for management on-premises couchbase cluster.

# Usage

- Download this repository
- Copy *src*, *lib* and *templates* folder to master template
- Add content of *.ps1.add* files to correspondent files from master template
- Add content of *config/config.db.json.add* to json config file from master template and set the required values

# Config parameters

Config variables description

| Variable | Default value | Description |
|----|----|---|
| env_type | on-premises | Type of environment |
| az_region | eastus | Azure region where resources will be created |
| az_resource_group | piptemplates-stage-east-us | Azure resource group name |
| az_subscription | piptemplates-DI | Azure subscription name |
| onprem_instance_username | piptemplatesadmin | On premises instance username to ssh |
| az_vm_ssh_keygen_enable | false | Switch for creation new ssh keys. If set to *true* - then new ssh keys in home directory will be created, if set to *false* you should set *ssh_private_key_path* and *az_vm_ssh_public_key_path* |
| az_vm_ssh_public_key_path | ./config/id_rsa.pub | Path to id_rsa.pub wich will be used for azure virtual machines |
| ssh_private_key_path | ./config/id_rsa | Path to id_rsa wich will be used for azure virtual machines |
| onprem_couchbase_vm_vnet | piptemplates-vm-vnet | Azure virtual network name for couchbase cluster |
| onprem_couchbase_vm_resources_prefix | piptemplates-vm-cb | Azure resources name prefix for couchbase cluster |
| onprem_couchbase_vm_size | Standard_DS1_v2 | Azure virtual machines size for couchbase cluster |
| onprem_couchbase_vm_count | 2 | Azure virtual machines count for couchbase cluster |
| couchbase_username | piptemplatesadmin | Azure virtual machines username for couchbase cluster |
| couchbase_password | piptemplatesadmin2019# | Azure virtual machines password for couchbase cluster |
| onprem_couchbase_ram | 512 | Couchbase cluster ram size |
| onprem_couchbase_bucket_name | default | Couchbase bucket name |
| onprem_couchbase_bucket_ram | 256 | Couchbase bucket ram size |
| onprem_couchbase_bucket_replicas | 1 | Couchbase bucket replicas |
