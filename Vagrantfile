# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu14.04-amd64"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.provider "virtualbox" do |vb|
    vb.customize ["modifyvm", :id, "--memory", "4096"]
  end

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get install software-properties-common
    sudo apt-add-repository ppa:ansible:/ansible
    sudo apt-get update
    sudo apt-get install ansible
    cd /vagrant; ansible-playbook -i localhost, playbook.yml
  SHELL
end
