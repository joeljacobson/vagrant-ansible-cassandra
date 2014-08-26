**Introduction**

Quickly provision 3 DSE 4.5 nodes across 3 VMs using Vagrant and Ansible. The memory in the VMs is set to 4096. You may edit this in the ```Vagrantfile``` if you wish to reduce it before booting the VMs.

**Prerequisites:**

Install [Vagrant](https://www.vagrantup.com/downloads)

Install [Ansible](http://docs.ansible.com/intro_installation.html)

Add the Ubuntu 14.04 vagrant base image ```vagrant box add precise64 http://files.vagrantup.com/precise64.box```

**Provisioning**

In the project directory enter ```vagrant up```. Your cluster will be ready shortly depending on your internet connection. The first time takes a while as ansible has to setup the VMs and download DSE & dependencies. DSE will be automatically configured and started.

The nodes will be running on; 192.168.56.10, 192.168.56.20, 192.168.56.30

To shutdown the VMs ```vagrant halt```

To resume VMs ```vagrant up```. DSE will be started automatically.

To completely destroy the VMs (requires re-provisioning) ```vagrant destroy```

**TODO** Lots.
