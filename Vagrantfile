# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define "centos" do |centos|
    centos.vm.box = "geerlingguy/centos7"
    centos.vm.network "forwarded_port", guest: 80, host: 8080
    centos.vm.provision "shell", inline: <<-SHELL
      yum -y update
      yum -y install git ansible
      git clone https://github.com/cu-library/hyrax-ansible /home/vagrant/hyrax-ansible
      chown -R vagrant:vagrant /home/vagrant/hyrax-ansible
    SHELL
  end

  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.box = "geerlingguy/ubuntu1804"
    ubuntu.vm.network "forwarded_port", guest: 80, host: 8082
    ubuntu.vm.provision "shell", inline: <<-SHELL
      echo 'set grub-pc/install_devices /dev/sda' | debconf-communicate
      apt-get update && apt-get upgrade -y
      apt-get install -y software-properties-common
      apt-add-repository -y ppa:ansible/ansible
      apt-get update
      apt-get install -y git ansible
      git clone https://github.com/cu-library/hyrax-ansible /home/vagrant/hyrax-ansible
      chown -R vagrant:vagrant /home/vagrant/hyrax-ansible
    SHELL
  end

  config.vm.define "debian" do |debian|
    debian.vm.box = "geerlingguy/debian9"
    debian.vm.network "forwarded_port", guest: 80, host: 8081
    debian.vm.provision "shell", inline: <<-SHELL
      apt-get update && apt-get upgrade -y
      grep -q -F 'deb http://ppa.launchpad.net/ansible/ansible/ubuntu trusty main' /etc/apt/sources.list || echo 'deb http://ppa.launchpad.net/ansible/ansible/ubuntu trusty main' >> /etc/apt/sources.list
      apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 93C4A3FD7BB9C367
      apt-get update
      apt-get install -y git ansible
      git clone https://github.com/cu-library/hyrax-ansible /home/vagrant/hyrax-ansible
      chown -R vagrant:vagrant /home/vagrant/hyrax-ansible
    SHELL
  end

end
