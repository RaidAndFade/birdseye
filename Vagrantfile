# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/xenial64"

  config.vm.network "forwarded_port", guest: 80, host: 8088

  config.vm.synced_folder ".", "/vagrant/", id: "vagrant-root0",
    owner: "ubuntu"

  config.vm.synced_folder "./storage", "/vagrant/storage", id: "vagrant-root1",
      owner: "ubuntu",
      group: "www-data",
      mount_options: ["dmode=775,fmode=664"]


  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end

  config.vm.provision :shell, path: "Vagrant-bootstrap.sh"
end
