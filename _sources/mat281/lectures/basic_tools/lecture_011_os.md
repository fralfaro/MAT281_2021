<!-- #region -->
# Linux

<img src="https://www.redeszone.net/app/uploads-redeszone.net/2017/11/instalar-linux-cosas.jpg" alt="" align="center" width="300" height="200" />

## Introducción
[GNU/Linux](https://en.wikipedia.org/wiki/Linux) es la denominación técnica y generalizada que reciben una serie de sistemas operativos de tipo Unix, que también suelen ser de código abierto, multiplataforma, multiusuario y multitarea.Estos sistemas operativos están formados mediante la combinación de varios proyectos, entre los cuales destaca el entorno GNU, encabezado por el programador estadounidense Richard Stallman junto a la Free Software Foundation, una fundación cuyo propósito es difundir el software libre (Open source), así como también el núcleo de sistema operativo conocido como **«Linux»**, encabezado por el programador finlandés [Linus Torvalds](https://en.wikipedia.org/wiki/Linus_Torvalds).

## Comandos Básicos (por línea de comando)


### comando pwd
Usa el comando pwd para encontrar la ruta del directorio (carpeta) de trabajo actual en el que te encuentras. El comando devolverá una ruta absoluta (completa), que es básicamente una ruta de todos los directorios que comienzan con una barra diagonal (/) Un ejemplo de una ruta absoluta es `/home/nombredeusuario`.

<!-- #endregion -->

```python
!pwd
```

### comando cd
Para navegar por los archivos y directorios de Linux, usa el comando cd. Te pedirá la ruta completa o el nombre del directorio, dependiendo del directorio de trabajo actual en el que te encuentres.

Supongamos que estás en `/home/nombredeusuario/Documentos` y deseas ir a Fotos, un subdirectorio de Documentos. Para hacerlo, simplemente escribe el siguiente comando: cd Fotos.

Otro escenario es si deseas ir a un directorio completamente nuevo, por ejemplo, `/home/nombredeusuario/Peliculas`. En este caso, debes escribir cd seguido de la ruta absoluta del directorio: `cd /home/nombredeusuario/Peliculas`.

Hay algunos atajos para ayudarte a navegar rápidamente:

* **cd ..** (con dos puntos) para ir un directorio hacia arriba
* **cd** para ir directamente a la carpeta de inicio

Como nota al margen, el shell de Linux distingue entre mayúsculas y minúsculas. Por lo tanto, debes escribir el nombre del directorio de forma exacta.

```python
!cd /home/fralfaro/PycharmProjects && pwd
```

```python
!cd .. && pwd
```

```python
!cd && pwd
```

### comando ls
El comando ls se usa para ver el contenido de un directorio. Por defecto, este comando mostrará el contenido de tu directorio de trabajo actual.

Si deseas ver el contenido de otros directorios, escribe ls y luego la ruta del directorio. Por ejemplo, ingresa `ls /home/nombredeusuario/Documentos` para ver el contenido de Documentos.

Hay variaciones que puedes usar con el comando ls:

* **ls -R** también listará todos los archivos en los subdirectorios
* **ls -a** mostrará los archivos ocultos
* **ls -al** listará los archivos y directorios con información detallada como los permisos, el tamaño, el propietario, etc.

```python
!ls
```

```python
!ls -R
```

```python
!ls -a
```

```python
!ls -al
```

### comando cat
Se utiliza para listar el contenido de un archivo en la salida estándar (sdout). Para ejecutar este comando, escribe cat seguido del nombre del archivo y su extensión. Por ejemplo: cat archivo.txt.

Aquí hay otras formas de usar el comando cat:

* `cat > nombredearchivo` crea un nuevo archivo.
* `cat nombredearchivo1 nombredearchivo2>nombredearchivo3 `une dos archivos (1 y 2) y almacena la salida de ellos en un nuevo archivo (3)
* convertir un archivo a mayúsculas o minúsculas, `cat nombredearchivo | tr a-z A-Z> salida.txt`

```python
!cat archivo.txt
```

### comando cp
Usa el comando cp para copiar archivos del directorio actual a un directorio diferente. Por ejemplo:

```python
!cp archivo.txt archivo_02.txt
```

### comando mv
El uso principal del comando mv es mover archivos, aunque también se puede usar para cambiar el nombre de los archivos.

Los argumentos en mv son similares al comando cp. Debes escribir mv, el nombre del archivo y el directorio destino. 

```python
!mv archivo_02.txt linux
```

Para cambiar el nombre de los archivos, el comando de Linux es `mv nombreviejo.ext nombrenuevo.ext`


### comando mkdir
Usa el comando mkdir para crear un nuevo directorio: si escribes mkdir Musica, creará un directorio llamado Musica.

También hay comandos adicionales de mkdir:

* Para generar un nuevo directorio dentro de otro directorio, usa este comando básico de Linux `mkdir Musica/Nuevoarchivo`
* Usa la opción p (padres) para crear un directorio entre dos directorios existentes. Por ejemplo, `mkdir -p Musica/2020/Nuevoarchivo` creará el nuevo archivo «2020».

```python
!mkdir Carpeta
```

```python
!mkdir Carpeta/nueva_carpeta
```

### comando touch

El comando touch te permite crear un nuevo archivo en blanco a través de la línea de comando de Linux. Como ejemplo, ingresa `touch /home/nombredeusuario/Documentos/Web.html` para crear un archivo HTML titulado Web en el directorio Documentos.

```python
!touch Web.html
```

```python
!ls
```

### comando rmdir
Si necesitas eliminar un directorio, usa el comando rmdir. Sin embargo, rmdir solo te permite eliminar directorios vacíos.

```python
!rmdir Carpeta
```

```python
!rmdir Carpeta/nueva_carpeta
```

<!-- #region -->
### comando rm
El comando rm se usa para eliminar directorios y el contenido dentro de ellos. Si solo deseas eliminar el directorio, como alternativa a rmdir, usa rm -r.


> **Nota**: Ten mucho cuidado con este comando y verifica en qué directorio te encuentras. Este comando elimina todo y no se puede deshacer.
<!-- #endregion -->

```python
!rm -r Carpeta 
```

```python
!rm Web.html linux/archivo_02.txt
```


## Referencia

1. [The Ultimate Linux Command Line Guide - Full Bash Tutorial](https://www.freecodecamp.org/news/linux-command-line-bash-tutorial/)
2. [35 comandos básicos de Linux que todo usuario debe saber](https://www.hostinger.es/tutoriales/linux-comandos)
