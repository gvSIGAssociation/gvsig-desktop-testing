---
title: Subir cambios en una capa con un plan topológico (que no pasen el plan)
proccode: VC00TP00CP0002
srcpath: "casos/VC00/TP00/CP002/testVC00TP00CP002.md"
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

Este proceso prueba que no es posible hacer un commit de una capa, ${ENTITIE},que no cumple un plan 
topológico, ${TPNAME}, asignado previamente en el repositorio, ${REPONAME}.

### Datos de entrada

1. ${check} **TMPFOLDER**=```${TMPFOLDER}```. Carpeta en la que se crearán los archivos que se precisen 
   durante la ejecución del test. Deberemos tener permiso de escritura en ella. 
   
2. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexión y del repositorio.

3. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia nueva de trabajo sobre la cual se realizará un checkout.

4. ${check} **TPNAME**=```${TPNAME}```. Nombre del plan topológico a asignar.

5. ${check} **ENTITIE1**=```${ENTITIE1}```. Capa o entidad del repositorio a la cual se le asigna el 
   plan topológico ${TPNAME}.

6. ${check} **ENTITIE2**=```${ENTITIE2}```. Capa o entidad del repositorio necesaria para 
    aplicar el plan topológico ${TPNAME}.

7. ${check} **USER**=```${USER}```. Nombre del usuario que realizará las operaciones con las tablas del repositorio.

8. ${check} **PASSWORD**=```${PASWORD}```. Contraseña del usuario que realizará las operaciones con las 
   tablas del repositorio.


### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas (hace menos de 1 hora) VC00TP00CP001,
    "Cargar un plan topológico en el repositorio"
    y no ha cerrado gvSIG, continúe con el paso 2. Si no, ejecútelo antes de continuar.

2. ${check} Cierre gvSIG.

3. ${check} Compruebe que no exista el fichero:
   * ```${TMPFOLDER}/${WCNAME}.mv.db``` (TMPFOLDER/WCNAME.mv.db). 
   
   En caso de que exista elimínelo.

4. ${check} Abra gvSIG

5. ${check} Inicialice una nueva copia de trabajo para ello siga los pasos de 
   [Inicializacion de una copia de trabajo (repositorio local en H2 con autorización)](../../PROC/008/procVC00PROC008.md.html?TMPFOLDER=${TMPFOLDER}&REPONAME=${REPONAME}&WCNAME=${WCNAME})

6. ${check} Asegúrese de que la vista que se ha creado al arrancar gvSIG se encuentra en "EPSG:4326",
   de no ser asi cámbie la proyección de la vista.

7. ${check} Seleccione la opción de menú "Herramientas"

8. ${check} Del desplegable surgido en la acción anterior seleccione la opción "VCSGis".

9. ${check} Del desplegable surgido en la acción anterior pulse la opción "Obtener copia local (checkout)" 

10. ${check} Tras lo anterior, se muestra la venanacon el título "Obtener copia local (checkout)".

11. ${check} Siga los pasos de [Obtención de una copia local (checkout)](../../PROC/006/procVC00PROC006.html?WCNAME=${WCNAME}&TABLENAME=${ENTITIE1}&USER=${USER}&PASSWORD=${PASSWORD})

12. ${check} Siga los pasos de [Obtención de una copia local (checkout)](../../PROC/005/procVC00PROC005.html?WCNAME=${WCNAME}&TABLENAME=${ENTITIE2})

13. ${check} Cierre el cuadro de diálogo "Obtener copia local (checkout)".

14. ${check} En la vista se habrá añadido las capas: 
    * ```${ENTITIE1}``` (ENTITIE1).
    * ```${ENTITIE2}``` (ENTITIE2).

15. ${check} Seleccione la capa ```${ENTITIE1}``` en el Toc.

16. ${check} Pulse botón derecho del mouse.

17. ${check} Seleccione la opción "Comenzar edición" del desplegable.

18. ${check} Seleccione la provincia de "Valencia" y desplacela fuera del área de la península ibérica hasta
    asegurarse de que no contenga ningúna población en su interior (Punto).

19. ${check} Seleccione la capa ```${ENTITIE1}``` en el Toc.

20. ${check} Pulse botón derecho del mouse.

21. ${check} Seleccione la opción "Terminar edición" del desplegable.

22. ${check} Tras realizar lo anterior, se despliega un ventana de diálogo titulada "Terminar edición".

23. ${check} Seleccione la opción "Guardar" para almacenar los cambios.

24. ${check} Pulse la opción de menú "Herramientas".

25. ${check} Del desplegable surgido en la acción anterior seleccione la opción "VCSGis".

26. ${check} Del desplegable surgido en la acción anterior pulse la opción "Mostrar cambios"

27. ${check} Se visualiza la ventana que muestra los cambios entre el repositorio y la copia de trabajo
   de título  "VCSGis Cambios".

28. ${check} Seleccione la copia de trabajo ```${WCNAME}``` (WCNAME).

29. ${check} Se muestra el contenido de la pestaña "Copia de trabajo" donde podrá apreciar,
    a la izquierda, un selector en forma de árbol (selector de entidades) que contiene la categoría que le 
    puso a la capa cuando la añadió y, bajo ésta, la capa añadida a la copia de trabajo.
    A la derecha se habrá mostrado una tabla vacía (tabla de cambios) y sobre ésta los botones de "Refrescar",
    "Revertir", "Commit", "Resaltar", "Centrar", "Zoom", "Limpiar geometrías resaltadas" y "Mostrar formulario".

30. ${check} Pulse la casilla de verificación asociada a la capa ```${ENTITIE1}``` (ENTITIE1).

31. ${check} En la tabla de cambios se muestran los cambios necesarios para insertar esta capa en el repositorio, 
    habilitandose también los botones de "Refrescar", "Revertir" y "Commit".

32. ${check} Introduzca en el campo "Fecha de entra en vigor" la fecha "3/05/2021"

33. ${check} Introduzca en el campo "Comentario" el texto "Modificación de la capa de ${ENTITIE1}"

34. ${check} Pulse el botón de "Commit"

35. ${check} Como consecuencia de lo anterior, se muestra una ventana que indica que es imposible realizar la 
    acción de commit puesto que hay elementos  de la capa ```${ENTITIE1}``` (ENTITIE1) que no cumplen el 
    plan topológico ```${TPNAME}```.
    
36. ${check} Pulse el botón de "Aceptar"

37. ${check} Tras esto , se muestra la ventana titulada "Inspector de errores del Plan de topología (${TPNAME})". 
    La cual presenta un error correspondiente a la provincia de "Valencia"
    
38. ${check} Cierre la ventana titulada "Inspector de errores del Plan de topología (${TPNAME})".

39. ${check} Cierre la ventana titulada "Mostrar cambios".

40. ${check} Deja la vista "Sin título" en primer plano y activa.
    
### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}