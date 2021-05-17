---
title: Crear una conexion a base de datos Oracle
proccode: VC00PROC020
srcpath: "casos/VC00/PROC/020/procVC00PROC020.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Crea una conexión a una base de datos de Oracle, si la conexión ya existe se eliminará y se volverá a crear.

### Datos de entrada

1. ${check} **NAME**={% include var_tag.html var="NAME" %}. Nombre de la conexion a crear.

2. ${check} **SERVER**=```${SERVER}```. Direccion o nombre del servidor donde esta ejecutándose la instancia de Oracle.

3. ${check} **PORT**=```${PORT}```. Puerto TCP en el que está escuchando el servicio de Oracle.

4. ${check} **DATABASE**=```${DATABASE}```. Nombre de la base de datos a la que se va a conectar.

5. ${check} **USER**=```${USER}```. Nombre del usuario de Oracle con el que se va a conectar.

6. ${check} **PASSWORD**=```${PASSWORD}```. Clave del usuario.

7. ${check} **MODE**=```${MODE}```. Modo de la conexion, debera ser "SID" o "Servicio". La opción elegida
   dependerá de como esté configurado el servidor de Oracle.

Debe **prestar especial atención a que el nombre de usuario y la contraseña coincida en mayúsculas y minúsculas**
con el nombre de usuario dado de alta en la base de datos de Oracle. Oracle, en general, aceptará establecer
la conexión aunque el nombre no coincida en mayúsculas/minúsculas pero luego gvSIG desktop no funcionará correctamente
si no coinciden.

### Pasos


1. ${check} Al iniciarse este procedimiento deberá estar abierta la venta de conexiones a base de datos, 
   de título "Parámetros de conexión" y deberá estar activa.

2. ${check} Compruebe si existe la conexión ```${NAME}``` (NAME). Para ello mire si ya existe en el desplegable 
   del campo "Nombre de conexión" un valor con el nombre ```${NAME}``` (NAME).

3. ${check} Si existe selecciónelo y pulse el botón inferior que dice "Más...", seleccionando la
   opción "Eliminar" en el desplegable.

4. ${check} Introduzca el nombre ```${NAME}``` (NAME) {% include var_copy.html var="NAME"%} en la caja de texto "Nombre de conexión".

5. ${check} Indique como conector "Oracle Server".

7. ${check} Indique como servidor ```${SERVER}``` (SERVER).

8. ${check} Indique como puerto ```${PORT}``` (PORT).

9. ${check} Indique como base de datos ```${DATABASE}``` (DATABASE).

10. ${check} Indique como usuario ```${USER}``` (USER).

11. ${check} Indique como contraseña ```${PASSWORD}``` (PASSWORD).

12. ${check} Pulse en el botón "Mas..." y seleccione la opción "Avanzado". 
    Esto presentará una ventana de titulo "OracleServerExplorerParameters".
   
13. ${check} Seleccione la pestaña "Connection".

14. ${check} En el desplegable del campo "mode" seleccione la opción ```${MODE}``` (MODE)

15. ${check} Pulse el botón "Aceptar", se cerrará la ventana de titulo "OracleServerExplorerParameters".
   
16. ${check} Se habrá vuelto a la ventana de titulo "Parámetros de conexión".

17. ${check} Pulse el botón "Aceptar", se cerrará la ventana.
   
### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

Si se produce un error repórtelo en el test que está ejecutando.

{% include es/footer.html %}
