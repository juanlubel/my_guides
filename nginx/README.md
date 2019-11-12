# Servidor apache

[BACK](../README.md)

[ejemplo usado en la guia del servidor NodeJs](https://github.com/juanlubel/git-flow-nodeJs)

## Configurar un servidor PHP

Vamos a crear dentro de nuestro ejemplo sitioPHP nuestro index.php

    cd /var/www/sitioPHP
    nano index.php
    
```php
<?php
    phpinfo()
?>
```

Ahora vamos a habilitar php en nuestro servidor Nginx, pero antes verifica que tienes PHP7.2 instalado
    
    php -v
    
Ahora vamos a configurar nuestro servidor

    sudo nano /etc/nginx/sites-available/sitioPHP
    
Y añadiremos lo siguiente

```
location ~ .php$ {
    include snippets/fastcgi-php.conf;
    fastcgi_pass unix:/run/php/php7.2-fpm.sock;
}
```

Para publicar el servidor en el puerto 82 tendremos que poner al inicio del documento de configuracion, cuando empieze la directiva server 

    listen 82

###Log personalizado

Añadiremos a la configuracion las siguientes lineas

    access_log /var/log/nginx/sitioPHP/access.log miformato;
    error_log /var/log/nginx/sitioPHP/error.log;

###Activar la compresion de fichecros
