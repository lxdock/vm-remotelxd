# -*- mode: ruby -*-
# vi: set ft=ruby :

$script = <<SCRIPT
sudo add-apt-repository -y ppa:ubuntu-lxc/lxd-stable
sudo apt-get update
sudo apt-get install -y lxd
newgrp lxd
sudo lxd init --auto
lxc network create lxdbr0 ipv6.address=none ipv4.address=10.0.3.1/24 ipv4.nat=true
lxc network attach-profile lxdbr0 default eth0
lxc config set core.https_address [::]:8443
lxc config set core.trust_password INSECURE
SCRIPT

Vagrant.configure(2) do |config|
  config.vm.box = 'bento/ubuntu-16.04'
  config.vm.network :private_network, ip: '172.48.127.10'
  config.vm.provision 'shell', inline: $script
end
