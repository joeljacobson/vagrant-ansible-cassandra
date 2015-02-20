# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

   config.vm.define "node1" do |node1|
    node1.vm.box = "precise64"
    node1.vm.network  "private_network", ip: "192.168.56.10"
  end

   config.vm.define "node2" do |node2|
    node2.vm.box = "precise64"
    node2.vm.network  "private_network", ip: "192.168.56.20"
  end

   config.vm.define "node3" do |node3|
    node3.vm.box = "precise64"
    node3.vm.network  "private_network", ip: "192.168.56.30"
  end

   config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
  end

  config.vm.define "opscenter" do |opscenter|
    opscenter.vm.box = "precise64"
    opscenter.vm.network  "private_network", ip: "192.168.56.40"
  end

  config.vm.provision "ansible" do |ansible|
   ansible.playbook = "tasks/opscenter.yml"
 end

 config.vm.provider "virtualbox" do |vb|
   vb.customize ["modifyvm", :id, "--memory", "2048"]
 end

end
