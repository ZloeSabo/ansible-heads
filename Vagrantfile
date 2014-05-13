# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "symfony"
  config.vm.box = "hashicorp/precise64"
  config.vm.network :private_network, ip: "192.168.62.86"
  config.ssh.forward_agent = true
  config.vm.synced_folder ".", "/var/www/symfony", :nfs => (RUBY_PLATFORM =~ /linux/ || RUBY_PLATFORM =~ /darwin/)

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
    ansible.inventory_path = "./hosts"
    #ansible.verbose = "vvv"
  end

end
