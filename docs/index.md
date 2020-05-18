# Como documento mis proyectos

Voy a tratar de poner en este tutorial todo lo necesario para crear de forma sencilla la documentación de un proyecto cualquiera y tenerlo disponible como una página de GitHub.

Para ello voy a seguir la plantilla de [La Jaqueria](https://github.com/lajaqueria/plantilla-taller) creada por Cristobal Contreras donde explica claramente todo lo que necesitamos para documentar de esta forma que vamos a explicar.

La plantilla realizada con MkDocs utiliza la libreria Material y el editor de texto que usaremos será el VSCode.

Antes de nada debemos asegurarnos de tener cubiertos los requisitos previos siguientes:

1.- Tener Python 3 instalado.

Antes de nada actualizamos nuestro sistema.

* `$ sudo apt update`. Actualizamos lista de paquetes y sus versiones
* `$ sudo apt -y upgrade`. Instala las nuevas versiones de los paquetes actualizados.

Comprobamos si tenemos instalado Python tecleando en una terminal lo siguiente:

* Versión 2.7: `$ python -V`. Devolverá algo similar a: `$ Python 2.7.17`
* Versión 3: `$ python3 -V`. Devolverá algo similar a: `$ Python 3.6.9`

2.- Instalar PIP, el gestor de paquetes de Python.

* `$ sudo apt install -y python3-pip`
* Comprobar la versión PIP instalada: `$ pip --version` o `$ pip3 --version` Esto devolverá algo similar a: `pip 20.0.2 from /usr/local/lib/python3.6/dist-packages/pip (python 3.6)`

3.- Instalar `Pipenv` para tener un flujo de trabajo en Python: `$ pip install pipenv`.

Toda la documentación va a estar realizada con Ubuntu 18.04 de nombre clave Bionic Beaver y todas las herramientas que se detallan en el apartado [software utilizado](Referencias/sof.md)
