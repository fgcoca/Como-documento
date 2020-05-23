# Git en VSCode

## Cosas básicas de Git

Git es un **software libre** de gestión de versiones, lo que viene a significar que es un sistema que nos ayuda a controlar y gestionar los cambios generados en nuestro trabajo, ya sea software, documentación o cualquier otro uso.

Fue creado por [Linus Torvalds](https://es.wikipedia.org/wiki/Linus_Torvalds) para la comunidad Linux hacia el año 2005.

La relación de tareas fundamentales en git y que vamos a describir en este tutorial son las siguientes:

* Configurar e inicializar un repositorio
* Iniciar y detener el seguimiento de archivos
* Preparar cambios con `stage`
* Confirmar cambios con `commit`
* Configurar git para que ignore ciertos archivos
* Corregir errores
* Recorrer la historia de nuestro proyecto y ver cambios entre confirmaciones
* Enviar con `push` y recibir con `pull` de repositorios remotos

Es necesario conocer, aunque sea brevemente, en que consisten estos pasos para poder efectuarlos con garantias desde VSCode. Se remite al lector a la webgrafía para consultar estos aspectos, y mas concretamente al libro de git.

Desde la paleta de comandos, disponible como se observa en la imagen 1, podemos hacer uso de comandos git.

<center>

| _Imagen 1_ |
| :-:|
| ![Acceso a la paleta de comandos](../img/git_VSCode/i1.png) |
| _Acceso a la paleta de comandos_ |

</center>

En la imagen 2 vemos la paleta de comandos con el comando clone de git y como una vez ejecutado nos pide la dirección URL a clonar.

<center>

| _Imagen 2_ | |
| :-:| :-:|
| ![Comando git clone](../img/git_VSCode/i2a.png) | ![Solicitud URL para clonar](../img/git_VSCode/i2b.png) |
| _Comando git clone_ | _Solicitud URL para clonar_ |

</center>

## Git en la barra de estado de VSCode

En la barra de estado que se muestra en la parte inferior de la ventana de VSCode se muestran funciones e información de Git muy útiles.

* A la izquierda se muestra el nombre de la rama de trabajo actual. Si modificamos los archivos con seguimiento en la rama de trabajo, la barra de estado agrega un símbolo de asterisco (*) junto al nombre de la rama, tal y como se observa en la imagen 3.

<center>

| _Imagen 3_ |
| :-:|
| ![Barra de estado: Rama de trabajo actual mostrando cambios](../img/git_VSCode/i3.png) |
| _Barra de estado: Rama de trabajo actual mostrando cambios_ |

</center>

Cuando agreguemos los cambios al `stage`, el asterisco se va a convertir en un signo más (+) para indicar que se han agregado. Cuando confirmemos los cambios `staged`, ese signo más desaparece y solamente se mostrará el nombre de la rama.

* A la derecha del nombre de la rama aparece un icono en forma de un círculo con flechas que indica que el sistema debe sincronizar cambios. En la imagen 4 vemos este icono.

<center>

| _Imagen 4_ |
| :-:|
| ![Barra de estado: icono sincronizar cambios](../img/git_VSCode/i4.png) |
| _Barra de estado: icono sincronizar cambios_ |

</center>

Ese icono con forma de circulo se convierte en una nube con una flecha hacia arriba cuando el sistema está listo para publicar cambios.

## Cambios en archivos

El editor VSCode dispone en su barra de actividades de un acceso a las herramientas git disponibles por defecto y, como veremos mas adelante, también se le pueden instalar complementos para este tema. En la imagen 5 observamos es icono de acceso y vemos un número en un circulo azul que nos indica que hay un número determinado de cambios pendientes de sincronizar con la nube. El número indica cuantos cambios hay pendientes, tanto staged como unstaged (con seguimiento y sin seguimiento)) y listos para confirmarse. El número se incrementa a medida que realicemos cambios en los archivos.

<center>

| _Imagen 5_ |
| :-:|
| ![Herramientas GIT en VSCode](../img/git_VSCode/i5.png) |
| _Herramientas GIT en VSCode_ |

</center>

Este número se corresponde con la aparición de un asterisco (*) en la barra de estado junto al nombre de la rama en la que estamos trabajando.

Una vez confirmemos, este icono  con número desaparece asi como el asterisco de la barra de estado.

También podemos consultar esto desde una terminal ejecutando un `git status` que nos devolverá información como la que vemos en la imagen 6. Lo habitual será usar una combinación de operaciones de Git desde la línea de comandos y funciones de Visual Studio Code integradas con Git.

<center>

| _Imagen 6_ |
| :-:|
| ![Consulta del estado de git desde una terminal](../img/git_VSCode/i6.png) |
| _Consulta del estado de git desde una terminal_ |

</center>

##  Ver cambios en Control de código fuente

Si pulsamos el icono de `Control de código fuente` de la barra de actividades (como vemos en la imagen 7) podremos ver los cambios `staged` y `unstaged`.

<center>

| _Imagen 7_ |
| :-:|
| ![Acceso a Control de cambios](../img/git_VSCode/i7.png) |
| _Acceso a Control de cambios_ |

</center>

Si hacemos clic, por ejemplo, en el archivo que vemos en la imagen 8 observamos una serie de iconos e información asociada al mismo que vamos a describir seguidamente.

<center>

| _Imagen 8_ |
| :-:|
| ![Información de control de seguimiento](../img/git_VSCode/i8.png) |
| _Información de control de seguimiento_ |

</center>

Lo primero que observamos es que el archivo aparece en **cambios**. Los iconos de izquierda a derecha son:

* **Archivo**: permite abrir el archivo en el editor .
* **Signo más (+)**: Al pulsar este icono se agregan los cambios al "stage" y se confirman.
* **Flecha sentido antihorario**: para descartar los cambios y revertir el archivo a su estado en la confirmación anterior.
* **Número**: indica los problemas que el editor encuentra en el archivo, tal y como se describió para la terminal. En este caso concreto 9+ nos está indicando que hay más de 9 problemas.
* **Letra**: Si es una _M_ nos indica que el archivo existía anteriormente y ha sido modificado y si es una _U_ nos está indicando que el archivo es nuevo y no tiene seguimiento.

Moviendo el cursor por los distintos archivos que se muestran en cambios podemos ir viendo toda la información descrita y realizando las acciones asociadas a los iconos.

Si presionamos el signo más por ejemplo en el archivo i1.png este archivo se traslada a la sección `cambios almacenados provisionalmente` o `stage`. Vemos el resultado en la imagen 9, donde se observan los iconos asociados al archivo para esta sección.

<center>

| _Imagen 9_ |
| :-:|
| ![Archivo cambiado a stage](../img/git_VSCode/i9.png) |
| _Archivo cambiado a stage_ |

</center>

Podemos ir añadiendo los archivos uno a uno de esta forma o bien hacerlo desde Cambios (imagen 10) para agregarlos todos a un tiempo.

<center>

| _Imagen 10_ |
| :-:|
| ![Almacenar todos los cambios](../img/git_VSCode/i10.png) |
| _Almacenar todos los cambios_ |

</center>

El signo menos (-) permite sacar el archivo a la sección `Cambios`, el icono archivo nos permite abrirlo y en este caso la letra A indica que se ha añadido (Add) al índice.

Es importante entender que en esta situación estos cambios son locales y no están sincronizados con la nube y tambén que observemos los cambios que se producen en la barra de estado para acostumbrarnos a reconocer el estado de nuestro trabajo.

## Introducir cambios, Commit

En el Control de código fuente se muestran varios iconos en la esquina superior derecha que encontramos destacados en amarillo en la imagen 10. El icono de marca de verificación sirve para empezar a confirmar los cambios. Si pulsamos este icono se nos presenta la situación de la imagen 11.

<center>

| _Imagen 11_ |
| :-:|
| ![Confirmar cambios](../img/git_VSCode/i11.png) |
| _Confirmar cambios_ |

</center>

La intención es agregar un mensaje de confirmación al commit que confirmamos con `Enter` (o bien `Ctrl + Enter` según donde hagamos clic) y como observamos se nos indica a que rama va a ser confirmado. Vamos en nuestro caso a teclear _Confirmar i1.png_. Hay que tener en cuenta que este mensaje se suele restringir a 50 caracteres.

Una vez confirmado el cambio podemos observar que en la barra de estado (imagen 12) aparece un mensaje indicador de que hay un archivo pendiente de sincronizar.

<center>

| _Imagen 12_ |
| :-:|
| ![Barra de estado: sincronizar](../img/git_VSCode/i12.png) |
| _Barra de estado: sincronizar_ |

</center>

Como se observa en la imagen 12 está el icono de sincronización y a su derecha una flecha hacia abajo con un cero, que indica que no hay confirmaciones pendientes de sincronizar o extraer. A la derecha hay una flecha hacia arriba con un 1 junto a ella, que indica que hay una confirmación para insertar en el repositorio.

Si hacemos clic en el icono se mostrará un mensaje (imagen 13) relativo a que vamos a realizar las operaciones `git pull` y, después, una operación `git push`.

<center>

| _Imagen 13_ |
| :-:|
| ![Sincronizar: git pull y git push](../img/git_VSCode/i13.png) |
| _Sincronizar: git pull y git push_ |

</center>

La operación `git pull` incorpora los cambios de un repositorio remoto a la rama local y la operación `git push` hace lo contrario, incorpora los cambios de una rama local a un repositorio. Hacer clic en el icono sincronizar de la barra de estado realiza ambas operaciones.

Si queremos o tenemos la necesidad de realizar estas operaciones por separado podemos recurrir a teclearlas en una terminal o bien señeccionarla desde las disponibles cuando hacems clic en el icono diéresis de la barra de Control de código fuente. En la imagen 14 vemos las opciones disponibles.

<center>

| _Imagen 14_ |
| :-:|
| ![Acciones de control de codigo fuente](../img/git_VSCode/i14.png) |
| _Acciones de control de codigo fuente_ |

</center>

Si ahora vamos al directorio correspondiente en nuestro github podemos comprobar como ya está el archivo añadido a la rama master, tal y como se observa en la imagen 15.

<center>

| _Imagen 15_ |
| :-:|
| ![Verificacion en Github del Push realizado desde VSCode](../img/git_VSCode/i15.png) |
| _Verificacion en Github del Push realizado_ |

</center>

## Analisis de cambios en archivos

Una herramienta muy útil de VSCode es la que vamos a ver seguidamente. Como observamos en la imagen 16 en el archivo señalado se han realizado cambios.

<center>

| _Imagen 16_ |
| :-:|
| ![Archivo que ha sufrido cambios](../img/git_VSCode/i16.png) |
| _Archivo que ha sufrido cambios_ |

</center>

 Pero ¿cuales son esos cambios?. Pues bien, si hacemos clic sobre el archivo y ocultamos el navegador haciendo clic sobre el icono de control de código veremos una ventana como la de la imagen 17, donde vemos dos columnas, la de la izquierda muestra el archivo antes de realizar cambios y la de la derecha muestra los cambios realizados.

<center>

| _Imagen 17_ |
| :-:|
| ![Comparación del archivo con cambios](../img/git_VSCode/i17.png) |
| _Comparación del archivo con cambios_ |

</center>

Esto se puede conseguir directamente desde la línea de comandos en una terminal tecleando `git status` que mostrará en que archivo se han realizado los cambios y después `git diff <nombre del archivo>` del que mostrar las diferencias. En la imagen 18 vemos el resultado de ejecutar estos comandos.

<center>

| _Imagen 18_ | |
| :-:| :-:|
| ![Resultado de git status](../img/git_VSCode/i18a.png) |![Resultado de git diff](../img/git_VSCode/i18b.png) |
| _Resultado de git status_ | _Resultado de git diff_ |

</center>

## Añadir extensiones Git

Vamos a añadir una extensión muy interesante de VSCode que se llama `GitLens` y que agrega muchas funcionalidades. En la imagen 19 vemos el resultado de buscar e instalar esta extensión.

<center>

| _Imagen 19_ | |
| :-:| :-:|
| ![Autorun de GitLens tras instalar](../img/git_VSCode/i19a.png) |![GitLens instalado](../img/git_VSCode/i19b.png) |
| _Autorun de GitLens tras instalar_ | _GitLens instalado_ |

</center>

Vamos a ver las principales funcionalidades de `GitLens`:
* Cuando nos situamos sobre cualquier linea (imagen 20), incluso en la que estamos escribiendo, se nos informa del autor del último commit, cuando se hizo y si los cambios han sido confirmados o no.

<center>

| _Imagen 20_ |
| :-:|
| ![Información de GitLens](../img/git_VSCode/i20.png) |
| _Información de GitLens_ |

</center>

Si dejamos unos instante el cursor sobre la información esta será ampliada en una ventana emergente tal y como observamos en la imagen 21.

<center>

| _Imagen 21_ |
| :-:|
| ![Información de GitLens ampliada](../img/git_VSCode/i21.png) |
| _Información de GitLens ampliada_ |

</center>

* Una segunda funcionalidad interesante de `GitLens` es la que observamos en la imagen 22. Se trata de unas líneas verticales de color azul o verde que indican los cambios realizados en el archivo, en concreto el color azul indica que la línea ha sido modificada y el color verde que ha sido añadida. En ambos casos, si situamos el cursor sobre la línea esta de engrosa.

<center>

| _Imagen 22_ |
| :-:|
| ![Información de GitLens: modificación o nuevo](../img/git_VSCode/i22.png) |
| _Información de GitLens: modificación o nuevo_ |

</center>

Si hacemos clic sobre una de las líneas, por ejemplo la modificada, se nos despliega la información que vemos en la imagen 23. 

<center>

| _Imagen 23_ |
| :-:|
| ![Información de GitLens: desiegue](../img/git_VSCode/i23.png) |
| _Información de GitLens: desiegue_ |

</center>

Podemos observar como se realiza la comparación de la linea antes y después de modificarla y muy importante es que para esta modificación (no para todo el archivo) disponemos de las herramientas asociadas a control de código, pero que si las usamos tan solo se aplican a esta línea.

* Si hacemos clic sobre el icono de `GitLen` se nos despliegan las funcionalidades que tiene la extensión y que van desde la información del repositorio o del archivo, permite realizar comparaciones (igual que `git staff`) e incluso buscar commits. En la imagen 24 las vemos.

<center>

| _Imagen 24_ |
| :-:|
| ![Funcionalidades de GitLens](../img/git_VSCode/i24.png) |
| _Funcionalidades de GitLens_ |

</center>

## Creación del archivo README.md remoto. `Git pull`

Para ver el funcionamiento de la orden `git pull` vamos a crear un archivo en la nube, para ello nos dirigimos al repositorio, donde nos encontramos con la situación que vemos en la image 25. 

<center>

| _Imagen 25_ |
| :-:|
| ![Creación en la nube de README.md](../img/git_VSCode/i25.png) |
| _Creación en la nube de README.md_ |

</center>

Si hacemos clic en el botón señalado se nos crea la estructura básica del archivo, tal y como observamos en la imagen 26, donde ya hemos añadido algunas líneas.

<center>

| _Imagen 26_ |
| :-:|
| ![El archivo README.md con su contenido inicial](../img/git_VSCode/i26.png) |
| _El archivo README.md con su contenido inicial_ |

</center>

Si nos desplazamos hacia abajo en la página nos encontramos con la información para `commit` que hacemos sin modificar el mensaje por defecto, tal y como se observa en la imagen 27.

<center>

| _Imagen 27_ |
| :-:|
| ![Realizamos commit del archivo README.md](../img/git_VSCode/i27.png) |
| _Realizamos commit del archivo README.md_ |

</center>

El resultado final en la nube lo vemos en la imagen 28, donde se observa aque ya existe el archivo y su aspecto.

<center>

| _Imagen 28_ |
| :-:|
| ![Archivo README.md creado](../img/git_VSCode/i28.png) |
| _Archivo README.md creado_ |

</center>

Lógicamente este archivo no lo tenemos en el repo local. Disponemos de varias formas de hacer que esto se solucione. Desde `control de cambios` escogemos la opción que vemos en la imagen 29 que se corresponde con `git pull`.

<center>

| _Imagen 29_ |
| :-:|
| ![Acceso a pull](../img/git_VSCode/i29.png) |
| _Acceso a pull_ |

</center>

Nos va a mostrar una ventana solicitando la selección del origen remoto del que hacer pull, tal y como observamos en la imagen 30. 

<center>

| _Imagen 30_ |
| :-:|
| ![Selección del origen remoto](../img/git_VSCode/i30.png) |
| _Selección del origen remoto_ |

</center>

Escogemos la rama de donde vamos a realizar la extracción, como se observa en la imagen 31.

<center>

| _Imagen 31_ |
| :-:|
| ![Selección de la rama remota](../img/git_VSCode/i31.png) |
| _Selección de la rama remota_ |

</center>

En unos instantes el aspecto que toma VSCode es el que vemos en la imagen 32.

<center>

| _Imagen 32_ |
| :-:|
| ![Reflejo de los cambios para pull](../img/git_VSCode/i32.png) |
| _Reflejo de los cambios para pull_ |

</center>

Cuando confirmemos los cambios nos aparecerá en el repo local el archivo creado en la nube, tal y como se observa en la imagen 33.

<center>

| _Imagen 33_ |
| :-:|
| ![Acción pull finalizada](../img/git_VSCode/i33.png) |
| _Acción pull finalizada_ |

</center>

## Observación final

Esto que hemos visto es tan solo lo imprescindible de Git para poder trabajar de forma local y poder reflejar los cambios en la nube pero en ningún caso es información completa de Git.
