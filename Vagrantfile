# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

Vagrant.configure(2) do |config|
	config.vm.box = "centos7"
	config.vm.provider "virtualbox" do |virtualbox|
		virtualbox.memory = 2048
		virtualbox.cpus = 2
	end

	(0..2).each do |index|
		config.vm.define "mesosphere_master-#{index}" do |mesosphere_master|
			mesosphere_master.vm.network "private_network", ip: "192.168.1.1#{index}", vitualbox__intnet: true
			mesosphere_master.vm.hostname="mesosphere-master-#{index}"
		end
	end
	(0..5).each do |index|
		config.vm.define "mesosphere_slave-#{index}" do |mesosphere_slave|
			mesosphere_slave.vm.network "private_network", ip: "192.168.1.2#{index}", vitualbox__intnet: true
			mesosphere_slave.vm.hostname="mesosphere-slave-#{index}"
		end
	end
end
