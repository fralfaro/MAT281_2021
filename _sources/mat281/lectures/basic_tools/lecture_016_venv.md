# Virtual Environment

## Introducción
Un entorno de desarrollo virtual python o simplemente entorno virtual python es un mecanismo que me permite gestionar programas y paquetes python sin tener permisos de administración, es decir, cualquier usuario sin privilegios puede tener uno o más **espacios aislados** (ya veremos más adelante que los entornos virtuales se guardan en directorios) donde poder instalar distintas versiones de programas y paquetes python.

Antes de empezar a crear nuestros entornos, deberíamos hacernos las siguientes preguntas:

### ¿Para qué se usan los entornos virtuales?

* Utilizar versiones de paquetes python que no son las que vienen empaquetadas oficialmente en nuestra OS. Una solución puede ser usar `pip` como administrador: esta solución nos puede dar muchos problemas, ya que podemos romper las dependencias entre las versiones de nuestros paquetes python instalados en el sistema y algún paquete puede dejar de funcionar.

* En el caso del desarrollo y despliegue de aplicaciones web, cada vez es más importante acercar los entornos de desarrollo, prueba y producción, es decir, que estos tres entornos sean los más parecidos posible, para no tener **sorpresas** a la hora de desplegar la aplicación en producción. 

* Los ciclos de desarrollo de aplicaciones son cada vez más rápidos, esto puede suponer que en una misma máquina podamos tener aplicaciones que utilicen diferentes dependencias y versiones de un mismo paquete. Por ejemplo, podemos tener dos aplicaciones web en producción, una que esté desarrollada con django 1.8 y otra con django 1.10. 

* Los entornos virtuales son una herramienta que favorecen las nuevas metodologías de trabajo que se denominan DevOps, que tratan de gestionar y automatizar la configuración. Es muy sencillo distribuir la configuración de nuetro en torno virtual y automatizar la creación de ellos en diferentes infraestructuras y escenarios.

### ¿Los entornos virtuales son propios sólo del lenguaje python?
No, existen herramientas parecidas en distintos lenguajes que nos ofrecen una funcionalidad parecida:

* `phpenv` para `php`
* `plen` y `perlbrew` para `perl`
* `rbenv` y RVM para ruby
* `nodeenv`, `nvm`, `n` y `nave` para `node.js`

### ¿Qué programa necesito para crear un entorno virtual con python 3?


Tradicionalmente se utiliza la herramienta `virtualenv` para crear nuestros entornos virtuales. Sin embargo, desde la versión 3.3 de Python tenemos a nuestra disposición un módulo del sistema `venv` que podemos utilizar para crear nuestro entorno virtual. Por otro lado, existen otras formas de crear ambientes virtuales, por ejemplo ocupando `conda`, `pipenv` y/o `poetry`, sin emabargo, estos pueden ser un poco más complejo de comeprender en un comienzo (sobre todo `pipenv` o `poetry` ), aunque con costo/benefificio de poder tener un gestor de paquetes mejor que un simple `requirements.txt` lo vale.

Comprendamos algunos conceptos básicos:

* `virtualenv`: software que se encuentra en el Python Package Index o PyPI , que es el repositorio de paquetes de software oficial para aplicaciones de terceros en el lenguaje de programación Python.
* `venv`: módulo oficial de Python que a partir de la versión 3.3 nos permite crear entornos virtuales.
* `pip` : Independientemente de la manera en que creamos el entorno virtual, utilizando una de las dos herramientas anteriores, vamos a utilizar este sistema de gestión de paquetes utilizado para instalar y administrar paquetes de software escritos en Python que se encuentran alojados en el repositorio PyPI .


## Creando ambientes virtuales

### Forma tradicional

La instalación y configuración se realizará en una distribución GNU/Linux Debian Jessie, en otra versión del sistema u otra distribución puede haber algunas diferencias.

Instalamos los paquetes necesarios como root:

```
# apt-get install python-virtualenv
```

Ahora ya como un usuario sin privilegio podemos crear un entorno virtual con el interprete Python (2.7 o 3.X):

```
$ virtualenv entorno1
```

Se ha creado un directorio, donde se instalarán posteriormente los paquetes que necesitemos:
```
$ cd entorno1
$ ls
```

Independientemente el interprete que utilicemos en nuestro entorno para activarlo tenemos que ejecutar la siguiente instrucción:
```
$ source entorno1/bin/activate$
```

Para desactivar el ambiente virtual, ejecutamos:

```
$ deactivate
```

Para poder instalar alguna librería, simplemente ocupamos la herramienta de `pip` (en python 3 se ocupa `pip3`)

```
$ pip install numpy
```

También podemos instalar alguna versión en específica, simplemente se realiza:

```
$ pip install numpy=="1.0.0"
```

Si necesitamos borrar un paquete podemos ejecutar:

```
$ pip uninstall numpy
```

Para terminar de repasar la herramienta `pip` , vamos a explicar como podemos guardar en un fichero (que se suele llamar `requirements.txt` ) la lista de paquetes instalados, que nos permite de manera sencilla crear otro entorno virtual en otra máquina con los mismos paquetes instalados. Para ello vamos a usar la siguiente opción de `pip` :

```
$ pip freeze
numpy==1.0.0
```

De tal manera que otro usuario, en otro entorno, teniendo este fichero pude reproducirlo e instalar los mismos paquetes de la siguiente manera:

```
pip install -r requirements.txt
```

### Ocupando la Interfaz de Conda

Lo primero es abrir el navegador de Conda de su sistema operativo:

<img src="https://docs.anaconda.com/_images/win-navigator1.png" alt="conda">


El navegador de conda luce así:

<img src="https://docs.anaconda.com/_images/nav-defaults.png" alt="conda">


Hacemos click en  `Enviroments`, luego click `Create` y comenzamos a crear nuestro ambiente virtual, en donde se debe especificar el `kernel` (Python o R) y el nombre del ambiente:

<img src="images/venv_01.png" alt="conda">


Finalmente, volvemos a `Home` y cambiamos *base* por el ambiente que hemos creado.

<img src="images/venv_02.png" alt="conda">


Para agregar librerías, puede ir a la parte de `Enviroments` y agregar las librerías que necesites.



## Referencias

* [venv — Creation of virtual environments](https://docs.python.org/3/library/venv.html)
* [The definitive guide to Python virtual environments with conda](https://whiteboxml.com/blog/the-definitive-guide-to-python-virtual-environments-with-conda)
