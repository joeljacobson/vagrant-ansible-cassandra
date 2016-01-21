# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
N = 3
(1..N).each do |machine_id|
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"
  config.vm.define "node#{machine_id}" do |machine|
    machine.vm.hostname = "node#{machine_id}"
    machine.vm.network "private_network", ip: "192.168.56.#{10+machine_id}"
    if machine_id == N
      machine.vm.provision :ansible do |ansible|
        ansible.limit = "all"
        ansible.playbook = "site.yml"
       config.vm.provider "virtualbox" do |vb|
         vb.customize ["modifyvm", :id, "--memory", "2048"]
       end
      end
    end
  end
end
  config.vm.define "opscenter" do |opscenter|
    opscenter.vm.box = "precise64"
    opscenter.vm.network  "private_network", ip: "192.168.56.14"
  config.vm.provision "ansible" do |ansible|
   ansible.playbook = "tasks/opscenter.yml"
 end
 end
end
