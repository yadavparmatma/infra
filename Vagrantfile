# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

	config.vm.define "windows_box" do |windows_box|

		windows_box.vm.provider :virtualbox do |v|
			v.name = "windows_box"
			v.memory = 2048
		end

		windows_box.vm.box = "mwrock/Windows2012R2"
		windows_box.vm.synced_folder "/Users/Parmatma/Workspace/vbox/vm_shared", "/vm_shared"
		windows_box.vm.network :forwarded_port, guest: 8080, host: 80
		windows_box.vm.network :private_network, ip: "192.168.50.4"
	end

	config.vm.define "circleci" do |circleci|

		circleci.vm.provider :virtualbox do |v|
			v.name = "circleci"
			v.memory = 8192
		end
		
		circleci.vm.box = "/Users/Parmatma/Workspace/vbox/boxes/CentOS-7.1.1503-x86_64-netboot.box"
		circleci.vm.synced_folder "/Users/Parmatma/Workspace/vbox/vm_shared", "/vm_shared"
		circleci.vm.provision :shell, path: "bootstrap.sh"
		circleci.vm.network :forwarded_port, guest: 8800, host: 8880
		circleci.vm.network :private_network, ip: "192.168.50.5"
	end

end