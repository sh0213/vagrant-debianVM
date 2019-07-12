Vagrant.configure("2") do |config|
  config.vm.box = "debian/contrib-testing64"
  config.vm.box_version = "2018.06.04"
  config.disksize.size = "12GB"
  config.vm.box_download_insecure = true

  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
  end

  config.vm.synced_folder ".", "/vagrant", disabled: false
  config.ssh.forward_x11 = true

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.verbose = "true"
    ansible.compatibility_mode = "2.0"
  end
end
