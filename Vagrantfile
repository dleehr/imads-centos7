# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  config.vm.box = "centos/7"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 443, host: 8443

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "gcb-ansible/imads.yml"
    ansible.groups = {"imads" => ["default"] }
    ansible.vault_password_file = "~/.vault_pass.txt"
  end
end
