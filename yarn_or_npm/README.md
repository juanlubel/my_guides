---
redirect_from: "/my_guides/"
---

# INSTALL YARN OR NPM

***Que funcion tienen?***

* Son instaladores de paquetes y gestores de dependencias
* Resuelven las dependencias entre paquetes y librerías JavaScript
* Revisan que el paquete no esté instalado anteriormente en el proyecto

***Con que se utiliza***

* Proyectos con VUE.JS y Angular

***Requirements***

* Tanto NPM como Yarn requieren NODE.JS

***/directorios y archivos utilizados:***

* /node_modules (ambos)
  > los módulos instalados aquí ya los podrás incluir en tu .js con:

        > var my_package = require('package_name');

* package.json (ambos)

        {
            "dependencies": {
                "@package_name": "^1.0.0"
            }
        }

* package-lock.json (npm)

* yarn.lock (yarn)
    >Yarn necesita almacenar exactamente qué versiones de cada dependencia se instalaron

## NPM

Instalación

    [sudo] apt install npm
 
    [sudo] npm install npm -g

El -g indica que las intalacion de global, para todo el sistema operativo, cuando uses el comando NPM en tu proyecto no necesitaras el -g

>una vez iniciado el proyecto accedemos al directorio y por comando nuevamente:

Package.json

	npm init

Esto creará el package.json [el que va a almacenar toda la información de las dependencias o librerías que necesitemos en nuestro proyecto]
   intro a todo, no es necesario rellenar los campos, los campos name y versión que son necesarios se rellenaran por defecto  

Agregar una dependencia o paquete

    npm install < package >

o

    npm i < package >

> [--save-dev] o [-D] instala paquetes y los guarda en package.json para futuras nuevas instalaciones.

    npm i -D < package >

esto instalará la dependencia y al mismo tiempo la añadirá en el package.json

## YARN

Instalación

[Yarn guide instalation](https://yarnpkg.com/en/docs/install#debian-stable)

Ubuntu 18.04

	curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
	echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

	sudo apt-get update && sudo apt-get install yarn

> Una vez iniciado el proyecto accedemos al directorio y por comando nuevamente:

    yarn init

esto creará el package.json [el que va a almacenar toda la información de las dependencias o librerías que necesitemos en nuestro proyecto]
    intro a todo, no es necesario rellenar los campos, los campos name y versión que son necesarios se rellenaran por defecto

Agregar una dependencia o paquete

    yarn add < package >

esto instalará la dependencia y al mismo tiempo la añadirá en el package.json para futuras instalaciones

Actualizar una dependencia

    yarn upgrade < package >

Eliminar una dependencia

    yarn remove < package >

Instalar todas la dependencias

    yarn || yarn install

esto instalar todas las dependencias si, por ejemplo de has bajado el proyecto en un nuevo pc desde un github

    yarn run [script]

este script tendrá que estar definido en package.json

    yarn upgrade-interactive

## Fuentes

<https://www.campusmvp.es/recursos/post/tiene-sentido-yarn-ahora-que-tenemos-npm-5.aspx>

<https://yarnpkg.com/lang/en/>

<https://www.npmjs.com>

