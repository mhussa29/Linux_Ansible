Playbook
(all files are in yml format)
-Git
-Java
-Jenkins
Commands:
ansible-playbook -i inventory playbook/install_jenkins.yml -> run playbook
ansible-playbook install_jenkins.yml -> also run playbook


Roles

Commands:
ansible-galaxy search (role_name) -> to search for existing roles in galaxy
ansible-galaxy init (role_name) -> to install/create roles

Inventory
**** The playbook files are linked to /etc/ansible/hosts and /etc/ansible/host_vars ***************
-host (Contains name of each servers)
-host_vars (Contains information about each servers)
Commands:
ansible -i host jenkins -m ping  -> pings and confirms the SSH connection (host=file in inventory (-i), jenkins=server_group, m=module) However, it pings only from ansible/inventory dir

 OR

ansible jenkins -i /home/ubuntu/ansible/inventory -m ping -> pings from any dir

OR

ansible all -m ping

Another one

ansible jenkins -i inventory -m shell -a "lsb_release -d"

Move into a Slave Directory:
Command: ssh -i ~/.ssh/Ubuntu_slave.pem ubuntu@IP
