***Prerequisites:***

Install [Vagrant](https://www.vagrantup.com/downloads)

Install Ansible on OSX and Ubuntu below.

**OSX**

[Homebrew](http://brew.sh/) ```brew install ansible```

**Ubuntu**

```sudo apt-get install software-properties-common```

```sudo apt-add-repository ppa:ansible/ansible```

```sudo apt-get update```

```sudo apt-get install ansible```

I am using Ubuntu 14.04 you may do the same by adding the image ```vagrant box add precise64 http://files.vagrantup.com/precise64.box```

***Provisioning the cluster***

```vagrant up```

For now you need to ssh into each node to start DSE. For example ```vagrant ssh node1``` and run ```dse cassandra```. TODO is the automate the dse start.  
