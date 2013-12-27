# -*- mode: ruby -*-
# vi: set ft=ruby :

$init = <<SCRIPT
if [ ! -f ~/runonce ]
then
  ## Init
  aptitude install -yq git

  ## Mininet, POX, OVSK, Wireshark dissector
  git clone git://github.com/mininet/mininet
  sudo -iu vagrant mininet/util/install.sh -a

  touch ~/runonce
fi
SCRIPT

Vagrant.configure("2") do |config|
  ## Box definition
  config.vm.box = "raring64"
  config.vm.box_url = "http://cloud-images.ubuntu.com/raring/current/raring-server-cloudimg-vagrant-amd64-disk1.box"
  #config.vm.box = "raring32"
  #config.vm.box_url = "http://cloud-images.ubuntu.com/raring/current/raring-server-cloudimg-vagrant-i386-disk1.box"

  ## VM config (optional)
  #config.vm.provider "virtualbox" do |v|
  #    v.gui = true
  #    v.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
  #    v.customize ["modifyvm", :id, "--memory", "2048"]
  #end

  ## Guest config
  config.vm.hostname = "mininet"
  config.vm.network :private_network, ip: "192.168.33.253"

  ## Provisioning
  config.vm.provision :shell, :inline => $init

  ## SSH config
  config.ssh.forward_x11 = true

end
