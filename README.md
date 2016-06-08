## Ansible Script for setup machines initally for DCOS installation

This script will set up a cluster with 6 machines:

1 bootstrap node 
- 192.168.199.10

5 compute nodes (1 master + 4 slave) 
- 192.168.199.11
- 192.168.199.12
- 192.168.199.13
- 192.168.199.14

## How to run this script

1) edit the inventory and provide the correct user, password and sudo password. 
[I assumed all hosts with the same login and password]

2) edit the playbook.yml and provide related information
[in nodes and boostrap sections]
- dockerRpmLocalSrcPath: <file_path_to>/docker-engine-1.9.1-1.el7.centos.x86_64.rpm
- dockerRpmRemoteDestPath: <remotefile_path_to>/docker-engine-1.9.1-1.el7.centos.x86_64.rpm
[in bootstrap section]
- userpw: <remote_user_password>
- sshKeyPath: <path_to>/.ssh/id_rsa.pub

3) Command: ansible-playbook playbook.yml