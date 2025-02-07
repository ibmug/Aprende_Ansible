# Laboratorio de Ansible 8 - Crear un archivo para Development/Production

Uno puede tener distintos sets de inventarios. Hagamos uno para produccion y uno para development y darles variables.

## Reunamos los detalles de ansible, estos son variables dynamicas que se reunen automaticamente con ansible.

1. Creamos el directorio de inventario.
2. Creamos un archivo de inventario para dev y para prod.
3. Fijamos una varaible de ambiente y ejecutamos el playbook.

```shell
ansible-playbook -i inventories/dev -K playbook1.yml
ansible-playbook -i inventories/prod -K playbook1.yml
```
