# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure('2') do |config|
  config.vm.box      = 'ubuntu/trusty64'
  config.vm.hostname = 'vagrant'

  config.vm.network :forwarded_port, guest: 3000, host: 3000

  config.vm.provision :shell, path: 'bootstrap.sh', keep_color: true

  config.vm.synced_folder '.', '/vagrant', type: 'rsync', rsync__exclude: ['.git/']

  # Add project file to user directory
  # config.vm.synced_folder ".", "/home/vagrant/project", type: "rsync",
  #   owner: "vagrant", group: "vagrant", rsync__exclude: [".git/"]

  config.vm.provider 'virtualbox' do |v|
    v.memory = 1024
    v.cpus = 2
  end
end
