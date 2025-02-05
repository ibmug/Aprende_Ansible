# Laboratorio de Ansible 5 - Roles y Ansible Galaxy

ansible-galaxy permite que descargues roles y tambien provee un framework robusto para crear los roles propios.

## Cambiamos el Playbook para que use la funcionalidad de roles para configurar en apache2.

1. Use ansible-galaxy to create webserver role scaffolding
2. Move the tasks to the roles\webserver folder
3. Run playbook

### Create Apache2 Role, move tasks/handlers/templates to new roles/apache2 structure. Run playbook.

```shell
ansible-galaxy init roles/apache2
ansible-playbook -i hosts -K playbook1.yml
```

### Create a 'common' Role and add it to 'web', 'loadbalancer' and 'database' servers

1. Use ansible-galaxy to create nginx role scaffolding
2. Setup tasks/main.yml and tasks/install_tools.yml
3. Run playbook and test

```shell
ansible-galaxy init roles/nginx
ansible-playbook -i hosts -K playbook1.yml
```

### Create a nginx Role and setup the configuration

1. Use ansible-galaxy to create nginx role scaffolding
2. Setup tasks, handlers and templates

```shell
ansible-galaxy init roles/nginx
ansible-playbook -i hosts -K playbook1.yml
```
