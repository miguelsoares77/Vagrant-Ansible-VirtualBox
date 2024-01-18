#export VAGRANT_WSL_WINDOWS_ACCESS_USER_HOME=/mnt/c/Users/migue
#export VAGRANT="$PATH:/mnt/c/Program Files/Oracle/VirtualBox"
#export VAGRANT_WSL_ENABLE_WINDOWS_ACCESS="1"
Vagrant.configure("2") do |config|
  config.vm.define "master" do |subconfig|
    subconfig.vm.box = "generic/ubuntu2004"
    subconfig.vm.hostname = "master"
    subconfig.vm.provider "virtualbox"
    subconfig.vm.network "public_network", bridge: "BRIDGE"

    subconfig.vm.provider "virtualbox" do |h|
    #       h.enable_virtualization_extensions = false
            h.linked_clone = false
    #       h.vmname = "ubuntu_cluster_master"
    end

    subconfig.vm.provision "ansible" do |a|
    a.verbose = "v"
    a.playbook = "master-playbook.yaml"
  end
end
end