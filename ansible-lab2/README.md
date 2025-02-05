# Laboratorio de Ansible 2 - Modulos y comandos

1. Usamos modulo APT para instalar servicios
2. Usamos el modulo de servicios para administrar los servicios.
3. Usamos ansible para reiniciar el webstack

### Usamos modulo APT para instalar servicios

https://docs.ansible.com/ansible/latest/modules/apt_module.html

```shell
ansible all -i hosts --become -m apt -a "update_cache=yes"
ansible webservers -i hosts --become -m apt -a "name=apache2 state=present"
ansible database -i hosts --become -m apt -a "name=mysql-server state=present"
```

### Usamos el modulo de servicios para administrar los servicios.(iniciar/reiniciar mysql)

https://docs.ansible.com/ansible/latest/modules/service_module.html

```shell
ansible database -i hosts -m service -a "name=mysql state=started"
ansible database --become -i hosts -m service -a "name=mysql state=restarted"
```

### Usamos ansible para reiniciar el webstack

```shell
ansible webstack -i hosts --become -a "reboot --reboot"
```
