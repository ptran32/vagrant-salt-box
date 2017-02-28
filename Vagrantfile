# -*- mode: ruby -*-
# vi: set ft=ruby :

 
VAGRANTFILE_API_VERSION = "2"

  Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    ## Choose your base box
    config.vm.box = "debian/wheezy64"

    ## Choose Node Name
    config.vm.hostname = "saltbox"

    ## For masterless, mount your salt file root and pillar
    config.vm.synced_folder "~/git/vagrant-salt-box/salt/roots", "/srv/salt/"
   config.vm.synced_folder "~/git/vagrant-salt-box/salt/pillar", "/srv/pillar/"
    ## Use all the defaults:
    config.vm.provision :salt do |salt|
      salt.masterless = true
      salt.minion_config = "salt/minion"
      salt.run_highstate = true

    end
  end
