# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.hostname =  "measurebox"
  config.vm.box = "arkmetrica/otter"
  config.vm.network "public_network", auto_config: false
  config.vm.synced_folder "./", "/vagrant", owner: 'vagrant', group: 'vagrant', mount_options: ['dmode=775,fmode=664'], automount: true
  config.vm.provider "virtualbox" do |vb|
    vb.name = "measurebox"
    vb.gui = true
    vb.customize ["modifyvm", :id, "--vram", "128"]
    vb.customize ["modifyvm", :id, "--graphicscontroller", "vmsvga"]  # "vboxvga"
    vb.customize ["modifyvm", :id, "--accelerate3d", "on"]
    vb.customize ["modifyvm", :id, "--clipboard", "bidirectional"]
    vb.memory = "6144"  #"8192"
  end
end
