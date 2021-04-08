k8s-binary
=========

Install ansible (must have):

pip3 install ansible

Install cluster kubernetes from binary files, NOT KUBEADM

Requirements
------------
python3-devel  
python3-pip  
ansible      min_stable(2.9.13)
netaddr      min_stable(0.8.0)   

Role Variables
--------------

project_name == Name of project
interface == virtual interface ($ ip a) # See what kind of interface you need

Dependencies
------------

nothing

Example Playbook
----------------

ansible-playbook -i hosts site.yml -e project_name=test -e interface=eth0 # Install kubernetes  
ansible-playbook -i hosts destroy.yml -e project_name=test -e interface=eth0 # Destroy kubernetes (clean dependency) !!! ALARM: CLEAN FULL ETCD DATA 

Add new worker,master node
-------------------
ansible-playbook -i hosts add_node.yml -e project_name=test -e interface=eth0
