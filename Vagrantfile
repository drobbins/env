# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "chef/centos-6.5"

  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
  end

  # Configure using Ansible
  config.vm.provision "ansible" do |ansible|
        ansible.playbook = "replicator.yml"
  end

  # Share the application's directory
  config.vm.synced_folder "../", "/app"

  # Forward Stardog Port
  config.vm.network "forwarded_port", guest: 5820, host: 5820

end
