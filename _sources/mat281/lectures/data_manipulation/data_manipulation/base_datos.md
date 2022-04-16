# Base de datos

¿Te imaginas como las grandes compañías o gobiernos almacenan sus datos?. No, no es en un excel gigante en un pendrive.

Es importante saber como modificar o crear valor a través de distintas tablas de datos, por lo que esta clase se centrará en hacer esto, motivando a partir del uso de bases de datos relacionales. 

Una __Base de Datos__ es un conjunto de datos almacenados en una computadora (generalmente un servidor, máquina virtual, etc.) y que poseen una estructura tal que sean de fácil acceso. 

## Base de Datos Relacional

Es el tipo de base de datos más ampliamente utilizado, aunque existen otros tipos de bases de datos para fines específicos. Utiliza una estructura tal que es posible identificar y acceder a datos relacionados entre si. Generalmente una base de datos relacional está organizada en __tablas__.

Las tablas están conformadas de filas y columnas. Cada columna posee un nombre y tiene un tipo de dato específico, mientras que las filas son registros almacenados. 

Por ejemplo, la siguiente tabla tiene tres columnas y cuatro registros. En particular, la columna ```age``` tiene tipo ```INTEGER``` y las otras dos tipo ```STRING```.

<img src="./images/table.jpg" align="center"/>


__¿Este formato de datos te parece familar?__

### ¿Qué es SQL?

Sus siglas significan _Structured Query Language_ (Lenguaje de Consulta Estructurada) es un lenguaje de programación utilizado para comunicarse con datos almacenados en un Sistema de Gestión de Bases de Datos Relacionales (_Relational Database Management System_ o RDBMS). Posee una sintaxis muy similar al idioma inglés, con lo cual se hace relativamente fácil de escribir, leer e interpretar.

Hay distintos RDBMS entre los cuales la sintaxis de SQL difiere ligeramente. Los más populares son:

- SQLite
- MySQL / MariaDB
- PostgreSQL
- Oracle DB
- SQL Server

En una empresa de tecnología hay cargos especialmente destinados a todo lo que tenga que ver con bases de datos, por ejemplo: creación, mantención, actualización, obtención de datos, transformación, seguridad y un largo etc.

Los matemáticos en la industria suelen tener cargos como _Data Scientist_, _Data Analyst_, _Data Statistician_, _Data X_ (reemplace _X_ con algo _fancy_ tal de formar un cargo que quede bien en Linkedin), en donde lo importante es otorgar valor a estos datos. Por ende, lo mínimo que deben satisfacer es:

- Entendimiento casi total del modelo de datos (tablas, relaciones, tipos, etc.)
- Seleccionar datos a medida (_queries_).

### Modelo de datos

Es la forma en que se organizan los datos. En las bases de datos incluso es posible conocer las relaciones entre tablas. A menudo se presentan gráficamente como en la imagen de abajo (esta será la base de datos que utilizaremos en los ejericios del día de 

<img src="./images/sqlite.jpg" align="center"/>



Esta base de datos se conoce con el nombre de _**chinook database**_. La descripción y las imágenes se pueden encontrar [aquí](http://www.sqlitetutorial.net/sqlite-sample-database/).

En la figura anterior, existen algunas columnas _especiales_ con una llave al lado de su nombre. ¿Qué crees que significan?

Las 11 tablas se definen de la siguiente forma (en inglés):

- ```employees``` table stores employees data such as employee id, last name, first name, etc. It also has a field named ReportsTo to specify who reports to whom.
- ```customers``` table stores customers data.
- ```invoices``` & ```invoice_items``` tables: these two tables store invoice data. The ```invoices``` table stores invoice header data and the ```invoice_items``` table stores the invoice line items data.
- ```artists``` table stores artists data. It is a simple table that contains only artist id and name.
- ```albums``` table stores data about a list of tracks. Each album belongs to one artist. However, one artist may have multiple albums.
- ```media_types``` table stores media types such as MPEG audio file, ACC audio file, etc.
- ```genres``` table stores music types such as rock, jazz, metal, etc.
- ```tracks``` table store the data of songs. Each track belongs to one album.
- ```playlists``` & ```playlist_track tables```: ```playlists``` table store data about playlists. Each playlist contains a list of tracks. Each track may belong to multiple playlists. The relationship between the ```playlists``` table and ```tracks``` table is many-to-many. The ```playlist_track``` table is used to reflect this relationship.
