deep-security-local-demo
======
Ansible playbook to create a local DSM linux demo environment with Vagrant.

#Requirements
Ansible
Vagrant
VirtualBox


## Usage

Initial TODOs
1. update ds.properties with you license key, username, and password
2. update setup-dsm.yml with the location to the DSM linux installer Manager-Linux-9.6.3177.x64.sh.
   The playbook is currently set up to locate this file in the files dir.

```code

  ##Step 1
  vagrant init centos64-x86_64-20140116

  ##Step 2
  Then add the following to your Vagrantfile:

  #adapter 1 defaults to NAT. Adapter 2 is set as host only to allow access to guest from host.
  config.vm.network "private_network", ip: "10.0.0.8", adapter: 2

  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
  end


  ##Step 3
  Vagrant up

  ##Step 4
  ansible-playbook setup-dsm.yml


  ##Step 5
  your are done nooo. use "vagrant ssh" to access your environment


```
