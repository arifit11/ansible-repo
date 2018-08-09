# -*- mode: ruby -*-
# vi: set ft=ruby :

# README
#
# Getting Started:
# 1. vagrant plugin install vagrant-hostmanager
# 2. vagrant up
# 3. vagrant ssh
#
# This should put you at the control host
#  with access, by name, to other vms
Vagrant.configure(2) do |config|
  config.hostmanager.enabled = true

  config.vm.box = "centos/7"
  
  config.vm.define "control", primary: true do |h|
    h.vm.network "private_network", ip: "192.168.135.10"

  end
  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id, "--memory", 1024]
    
  end
  config.vm.define "lb01" do |h|
    
    h.vm.network "private_network", ip: "192.168.135.101"
    
  end
  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id, "--memory", 512]
    
  end

  config.vm.define "app01" do |h|
    
    h.vm.network "private_network", ip: "192.168.135.111"
    
  end
  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id, "--memory", 512]
    
  end

  config.vm.define "app02" do |h|
    
    h.vm.network "private_network", ip: "192.168.135.112"
    
  end
  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id, "--memory", 512]
    
  end

  config.vm.define "db01" do |h|
    
    h.vm.network "private_network", ip: "192.168.135.121"
    
  end
  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id, "--memory", 512]
    
  end
end
