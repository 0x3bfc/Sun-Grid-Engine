# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

	common_virtualbox = Proc.new do |virtualbox, override|
		config.vm.box = "ubuntu/precise64"
		config.vm.hostname = "bioinformatics"
		config.vm.network :private_network, ip: "192.168.0.41"

		config.ssh.username = "vagrant"
		config.ssh.password = "vagrant"
		config.ssh.insert_key = 'true'
	end

	config.vm.define 'primary' do |cfg|
		cfg.vm.provider :virtualbox do |virtualbox, override|
			common_virtualbox.call virtualbox, override
			 virtualbox.customize ["modifyvm", :id,"--memory", "1024"]
		end
	end
end
