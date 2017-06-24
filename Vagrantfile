# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  #config.vm.box = "ubuntu/xenial64"
  config.vm.box = "boxcutter/ubuntu1604"

  config.vm.define "vtep1" do |vtep1|
    vtep1.vm.host_name = "VTEP1"
    vtep1.vm.network "private_network",
                         ip: "10.11.12.10",
                         virtualbox__intnet: "fabric"
    vtep1.vm.network "private_network",
                         virtualbox__intnet: "vtep1-vni100",
                         auto_config: false
    vtep1.vm.network "private_network",
                         virtualbox__intnet: "vtep1-vni200",
                         auto_config: false
    vtep1.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
    end
    vtep1.vm.provision "ansible" do |ansible|
      ansible.playbook = "vtep1.yml"
    end
  end

end
