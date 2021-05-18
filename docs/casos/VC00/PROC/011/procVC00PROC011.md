---
title: Abrir tabla de base de datos
proccode: VC00PROC011
srcpath: "casos/VC00/PROC/011/procVC00PROC011.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Este proceso carga una tabla de base de datos desde la conexión a la base de datos indicada.

### Datos de entrada

1. ${check} **CONNAME**=```${CONNAME}```. Nombre de la base de datos.

2. ${check} **TABLENAME**=```${TABLENAME}```. Nombre de la tabla que se desea abrir.


### Pasos
1. ${check} Seleccione la opción de menú "Mostrar/Gestor de proyecto".

3. ${check} Se mostrará la ventana del gestor de proyecto, con ese mismo título.

4. ${check} Seleccione la opción "Tabla".

5. ${check} Pulse el botón "Nuevo". 

6. ${check} Se muestra una ventana de diálogo titulada "Nueva Tabla". 

7. ${check} De las pestañas situadas en la zona superior de la ventana seleccione la opción "Base de datos".

8. ${check} Tras lo anterior, el diálogo cambia permitiendo seleccionar conexiones a una base de datos.
   
9. ${check} En el desplegable "Conexión", seleccione la conexión ```${CONNAME}```.
   
10. ${check} Se mostrarán las tablas de la base de datos ```${CONNAME}```.

11. ${check} Seleccione y marque la casilla de verificación de la tabla ```${TABLENAME}```.

12. ${check} Pulse el botón "Aceptar" situado en la zona inferior del cuadro de diálogo.

13. ${check} Tras lo anterior, se muestra la tabla de nombre ```${TABLENAME}```.

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
