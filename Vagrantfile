# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

    config.vm.provider "virtualbox" do |vb|
    # Customize the amount of memory on the VM:
    vb.memory = "3072"
    end

    config.vm.define "abc1-nag1" do |node|
      node.vm.box = "iosxe/16.06.05"
      node.vm.guest = :tinycore

      node.vm.hostname = "abc1-nag1"
      # Default Gi1 connect to link 1
      node.vm.network :private_network, virtualbox__intnet: "link2", auto_config: false
#       node.vm.network :private_network, virtualbox__intnet: "link3", auto_config: false
      node.vm.network :private_network, type: "dhcp"

      node.vm.network :forwarded_port, guest: 22, host: 3221, id: 'ssh', auto_correct: true
    end




    config.vm.define "abc1-nag2" do |node|
      node.vm.box = "iosxe/16.06.05"
      node.vm.guest = :tinycore

      node.vm.hostname = "abc1-nag2"
      # Default Gi1 connect to link 1
      node.vm.network :private_network, virtualbox__intnet: "link2", auto_config: false
#       node.vm.network :private_network, virtualbox__intnet: "link3", auto_config: false
      node.vm.network :private_network, type: "dhcp"

      node.vm.network :forwarded_port, guest: 22, host: 3222, id: 'ssh', auto_correct: true
    end


    # Provisioning the switch
    config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible_provision.yaml"
    ansible.inventory_path = "./hosts.yaml"
    ansible.raw_arguments = ["--connection=paramiko"]
    end
end