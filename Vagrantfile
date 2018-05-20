# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"

  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.network "forwarded_port", guest: 9090, host: 9090

  config.vm.synced_folder "./data", "/vagrant_data"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end
  
  config.vm.provision "shell", inline: <<-SHELL
    curl -fsSL get.docker.com -o get-docker.sh
    sudo sh get-docker.sh
    sudo usermod -aG docker vagrant
    docker swarm init

    git clone https://github.com/openfaas/faas
    cd faas
    git checkout 0.8.0
    ./deploy_stack.sh

    curl -sSL https://cli.openfaas.com | sudo sh
  SHELL
end
