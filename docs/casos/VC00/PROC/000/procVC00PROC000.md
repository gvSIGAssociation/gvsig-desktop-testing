---
title: Crear una conexion a base de datos H2
proccode: VC00PROC000
srcpath: "casos/VC00/PROC/000/procVC00PROC000.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Crea una conexion a una base de datos H2, si la conexion ya existe se eliminara y se volvera a crear.

### Datos de entrada

1. ${check} **PATHNAME**=```${PATHNAME}```. Ruta completa en la que crear la base de datos H2.

2. ${check} **NAME**=```${NAME}```. Nombre de la conexion a crear.

### Pasos


1. ${check} Al iniciarse este procedimiento debera estar abierta la venta de conexiones a base de datos, 
   de titulo "Parametros de conexion" y debera estar activa.

2. ${check} Comprobaremos si existe la conexion ```${NAME}``` (NAME). Para ello miraremos si ya existe en el desplegable 
   del campo "Nombre de conexion" un valor con el nombre ```${NAME}``` (NAME).

3. ${check} Si existe lo seleccionaremos y pulsaremos el boton inferior que dice "Mas...", seleccionando la
   opcion "Eliminar" en el desplegable.

4. ${check} Escribiremos el nombre ```${NAME}``` (NAME) en la caja de texto "Nombre de conexion".

5. ${check} Indicaremos como conector el de H2. Para ello seleccionaremos el valor "H2Spatial" en el desplegable 
   del campo "Conector".

6. ${check} Pulsaremos en el boton asociado al campo 'Fichero' y en el dialogo de seleccion de fichero que aparecera
   introduciremos en el campo "Nombre de archivo" el valor ```${PATHNAME}``` (PATHNAME) y pulsaremos 
   en el boton "Abrir" de ese dialogo.

7. ${check} Se habra cerrado el dialogo de seleccion de fichero y deberemos estar de vuelta al dialgo de 
   creacion de conexion a base de datos.

8. ${check} Pulsaremos el boton "Aceptar", que cerrara la ventana.
   
### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

Si se produce un error reportelo en el test que esta ejecutando.

{% include es/footer.html %}
