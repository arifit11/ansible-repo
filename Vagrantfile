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
  ssh_pub_key = File.readlines("/Users/arifkhan/.ssh/id_rsa.pub").first.strip

  # control
  config.vm.define "control", primary: true do |h|
    h.vm.network "private_network", ip: "192.168.135.10"
    h.vm.provider :virtualbox do |ps|
      ps.memory = 512
      ps.name = "vb-control"
    end
    h.vm.provision 'shell', inline: 'mkdir -p /root/.ssh'
    h.vm.provision 'shell', inline: "echo #{ssh_pub_key} > /root/.ssh/authorized_keys"
    h.vm.provision 'shell', inline: 'chmod 600 /root/.ssh/authorized_keys'
    h.vm.provision 'shell', inline: 'chmod 700 /root/.ssh'
    h.vm.provision "ansible" do |ansible|
      ansible.playbook = "repo/sensu-server.yml"
      ansible.playbook = "/Users/arifkhan/workspace/ansible/ansible-repo/playbook/jenkins.yml"

    end
  end

  # lb01
  config.vm.define "lb01" do |h|
    h.vm.network "private_network", ip: "192.168.135.101"
    h.vm.provider :virtualbox do |ps|
      ps.memory = 512
      ps.name = "vb-lb01"
    end
    h.vm.provision 'shell', inline: 'mkdir -p /root/.ssh'
    h.vm.provision 'shell', inline: "echo #{ssh_pub_key} > /root/.ssh/authorized_keys"
    h.vm.provision 'shell', inline: 'chmod 600 /root/.ssh/authorized_keys'
    h.vm.provision 'shell', inline: 'chmod 700 /root/.ssh'
    #h.vm.provision "ansible" do |ansible|
    #  ansible.playbook = "repo/sensu-client.yml"
    #end
  end

  # app01
  config.vm.define "app01" do |h|
    h.vm.network "private_network", ip: "192.168.135.111"
    h.vm.provider :virtualbox do |ps|
      ps.memory = 512
      ps.name = "vb-app01"
    end
    h.vm.provision 'shell', inline: 'mkdir -p /root/.ssh'
    h.vm.provision 'shell', inline: "echo #{ssh_pub_key} > /root/.ssh/authorized_keys"
    h.vm.provision 'shell', inline: 'chmod 600 /root/.ssh/authorized_keys'
    h.vm.provision 'shell', inline: 'chmod 700 /root/.ssh'
    #h.vm.provision "ansible" do |ansible|
    #  ansible.playbook = "repo/sensu-client.yml"
    #end
  end

  # app02
  config.vm.define "app02" do |h|
    h.vm.network "private_network", ip: "192.168.135.112"
    h.vm.provider :virtualbox do |ps|
      ps.memory = 512
      ps.name = "vb-app02"
    end
    h.vm.provision 'shell', inline: 'mkdir -p /root/.ssh'
    h.vm.provision 'shell', inline: "echo #{ssh_pub_key} > /root/.ssh/authorized_keys"
    h.vm.provision 'shell', inline: 'chmod 600 /root/.ssh/authorized_keys'
    h.vm.provision 'shell', inline: 'chmod 700 /root/.ssh'
    #h.vm.provision "ansible" do |ansible|
    #  ansible.playbook = "repo/sensu-client.yml"
    #end
  end

  # db01
  config.vm.define "db01" do |h|
    h.vm.network "private_network", ip: "192.168.135.121"
    h.vm.provider :virtualbox do |ps|
      ps.memory = 512
      ps.name = "vb-db01"
    end
    h.vm.provision 'shell', inline: 'mkdir -p /root/.ssh'
    h.vm.provision 'shell', inline: "echo #{ssh_pub_key} > /root/.ssh/authorized_keys"
    h.vm.provision 'shell', inline: 'chmod 600 /root/.ssh/authorized_keys'
    h.vm.provision 'shell', inline: 'chmod 700 /root/.ssh'
    h.vm.provision 'shell', inline: 'hostnamectl set-hostname db01'
    #h.vm.provision "ansible" do |ansible|
    #  ansible.playbook = "repo/sensu-client.yml"
    #end
  end
end
