Vagrant.configure("2") do |config|
  config.ssh.insert_key = false 
  config.vm.define "node1" do |node1|
    node1.vm.box = "geerlingguy/centos7"
    node1.vm.box_version = "1.2.15"
	node1.vm.box_download_insecure = true
    node1.vm.network "private_network", ip: "192.168.199.2"
    node1.vm.hostname = "node1.example.com"    
    node1.vm.network "forwarded_port", guest: 8080, host: 8080
    node1.vm.provider "virtualbox" do |v|
      v.memory = 2048
      v.cpus = 2
      v.customize ['modifyvm', :id, '--cableconnected1', 'on']
    end
  end
  config.vm.define "node2" do |node2|
    node2.vm.box = "geerlingguy/centos7"
    node2.vm.box_version = "1.2.15"
	node2.vm.box_download_insecure = true
    node2.vm.network "private_network", ip: "192.168.199.3"
    node2.vm.hostname = "node2.example.com"    
    node2.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 2
      v.customize ['modifyvm', :id, '--cableconnected1', 'on']
    end
  end
 end
