IMAGE_NAME = "bento/ubuntu-20.04"

Vagrant.configure("2") do |config|

  # First virtual machine
  config.vm.define "crc-desktop" do |crc_vm|
    crc_vm.vm.box = IMAGE_NAME
    crc_vm.vm.network "private_network", ip: "192.168.50.10"
    crc_vm.vm.provision "ansible" do |ansible|
      ansible.playbook = "crc-desktop.yml"
      ansible.extra_vars = {
        crc_home: "/home/vagrant"
      }
    end
    crc_vm.vm.provider "virtualbox" do |vb|
      vb.name = "crc-desktop"
      vb.memory = 10240
      vb.cpus = 4
    end
  end

  # # Second virtual machine
  # config.vm.define "vault" do |vault_vm|
  #   vault_vm.vm.box = "generic/ubuntu2004"
  #   vault_vm.vm.network "private_network", ip: "192.168.50.11"
  #   vault_vm.vm.provider "virtualbox" do |vb|
  #     vb.memory = 10240
  #     vb.cpus = 2
  #   end
  #   vault_vm.vm.provision "ansible" do |ansible|
  #     ansible.playbook = "vault.yml"
  #   end
end  
 
