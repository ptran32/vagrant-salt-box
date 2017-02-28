#OS:

Ubuntu 16.04

#What this box do ?

Install a VM vagrant with a minion installed.
This minion will listen to your localhost guest
The guest folders will be mount on /srv/salt and /srv/pillar

#Requirements:

Install Vagrant
Install Salty Vagrant (vagrant plugin install vagrant-salt)
Install Vbox Addition to grant shared folder betwwen guest OS and vagrantbox
(vagrant plugin install vagrant-vbguest)

#Bug
I get a bug on Ubuntu 16.04 that break the plugin install command.
I Modified the ruby file (/usr/lib/ruby/vendor_ruby/vagrant/bundler.rb) regarding the following workaround on github (https://github.com/mitchellh/vagrant/commit/ba77d4b533e449fa610531a7832b8fd1837eb9db)

#How to use this box ?

vagrant ssh 
sudo salt-call state.highstate [Execute all states]
sudo salt-call state.sls apache2 [Execute one state]
