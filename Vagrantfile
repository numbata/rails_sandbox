# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  config.vm.box = "rails_sanbox"
  config.vm.box_url = "https://dl.dropbox.com/u/1543052/Boxes/UbuntuServer12.04amd64.box"

  #config.vm.network :hostonly, "192.168.1.15"
  config.vm.network :bridged
  config.vm.customize ["modifyvm", :id, "--memory", 1536]

  config.vm.forward_port 80, 8085

  config.vm.share_folder "apps", "/apps", "/apps"

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = ["cookbooks", "my-cookbooks"]
    chef.roles_path = "roles"
    chef.add_role "sandbox"
  end

end
