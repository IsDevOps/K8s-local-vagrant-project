# Vagrantfile
Vagrant.configure("2") do |config|
    # Define the base box to use
    config.vm.box = "ubuntu/bionic64"
  
    # Define the first node
    config.vm.define "node1" do |node1|
      node1.vm.hostname = "node1"
      node1.vm.network "public_network", bridge: "wlp2s0" # Adjust the bridge adapter name if necessary
      node1.vm.provider "virtualbox" do |vb|
        vb.name = "node1"
        vb.memory = "1024"
        vb.cpus = 1
      end
      node1.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y net-tools
        apt-get install nginx -y
      SHELL
    end
  
    # Define the second node
    config.vm.define "node2" do |node2|
      node2.vm.hostname = "node2"
      node2.vm.network "public_network", bridge: "wlp2s0" # Adjust the bridge adapter name if necessary
      node2.vm.provider "virtualbox" do |vb|
        vb.name = "node2"
        vb.memory = "1024"
        vb.cpus = 1
      end
      node2.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y net-tools
        apt-get install nginx -y

      SHELL
    end
  end
  