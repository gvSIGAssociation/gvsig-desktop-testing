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

{% include parameter.html name="ENTITIE2" value="esp_poblaciones" %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="WCNAME" value="CopiaDeTrabajo2" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}


## {{ page.title }}

### Descripción

Este proceso prueba que es posible hacer un commit de una capa, ```${ENTITIE1}``` (ENTITIE1), que cumple un plan 
topológico, ```${TPNAME}``` (TPNAME), asignado previamente en el repositorio, ```${REPONAME}``` (REPONAME).

### Datos de entrada
  
1. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexión y del repositorio.

2. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia nueva de trabajo sobre la cual se realizará un checkout.

3. ${check} **TPNAME**=```${TPNAME}```. Nombre del plan topológico a asignar.

4. ${check} **ENTITIE1**=```${ENTITIE1}```. Capa o entidad del repositorio a la cual se le asigna el 
   plan topológico ```${TPNAME}``` (TPNAME).

5. ${check} **ENTITIE2**=```${ENTITIE2}```. Capa o entidad del repositorio necesaria para 
    aplicar el plan topológico ```${TPNAME}``` (TPNAME).

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya versión sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} El complemento de Topología debe estar instalado y activo.

4. ${check} El caso de prueba 
   [VC00TP00CP002, "Subir cambios en una capa con un plan topológico (que no pasen el plan)"](../../TP00/CP002/testVC00TP00CP002.md),
   ha pasado sin errores.

### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas (hace menos de 1 hora) VC00TP00CP002,
    "Subir cambios en una capa con un plan topológico (que no pasen el plan)"
    y no ha cerrado gvSIG, continúe con el paso 2. Si no, ejecútelo antes de continuar.

2. ${check} Asegúrese de estar en la aplicación gvSIG Desktop ```cliente```.

3. ${check} Seleccione la capa ```${ENTITIE1}``` (ENTITIE1) en el Toc.

4. ${check} Pulse botón derecho del mouse.

5. ${check} Seleccione la opción "Comenzar edición" del desplegable.

6. ${check} Seleccione la provincia de "Valencia" y desplacela dentro del área de la península ibérica hasta
    asegurarse de que contenga alguna población en su interior (Punto) de la capa ```${ENTITIE2}``` (ENTITIE2).

7. ${check} Seleccione la capa ```${ENTITIE1}``` (ENTITIE1) en el Toc.

8. ${check} Pulse botón derecho del mouse.

9. ${check} Seleccione la opción "Terminar edición" del desplegable.

10. ${check} Tras realizar lo anterior, se despliega un ventana de diálogo titulada "Terminar edición".

11. ${check} Seleccione la opción "Guardar" para almacenar los cambios.

12. ${check} Pulse la opción de menú "Herramientas".

13. ${check} Del desplegable surgido en la acción anterior seleccione la opción "VCSGis".

14. ${check} Del desplegable surgido en la acción anterior pulse la opción "Mostrar cambios".

15. ${check} Se visualiza la ventana que muestra los cambios entre el repositorio y la copia de trabajo
   de título  "VCSGis Cambios".

16. ${check} Seleccione la copia de trabajo ```${WCNAME}``` (WCNAME).

17. ${check} Se muestra el contenido de la pestaña "Copia de trabajo" donde podrá apreciar,
    a la izquierda, un selector en forma de árbol (selector de entidades) que contiene la categoría que le 
    puso a la capa cuando la añadió y, bajo ésta, la capa añadida a la copia de trabajo.
    A la derecha se habrá mostrado una tabla vacía (tabla de cambios) y sobre ésta los botones de "Refrescar",
    "Revertir", "Commit", "Resaltar", "Centrar", "Zoom", "Limpiar geometrías resaltadas" y "Mostrar formulario".

18. ${check} Pulse la casilla de verificación asociada a la capa ```${ENTITIE1}``` (ENTITIE1).

19. ${check} En la tabla de cambios se muestran los cambios necesarios para insertar esta capa en el repositorio, 
    habilitandose también los botones de "Refrescar", "Revertir" y "Commit".

20. ${check} Introduzca en el campo "Fecha de entra en vigor" la fecha "3/05/2021"

21. ${check} Introduzca en el campo "Comentario" el texto "Modificación de la capa de ${ENTITIE1}"

22. ${check} Pulse el botón de "Commit"

23. ${check} Cierre la ventana titulada "Mostrar cambios".

24. ${check} Deja la vista "Sin título" en primer plano y activa.

    
### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}