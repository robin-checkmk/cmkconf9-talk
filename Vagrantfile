# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

    # Server
    config.vm.define "cmkconf9-server", primary: true do |srv|
      srv.vm.box = "ubuntu/jammy64"
      srv.vm.network "private_network", ip: "192.168.56.9"
      srv.ssh.insert_key = false
      srv.vm.provider "virtualbox" do |v|
        v.name = 'cmkconf9-server'
        v.memory = 4096
        v.cpus = 4
      end
      srv.vm.provision "shell",
          inline: "apt-get -y update --quiet && apt-get -y install vim htop curl wget git"
    end

    # Agents
    config.vm.define "cmkconf9-ubuntu", primary: true do |srv|
      srv.vm.box = "ubuntu/jammy64"
      srv.vm.network "private_network", ip: "192.168.56.19"
      srv.ssh.insert_key = false
      srv.vm.provider "virtualbox" do |v|
          v.name = 'cmkconf9-ubuntu'
          v.memory = 1024
          v.cpus = 2
      end
      srv.vm.provision "shell",
          inline: "apt-get -y update --quiet && apt-get -y install vim htop curl wget git"
    end

    config.vm.define "cmkconf9-debian", primary: true do |srv|
      srv.vm.box = "debian/bullseye64"
      srv.vm.network "private_network", ip: "192.168.56.29"
      srv.ssh.insert_key = false
      srv.vm.provider "virtualbox" do |v|
          v.name = 'cmkconf9-debian'
          v.memory = 1024
          v.cpus = 2
      end
      srv.vm.provision "shell",
          inline: "apt-get -y update --quiet && apt-get -y install vim htop curl wget git"          
    end

    config.vm.define "cmkconf9-centos", primary: true do |srv|
      srv.vm.box = "centos/stream8"
      srv.vm.network "private_network", ip: "192.168.56.39"
      srv.ssh.insert_key = false
      srv.vm.provider "virtualbox" do |v|
          v.name = 'cmkconf9-centos'
          v.memory = 1024
          v.cpus = 2
      end
      srv.vm.provision "shell",
          inline: "dnf --quiet check-update ; dnf -y install vim curl wget git"
    end

    config.vm.define "cmkconf9-suse", primary: true do |srv|
      srv.vm.box = "opensuse/Tumbleweed.x86_64"
      srv.vm.network "private_network", ip: "192.168.56.49"
      srv.ssh.insert_key = false
      srv.vm.provider "virtualbox" do |v|
          v.name = 'cmkconf9-suse'
          v.memory = 1024
          v.cpus = 2
      end
      srv.vm.provision "shell",
          inline: "zypper --quiet up -y"
    end
end
