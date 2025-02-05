# Laboratorio de Ansible 3 - Playbooks y Planillas

1. Revisamos los detalles del archivo YAML en uno ya creado.
2. Creamos una planilla(template)
3. Corremos el playbook
4. Probamos

### Corramos el playbook ya existente para analizar los detalles.

```shell
ansible-playbook -i hosts -K playbook1.yml
```

### Probamos conexion.

```shell
curl web01:8000
```
