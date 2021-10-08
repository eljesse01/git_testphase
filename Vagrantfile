Vagrant.configure("2") do |config|
 
  config.vm.box = "bento/ubuntu-18.04"

 
  config.vm.provider "virtualbox" do |vb|
    
    vb.gui = false  
    
    vb.memory = "1024"
    vb.cpus = "1"
  end

  config.vm.define "web" do |web|
    web.vm.hostname = "Web"
    web.vm.network "private_network", ip: "192.168.2.130"
    web.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "configure.yml"
    end
  end
  config.vm.define "web1" do |web1|
    web1.vm.hostname = "Web1"
    web1.vm.network "private_network", ip: "192.168.2.131"
    web1.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "configure.yml"
    end
  end
  # config.vm.define "web2" do |web2|
  #   web2.vm.hostname = "Web2"
  #   web2.vm.network "private_network", ip: "192.168.2.132"
  #   web2.vm.provision "ansible_local" do |ansible|
  #     ansible.playbook = "configure.yml"
  #   end
  # end
  # config.vm.define "web3" do |web3|
  #   web3.vm.hostname = "Web3"
  #   web3.vm.network "private_network", ip: "192.168.2.133"
  #   web3.vm.provision "ansible_local" do |ansible|
  #     ansible.playbook = "configure.yml"
  #   end
  # end
  

  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y wget 
  #  SHELL
end