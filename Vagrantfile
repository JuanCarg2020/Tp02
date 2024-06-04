Vagrant.configure("2") do |config|
  # Configurar la box de Debian
  config.vm.box = "bento/debian-12"

<<<<<<< HEAD
  # le pone el nombre "Atenas" a la máquina virtual y configura la memoria
=======
  # Nombre "Atenas" a la máquina virtual y configurar la memoria
>>>>>>> fcbfe61126bc04c14fda6246fe49108430b15dd4
  config.vm.provider "virtualbox" do |vb|
    vb.name = "Atenas"
    vb.memory = "4096"
  end

<<<<<<< HEAD
  # actualiza el so e instala Docker
=======
  # Provisión para actualizar el sistema e instalar Docker
>>>>>>> fcbfe61126bc04c14fda6246fe49108430b15dd4
  config.vm.provision "shell", inline: <<-SHELL
    # Actualizar los paquetes e instalar dependencias necesarias
    sudo apt-get update
    sudo apt-get upgrade -y
    sudo apt-get install -y apt-transport-https ca-certificates curl gnupg lsb-release

<<<<<<< HEAD
    # Elimina cualquier versión anterior de Docker
    sudo apt-get remove -y docker.io docker-doc docker-compose podman-docker containerd runc

    # Agrega la clave GPG oficial de Docker
    sudo install -m 0755 -d /etc/apt/keyrings
    curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker-archive-keyring.gpg

    # Agrega el repositorio de Docker a las fuentes de apt
    echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

    # Actualiza el índice del paquete apt nuevamente
  sudo apt-get update

    # Instala Docker
    sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

    # Agrega el usuario vagrant al grupo de Docker para poder ejecutar Docker sin sudo
    sudo usermod -aG docker vagrant

    # Crea una red Docker llamada red01
    sudo docker network create red01

    # Ejecuta un contenedor de prueba
    sudo docker run hello-world

    # Crea el directorio wordpress y descargar el archivo docker-compose.yml
=======
    # Eliminar cualquier versión anterior de Docker
    sudo apt-get remove -y docker.io docker-doc docker-compose podman-docker containerd runc

    # Agregar la clave GPG oficial de Docker
    sudo install -m 0755 -d /etc/apt/keyrings
    curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker-archive-keyring.gpg

    # Agregar el repositorio de Docker a las fuentes de apt
    echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

    # Actualizar el índice del paquete apt nuevamente
  sudo apt-get update

    # Instalar Docker
    sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

    # Agregar el usuario vagrant al grupo de Docker para poder ejecutar Docker sin sudo
    sudo usermod -aG docker vagrant

    # Crear una red Docker llamada red01
    sudo docker network create red01

    # Ejecutar un contenedor de prueba
    sudo docker run hello-world

    # Crear el directorio wordpress y descargar el archivo docker-compose.yml
>>>>>>> fcbfe61126bc04c14fda6246fe49108430b15dd4
    mkdir -p /home/vagrant/wordpress
    cd /home/vagrant/wordpress
    curl -L -o docker-compose.yml https://raw.githubusercontent.com/JuanCarg2020/Tp02/main/docker-compose.yml

<<<<<<< HEAD
    # Levanta los contenedores con Docker Compose
=======
    # Levantar los contenedores con Docker Compose
>>>>>>> fcbfe61126bc04c14fda6246fe49108430b15dd4
   cd /home/vagrant/wordpress 
  sudo docker compose up -d 

sudo docker start wordpress
sudo docker start mariadb
  SHELL
end
