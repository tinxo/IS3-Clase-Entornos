# Demo 3

## Usando Docker en un entorno online

### Pre-requisitos

* Generar una cuenta en [Play With Docker](https://labs.play-with-docker.com/) (PWD)

### Descripción del ejemplo

En este caso se va a trabajar sobre una versión online de Docker para no tener que hacer una instalación en su PC.
Se mostrarán dos ejemplos con otros lenguajes.

### Caso 1 - PHP

Para comenzar se debería buscar una imagen compatible para lograr imprimir un mensaje de "Hola mundo" con el lenguaje PHP.

Por ejemplo desde [Docker Hub](https://hub.docker.com/search?q=&type=image) se puede usar la imagen oficial de [PHP](https://hub.docker.com/_/php).

Paso a paso:

1. Una vez abierta la sesión de trabajo en PWD se genera una **nueva instancia**.
2. Se debe hacer clic en el botón **Editor** para poder ingresar el contenido del archivo a ejecutar.
3. Antes de eso, en la consola se genera un nuevo archivo .php con el comando **touch**. Por ejemplo: `touch index.php`.
4. Se vuelve a la ventana de edición y se carga el contenido del archivo:

    ~~~ php
    <?php
        echo "Hola mundo desde PHP!\n";
    ?>
    ~~~

5. Se cierra la ventana de edición y se procede a ejecutar el script en un contenedor de la imagen oficial de PHP (según explica la documentación):

    ~~~ bash
    docker run -it --rm --name my-running-script -v "$PWD":/usr/src/myapp -w /usr/src/myapp php:7.4-cli php index.php
    ~~~

---

### Caso 2 - Javascript

Para comenzar se debería buscar una imagen compatible para lograr imprimir un mensaje de "Hola mundo" con el lenguaje JS.

Por ejemplo desde [Docker Hub](https://hub.docker.com/search?q=&type=image) se puede usar la imagen oficial de [Node.js](https://hub.docker.com/_/node).

Paso a paso:

1. Una vez abierta la sesión de trabajo en PWD se genera una **nueva instancia**.
2. Se debe hacer clic en el botón **Editor** para poder ingresar el contenido del archivo a ejecutar.
3. Antes de eso, en la consola se genera un nuevo archivo .php con el comando **touch**. Por ejemplo: `touch index.js`.
4. Se vuelve a la ventana de edición y se carga el contenido del archivo:

    ~~~ javascript
    console.log("Hola mundo desde JS!");
    ~~~

5. Se cierra la ventana de edición y se procede a ejecutar el script en un contenedor de la imagen oficial de Node (según explica la documentación en [GitHub](https://github.com/nodejs/docker-node/blob/master/README.md#how-to-use-this-image)):

    ~~~ bash
    docker run -it --rm --name my-running-script -v "$PWD":/usr/src/app -w /usr/src/app node:8 node index.js
    ~~~
