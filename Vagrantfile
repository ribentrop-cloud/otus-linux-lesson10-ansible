# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

config.vm.define "vm-ansible" do |subconfig|
	subconfig.vm.box = "centos/7"
	subconfig.vm.hostname = "vm-ansible"
	subconfig.vm.network :private_network, ip: "192.168.50.11"
	subconfig.vm.provider "virtualbox" do |vb|
		vb.memory = "1024"
		vb.cpus = "1"
	end
end

config.vm.define "vm-ansible2" do |subconfig|
	subconfig.vm.box = "centos/7"
	subconfig.vm.hostname = "vm-ansible2"
	subconfig.vm.network :private_network, ip: "192.168.50.12"
	subconfig.vm.provider "virtualbox" do |vb|
		vb.memory = "1024"
		vb.cpus = "1"
	end
end

end
