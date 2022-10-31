Vagrant.configure("2") do |config|

  config.vm.define "windows10" do |win10|
    win10.vm.box = "gusztavvargadr/visual-studio"
    win10.vm.network "private_network", ip: "10.0.0.10"
    win10.ssh.forward_agent = true
    win10.vm.boot_timeout = 60
    win10.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.cpus = 1
    end
  end

  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.box = "ubuntu/trusty64"
    ubuntu.vm.network "private_network", ip: "10.0.0.20"
    ubuntu.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.cpus = 1
    end
    ubuntu.vm.provision "shell", inline: <<-SHELL
      apt-get upgrade
      sudo apt install apache2 -y
    SHELL
  end

  config.vm.define "centos" do |centos|
    centos.vm.box = "generic/centos7"
    centos.vm.network "private_network", ip: "10.0.0.30"
    centos.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 1
    end
  end
end