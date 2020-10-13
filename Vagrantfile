# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.hostname =  "measurebox"
  config.vm.box = "arkmetrica/otter"
  config.vm.box_version = "0.0.11"
  config.vm.network "public_network", auto_config: false
  config.vm.synced_folder ".", "/vagrant", mount_options: ["fmode=666","dmode=777","dmask=000","fmask=000"]
  config.vm.provider "virtualbox" do |vb|
    vb.name = "measurebox"
    vb.gui = false
    vb.customize ["modifyvm", :id, "--vram", "128"]
    vb.customize ["modifyvm", :id, "--graphicscontroller", "vmsvga"]  # vmsvga,vboxvga
    vb.customize ["modifyvm", :id, "--accelerate3d", "off"] # on or off. on is known to cause glitches on linux hosts
    vb.customize ["modifyvm", :id, "--clipboard", "bidirectional"]
    vb.memory = "6144"  #"8192"
  end
end
