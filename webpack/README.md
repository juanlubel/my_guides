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
// saludo.js

export function holamundo() {
    console.log('hola mundo')
}
```

```
// main.js

import holamundo from './saludo'

holamundo()
```
y webpack los relacionara y unirá por nosotros encargandose de las dependencias sin preocuparnos de que js va primero o no.

## Componentes clave

webpack.config.js, el formato de este documento sera el de un objeto de JS en el que tendremos que definir algunos valores por defecto que voy a detallar y donde se podrán configurar diferentes funciones mas.

> las rutas especificadas de ahora en adelante son las he usado o he visto que se usan.

entry => ruta de la entrada de nuestra app, el primer o el js padre (se pueden configurar mas de uno)

    entry: './src/main/app.js'

output => ruta del archivo que se creara con todos los modulos.

    output: {
        path: __dirname + /build,
        filemane: bundle.js
    }
con la configuracion adecuada, sera webpack el que añadira bundle.js al index.html. Pero tambien se puede añadir manualmente en un index.html que estara en la misma carpeta /build.

loaders =>

## Instalación

npm install webpack -g

npm install webpack webpack-dev-server -D

o

yarn add webpack -g
