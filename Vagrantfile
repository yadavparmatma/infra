# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

	config.vm.define "circleci" do |circleci|

		circleci.vm.provider :virtualbox do |v|
			v.name = "circleci"
			v.memory = 8192
		end
		
		circleci.vm.box = "/Users/Parmatma/Workspace/vbox/boxes/CentOS-7.1.1503-x86_64-netboot.box" #provide a box path if having locally otherwise give hasicorp box name
		circleci.vm.synced_folder "/Users/Parmatma/Workspace/vbox/vm_shared", "/vm_shared" #shared folder path
		circleci.vm.provision :shell, path: "bootstrap.sh"
		circleci.vm.network :forwarded_port, guest: 8800, host: 8880 #for ci setup and docs 
		circleci.vm.network :forwarded_port, guest: 80, host: 8080   #for public interface
		circleci.vm.network :forwarded_port, guest: 443, host: 443   #for reverse proxy
		circleci.vm.network :forwarded_port, guest: 64535, host: 64535 #for dev purpose
		circleci.vm.network :private_network, ip: "192.168.50.5"
	end

end
