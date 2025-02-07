# Laboratorio de Ansible 7 - Variables

Existen dos tipos de variables. Las definidas por usuario y 'ansible facts'

## Reunamos los ansible facts, estos son variables dinamicas que se reunen automaticamente por Ansible.

1. Usamos el modulo de setup para reunir estos detalles del sistema.
2. Observamos el resultado y descubrimos informacion util.
3. Usamos {{ ansible_facts['nodename'] }} para la variable de localhost 'nodename'. Agregamos esto al index.html.
4. Usamos un loop para accesar dinamicamente el nombre del nodo de los dos webservers. Agregamos esto a la configuracion de mysite del servidor proxy nginx.

```shell
ansible -i hosts proxy -m setup >> ansible_facts.json
{{ ansible_facts['nodename'] }}

	{% for host in groups['webservers'] %}
        server {{ hostvars[host]['ansible_facts']['nodename'] }}:8000;
    {% endfor %}
```

## Movemos las variables definidas por el usuario a una locacion distinta.

1. Movemos nuestras variables actuales a group_vars/all variables.
2. Agregamos estas variables a la configuracion de mysite de nginx.
3. Creamos el folder host_vars y lo hacemos una variable unica para web01.
