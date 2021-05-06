# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "peru/ubuntu-20.04-desktop-amd64"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "main.yml"
    ansible.ask_vault_pass = true
  end
end
