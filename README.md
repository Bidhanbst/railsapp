# Reproduction Steps for Vagrant setup
Before starting, We need to install virtualbox, ansible and vagrant on our local computer to work with vagrant.
1. To run Ansible against your Vagrant guest, the basic Vagrantfile configuration looks like:
```
Vagrant.configure("2") do |config|
config.vm.box = "hashicorp/bionic64"
config.vm.box_version = "1.0.282"
config.vm.provision "ansible" do |ansible|
  ansible.playbook = "playbook.yml"
 end
 end
```
2. Save this configuration file on the host and on that directory open terminal and run the following command.
```
$ vagrant up
```
- This will start the VM, and run the provisioning playbook (on the first VM startup).
- To re-run a playbook on an existing VM, just run:
```
$ vagrant provision
```
3. Now your VM is ready for use.


# Reproduction Steps for Ansible
1. Install Ansible on your host machine.
2. First, create a project folder and add the configuration files for the playbook.
3. Specify the playbook file to run in vagrant configuration file.
```
config.vm.provision "ansible" do |ansible|
  ansible.playbook = "playbook.yml"
 end
```
4. Running the above vagrant config file will automatically run the provisioning playbook on that vagrant host.
5. In case of running ansible playbook manually, create a file vagrant-hosts to specify the target nodes where playbooks are intended to run.
6. To run ansible manually apply the following command on the project directory.
```
$ ansible-playbook -i vagrant-hosts vagrant.yaml -vvv
```
