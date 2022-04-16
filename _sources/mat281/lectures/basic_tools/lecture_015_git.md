# Git
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQHG2qgaSuI_FvrlphFXxKnjZixfFmOs3-iNlkMxxnWazUiWMlyc3C-zMlZMTS2U2J9CZI&usqp=CAU" align="center"/>


## Introducción

[Git](https://en.wikipedia.org/wiki/Git) es un software de control de versiones diseñado por Linus Torvalds, pensando en la eficiencia, la confiabilidad y compatibilidad del mantenimiento de versiones de aplicaciones cuando estas tienen un gran número de archivos de código fuente. Su propósito es llevar registro de los cambios en archivos de computadora incluyendo coordinar el trabajo que varias personas realizan sobre archivos compartidos en un repositorio de código.

Al principio, Git se pensó como un motor de bajo nivel sobre el cual otros pudieran escribir la interfaz de usuario o front end como Cogito o StGIT. Sin embargo, Git se ha convertido desde entonces en un sistema de control de versiones con funcionalidad plena. Hay algunos proyectos de mucha relevancia que ya usan Git, en particular, el grupo de programación del núcleo Linux.

El mantenimiento del software Git está actualmente (2009) supervisado por Junio Hamano, quien recibe contribuciones al código de alrededor de 280 programadores. En cuanto a derechos de autor Git es un software libre distribuible bajo los términos de la versión 2 de la Licencia Pública General de GNU.


## Comandos básicos

### Configuración inicial

Abra su terminal de Git para comenzar con la ejecución de comandos, por ejemplo, abrirá el programa Git bash en Windows para ingresar a la línea de comandos de este programa.

Una vez que ingrese, use el siguiente comando para establecer el nombre de usuario de git:

```terminal
git config --global user.name "tunombre"
```




Recuerde sustituir el texto entre comillas por su nombre real. Ahora indique el correo electrónico del usuario para git:

```terminal
git config --global user.email "tuemail"
```


### crea un repositorio nuevo

Crea un directorio nuevo, ábrelo y ejecuta
```terminal
git init
```

para crear un nuevo repositorio de git.

<!-- #region -->
### hacer checkout a un repositorio



Crea una copia local del repositorio ejecutando:
```terminal
git clone /path/to/repository
```

Si utilizas un servidor remoto, ejecuta:

```terminal
git clone username@host:/path/to/repository
```

<img src="https://bobbelderbos.com/assets/git-clone.png" alt="" width="300" height="300" align="center"/>

<!-- #endregion -->

### flujo de trabajo
Tu repositorio local esta compuesto por tres "árboles" administrados por git. El primero es tu `Directorio de trabajo` que contiene los archivos, el segundo es el `Index` que actua como una zona intermedia, y el último es el `HEAD` que apunta al último commit realizado.
<img src="images/trees.png" alt="" width="500" height="300" align="center"/>


### git status

El comando `git status` muestra el estado del directorio de trabajo y del área del entorno de ensayo. Permite ver los cambios que se han preparado, los que no y los archivos en los que Git no va a realizar el seguimiento.

```terminal
git status
```

<!-- #region -->
### add & commit
Puedes registrar cambios (añadirlos al Index) usando


```terminal
git add <filename>
git add .
```

Este es el primer paso en el flujo de trabajo básico. Para hacer commit a estos cambios usa
```terminal
git commit -m "Commit message"
```

Ahora el archivo esta incluído en el `HEAD`, pero aún no en tu repositorio remoto.

<img src="images/flujo.jpg" alt="" width="300" height="500" align="center"/>

<!-- #endregion -->

### ramas (branches)
Las ramas son utilizadas para desarrollar funcionalidades aisladas unas de otras. La rama master es la rama "por defecto" cuando creas un repositorio. Crea nuevas ramas durante el desarrollo y fusiónalas a la rama principal cuando termines.

<img src="images/branches.png" alt="" width="500" height="300" align="center"/>



Crea una nueva rama llamada "feature_x" y cámbiate a ella usando

```terminal
git checkout -b feature_x
```

vuelve a la rama principal

```terminal
git checkout master
```

y borra la rama

```terminal
git branch -d feature_x
```

Una rama nueva no estará disponible para los demás a menos que subas (push) la rama a tu repositorio remoto

```terminal
git push origin <branch>
```

<!-- #region -->
### actualiza & fusiona (pull & merge)


Para actualizar tu repositorio local al commit más nuevo, ejecuta

```terminal
git pull
```

<img src="https://www.maixuanviet.com/wp-content/uploads/2020/05/git-pull2.png" alt="" width="500" height="300" align="center"/>



en tu directorio de trabajo para bajar y fusionar los cambios remotos.
Para fusionar otra rama a tu rama activa (por ejemplo master), utiliza


```terminal
git merge <branch>
```

en ambos casos git intentará fusionar automáticamente los cambios. Desafortunadamente, no siempre será posible y se podrán producir conflictos. Tú eres responsable de fusionar esos conflictos manualmente al editar los archivos mostrados por git. Después de modificarlos, necesitas marcarlos como fusionados con
    

```terminal
git add <filename>
```
    
Antes de fusionar los cambios, puedes revisarlos usando
    
```terminal
git diff <source_branch> <target_branch>```
```

<img src="https://static.javatpoint.com/tutorial/git/images/git-merge-and-merge-conflict.png" alt="" width="500" height="300" align="center"/>

<!-- #endregion -->

<!-- #region -->
### gitignore
El archivo `.gitignore`, es un archivo de texto que le dice a Git qué archivos o carpetas ignorar en un proyecto.

Un archivo local `.gitignore` generalmente se coloca en el directorio raíz de un proyecto. También puedes crear un archivo global `.gitignore`, y cualquier entrada en ese archivo se ignorará en todos tus repositorios de Git.

Las entradas de este archivo también pueden seguir un patrón coincidente:

* `*` se utiliza como una coincidencia comodín.
* `/` se usa para ignorar las rutas relativas al archivo .gitignore.
* `#` es usado para agregar comentarios


<img src="images/gitignore.jpg" alt="" width="300" height="300" align="center"/>

<!-- #endregion -->

<!-- #region -->
### reemplaza cambios locales
En caso de que hagas algo mal (lo que seguramente nunca suceda ;) puedes reemplazar cambios locales usando el comando
```terminal
git checkout -- <filename>
```

Este comando reemplaza los cambios en tu directorio de trabajo con el último contenido de `HEAD`. Los cambios que ya han sido agregados al Index, así como también los nuevos archivos, se mantendrán sin cambio.




Por otro lado, si quieres deshacer todos los cambios locales y commits, puedes traer la última versión del servidor y apuntar a tu copia local principal de esta forma

```terminal
git fetch origin
git reset --hard origin/master
```
<!-- #endregion -->

## Referencia

1. [La guía sencilla](https://rogerdudler.github.io/git-guide/index.es.html)

