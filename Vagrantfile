# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
	config.vm.box = "precise64"

	config.vm.box_url = "http://files.vagrantup.com/precise64.box"

	config.vm.network :private_network, ip: "33.33.33.10"

	config.vm.synced_folder "./", "/vagrant", type: "nfs"

	config.vm.provider "virtualbox" do |vb|
		vb.customize ["modifyvm", :id, "--groups", "/Vagrant"]
	end

    config.vm.provision :puppet do |puppet|
        puppet.manifests_path = "puppet/manifests"
        puppet.module_path = "puppet/modules"
        puppet.options = ['--verbose']
	end
end
