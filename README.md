##Introduction

Easily provision 3 DataStax Enterprise 4.5 nodes and Opscenter 5.0 across 4 VMs using Ansible with Vagrant & Virtualbox.

##Prerequisites

* [Virtualbox](https://www.virtualbox.org/)
* [Vagrant](https://www.vagrantup.com/downloads)
* [Ansible](http://docs.ansible.com/intro_installation.html)

Add the Ubuntu 14.04 vagrant base image: ```vagrant box add precise64 http://files.vagrantup.com/precise64.box```

##Provisioning

Clone the project: ```git clone https://github.com/joeljacobson/dse-ansible-vagrant-cluster.git```

In the project directory enter: ```vagrant up```

Ansible will begin to provision the cluster.

![](https://camo.githubusercontent.com/ae0fd6b1ef28ea75df765593f278c5abc03a4e86/687474703a2f2f69313136362e70686f746f6275636b65742e636f6d2f616c62756d732f713631332f6a6f656c6a61636f62736f6e2f53637265656e53686f74323031342d30382d323761743137313033395f7a707363666662373731362e706e67)

Your cluster will be ready shortly depending on your internet connection. The initial boot takes some time as Ansible has to download, setup and configure DSE across each VM. Subsequent reboots are fast.

DSE and Opscenter will be automatically configured and started once installed. They will also be automatically started each time the VMs are booted.

Nodes will be running on: ```192.168.56.10```, ```192.168.56.20```, ```192.168.56.30```

Opscenter will be running on: ```192.168.56.40:8888```

Install the datastax-agents by entering ```vagrant``` for both the username and password.

SSH into a node with: ```vagrant ssh <nodename>```

Shutdown the VMs: ```vagrant halt```

Resume VMs: ```vagrant up```

Destroy the VMs (requires re-provisioning): ```vagrant destroy```

**TODO**

Ability to provision Spark & Solr nodes across multiple datacenters.
