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

    server.vm.provision "shell", inline: <<-SHELL
      apt update
      apt upgrade -y
      apt install -y python3-pip nginx

      systemctl enable nginx
      systemctl start nginx

      mkdir -p /var/www/app
      chown -R vagrant:www-data /var/www/app
      chmod -R 775 /var/www/app



    SHELL

    server.vm.provision "shell", privileged: false, inline: <<-SHELL
     export PATH="$HOME/.local/bin:$PATH"
      echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc

      pip3 install --user pipenv
      pip3 install --user python-dotenv

      cd /var/www/app

      cp /vagrant/config/.env /var/www/app/.env

      pipenv install flask gunicorn

      cp /vagrant/config/application.py /var/www/app/
      cp /vagrant/config/wsgi.py /var/www/app/

    SHELL
    
  end
end
