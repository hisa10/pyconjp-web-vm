=====================================
PyCon JP website test VM provisioning
=====================================


Requirement
===========

* Vagrant >= 1.9.1
* Ansible >= 2.1
* Python >= 2.7
* Basic skill to use Vagrant and CentOS

Howto
=====

* Clone repository

    $ git clone https://github.com/hisa10/pyconjp-web-vm.git


* Vagrant up

    $ cd pyconjp-web-vm
    $ vagrant up


* Wait for 15 min to severeral hours. 
  
  Depends on your machine spec and network bandwidth.
 

* Login

  $ vagrant ssh
  $ sudo su - pyconjp
  $ cd /opt/workspace/pyconjp-2017


* Prepare development environment

  * See this document: https://github.com/pyconjp/pyconjp-website/blob/develop/README.rst
  * NOTE: Use "runserver 0.0.0.0:8000" instead of "runserver" to allow connection from outside of VM.


* Connect from host web browser to internal IP of VM

  ex. http://192.168.33.10:8000


Files
=====

* ./Vagrantfile

  Settings of Vagrant.


* ./provisioning/hosts

  Set internal IP address of VM used for provision with Ansible.


* ./provisioning/site.yml

  Main Ansible playbook.


* ./provisioning/group_vars/all.yml

  Additional parameters for provisioning.


* ./provisioning/roles/<role_name>/tasks/main.yml

  Main playbook of the role.


