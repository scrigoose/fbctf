# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  #config.proxy.http     = "http://10.144.1.10:8080"
  #config.proxy.https    = "http://10.144.1.10:8080"
  #config.proxy.no_proxy = "localhost,127.0.0.1"
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "private_network", ip: "10.10.10.5"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 443, host: 8443
  config.vm.synced_folder "../share", "/opt/scripts"
  config.vm.hostname = "facebookCTF-Dev"
  config.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"
  config.vm.provision "shell", path: "extra/provision.sh", privileged: false
  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 4
  end
end
