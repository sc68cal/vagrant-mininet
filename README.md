# vagrant-mininet

Vagrant recipe that automates [Mininet's Native Installation from
Source option][NativeInstall], in order to complete the [OpenFlow
Tutorial][OpenFlowTutorial].

# Why

Because the images that Mininet has on their download page are broken.

* 2.1.0 has a broken VMDK image, and will not import into Virtualbox
* 2.0.0 boots in VirtualBox, but requires manual set up for the second
  interface - which Vagrant does for you. So why not automate the whole
  thing?

[NativeInstall]: http://mininet.org/download/
[OpenFlowTutorial]: http

## Usage

You have to have VirtualBox and Vagrant installed. Next, download the
Vagrantfile and run `vagrant up` from the folder it is located.

After the script finishes its job, `vagrant ssh` should provide you the
VM terminal. Windows users may want to install `msysgit` distribution for a
seamless ssh experience.
