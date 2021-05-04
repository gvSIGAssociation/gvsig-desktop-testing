---
title: Abrir tabla de base de datos
proccode: VC00PROC011
srcpath: "casos/VC00/PROC/011/procVC00PROC011.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Este proceso accede a la tabla llamada ```${TABLENAME}``` de la base de datos ```${BBDD}``` y la abre.

### Datos de entrada

1. ${check} **BBDD**=```${BBDD}```. Nombre de la base de datos.

2. ${check} **TABLENAME**=```${TABLENAME}```. Nombre de la tabla que se desea abrir.


### Pasos
1. ${check} Para inicial el proceso acceda al menú Mostrar .

2. ${check} Seleccione del despeglable anterior la opción "Gestor de proyecto". 

3. ${check} Cuando se inicia este procedimiento se debe ver la ventana del gestor de proyecto, con ese mismo título.

4. ${check} Marque la opción "Tabla".

5. ${check} Pulse el botón "Nuevo". Solo tiene que estas ese habilitado.

6. ${check} Como resultado de lo anterior se muestra una ventana de diálogo titulada "Nueva Tabla". 

7. ${check} De las pestañas situadas en la zona superior de la ventana seleccione la opción "Base de datos".

8. ${check} Tras lo anterior, el diálogo cambia permitiendo seleccionar conexiones a una base de datos.
   
9. ${check} En el desplegable llamado "Conexión", seleccione la conexión ```${BBDD}```.
   
10. ${check} La acción anterior recarga uno de los cuadros inferiores con todas las tablas de la base de datos ```${BBDD}```.

11. ${check} Seleccione y marque el "check" de la tabla ```${TABLENAME}```.

12. ${check} Pulse el botón "Aceptar" situado en la zona inferior del cuadro de diálogo.

13. ${check} Tras lo anterior, se muestra la tabla de nombre ```${TABLENAME}```.

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
