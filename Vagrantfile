Vagrant.configure("2") do |config|

    config.vm.box = "jsantiago/trusty64"

    # docker registry
    config.vm.network :forwarded_port, guest: 5000, host: 5000

    # shipyard
    config.vm.network :forwarded_port, guest: 8000, host: 8000

    config.vm.provider "virtualbox" do |v|
        v.destroy_unused_network_interfaces = true
        v.memory = 2048
        v.cpus = 4
    end

end
