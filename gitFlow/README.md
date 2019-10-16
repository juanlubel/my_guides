#Evolucion de un servidor con NodeJs

## Usando metodo Git-Flow

### Creacion

En este ejemplo hemos usado la creación de la estructura base desde WebStorm de JetBrain y a continuación

    git init .
    git branch develop
    
Ahora tenemos que crear el repositorio donde queremos alojar el proyecto en GitHub

    https://github.com/juanlubel/git-flow-nodeJs.git
    
A continuación vamos a hacer el commit del repositorio iniciado.

###Desarrollo

Bien! todo parece ir bien. Vamos a crear un endpoint para los usuarios. Vamos a trabajar en la rama develop.
Asi que asegurate de estar en la rama correcta

    git branch
    
    * develop
      master

### Creacion de una feature

Ahora vamos a crear un feature para desarrollar un nuevo endpoint

    git checkout -b feature-items
    git add . 
    git commit -m "feature-items"
    git push origin feature-items
    
Perfecto, la routa ITEMS funciona, asi que vamos a cerrar la rama y hacer el merge con Develop

Notese que esta feature ha creado un archivo y ha modificado app.js. Ojito con los cambios.

Sigue los pasos

    git add . 
    git commit -m "items end"
    git checkout develop
    
### Error en APP.JS, hacemos un hot fix

Nos vemos obligados a cambiar el puerto de salida de nuestro server, por lo que es algo que afecta tanto a master como a develop
Lo haremos de la siguiente manera

    git checkout master;
    git branch hotfix-app_port;
    git checkout hotfix-app_port;
    git add . ; git commit -m "hotfix-app_port"; git push origin hotfix-app_port

Hemos modificado parte del contenido de app.js que afecta directamente en la produccion y testing de la App, por lo que ahora que sabemos que funciona tenemos que
hacer el merge a las dos ramas-pilar del proyecto MASTER y DEVELOP

>El cambio es el mismo, pero los dos app.js no estaran igual. Develop tiene un app.js con los items añadidos. Atento a ese cambio

    git add . ; git commit -m "close hotfix-app_port";

    git checkout master;
    git merge hotfix-app_port;

Revisemos los cambios

    git add . ; git commit -m "close hotfix-app_port"; git push origin master
    
Y ahora lo mismo con develop

    git checkout develop;
    git merge hotfix-app_port;
    git add . ; git commit -m "close hotfix-app_port"; git push origin develop

###Release

Ahora vamos a crear un Release para preparar el develop actual y poder enviarlo a master y conseguir la version v1.0

Nos aseguramos que estamos en la rama develop, y que hemos hecho los merge de las features que tengamos terminadas. 
Asi cuando creemos la rama de release tendra los cambios que queremos poner en produccion.

    git checkout -b release-v1.0

Esto no creara y posicionara en la nueva rama release-v1.0

    git add . ; git commit -m "open release-v1.0"; git push origin release-v1.0
    
Ahora realizaremos los cambios necesarios para que el app funcione en produccion y no en develop (ej: host o puertos, webpack si fuera necesario. Añadir, no sustituir)

> En este caso estos cambios no estan representados

Despues de realizar los cambios necesarios, haremos un merge con las dos ramas de master y develop (por si algun cambio afecta a develop)

> en el ejemplo no se muestra este el siguiente paso correctamente

Realizamos el push del la rama antes de realizar ningun merge

    git add . ; git commit -m "close release-v1.0"; git push origin release-v1.0

Primero vamos a Master

    git checkout master;
    git merge release-v1.0
    git tag -a v1.0 -m "primera version para produccion";

Añadiendo la tag, ahora tendremos en nuestro repositorio una version actualizada de master, no es lo mismo que el commit de la rama Master.
Que realizaremos cuando tengamos una fase mas madura para produccion.

Ahora la rama develop, para seguir con el desarollo

    git checkout develop;
    git merge release-v1.0;
    git add . ; git commit -m "close release-v1.0"; git push origin develop
    
Esta vez si haremos el commit y el push, por si colaboradores necesitan actualizar la rama develop para continuar con alguna feature

