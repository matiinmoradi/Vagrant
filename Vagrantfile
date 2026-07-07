# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/jammy64"

  config.ssh.insert_key = false

  machines = {
    "control" => "192.168.56.10",
    "lb"       => "192.168.56.20",
    "web01"    => "192.168.56.21",
    "web02"    => "192.168.56.22"
  }

  machines.each do |name, ip|
    config.vm.define name do |node|

      node.vm.hostname = name

      node.vm.network "private_network", ip: ip

      node.vm.provider "virtualbox" do |vb|
        vb.name = name

        if name == "control"
          vb.memory = 2048
          vb.cpus = 2
        else
          vb.memory = 1024
          vb.cpus = 1
        end
      end

      node.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y vim curl wget net-tools
      SHELL

    end
  end

end
