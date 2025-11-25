## 1 Creamos un VagrantFile le ponemos lo siguiente 
```
    Vagrant.configure("2") do |config|


  config.vm.box = "debian/bullseye64"

  # --- Red privada ---
  config.vm.network "private_network", ip: "192.168.56.21"

  # --- Nombre de la máquina ---
  config.vm.hostname = "PabloNgix-test"

  # --- Provisionamiento automático ---
  config.vm.provision "shell", path: "provision.sh"

end
```

## 2 Creamos un Provision.sh y ponemos lo siguiente es para actualizar y intalar Ngix
```
    echo "==> Actualizando repositorios"
apt update -y

echo "==> Instalando Nginx"
apt install nginx -y

echo "==> Instalando Git"
apt install git -y
```
