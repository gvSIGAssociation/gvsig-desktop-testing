---
title: Commitar una capa nueva (repositorio remoto con autorización)
testcode: VC00SY00CP002
srcpath: casos/VC00/SY00/CP002/testVC00SY00CP002.md
---

{% include es/header.md %}

{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo" %}

{% include parameter.html name="TABLENAME" value="esp_provincias" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}


## {{ page.title }}

### Descripción

Este caso verifica que se puede commitar al repositorio una capa recién añadida a una copia de trabajo.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada:

1. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia de trabajo. 

2. ${check} **TABLENAME** ```${TABLENAME}```. Capa a usar en este test. 

2. ${check} **USER** ```${USER}```. Identificador de usuario para este test. 

2. ${check} **PASSWORD** ```${PASSWORD}```. Contraseña de usuario para este test. 


### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya versión sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} El caso de prueba [VC00AD00CP002, "Añadir capa a copia de trabajo)"](../../AD00/CP002/testVC00AD00CP002.md),
   ha pasado sin errores.

### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas
   [VC00AD00CP002, "Añadir capa a copia de trabajo (repositorio remoto con autorización)"](../../AD00/CP002/testVC00AD00CP002.md)
   (hace menos de 1 hora) y no ha cerrado gvSIG, continúe con el paso 2. 
   Si no, ejecútelo antes de continuar.
   
2. ${check} Pulse en la opción de menú "Herramientas/VCSGis/Mostrar cambios".

3. ${check} Se habrá presentado la ventana de título  "VCSGis Cambios" que muestra los cambios entre el repositorio y la copia de trabajo.

4. ${check} Seleccione la copia de trabajo ```${WORKINGCOPY}``` (WCNAME).

5. ${check} Se habrá mostrado el contenido de la pestaña "Copia de trabajo" donde podrá apreciar, a la izquierda, 
   un selector en forma de árbol (selector de entidades) que contiene la categoría que le puso a la capa cuando la añadió y, 
   bajo ésta, la capa añadida a la copia de trabajo. A la derecha se habrá mostrado una tabla vacía (tabla de cambios) y 
   sobre ésta los botones de "Refrescar", "Revertir", "Commit", "Resaltar", "Centrar", "Zoom", "Limpiar geometrías resaltadas" y "Mostrar formulario".

6. ${check} Pulse la casilla de verificación asociada a la capa ```${TABLENAME}``` (TABLENAME).

7. ${check} En la tabla de cambios se habrán mostrado los cambios necesarios para insertar esta capa en el repositorio y se habrán habilitado 
   los botones de "Refrescar", "Revertir" y "Commit".

8. ${check} Introduzca en el campo "Fecha de entra en vigor" la fecha "3/05/2021"

9. ${check} Introduzca en el campo "Comentario" el texto "Adición de la capa de ${TABLENAME}"

10. ${check} Pulse el botón de "Commit"

11. ${check} Una vez termine el proceso, cuyo progreso se puede ver en la barra de estado de este diálogo, 
    se habrá vaciado la tabla de cambios y se habrán deshabilitado los botones de "Revertir" y "Commit".

12. ${check} Cierre la ventana de cambios. 

13. ${check} Cierre la ventana de la vista "Sin título". 

14. ${check} Únicamente deberá estar abierta la ventana del proyecto de gvSIG.

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
