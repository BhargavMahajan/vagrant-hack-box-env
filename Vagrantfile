# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
	# For tuning, check https://github.com/rapid7/metasploitable3
	config.vm.define :metasploitable3_linux do |ms_l|
		ms_l.vm.box = "rapid7/metasploitable3-ub1404"
		ms_l.vm.network :private_network, ip: "172.28.128.10"
		config.ssh.username = "vagrant"
		config.ssh.password = "vagrant"
		ms_l.vm.provider "virtualbox" do |vb|
			vb.name = "metasploitable3-ub1404"
			vb.memory = 1024
		end
		ms_l.vm.provider "vmware_desktop" do |vm|
			vm.vmx["memsize"] = "1024"
		end
	end

	config.vm.define :metasploitable3_windows do |ms_win|
		ms_win.vm.box = "rapid7/metasploitable3-win2k8"
		ms_win.vm.network :private_network, ip: "172.28.128.15"
		ms_win.vm.communicator = "winrm"
		ms_win.winrm.retry_limit = 60
		ms_win.winrm.retry_delay = 10
		ms_win.vm.provider "virtualbox" do |vb|
			vb.gui = true
			vb.name = "metasploitable3-win2k8"
			vb.memory = 1024
		end
		ms_win.vm.provider "vmware_desktop" do |vm|
			vm.vmx["memsize"] = "1024"
		end
	end

	config.vm.define :kali do |kali|
		# You can also use offensive-security/kali-linux-light box
		kali.vm.box = "offensive-security/kali-linux"
		kali.vm.network :private_network, ip: "172.28.128.5"
		kali.vm.provider "virtualbox" do |vb|
			vb.name = "kali-linux"
			vb.memory = 1024
		end
	end
end
