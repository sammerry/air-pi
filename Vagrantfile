# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "base"

  config.vm.define 'hydro-schema-master' do |machine|
    machine.vm.network "private_network", ip: "192.168.10.10"
    machine.vm.network "forwarded_port", guest: 8000, host: 8000

    machine.vm.synced_folder ".", "/airPI"

    machine.vm.provision :ansible do |ansible|
      ansible.playbook = "playbook/airPI.yml"
      ansible.limit = "all"
      ansible.sudo = true
      ansible.groups = {
        "master" => ["hydro-schema-master"],
      }
    end
  end

  config.vm.provider "virtualbox" do |vb, override|
    override.vm.box = "hashicorp/precise64"
    override.vm.box_url = "http://files.vagrantup.com/precise64.box"
  end
  
end

