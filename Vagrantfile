# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config| #vagrant api/syntax def

machines = {
  "ConsulServer" => {  :ip => "192.168.56.2", :mem => 1024 },
  "ConsulClient" => { :ip => "192.168.56.3", :mem => 2048 },
  "AnsibleMaster" => { :ip => "192.168.56.4", :mem => 2048 }
  }

machines.each_with_index do |(hname, info), index|
  config.vm.define hname do |cfg|
    cfg.vm.provider "virtualbox" do |vb,override|
      config.vm.box = "ubuntu/bionic64"
      override.vm.network :private_network, ip: "#{info[:ip]}"
      override.vm.hostname = hname
      vb.name = hname
      vb.memory =  "#{info[:mem]}"
    end #end vm prov
  end #end vm cfg
 end #end machines
end
