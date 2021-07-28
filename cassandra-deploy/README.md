Role Name
=========

- Role Name- cassandra-deploy
- Deploy scripts to cassandra nodes (azure).
- Configure cassandra on the nodes which were created with 'cassandra' roles.
- Mount the data disk to azure vms (nodes) using shell script located at 'templates/cass_diskmount.sh.j2' 

Requirements
------------
- ansible 2.9.5
- Python 2.7.17
- Azure CLI (Login to interact with azure from host)
- Make sure the ssk keys have correct permission to excute the scripts '$chmod 600 -R secrets/ssh-keys/'

Role Variables
--------------

- Use host group to execute the scripts and roles in the cassandra nodes.

Dependencies
------------

- Require to pre execute the 'cassandra' role in order to create infrastructure in azure.

Example Playbook
----------------

- Please find below example to execute the playbook and stand up the cassandra cluster.

- Please make sure you have already have the RG, VPC and subnets created if not please create using this command-
    
    ansible-playbook vpc.yml -e 'action=create' -e @secrets/[env]-parameters.yaml -vvvv

- Execute the playbook using below command-

    ansible-playbook cassandra.yml -e 'action=create' -e @secrets/[env]-parameters.yaml -vvvv

License
-------

BSD

