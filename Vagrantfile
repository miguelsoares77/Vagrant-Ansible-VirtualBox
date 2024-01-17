# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
    config.vm.define "master" do |subconfig|
        subconfig.vm.box = "generic/ubuntu2004"
        subconfig.vm.hostname = "master"
        subconfig.vm.provider "virtualbox"
        subconfig.vm.network "public_network", bridge: "BRIDGE"

        subconfig.vm.provider "virtualbox" do |h|
            h.enable_virtualization_extensions = false
            h.linked_clone = false
            h.vmname = "ubuntu_cluster_master"
        end

        subconfig.vm.provision "ansible" do |a|
            a.verbose = "v"
            a.playbook = "master_playbook.yaml"
        end
    end
end