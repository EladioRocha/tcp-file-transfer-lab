# FTP

Proyecto de cliente de escritorio y servidor de transferencia de archivos. El cliente usa Electron; el servidor implementa comandos propios sobre sockets TCP con el módulo `net` de Node.js. No debe asumirse compatibilidad con un cliente FTP estándar.

## Estructura

- [Client-FTP](Client-FTP)
- [Server-FTP](Server-FTP)

## Preparación y uso

Ejecuta `node index.js` desde `Server-FTP/` para iniciar el servidor. Revisa la dirección de conexión en `Client-FTP/main.js`. Los comandos de transferencia modifican archivos: prueba con un directorio desechable. El servidor requiere revisión del protocolo y validación de entradas antes de exponerlo a una red.

### Client-FTP

Requiere Node.js. Este paquete no fija una versión del runtime; valida compatibilidad con las dependencias antes de actualizarlo.

```sh
cd Client-FTP
npm ci
npm run dev
```

Comandos declarados en [Client-FTP/package.json](Client-FTP/package.json):

| Comando | Acción |
| --- | --- |
| `npm run test` | `echo "Error: no test specified" && exit 1` |
| `npm run start` | `electron .` |
| `npm run dev` | `nodemon --exec npm start` |

El script `test` es un marcador inicial, no una suite de pruebas.

### Server-FTP

Requiere Node.js. Este paquete no fija una versión del runtime; valida compatibilidad con las dependencias antes de actualizarlo.

```sh
cd Server-FTP
npm install
```

No hay un script de arranque declarado en este paquete. Revisa el punto de entrada indicado arriba antes de ejecutar el código.

Comandos declarados en [Server-FTP/package.json](Server-FTP/package.json):

| Comando | Acción |
| --- | --- |
| `npm run test` | `echo "Error: no test specified" && exit 1` |

El script `test` es un marcador inicial, no una suite de pruebas.

## Validación y estado

Esta guía se contrastó con el árbol de archivos y los manifiestos del repositorio. No se ha validado una ejecución completa contra servicios externos, bases de datos o hardware. Las versiones y los scripts mostrados describen el código actual; no implican que sus dependencias antiguas sigan siendo compatibles.
