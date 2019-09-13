---
redirect_from: "/my_guides/"
---

# WEBPACK

[BACK](../README.md)

***Su función***

la función de webpack sera agrupar y conectar todos nuestros HTML, CSS y JS documentos en uno.

Nos brinda un servidor de desarollo que se ejecutar en vivo y actualiza los cambios segundo vamos escribidiendo y guardando el codigo en nuestro editor o IDE.

Despues de la configuración adecuada, podremos
```
// saludo/index.js

export function holamundo() {
    console.log('hola mundo')
}
```
Al llamarlo index.js cuando importemos la ruta (siguiente recuadro) no tendremos que introducir el nombre del js.
```
// main.js

import { holamundo } from './saludo'

holamundo()
```

Si tenemos algun documento mas, como; por ejemplo despedida.js 
```
export funcion adios () {
    console.log('hasta la vista baby!')
}

```
El import sera el siguiente

    import { adios } from './saludo/despedida

> notese que no hace falta indicar el .js

> Si importamos funciones, detallaremos los nombre dentro de las llaves {}, si importamos una clase entera, no debera llevarlos

Webpack los relacionara y unirá por nosotros encargandose de las dependencias sin preocuparnos de que js va primero o no.

## Instalación

npm install webpack -g

npm install webpack webpack-dev-server -D

o

yarn add webpack -g

## Componentes clave

Primero debes crear el documento 'webpack.config.js' en la carpeta raiz.

webpack.config.js, el formato de este documento sera el de un objeto de JS en el que tendremos que definir algunos valores por defecto que voy a detallar y donde se podrán configurar diferentes funciones mas.

> las rutas especificadas de ahora en adelante son las he usado o he visto que se usan.

module.exports => para que node entienda la configuracion de webpack debemos poner toda la configuracion que detallo a continuacion dentro del document export

    module.exports = {
        ...
    }

entry => ruta de la entrada de nuestra app, el primer o el js padre (se pueden configurar mas de uno)

    entry: './src/main/app.js'

output => ruta del archivo que se creara con todos los modulos.

    output: {
        path: __dirname + /build,
        filemane: bundle.js
    }
con la configuracion adecuada, sera webpack el que añadira bundle.js al index.html. Pero tambien se puede añadir manualmente en un index.html que estara en la misma carpeta /build.

## EJECUCION

Necesitaremos el siguiente comando
```
webpack --watch --color
```
> --watch generara automaticamente el bundle.js (en nuestro ejemplo) cada vez que se salven los cambios

Este comando lo puedes insertar en tu package.json dentro de scripts para abreviar. Ver tutorial [YARN OR NPM](/yarn_or_npm/README.md)
