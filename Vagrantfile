# -*- mode: ruby -*-
# vi: set ft=ruby :
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = 'bento/ubuntu-18.04'
    config.vm.box_version = '201807.12.0'

    (1..3).each do |i|
        config.vm.define "webserver0#{i}" do |host|
            host.vm.hostname = "webserver0#{i}.local"
            host.vm.network 'private_network', ip: "192.168.56.10#{i}"
            host.vm.network 'forwarded_port', guest: '80', host: "1808#{i}"

            host.vm.provider 'virtualbox' do |v|
                v.memory = '512'
                v.cpus   = '1'
                v.name   = "Web Server 0#{i}"
            end
        end
    end
end
