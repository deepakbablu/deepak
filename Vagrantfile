Vagrant.require_version ">= 1.7.0"

Vagrant.configure(2) do |config|

  config.vm.box = "hashicorp/precise64"
  
  
  config.ssh.insert_key = false


  config.vm.define :DB do |cfg|
        cfg.vm.network :private_network, ip: "172.168.0.3"
        cfg.vm.provider :virtualbox do |v|
            v.name = "mqlDB"
        end
    end
    
  config.vm.define :App do |cfg|
        cfg.vm.network :private_network, ip: "172.168.0.2"
        cfg.vm.provider :virtualbox do |v|
            v.name = "flaskApp"
        end
    end

  config.vm.define :Web do |cfg|
        cfg.vm.network "forwarded_port", guest: 80, host: 9090
        cfg.vm.network :private_network, ip: "172.168.0.1"
        cfg.vm.provider :virtualbox do |v|
            v.name = "nginxWeb"
        end
    end

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "playbook.yaml"
    ansible.sudo = true
  end
end
