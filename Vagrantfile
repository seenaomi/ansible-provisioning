# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  # config.vm.box = "tm/centos6.6"  # From vagrantbox.es
  config.vm.box = "ubuntu/trusty64"

  config.vm.network "private_network", ip: "192.168.111.222"
  config.vm.network "forwarded_port", guest: 8000, host: 8000


  config.vm.synced_folder "./", "/opt/<PROJECT_NAME>/src"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  #  vb.gui = true
  end

  config.vm.provision "ansible" do |ansible|
    ansible.limit = 'all'
    ansible.inventory_path = "provision/hosts"
    ansible.playbook = "provision/vagrant.yml"
    ansible.host_key_checking = false
    ansible.verbose = "v"
  end

end
