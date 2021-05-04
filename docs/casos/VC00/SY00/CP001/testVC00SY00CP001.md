---
title: Commitar una capa nueva (repositorio local en H2 con autorización)
testcode: VC00SY00CP001
srcpath: casos/VC00/SY00/CP001/testVC00SY00CP001.md
---


**------------- FIXME (paco) --------------**



{% include es/header.md %}

{% include parameter.html name="WCNAME" value="CopiaDeTrabajo" %}

{% include parameter.html name="TABLENAME" value="esp_comunidades" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}


## {{ page.title }}

### Descripción

Este caso verifica que se puede commitar al repositorio una capa recien añadida a una copia de trabajo.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada:

1. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia de trabajo. 

2. ${check} **TABLENAME** ```${TABLENAME}```. Capa a usar en este test. 

2. ${check} **USER** ```${USER}```. Identificador de usuario para este test. 

2. ${check} **PASSWORD** ```${PASSWORD}```. Contraseña de usuario para este test. 


### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya version sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} El caso de prueba [VC00AD00CP001, "Añadir capa a copia de trabajo (con autorizacion)"](../../AD00/CP001/testVC00AD00CP001.md),
   ha pasado sin errores.

### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas (hace menos de 1 hora)
   [VC00AD00CP001, "Añadir capa a copia de trabajo (con autorizacion)"](../../AD00/CP001/testVC00AD00CP001.md)
   y no ha cerrado gvSIG, continúe con el paso 2. 
   Si no, lo ejecútelo antes de continuar.
   
2. ${check} Pulse en la opcion de menu "Herramientas/VCSGis/Mostrar cambios".

3. ${check} Se habrá presentado la ventana que muestra los cambios entre el repositorio y la copia de trabajo
   de titulo  "VCSGis Cambios".

4. ${check} Seleccione la copia de trabajo ```${WCNAME}``` (WCNAME).

6. ${check} Se habrá mostrado el contenido de la pestaña "Copia de trabajo" donde podrá apreciar, a la izquierda, un selector en forma de árbol (selector de entidades) que contiene la categoría que le puso a la capa cuando la añadió y, bajo ésta, la capa añadida a la copia de trabajo. A la derecha se habrá mostrado una tabla vacía (tabla de cambios) y sobre ésta los botones de "Refrescar", "Revertir", "Commit", "Resaltar", "Centrar", "Zoom", "Limpiar geometrías resaltadas" y "Mostrar formulario".

7. ${check} Pulse la casilla de verificación asociada a la capa ```${TABLENAME}``` (TABLENAME).

8. ${check} En la tabla de cambios se habrán mostrado los cambios necesarios para insertar esta capa en el repositorio y se habrán habilitado los botones de "Refrescar", "Revertir" y "Commit".

9. ${check} Introduzca en el campo "Fecha de entra en vigor" la fecha "3/05/2021"

11. ${check} Introduzca en el campo "Comentario" el texto "Adición de la capa de autonomías"

11. ${check} Pulse el botón de "Commit"

12. ${check} Una vez termine el proceso, cuyo progreso se puede ver en la barra de estado de este diálogo, se habrá vaciado la tabla de cambios.



### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
