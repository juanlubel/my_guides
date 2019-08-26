# INSTALL YARN OR NPM

***Que funcion tienen?***

- Son isntaladores de paquetes y gestor de dependencias
- Resuelven las dependencias entre paquetes y librerias JavaScript
- Revisan que el paquete no este instalado anteriormente en el proyecto

***Quien los utiliza***

- Proyectos con VUE.JS y Angular

***Requierements***

- Tanto NPM como Yarn requeiren NODE.JS

***/directorios y archivos utilizados:***

- /node_modules 
  
  > los modulos instalados aqui ya los podras incluir en tu .js con:
  
  		> var my_package = require('package_name');

- package.json

		{
			"dependencies": {
				"@package_name": "^1.0.0"
			}
		}

- package-lock.json (npm install ) * despues de descargar el proyecto

- yarn.lock 
	>Yarn necesita almacenar exacatmente que versiones de cada dependencia se instalaron

# NPM

*Instalacion*

	[sudo] npm install npm -g 

El -g indica que las intalacion de global, para todo el sistema operativo, cuando uses el comando NPM en tu proyecto no necesitaras el -g

>una vez iniciado el proyecto accedemos al directorio y por comando nuevamente:

	$ npm init

Esto creara el package.json [el que va a almacenar toda la informacion de las dependencias o librerias que necesitemos en nuestro proyecto]
 	intro a todo, no es necesario rellenar los campos, los comapos name y version que son necesarios se rellenaran por defecto	

_agregar una dependencia o paquete_

	$ npm intall < package >
	
o

	$ npm i < package >

[--save-dev] o [-D] instala o paquetes y los guarda en package.json para futuruas nuesvas intalaciones.

	$ npm i -D < package >

esto instalara la dependicia y al mismo tiempo la añadira en el package.json
# YARN

*Instalacion*

 [Yarn guide instalation](https://yarnpkg.com/en/docs/install#debian-stable)

Ubuntu 18.04
 	
	curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - 
 	echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

>

 	sudo apt-get update && sudo apt-get install yarn

> una vez iniciado el proyecto accedemos al directorio y por comando nuevamente:

	yarn init

esto creara el package.json [el que va a almacenar toda la informacion de las dependencias o librerias que necesitemos en nuestro proyecto]
	intro a todo, no es necesario rellenar los campos, los comapos name y version que son necesarios se rellenaran por defecto

_agregar una dependencia o paquete_

	yarn add < package >

esto instalara la dependicia y al mismo tiempo la añadira en el package.json

_Actualizar una dependencia_

	yarn upgrade < package >

_Eliminar una dependencia_

	yarn remove < package >

_Instalar todas la dependencias_

	yarn || yarn install
	
esto instalar todas las dependencias si, por ejemplo de has bajado el proyecto en un nuevo pc desde un github

	yarn run [script]

este script tendra que estar definido en package.json

	yarn upgrade-interactive

# Fuentes:
```
https://www.campusmvp.es/recursos/post/tiene-sentido-yarn-ahora-que-tenemos-npm-5.aspx

https://yarnpkg.com/lang/en/

https://www.npmjs.com
```