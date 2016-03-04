$script = <<SCRIPT
    locale-gen en_GB.UTF-8
    apt-get --assume-yes update
    apt-get --assume-yes dist-upgrade
    apt-get --assume-yes install python3-pip

    pip3 install -r requirements.txt
SCRIPT

Vagrant.configure(2) do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.network "private_network", ip: "192.168.33.27"
    config.vm.provision "shell", inline: $script
end
