# -*- mode: ruby -*-
# vi: set ft=ruby :
targets = [
    {
        :hostname => "host1",
        :box => "bento/centos-7.1",
        :ram => 1024,
        :cpu => 2
    },
    {
        :hostname => "host2",
        :box => "bento/ubuntu-16.04",
        :ram => 1024,
        :cpu => 2
    }
]

Vagrant.configure("2") do |config|
    targets.each do |target|
        config.vm.define target[:hostname] do |node|
            node.vm.box = target[:box]
            node.vm.hostname = target[:hostname]
            node.vm.synced_folder ".", "/vagrant", disabled: true
            node.vm.provider "vmware_fusion" do |vb|
                vb.vmx["memsize"] = target[:ram]
                vb.vmx["numvcpus"] = target[:cpu]
            end #node.vm.provider
        end #config.vm.define
    config.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/authorized_keys"  # replace with your key
    end #targets.each
end #Vagrant.configure