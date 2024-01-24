# Setup Guide for Mac Silicon Users

Currently, VirtualBox does not have a production-ready release for arm and also there are no arm releases for P4 binaries. 
So, to setup an Ubuntu VM and use P4 compiler on the Mac Silicon computers you need to:
- Use VMWare Fusion for creating VMs
- Build the P4 binaries on an arm VM

## Setup Guide

1. Install [VMware](https://www.vmware.com/ca/products/fusion/fusion-evaluation.html)
1. Install [Vagrant](https://developer.hashicorp.com/vagrant/install?product_intent=vagrant)
1. Install Vagrant VMware provider:
```
brew install --cask vagrant-vmware-utility
vagrant plugin install vagrant-vmware-desktop
```

4. Set the following environment variable in your shell so that `arm.Vagrantfile` is used:
```
export VAGRANT_VAGRANTFILE=silicon.Vagrantfile
```

Now you can continue the tutorial from starting from `vagrant up`.


> Use this [guide](https://gist.github.com/sbailliez/2305d831ebcf56094fd432a8717bed93) if you encountered problems when installing VMware or Vagrant

> Since there is no release of P4 compiler and runtime binary files for arm, they are built from source code on the VM so, the executing the `vagrant up` takes much longer (about an hour on a Mac with M1 Pro).