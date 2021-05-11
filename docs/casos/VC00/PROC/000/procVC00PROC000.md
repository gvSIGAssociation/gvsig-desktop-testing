---
title: Crear una conexion a base de datos H2
proccode: VC00PROC000
srcpath: "casos/VC00/PROC/000/procVC00PROC000.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Crea una conexión a una base de datos H2, si la conexión ya existe se eliminara y se volvera a crear.

### Datos de entrada

1. ${check} **PATHNAME**=```${PATH}```. Ruta completa en la que crear la base de datos H2.

2. ${check} **FILENAME**=```${FILENAME}```. Nombre del fichero (sin ruta) a utilizar para crear la base de datos H2.

3. ${check} **NAME**=```${NAME}```. Nombre de la conexion a crear.

### Pasos


1. ${check} Al iniciarse este procedimiento debera estar abierta la venta de conexiones a base de datos, 
   de título "Parámetros de conexión" y debera estar activa.

2. ${check} Comprobaremos si existe la conexión ```${NAME}``` (NAME). Para ello miraremos si ya existe en el desplegable 
   del campo "Nombre de conexión" un valor con el nombre ```${NAME}``` (NAME).

3. ${check} Si existe lo seleccionaremos y pulsaremos el botón inferior que dice "Mas...", seleccionando la
   opción "Eliminar" en el desplegable.

4. ${check} Escribiremos el nombre ```${NAME}``` (NAME) en la caja de texto "Nombre de conexión".

5. ${check} Indicaremos como conector el de H2. Para ello seleccionaremos el valor "H2Spatial" en el desplegable 
   del campo "Conector".

6. ${check} Pulsaremos en el botón asociado al campo 'Fichero' y en el diálogo de selección de fichero que aparecera 
   navegue hasta el directorio ```${PATH}``` (PATH) e introduzca ```${FILENAME}``` en el campo "Nombre de archivo".
   Una vez hecho esto pulsaremos en el boton "Abrir" de ese diálogo.

7. ${check} Se habrá cerrado el diálogo de selección de fichero y deberemos estar de vuelta al dialogo de 
   creación de conexión a base de datos.

8. ${check} Pulsaremos el botón "Aceptar", que cerrara la ventana.
   
### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

Si se produce un error reportelo en el test que esta ejecutando.

{% include es/footer.html %}
