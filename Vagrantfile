Vagrant::Config.run do |config|
  config.vm.box = "precise64"

  config.vm.forward_port 3000, 3000

  config.vm.share_folder "app", "/home/vagrant/app", "app"

  # allow for symlinks in the app folder
  
  config.vm.customize [
      "setextradata", 
      :id, 
      "VBoxInternal2/SharedFoldersEnableSymlinksCreate/app", 
      "1"
  ]
  
  config.vm.customize [
      "modifyvm", 
      :id, 
      "--memory", 512, 
      "--cpus", 1
  ]

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = "cookbooks"
    chef.add_recipe "apt"
    chef.add_recipe "build-essential"
    chef.add_recipe "git"
    chef.add_recipe "nodejs"
    chef.add_recipe "mongodb"

    chef.json = {
      "nodejs" => {
        "version" => "0.10.0"
#        "install_method" => "source",
#        "npm" => "1.2.14"
      }
    }
  end
end
