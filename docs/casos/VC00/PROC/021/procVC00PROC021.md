---
title: Commit simple de una tabla.
proccode: VC00PROC021
srcpath: "casos/VC00/PROC/021/procVC00PROC021.md"
---

{% include es/header.md %}

## {{ page.title }}

{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo" %}

{% include parameter.html name="TABLENAME" value="esp_provincias" %}

{% include parameter.html name="EFECTIVEDATE" value="3/05/2021" %}

{% include parameter.html name="COMMENT" value="Adición de la capa de esp_provincias" %}


### Descripción

Commita los cambios que hay pendientes de la capa indicada.

### Datos de entrada

1. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia de trabajo a usar. 

1. ${check} **TABLENAME** ```${TABLENAME}```. Capa de la que queremos commitar los cambios. 

1. ${check} **EFECTIVEDATE**={% include var_tag.html var="EFECTIVEDATE" %} Fecha de entrada en vigor para el commit.

1. ${check} **COMMENT**={% include var_tag.html var="COMMENT" %} Comentario para el commit.

### Pasos

1. ${check} Al entrar en este procedimiento se estará viendo y activa la ventana de titulo "VCSGis Cambios".

2. ${check} Seleccione la copia de trabajo ```${WORKINGCOPY}``` (WORKINGCOPY).

3. ${check} Se habrá mostrado el contenido de la pestaña "Copia de trabajo" donde podrá apreciar, a la izquierda, 
   un selector en forma de árbol (selector de entidades) que contiene la categoría que le puso a la capa cuando la añadió y, 
   bajo ésta, la capa añadida a la copia de trabajo. A la derecha se habrá mostrado una tabla vacía (tabla de cambios) y 
   sobre ésta los botones de "Refrescar", "Revertir", "Commit", "Resaltar", "Centrar", "Zoom", "Limpiar geometrías resaltadas" y "Mostrar formulario".

4. ${check} Pulse la casilla de verificación asociada a la tabla ```${TABLENAME}``` (TABLENAME).

5. ${check} En la tabla de cambios se habrán mostrado los cambios que se deben commitar al repositorio y se habrán habilitado 
   los botones de "Refrescar", "Revertir" y "Commit".

6. ${check} Introduzca en el campo "Fecha de entra en vigor" la fecha ```${EFECTIVEDATE}``` {% include var_copy.html var="EFECTIVEDATE"%}.

7. ${check} Introduzca en el campo "Comentario" el texto ```${COMMENT}``` {% include var_copy.html var="COMMENT"%}.

8. ${check} Pulse el botón de "Commit"

9. ${check} Una vez termine el proceso, cuyo progreso se puede ver en la barra de estado de este diálogo, 
    se habrá vaciado la tabla de cambios y se habrán deshabilitado los botones de "Revertir" y "Commit".

10. ${check} Cierre la ventana de cambios. 
 
### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

Si se produce un error reportelo en el test que esta ejecutando.

{% include es/footer.html %}
