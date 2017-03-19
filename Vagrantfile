# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Using official CentOS box.
  config.vm.box = "centos/6"

  # Change IP address to fit your environment.
  # NOTE: Do not forget also change ansible "hosts" file.
  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/site.yml"
    ansible.inventory_path = "provisioning/hosts"
    ansible.limit = "all"
  end
end
