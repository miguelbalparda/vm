# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    # Set the box name and URL
    config.vm.box = "trusty-server"
    config.vm.box = "alfa"
    config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"

    # Hostmanager plugin config
    config.hostmanager.enabled           = true
    config.hostmanager.manage_host       = true
    config.hostmanager.ignore_private_ip = false
    config.hostmanager.include_offline   = true


    # Fix TTY problem
    config.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"

    # Basic box configuration
    config.vm.network "private_network", ip: "192.168.100.119"
    config.vm.hostname = "vm-dev.com"
  	config.vm.synced_folder ".", "/vagrant", :mount_options => ['dmode=777', 'fmode=777']
	
	# Provision using Ansible
    config.vm.provision "ansible" do |ansible|
        ansible.playbook = "provisioning/playbook.yml"
    end

    config.vm.provision :hostmanager
end
