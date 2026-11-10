Vagrant.configure("2") do |config|
  # rokcy linux 9 fully compatible with RHEL 9/10
  # config.vm.box = "rockylinux/9"
  config.vm.box = "rockylinux-10-local"
  config.vm.box_url = "https://dl.rockylinux.org/pub/rocky/10/images/x86_64/Rocky-10-Vagrant-Vbox.latest.x86_64.vagrant.virtualbox.box"

  # private network
  config.vm.network "private_network", ip: "192.168.56.15"

  # provider settings
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048" # 2 GB de RAM es ideal para pruebas
    vb.cpus = 2
    vb.name = "node_master"
  end

  # automate provisioning with Ansible
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    # Avoid common SSH key permission issues in test environments
    ansible.compatibility_mode = "2.0"
  end
end
