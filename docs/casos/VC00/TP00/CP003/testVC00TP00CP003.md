---
title: Subir cambios en una capa con un plan topológico (que sí pasen el plan)
proccode: VC00TP00CP0003
srcpath: "casos/VC00/TP00/CP003/testVC00TP00CP003.md"
---

**EN CONSTRUCCION**

{% include es/header.md %}

{% include parameter.html name="REPONAME" value="Repositorio" %}

{% include parameter.html name="TPNAME" value="ProvinciasDebenTenerPoblaciones" %}

{% include parameter.html name="ENTITIE1" value="esp_provincias" %}

{% include parameter.html name="ENTITIE2" value="esp_provincias" %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="WCNAME" value="CopiaDeTrabajo2" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}


## {{ page.title }}

### Descripción

Este proceso prueba que es posible hacer un commit de una capa, ${ENTITIE1},que cumple un plan 
topológico, ${TPNAME}, asignado previamente en el repositorio, ${REPONAME}.

### Datos de entrada
  
1. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexión y del repositorio.

2. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia nueva de trabajo sobre la cual se realizará un checkout.

3. ${check} **TPNAME**=```${TPNAME}```. Nombre del plan topológico a asignar.

4. ${check} **ENTITIE1**=```${ENTITIE1}```. Capa o entidad del repositorio a la cual se le asigna el 
   plan topológico ${TPNAME}.

5. ${check} **ENTITIE2**=```${ENTITIE2}```. Capa o entidad del repositorio necesaria para 
    aplicar el plan topológico ${TPNAME}.


### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas (hace menos de 1 hora) VC00TP00CP002,
    "Subir cambios en una capa con un plan topológico (que no pasen el plan)"
    y no ha cerrado gvSIG, continúe con el paso 2. Si no, ejecútelo antes de continuar.

2. ${check} Seleccione la capa ```${ENTITIE1}``` en el Toc.

3. ${check} Pulse botón derecho del mouse.

4. ${check} Seleccione la opción "Comenzar edición" del desplegable.

5. ${check} Seleccione la provincia de "Valencia" y desplacela dentro del área de la península ibérica hasta
    asegurarse de que contenga alguna población en su interior (Punto) de la capa ```${ENTITIE2}```.

6. ${check} Seleccione la capa ```${ENTITIE1}``` en el Toc.

7. ${check} Pulse botón derecho del mouse.

8. ${check} Seleccione la opción "Terminar edición" del desplegable.

9. ${check} Tras realizar lo anterior, se despliega un ventana de diálogo titulada "Terminar edición".

10. ${check} Seleccione la opción "Guardar" para almacenar los cambios.

11. ${check} Pulse la opción de menú "Herramientas".

12. ${check} Del desplegable surgido en la acción anterior seleccione la opción "VCSGis".

13. ${check} Del desplegable surgido en la acción anterior pulse la opción "Mostrar cambios".

14. ${check} Se visualiza la ventana que muestra los cambios entre el repositorio y la copia de trabajo
   de título  "VCSGis Cambios".

15. ${check} Seleccione la copia de trabajo ```${WCNAME}``` (WCNAME).

16. ${check} Se muestra el contenido de la pestaña "Copia de trabajo" donde podrá apreciar,
    a la izquierda, un selector en forma de árbol (selector de entidades) que contiene la categoría que le 
    puso a la capa cuando la añadió y, bajo ésta, la capa añadida a la copia de trabajo.
    A la derecha se habrá mostrado una tabla vacía (tabla de cambios) y sobre ésta los botones de "Refrescar",
    "Revertir", "Commit", "Resaltar", "Centrar", "Zoom", "Limpiar geometrías resaltadas" y "Mostrar formulario".

17. ${check} Pulse la casilla de verificación asociada a la capa ```${ENTITIE1}``` (ENTITIE1).

18. ${check} En la tabla de cambios se muestran los cambios necesarios para insertar esta capa en el repositorio, 
    habilitandose también los botones de "Refrescar", "Revertir" y "Commit".

19. ${check} Introduzca en el campo "Fecha de entra en vigor" la fecha "3/05/2021"

20. ${check} Introduzca en el campo "Comentario" el texto "Modificación de la capa de ${ENTITIE1}"

21. ${check} Pulse el botón de "Commit"

22. ${check} Cierre la ventana titulada "Mostrar cambios".

23. ${check} Deja la vista "Sin título" en primer plano y activa.
    
### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}