# Declaring VirtualBox provider
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'virtualbox'

# Variables
VAGRANTFILE_API_VERSION = 2
net_ip = "192.168.100"
distro_fedora = "fedora/32-cloud-base"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define "docker1" do |docker1|
    vmname = "docker1"

    docker1.vm.box = "#{distro_fedora}"
    docker1.vm.hostname = "#{vmname}"

    docker1.vm.network :private_network, ip: "#{net_ip}.101"
    # We'll enable as we begin to build out web server functionality
    docker1.vm.network :forwarded_port, guest: 80, host: 8080

    docker1.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 1024]
      v.customize ["modifyvm", :id, "--name", "#{vmname}"]
    end

    config.vm.provision "ansible" do |a|
      a.playbook = "create.yml"
      a.extra_vars = { 
        ansible_python_interpreter: "/usr/bin/python3",
        server_hostname: "#{vmname}"
      }
    end
  end
end
