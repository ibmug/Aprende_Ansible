# Ansible Lab 1 - Instalacion y basicos de los archivos de inventario.

1. Crear las maquinas usando vagrant y hacer ssh a nuestra torre de control.
2. Copiar /vagrant/hosts_file a /etc/hosts
3. Instalamos ansible
4. Creamos un archivo inventory y lo llamamos hosts
5. Probamos
6. Generamos SSH Keys y las copiamos a los hosts
7. Probamos la configuracion corriendo comandos usando los hosts
8. Instalamos python-simplejson. Esto permite que los clientes sean administrados completamente.

### Crear las maquinas usando vagrant y hacer ssh a nuestra torre de control.

```shell
 vagrant up
 vagrant ssh ansible-control
```

### Copiar /vagrant/hosts_file a /etc/hosts

```shell
cp /vagrant/hosts_file /etc/hosts
```

### Creamos un archivo inventory y lo llamamos hosts

```shell
 sudo apt-get install ansible
```

### Generamos SSH Keys y las copiamos a los hosts

```shell
ssh-keygen
ssh-copy-id localhost
ssh-copy-id web01 && ssh-copy-id web02 && ssh-copy-id loadbalancer && ssh-copy-id db01
```

### Probamos la configuracion corriendo comandos usando los hosts

```shell
ansible webstack -i hosts -m command -a hostname
```

### Instalamos python-simplejson

```shell
ansible all -i hosts -m command -a 'sudo apt-get -y install python-simplejson'
```
