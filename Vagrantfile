Vagrant.configure("2") do |config|
  config.vm.define "python-flask" do |server|
    server.vm.box = "bento/debian-11"

    server.vm.provider "parallels" do |prl|
      prl.name = "python-flask"
      prl.memory = 2048
      prl.cpus = 2
    end

    server.vm.network "private_network", ip: "192.168.18.10"
    server.vm.network "forwarded_port", guest: 8080, host: 8080    

    # Comandos como root
    server.vm.provision "shell", inline: <<-SHELL
      apt update
      apt upgrade -y
      apt install -y nginx gunicorn
      apt-get update && sudo apt-get install -y python3-pip
      sudo mkdir -p /var/www/app
      sudo chown -R $USER:www-data /var/www/app
      sudo chmod -R 775 /var/www/app



    SHELL

    # Comandos como vagrant
    server.vm.provision "shell", privileged: false, inline: <<-SHELL
      pip3 install pipenv
      PATH=$PATH:/home/$USER/.local/bin
      pip3 install python-dotenv
      cp /vagrant/config/.env /var/www/appp
      cd /var/www/app
      pipenv shell
      pipenv install flask gunicorn
      cp /vagrant/config/applicacion.py /var/www/app/
      cp /vagrant/config/wsgi.py /var/www/app/

    SHELL
    
  end
end
