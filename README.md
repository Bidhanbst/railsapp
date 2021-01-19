# Reproduction Steps
Before starting, We need to install virtualbox and vagrant on our local computer to work with vagrant.
1. To run Ansible against your Vagrant guest, the basic Vagrantfile configuration looks like:

>Vagrant.configure("2") do |config|
> #
> # Run Ansible from the Vagrant Host
> #
>config.vm.box = "hashicorp/bionic64"
>config.vm.box_version = "1.0.282"
>config.vm.provision "ansible" do |ansible|
>  ansible.playbook = "playbook.yml"
> end

> end
