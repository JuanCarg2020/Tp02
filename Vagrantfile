Vagrant.configure("2") do |config|
  # Configurar la box de Debian
  config.vm.box = "bento/debian-12"

  # le pone el Nombre "Atenas" a la máquina virtual y configura la memoria
  config.vm.provider "virtualbox" do |vb|
    vb.name = "Atenas"
    vb.memory = "4096"
  end

  
  config.vm.provision "shell", inline: <<-SHELL
    # Actualiza 
    sudo apt-get update
    sudo apt-get upgrade -y
    sudo apt-get install -y apt-transport-https ca-certificates curl gnupg lsb-release
    #segui la documentacion oficial
    # Elimina cualquier versión anterior de Docker
    sudo apt-get remove -y docker.io docker-doc docker-compose podman-docker containerd runc

    # Agrega la clave GPG oficial de Docker
    sudo install -m 0755 -d /etc/apt/keyrings
    curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker-archive-keyring.gpg

    # Agrega el repositorio de Docker a las fuentes de apt
    echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

    # Actualiza 
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
    mkdir -p /home/vagrant/wordpress
    cd /home/vagrant/wordpress
    curl -L -o docker-compose.yml https://raw.githubusercontent.com/JuanCarg2020/Tp02/main/docker-compose.yml

    # crea un directorio ingresa a ese directorio que esta el ym y comienza la instalacion completa
   cd /home/vagrant/wordpress 
  sudo docker compose up -d 

sudo docker start wordpress
sudo docker start mariadb
  SHELL
end