# Laboratorio de Ansible 9 - Agregar el servidor de base de datos.

Hemos aprendido mucho hasta ahora, pongamos todo eso en practica para agregar un rol de mysql y levantar una base de datos.

## Configuremos mysql-server en el servidor de BdD.

1. Agreguemos python-pip a los items comunes de instalacion.
2. Creamos el rol de mysql usando ansible-galaxy.
3. Creamos una tarea y sus handles para el rol de mysql.
4. Ejecutamos el playbook.
5. Probamos una conexion sql a la base de datos.

```shell
ansible-galaxy init roles/mysql
ansible-playbook -i inventories/prod -K playbook1.yml --tags database
ssh db01
sudo /usr/bin/mysql -u root -p
```
