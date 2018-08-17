# -*- mode: ruby -*-
# vi: set ft=ruby : 

VAGRANTFILE_API_VERSION = "2" 

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
config.ssh.pty = true
config.ssh.insert_key = false

  config.vm.define "arch_box" do |machine|
    machine.vm.box = "archlinux/archlinux"
    machine.vm.synced_folder '.', '/vagrant', disabled: true
    machine.vm.network :private_network, ip: "10.0.0.10",
                       :netmask => "255.255.0.0"
    machine.vm.provider :virtualbox do |v|
      v.memory = 4096
      v.cpus = 4
    end
  end
  
end
