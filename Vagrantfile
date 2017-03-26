# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/centos-7.1"

  config.vm.network "public_network"

  config.vm.provider "virtualbox" do |vb|
    vb.name = "learn-python"
    vb.gui = false
    vb.memory = "1024"
  end

  config.vm.provision "shell", inline: <<-SHELL
    #
    # EPEL
    #
    yum install -y epel-release
    yum install -y deltarpm
    yum update -y

    # 
    # vim
    #
    command -v vim || yum install -y vim
    
    #
    # Python and pip
    #
    command -v python && python --version || yum install -y python34
    command -v pip || yum install -y python-pip

    pip install -U pip
    command -v virtualenv && virtualenv --version || pip install virtualenv
   
    echo $( hostname -I | awk '{ print $2 }' ) | tee /vagrant/myipaddr.txt
  SHELL
end
