# -*- mode: ruby -*-
# vi: set ft=ruby :

# configure Vagrant
Vagrant.configure("2") do |config|

  # general config
  config.vm.box = "ubuntu/bionic64"
  config.vm.hostname = "plex01"

  # network config
  config.vm.network "forwarded_port", guest: 80, host: 8888
  config.vm.network "forwarded_port", guest: 443, host: 4443
  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.network "forwarded_port", guest: 8088, host: 8088
  config.vm.network "forwarded_port", guest: 8089, host: 8089
  config.vm.network "forwarded_port", guest: 32400, host: 32400

  # vbox config
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end

  # ansible config
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "install.yml"
    ansible.compatibility_mode = "2.0"
    ansible.verbose = false
  end

end
