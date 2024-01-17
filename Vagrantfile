#export VAGRANT_WSL_WINDOWS_ACCESS_USER_HOME=/mnt/c/Users/migue
#export VAGRANT="$PATH:/mnt/c/Program Files/Oracle/VirtualBox"
#export VAGRANT_WSL_ENABLE_WINDOWS_ACCESS="1"
Vagrant.configure("2") do |config|
    config.vm.box = "precise32"
    config.vm.hostname = "myprecise.box"
    config.vm.network :private_network, ip: "192.168.0.42"
  
    config.vm.provider : "virtualbox" do |vb|
      vb.customize [
        "modifyvm", :id,
        "--cpuexecutioncap", "50",
        "--memory", "256",
      ]
    end