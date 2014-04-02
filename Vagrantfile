# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # current のほうがいいかも?
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/saucy/20140402/saucy-server-cloudimg-amd64-vagrant-disk1.box"
  config.vm.box = "saucy-20140402"
  config.vm.hostname = 'vagrant-rails'

  config.vm.provision "ansible" do |ansible|
    ansible.inventory_path = "vagrant_hosts"
    ansible.limit = 'all'
    ansible.playbook = "vagrant.yml"
  end

  config.vm.network "private_network", ip: "192.168.99.10"
end
