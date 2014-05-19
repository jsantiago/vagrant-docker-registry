CONFIG = "config.rb"

if File.exists?(CONFIG)
    require_relative CONFIG
end

Vagrant.configure("2") do |config|

    config.vm.box = "jsantiago/trusty64"

    if $synced_folders
        $synced_folders.each { |host, guest|
            config.vm.synced_folder "#{host}", "#{guest}"
        }
    end

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
