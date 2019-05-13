# Overview
Scriptable databases introduce “infrastructure as a code” into devops practices. Couchbase installed on separate instances, couchbase sync gateway deployed as platform service to kubernetes cluster. Also created install azure virtual machines script to simulate existing instances.

# Syntax
All sripts have one required paramenter - *$ConfigPath*. This is the path to config, path can be absolute or relative. 

**Examples of installing on-premises couchbase cluster**
Relative path example (you should be in *piptemplates-devops-envmgmt* folder):
`
./on-premises/install_couchbase.ps1 ./config/onprem_config.json
`
Absolute path example:
`
~/pip-templates-db-onpremises/on-premises/install_couchbase.ps1 ~/pip-templates-db-onpremises/config/onprem_config.json
`

**Example delete script**
`
./on-premises/destroy_couchbase.ps1 ./config/onprem_config.json
`

Also you can install environment using single script:
`
./create_env.ps1 ./config/onprem_config.json
`

Delete whole environment:
`
./delete_env.ps1 ./config/onprem_config.json
`

If you have any problem with not installed tools - use `install_prereq_` script for you type of operation system.

# Project structure
| Folder | Description |
|----|----|
| Config | Config files for scripts. Store *example* configs for each environment, recomendation is not change this files with actual values, set actual values in duplicate config files without *example* in name. Also stores *resources* files, created automaticaly. | 
| Lib | Scripts with support functions like working with configs, templates etc. |  
| On-premises | Scripts related to management on premises couchbase cluster | 
| Templates | Folder for storing templates, such as couchbase yml files, ansible playbooks, etc. | 


### On premises couchbase

* On premises couchbase config parameters

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
