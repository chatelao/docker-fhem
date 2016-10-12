
Vagrant.configure("2") do |config|
  config.vm.box = "minimal/trusty64"
  config.vm.provider "virtualbox" do |vb|
        vb.memory = "4096"
        vb.cpus   = 3
        vb.customize ["modifyvm", :id, "--cpuexecutioncap", "70"]        
  end
  config.vm.network "forwarded_port", guest: 8083, host: 8083

  config.vm.provision :docker
  config.vm.provision :docker_compose, yml: "/vagrant/docker-compose.yml", run: "always"
end