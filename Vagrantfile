# -*- mode: ruby -*-
# vi: set ft=ruby :
targets = [
    {
        :hostname => "host1",
        :box => "bento/centos-7.1",
        :ram => 512,
        :cpu => 1
    },
    {
        :hostname => "host2",
        :box => "bento/ubuntu-16.04",
        :ram => 512,
        :cpu => 1
    }
]

Vagrant.configure("2") do |config|
    targets.each do |target|
        config.vm.define target[:hostname] do |node|
            node.vm.box = target[:box]
            node.vm.hostname = target[:hostname]
            node.vm.network "public_network", ip: target[:ip]
            node.vm.synced_folder ".", "/vagrant", disabled: true
            node.vm.provider "vmware_fusion" do |vb|
                vb.vmx["memsize"] = target[:ram]
                vb.vmx["numvcpus"] = target[:cpu]
            end #node.vm.provider
        end #config.vm.define
    end #targets.each
end #Vagrant.configure