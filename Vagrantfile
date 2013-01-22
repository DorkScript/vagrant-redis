# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"
  config.vm.network :hostonly, "192.168.2.2"

  config.vm.provision :chef_solo do |chef|
     chef.cookbooks_path = "cookbooks"
     chef.add_recipe "redis::source"
     chef.log_level = :debug
     chef.json = { 
        'redis' => {
          'bind' => nil,
          'port' => "6379",
        }
      }
  end
end