# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "jumperfly/centos-7-ansible"

  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 1
  end

  config.vm.provision "shell", inline: "mkdir -p /etc/ansible/roles && ln -snf /vagrant/ /etc/ansible/roles/java"

  config.vm.provision "ansible_local" do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "tests/test.yml"
  end
end
