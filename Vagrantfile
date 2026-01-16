Vagrant.configure("2") do |config|
  config.vm.define "python-flask" do |server|
    server.vm.box = "bento/debian-11"

    server.vm.provider "parallels" do |prl|
      prl.name = "python-flask"
      prl.memory = 2048
      prl.cpus = 2
    end

    server.vm.provision "shell", path: "provisional.sh"

    server.vm.network "private_network", ip: "192.168.18.10"
    server.vm.network "forwarded_port", guest: 8080, host: 8080
  end
end
