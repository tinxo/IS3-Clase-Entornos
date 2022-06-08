# Gestión de configuración > Entornos (con Docker)

## Ingeniería de Software III (LSI) / Actualidad Informática (ASC) - FCEQyN - UNaM

Repositorio de la clase de gestión de entornos.

El contenido de este repositorio es el que se ha usado para el demo ejecutado en clase.
En los diferentes archivos de instrucciones se encuentra el detalle de los pasos ejecutados.

Fuentes:

* [FreeCodeCamp - Tutorial inicial de docker para devs](https://www.freecodecamp.org/news/docker-101-fundamentals-and-practice-edb047b71a51/)


### En caso de usar un repositorio local

Los repositorios locales de imágenes [[REF]](https://docs.docker.com/registry/) se tiene que ajustar la configuración para que se pueda "tomar" una o más imágenes desde ellos [[REF]](https://docs.docker.com/registry/insecure/).

Para eso se va a tener que generar o modificar el siguiente archivo (bajo linux):

* /etc/docker/**daemon.json**

En ese archivo se tiene que agregar la siguiente línea (**modificando la IP correspondiente**):

~~~ javascript
{
    "insecure-registries": [
        "IP:5000"
    ]
}
~~~

Una vez realizado el cambio se tiene que reiniciar el servicio de docker mediante el comando:

~~~ bash
sudo systemctl restart docker
~~~