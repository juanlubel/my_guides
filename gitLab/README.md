# Instalación de GitLab en tu ordenador

[BACK](../README.md)

## Siguiendo los pasos de GitLab

Instalar y configurar dependencias

```
sudo apt-get update
sudo apt-get install -y curl openssh-server ca-certificates
```
> Nos sugiere instalar postfix, pero si prefieres usar otra configuración para enviar mails no hay problema

```
sudo apt-get install -y postfix
```
Nos aparecerán unas opciones de configuración en la consola, en la que podremos; para este ejemplo, usar Local only

A continuación introducimos el nombre, que puede ser por defecto el de nuestro usuario-máquina.

Y continuará la configuración

Añadimos el paquete de GitLab

```
curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ee/script.deb.sh | sudo bash
```

A continuación necesitamos saber en qué dirección de GitLab queremos alojar la instancia.
Git se va a encargar de crearla por nosotros.

> Recuerda cambiar la URL de ejemplo
>
> Siempre es mejor que pongáis el nombre de la máquina o la IP.

```
sudo EXTERNAL_URL="https://gitlab.example.com" apt-get install gitlab-ee
```

Vamos a necesitar tener instalado openssh para poder acceder a nuestro servidor.

Y ya tenemos nuestro servidor GitHub listo

##Configuraciones

### Cambiar puerto de acceso

Entramos a la terminal donde esta el server Gitlab y tecleamos lo siguiente:
```
sudo -e /etc/gitlab/gitlab.rb
```
Agregamos el puerto 4444, por ejemplo:
```
external_url 'http://gitlab.example.com:4444'
```
Luego lo guardamos. Volvemos a teclear en la terminal:
```
sudo gitlab-ctl reconfigure
```

### Impedir que usuarios nuevos puedan modificar su identificador

### Modificar el tiempo de expiración de la sesión




