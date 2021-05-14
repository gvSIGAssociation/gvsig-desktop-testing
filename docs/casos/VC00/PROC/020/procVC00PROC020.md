---
title: Crear una conexion a base de datos Oracle
proccode: VC00PROC020
srcpath: "casos/VC00/PROC/020/procVC00PROC020.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Crea una conexión a una base de datos de Oracle, si la conexión ya existe se eliminara y se volvera a crear.

### Datos de entrada

1. ${check} **NAME**={% include var_tag.html var="NAME" %}. Nombre de la conexion a crear.

2. ${check} **SERVER**=```${SERVER}```. Direccion o nombre del servidor donde esta ejecutandose la instancia de Oracle.

3. ${check} **PORT**=```${PORT}```. Puerto TCP en el que esta escuchando el servicio de Oracle.

4. ${check} **DATABASE**=```${DATABASE}```. Nombre de la base de datos a la que nos vamos a conectar.

5. ${check} **USER**=```${USER}```. Nombre del usuario de Oracle con el que nos vamos a conectar.

6. ${check} **PASSWORD**=```${PASSWORD}```. Clave del usuario.

7. ${check} **MODE**=```${MODE}```. Mode de la conexion, debera ser "SID" o "Servicio". La opcion elegida
   dependera de como esta configurado el servidor de Oracle.

Tenemos que **prestar especial atencion a que el nombre de usuario y la contraseña coincida en mayusculas y minusculas**
con el nombre de usuario dado de alta en la base de datos de Oracle. Oracle, en general, aceptara establecer
la conexion aunque el nombre no coincida en mayusculas/minusculas pero luego gvSIG desktop no funcionara correctamente
si no coinciden.

### Pasos


1. ${check} Al iniciarse este procedimiento debera estar abierta la venta de conexiones a base de datos, 
   de título "Parámetros de conexión" y debera estar activa.

2. ${check} Comprobaremos si existe la conexión ```${NAME}``` (NAME). Para ello miraremos si ya existe en el desplegable 
   del campo "Nombre de conexión" un valor con el nombre ```${NAME}``` (NAME).

3. ${check} Si existe lo seleccionaremos y pulsaremos el botón inferior que dice "Mas...", seleccionando la
   opción "Eliminar" en el desplegable.

4. ${check} Introduciremos el nombre ```${NAME}``` (NAME) {% include var_copy.html var="NAME"%} en la caja de texto "Nombre de conexión".

5. ${check} Indicaremos como conector "Oracle Server".

7. ${check} Indicaremos como servidor ```${SERVER}``` (SERVER).

8. ${check} Indicaremos como puerto ```${PORT}``` (PORT).

9. ${check} Indicaremos como base de datos ```${DATABASE}``` (DATABASE).

10. ${check} Indicaremos como usuario ```${USER}``` (USER).

11. ${check} Indicaremos como contraseña ```${PASSWORD}``` (PASSWORD).

12. ${check} Pulsaremos en el boton "Mas..." y seleccionaremos la opcion "Avanzado". 
    Esto presentara una ventana de titulo "OracleServerExplorerParameters".
   
13. ${check} Seleccionaremos la pestaña "Connection".

14. ${check} En el desplegable del campo "mode" seleccionaremos la opción ```${MODE}``` (MODE)

15. ${check} Pulsaremos el botón "Aceptar", que cerrara la ventana de titulo "OracleServerExplorerParameters".
   
16. ${check} Habremos vuelto a la ventana de titulo "Parámetros de conexión".

17. ${check} Pulsaremos el botón "Aceptar", que cerrara la ventana.
   
### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

Si se produce un error reportelo en el test que esta ejecutando.

{% include es/footer.html %}
