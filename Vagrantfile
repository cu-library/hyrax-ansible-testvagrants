# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define "centos" do |centos|
    centos.vm.box = "centos/7"
    centos.vm.network "forwarded_port", guest: 80, host: 8080
    centos.vm.network "forwarded_port", guest: 8080, host: 8081
    centos.vm.provider "virtualbox" do |v|
        v.memory = 2048
    end
    centos.vm.provision "shell", inline: <<-SHELL
      yum -y update
      yum -y install git ansible
      if [ -d "/home/vagrant/hyrax-ansible" ]
      then
          pushd /home/vagrant/hyrax-ansible; git pull; popd
      else
          git clone https://github.com/cu-library/hyrax-ansible /home/vagrant/hyrax-ansible
      fi
      chown -R vagrant:vagrant /home/vagrant/hyrax-ansible
      chmod u+x /home/vagrant/hyrax-ansible/prepare.sh
      /home/vagrant/hyrax-ansible/prepare.sh
      cd /home/vagrant/hyrax-ansible
      ansible-playbook install_hyrax_on_localhost.yml
    SHELL
  end

  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.box = "ubuntu/bionic64"
    ubuntu.vm.network "forwarded_port", guest: 80, host: 8082
    ubuntu.vm.network "forwarded_port", guest: 8080, host: 8083
    ubuntu.vm.provider "virtualbox" do |v|
        v.memory = 2048
        v.customize [ "modifyvm", :id, "--uartmode1", "disconnected" ]
    end
    ubuntu.vm.provision "shell", inline: <<-SHELL
      echo 'set grub-pc/install_devices /dev/sda' | debconf-communicate
      apt-get update && apt-get upgrade -y
      apt-get install -y software-properties-common git curl
      apt-add-repository -y ppa:ansible/ansible
      apt-get update
      apt-get install -y ansible
      if [ -d "/home/vagrant/hyrax-ansible" ]
      then
          pushd /home/vagrant/hyrax-ansible; git pull; popd
      else
          git clone https://github.com/cu-library/hyrax-ansible /home/vagrant/hyrax-ansible
      fi
      chown -R vagrant:vagrant /home/vagrant/hyrax-ansible
      chmod u+x /home/vagrant/hyrax-ansible/prepare.sh
      /home/vagrant/hyrax-ansible/prepare.sh
      cd /home/vagrant/hyrax-ansible
      ansible-playbook install_hyrax_on_localhost.yml
    SHELL
  end

  config.vm.define "debian" do |debian|
    debian.vm.box = "debian/stretch64"
    debian.vm.network "forwarded_port", guest: 80, host: 8084
    debian.vm.network "forwarded_port", guest: 8080, host: 8085
    debian.vm.provider "virtualbox" do |v|
        v.memory = 2048
    end
    debian.vm.provision "shell", inline: <<-SHELL
      apt-get update && apt-get upgrade -y
      apt-get install -y dirmngr gpg curl git
      grep -q -F 'deb http://ppa.launchpad.net/ansible/ansible/ubuntu trusty main' /etc/apt/sources.list || echo 'deb http://ppa.launchpad.net/ansible/ansible/ubuntu trusty main' >> /etc/apt/sources.list
      apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 93C4A3FD7BB9C367
      apt-get update
      apt-get install -y ansible
      if [ -d "/home/vagrant/hyrax-ansible" ]
      then
          pushd /home/vagrant/hyrax-ansible; git pull; popd
      else
          git clone https://github.com/cu-library/hyrax-ansible /home/vagrant/hyrax-ansible
      fi
      chown -R vagrant:vagrant /home/vagrant/hyrax-ansible
      chmod u+x /home/vagrant/hyrax-ansible/prepare.sh
      /home/vagrant/hyrax-ansible/prepare.sh
      cd /home/vagrant/hyrax-ansible
      ansible-playbook install_hyrax_on_localhost.yml
    SHELL
  end

end
