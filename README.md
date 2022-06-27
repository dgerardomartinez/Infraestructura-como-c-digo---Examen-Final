## EJERCICIO TERRAFORM
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Antes de iniciar hay que tener instalado lo siguiente en la maquina host:
    +[Terraform v0.12.0]
    +[provider.digitalocean v1.3.0]

# Clone this repository
```
git clone https://github.com/dgerardomartinez/Infraestructura-como-c-digo---Examen-Final.git
```
# Token Digital Ocean y SSH KEY

Para provisionar aplicaciones y cración de droplets se debe tener una cuenta en Digital Ocean y generar el TOKEN: https://cloud.digitalocean.com/account/api/tokens 

Para generar una key ssh en el host debemos crearla con el siguiente comando:

    1. "ssh-keygen" y guardamos en una carpeta con un nombre especifico (C:\Users\DenisG Martinez/.ssh/id_rsa)
    2. Con el comando "cat ~/.ssh/id_rsa.pub" podremos ver la key en nuestro host después agregar la ssh key en Digital Ocean : https://cloud.digitalocean.com/account/security?i=33f45d se agregar una key.pub.


-Se utilizará un archivo de variables vagrant.tfvars (Está en el repositorio):

    do_token = "[TOKEN]"
    ssh_key_private = "~/.ssh/id_rsa"
    droplet_ssh_key_id = "[ID SSH KEY]"
    droplet_name = "web"
    droplet_size = "s-1vcpu-1gb"
    droplet_region = "nyc1"

-Para ver todas las claves ssh disponibles en la cuenta:

    doctl  -t [TOKEN] compute ssh-key list

# Ejecutar Terraform

    terraform plan (Para ver lo que se ejecutará en el código)

    terraform apply (Para aplicar la configuración y cración de recursos en Digital Ocean)

    terraform destroy (Para eliminar todos los recursos que se ejecutaron)

    Ingresamos en un navegador http://ip_server y tendrá que mostrar el blog de wordpress.






