master-instance
=========

This role will launch one master on AWS cloud and it'll tagged as k8s_master_an which is helpful to apply certain plays on certain instance

Requirements
------------

You need to install boto. 
Command to install boto is : pip3 install boto
You should have your pre-created dynamic inventory ready to fetch the instance, also configuration file of ansible should be ready.

Role Variables
--------------

The variables in this file used are aws_access_key which are located in /vars/main.yml file. In aws_access_key variable the value should be your own AWS access key. Similarly other variable is aws_secret_key whose value is AWS secret key located in same file.

Dependencies
------------

This role is one of the four which is designed to setup multi node k8s setup on the top of AWS instance by use of automation tool Ansible. So, for complete setup you have to download all four roles which are :
1. master-instance
2. master_conf
3. slave-instance
4. slave_conf
The roles should be applied serially.

Example Playbook
----------------

    - hosts: localhost
      roles:
         - master-instance
