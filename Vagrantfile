Vagrant.configure("2") do |config|

  config.vm.box = "hashicorp/bionic64"
  config.vm.box_version = "1.0.282"
  config.vm.provision "ansible" do |ansible|
  ansible.playbook = "playbook.yaml"
 end
end
