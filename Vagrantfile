# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "demo" , primary: true do |demo|
    demo.vm.box = "centos-6.6-x86_64"
    demo.vm.box_url = "https://dl.dropboxusercontent.com/s/ijt3ppej789liyp/centos-6.6-x86_64.box"

    demo.vm.hostname = "demo.example.com"
    demo.vm.synced_folder ".", "/vagrant", :mount_options => ["dmode=777","fmode=777"]

    demo.vm.network :private_network, ip: "10.10.10.8"

    demo.vm.provision :shell, :inline => "ln -sf /vagrant/puppet/hiera.yaml /etc/puppet/hiera.yaml;rm -rf /etc/puppet/modules;ln -sf /vagrant/puppet/modules /etc/puppet/modules; rm -rf /var/lib/hiera; ln -sf /vagrant/puppet/hieradata /var/lib/hiera"

  end

end
