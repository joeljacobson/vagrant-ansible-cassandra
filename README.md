**Introduction**

Quickly provision 3 DSE 4.5 nodes and Opscenter across 4 VMs using Ansible with Vagrant & Virtualbox.

**Prerequisites**

[Vagrant](https://www.vagrantup.com/downloads)

[Ansible](http://docs.ansible.com/intro_installation.html)

Add the Ubuntu 14.04 vagrant base image ```vagrant box add precise64 http://files.vagrantup.com/precise64.box```

**Provisioning**

In the project directory enter ```vagrant up```.

Your cluster will be ready shortly depending on your internet connection. The first time takes a while as Ansible has to download, setup and configure DSE across each VMs. Subsequent shutdowns and restarts are fast.

DSE and Opscenter will be automatically configured and started once they have been installed. They will also be automatically started each time the VMs are booted.

The nodes will be running on: ```192.168.56.10```, ```192.168.56.20```, ```192.168.56.30```

Opscenter will be running on:```192.168.56.40:8888```

Install the agents with by entering vagrant for both the username and password.

ssh onto a node with ```vagrant ssh node1```

To shutdown the VMs ```vagrant halt```

To resume VMs ```vagrant up```

To completely destroy the VMs (requires re-provisioning) ```vagrant destroy```

**TODO**

Ability to provision Spark & Solr nodes.
