# Ansible Lab 6 - Using Tags

Tags allow you to categorize items in your playbooks and tasks.

1. Usamos --list-tags para ver los tags que estan habilitados.
2. Empezamos a agregar etiquetas(tags) al playbook y a las tareas. Usaremos el keyword de 'always'para tareas comunes de copiar el archivo de host.
3. Revisamos los tags que imlpementamos y empzamos con tag inheritance.
4. Corremos el playbook usando tags para solo ejecutar ciertos items

## Revisamos los tags

```shell
ansible-playbook -i hosts -K playbook1.yml --list-tags
```

## Ejecutemos el playbook para tags especificos

```shell
ansible-playbook -i hosts -K playbook1.yml --tags configuration
ansible-playbook -i hosts -K playbook1.yml --tags proxy
```

### Notas:

Tags usan la logica de "OR", no la de "AND". Si alguno de tus tags es igual a lo que solicitaste, el item correra. Uno deberia de usar tags especificos para casos especificos...

Tags especiales: always, never. Significando "always"(siempre) ejecutalo o "never"(nunca) ejecutar a menos que sea explicitamente solicitado.
keywords de tags especiales: tagged, untagged and all. Por default, ejecutamos los playbooks con -tags all
