# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.hostname =  "measurebox"
  config.vm.box = "arkmetrica/otter"
  config.vm.box_version = "0.0.9"
  config.vm.network "public_network", auto_config: false
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.synced_folder ".", "/portal", mount_options: ["umask=002"], automount: true
  config.vm.provider "virtualbox" do |vb|
    vb.name = "measurebox"
    vb.gui = true
    vb.customize ["modifyvm", :id, "--vram", "128"]
    vb.customize ["modifyvm", :id, "--graphicscontroller", "vmsvga"]  # vmsvga,vboxvga
    vb.customize ["modifyvm", :id, "--accelerate3d", "off"] # on or off. on is known to cause glitches on linux hosts
    vb.customize ["modifyvm", :id, "--clipboard", "bidirectional"]
    vb.memory = "6144"  #"8192"
  end
end
