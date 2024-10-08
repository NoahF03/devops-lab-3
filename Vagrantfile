Vagrant.configure("2") do |config|
  config.vm.box = "archlinux/archlinux"
  
  config.vm.network "forwarded_port", guest: 5000, host: 8080
  
  config.vm.provision "file", source: "hello.py", destination: "/home/vagrant/hello.py"
  
  config.vm.provision "shell", inline: <<-SHELL
    sudo pacman -Syu --noconfirm git nano vim python python-virtualenv python-pip
    python -m venv flask_venv
    # Activate the virtual environment and install Flask in a single command
    flask_venv/bin/pip install Flask
  SHELL
end
