** INSTALL YARN OR NPM **

Que funcion tienen? 
Son isntaladores de paquetes y gestor de dependencias

	-	resuelven las dependencias entre paquetes y librerias JavaScript
	-	revisa que el paquete no este instalado anteriormente en el proyecto

Quien los utiliza
Proyectos con VUE.JS y Angular

Tanto NPM como Yarn requeiren NODE.JS

archivos /directorios utilizados
/node_modules
package-lock.json (npm install ) * despues de descargar el proyecto

package.json []
yarn.lock [ Yarn necesita almacenar exacatmente que versiones de cada dependencia se instalaron ]

** NPM **

 [--save-dev] o [-D] instala o paquetes y los guarda en package.json para futuruas nuesvas intalaciones.

 Instalacion

 	- [sudo] npm install npm -g 
 	El -g indica que las intalacion de global, para todo el sistema operativo, cuando uses el comando NPM en tu proyecto no necesitaras el -g

 	-  npm init
  	esto creara el package.json [el que va a almacenar toda la informacion de las dependencias o librerias que necesitemos en nuestro proyecto]
 	intro a todo, no es necesario rellenar los campos, los comapos name y version que son necesarios se rellenaran por defecto	

 	agregar una dependencia o paquete
 	-  npm intall <package> || npm i <package>
 	esto instalara la dependicia y al mismo tiempo la añadira en el package.json

 ** YARN **

 intalation

 https://yarnpkg.com/en/docs/install#debian-stable

 Ubuntu 18.04
 - curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
 - echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

 - sudo apt-get update && sudo apt-get install yarn

 una vez iniciado el proyecto accedemos al directorio y por comando nuevamente:

 	- yarn init
 	esto creara el package.json [el que va a almacenar toda la informacion de las dependencias o librerias que necesitemos en nuestro proyecto]
 	intro a todo, no es necesario rellenar los campos, los comapos name y version que son necesarios se rellenaran por defecto

 	agregar una dependencia o paquete
 	-  yarn add <package>
 	esto instalara la dependicia y al mismo tiempo la añadira en el package.json

 	Actualizar una dependencia
	- yarn upgrade <package>

	Eliminar una dependencia
	- yarn remove <package>

	Instalar todas la dependencias
	- yarn || yarn install
	esto instalar todas las dependencias si, por ejemplo de has bajado el proyecto en un nuevo pc desde un github

	- yarn run [script]
	este script tendra que estar definido en package.json

 yarn upgrade-interactive

fuentes de la informacion

https://www.campusmvp.es/recursos/post/tiene-sentido-yarn-ahora-que-tenemos-npm-5.aspx
https://yarnpkg.com/lang/en/
https://www.npmjs.com