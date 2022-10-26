# # -*- mode: ruby -*-
# # vi: set ft=ruby :

Vagrant.configure("2") do |config|

  if Vagrant.has_plugin? "vagrant-vbguest"
    config.vbguest.no_install = true
    config.vbguest.auto_update = false
    config.vbguest.no_remote = true
  end

  config.vm.define :servidorUbuntu do |servidorUbuntu|
    servidorUbuntu.vm.box = "bento/ubuntu-20.04"
    servidorUbuntu.vm.network :private_network, ip: "192.168.80.3"
    servidorUbuntu.vm.provision "chef_solo" do |chef|
      chef.arguments = "--chef-license accept"
      chef.log_level = "debug"
      chef.cookbooks_path = ["cookbooks"]
      chef.add_recipe "apache2"    
    end
  end
end