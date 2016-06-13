# -*- mode: ruby -*-
# vi: set ft=ruby :

# Versão minima do Vagrant
Vagrant.require_version ">= 1.8.1"

Vagrant.configure("2") do |config|
    
	config.vm.box = "e-cogni/centos7"
	config.vm.box_url = "https://github.com/e-cogni/vagrant-centos/releases/download/7/centos-7-x64-pt_br.box"
	config.vm.usable_port_range = 2800..2900 
	config.vm.boot_timeout = 600
	config.vm.hostname = "centos7.local"
	#config.vm.synced_folder ".", "/vagrant", type: "nfs"

	#config.vm.network :public_network, ip: "192.168.0.100", :netmask => "255.255.255.0", bridge: "wlan0", auto_config: true
	#config.vm.network :private_network, virtualbox__intnet: "rede_interna", ip: "10.100.0.100", :netmask => "255.255.0.0"
	#config.vm.network :private_network, ip: "172.16.0.100", :netmask => "255.255.255.0" 

	#config.vm.provision "shell",
    	#	run: "always",
    	#	inline: "ip route add 0/0 via 192.168.0.1 dev eth1"

	if Vagrant.has_plugin?("vagrant-cachier")
		config.cache.scope = :box
		config.cache.enable :yum
	else
		puts "[-] ALERTA: O provisionamento ocorrerá mais rápido se você primeiro executar: 'vagrant plugin install vagrant-cachier' "
	end

	config.vm.provider :virtualbox do |vbox|
		vbox.customize ["modifyvm", :id, "--name", "CentOS 7 x64 - pt_BR"]
		vbox.customize ["modifyvm", :id, "--groups", "/Boxes"]
		#vbox.customize ["modifyvm", :id, "--memory", 1024]
		#vbox.customize ["modifyvm", :id, "--cpus", 1]
		#vbox.customize ["modifyvm", :id, "--nicpromisc4", "allow-all"]
	end
end
