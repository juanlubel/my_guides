### Crear un contenedor MYSQL pasando variables de entorno

Para poder crear el conenedor necesitamos tener descargala la IMAGEN de mysql. Para ello usaremos el siguiente comando

    docker pull mysql

Como vamos a necesitar la siguiente variables de entorno, vamos a preparar un .env.
> Igualmente podemos pasar la variable en el mismo comando run, pero al ser tantas mejor usar esta forma

```
MYSQL_ROOT_PASSWORD=12345678
MYSQL_DATABASE=wordpress
MYSQL_USER=wordpress
MYSQL_PASSWORD=wordpress
```

Metodo en linea: 

    docker run -e MYSQL_ROOT_PASSWORD=12345678 -3 OTHER_VARIABLE=ejemplo mysql

Metodo en archivo:

Creamos un archivo con el nombre que queramos, en mi caso sera .env

![](images/Screenshot%20from%202019-12-04%2017-45-04.png)

posteriormente lo insertaremos con --env-file [ruta]

Ahora, necesitamos crear una red, para luego poder conectar otros contenedores y que despues asociaremos a nuestro contenedor

Usaremos el comando:

    docker network create my_net

![](images/images_mysql.png)

El siguiente paso será crear un volumen que tambien podremos incluir en nuestro contenedor para poder asociarlo a otros contenedores posteriormente. Y lo haremos de la siguiente manera:

    docker volume create vol_mysql

![](images/images_mysql.png)

Para finalizar, prepararemos la linea de comando que lanzara el contendor con todas las especificaciones definidas anteriormente en una sola linea. Añadiendo que el puerto de salida sera el 3306 (en mi ejemplo por conflictos uso el 33066)

    docker run -d -p 33066:3306 --env-file ./.env --network=my_net -v vol_mysql:/var/lib/mysql --name my-mysql mysql 

![](images/docker%20run.png)

Ahora vamos a verificar que el contendor funciona correctamente y que se han insertado bien las variables de entorno.

![](images/docker_run_mysql.png)


### Crear un contenedor Wordpress

Este ejercicio es muy parecido al anterior, pero vamos a detallar los pasos:

En este caso no descargaremos con pull la imagen de wordpress, porque el comando RUN lo hace por nosotros en caso de que no este en local. En el ejemplo anterior habria funcionado igual.

Empezamos.

Primero prepararemos nuestro .env.wordpress con las siguientes variables de entorno

```
WORDPRESS_DB_HOST=127.0.0.1:33066
WORDPRESS_DB_USER=wordpress
WORDPRESS_DB_PASSWORD=wordpress
```

    sudo nano .env.wordpress
    
![](images/wordpress-env.png)

Creamos el volumen para este contenedor

    docker volume create vol_wordpress
    
![](images/vol_wordpress.png)
Y como la red que vamos a gastar es la misma, para que los dos contenedores que estamos creando se puedas ver. El comando RUN será el siguiente

    docker run -d -p 8080:80 --env-file ./.env.wordpress --network=my_net -v vol_wordpress:/var/www/html --name my_wordpress wordpress


