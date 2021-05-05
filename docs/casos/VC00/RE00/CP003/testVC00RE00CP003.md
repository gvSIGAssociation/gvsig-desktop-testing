---
title: Asociar leyenda a una capa (repositorio remoto en H2 con autorización)
proccode: VC00RE00CP0003
srcpath: "casos/VC00/RE00/CP003/testVC00RE00CP003.md"
---

**EN CONSTRUCCION**

{% include es/header.md %}

{% include parameter.html name="TABLE1_NAME" value="esp_provincias" %}

{% include parameter.html name="TABLE2_NAME" value="esp_poblaciones" %}

{% include parameter.html name="TABLE1_LINK" value="<a href='../../data/esp_provincias.csv'>ESP_PROVINCIAS</a>" %}

{% include parameter.html name="TABLE2_LINK" value="<a href='../../data/esp_poblaciones.csv'>ESP_POBLACIONES</a>" %}

{% include parameter.html name="TPNAME" value="ProvinciasDebenTenerPoblaciones" %}

{% include parameter.html name="TPDESCRIPTION" value="Las provincias deben tener alguna población" %}

{% include parameter.html name="TABLE2_FIELDFORLABEL" value="esp_poblaciones" %}

{% include parameter.html name="CATEGORY" value="Cartografia base" %}

{% include parameter.html name="WCNAME" value="CopiaDeTrabajo" %}

{% include parameter.html name="REPONAME" value="Repositorio" %}

{% include parameter.html name="LEYENDA_NAME" value="esp_provincias" %}

{% include parameter.html name="LEYENDA_LINK" value="<a href='../../data/esp_provincias.gvsleg'>ESP_PROVINCIAS</a>" %}


## {{ page.title }}

### Descripción

Este proceso carga un plan topológico en el repositorio.

### Datos de entrada

1. ${check} Archivo de datos 1: ```${TABLE1_NAME}``` (${TABLE1_LINK}). Capa número 1 a usar en este test. 

2. ${check} Archivo de datos 2: ```${TABLE2_NAME}``` (${TABLE2_LINK}). Capa número 2 a usar en este test. 

3. ${check} Archivo con leyenda predefinida: ```${LEYENDA_NAME}``` (${LEYENDA_LINK}). 
   Leyenda predefinida para la capa ```${TABLE1_NAME}``` (${TABLE1_LINK}). 

4. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexión y del repositorio.

5. ${check} **NAME**=```${TPNAME}```. Nombre del nuevo plan topológico a registrar.

6. ${check} **DESCRIPTION**=```${TPDESCRIPTION}```. Descripción del nuevo plan topológico a registrar.

7. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia de trabajo sobre la que se realiza el checkout.

8. ${check} **TABLE2_FIELDFORLABEL**=```${TABLE2_FIELDFORLABEL}```. Etiqueta de la 
   capa ```${TABLE2_NAME}``` (TABLE2_NAME)cargada en la copia de trabajo ```${WCNAME}``` (WCNAME).

9. ${check} **CATEGORY**=```${CATEGORY}```. Categoria a asignar la capa al hacer checkout.

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya versión sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} El caso de prueba 
   [VC00SY00CP002, "Commitar una capa nueva (repositorio remoto en H2 con autorización)"](../../SY00/CP002/testVC00SY00CP002.md),
   ha pasado sin errores.
   
### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas (hace menos de 1 hora) VC00SY00CP002,
    "Commitar una capa nueva (repositorio remoto en H2 con autorización)"
    y no ha cerrado gvSIG, continúe con el paso 2. Si no, ejecútelo antes de continuar.
    
2. ${check} Asegúrese de estar en la aplicación gvSIG Desktop ```cliente``` puesto que en primer lugar va a crear 
   una tabla de recursos que posteriormente va a rellenar con la leyenda de la capa. Tras esto va a hacer commit 
   de dicha información al repositorio.

3. ${check} Proceda a crear la tabla de recursos. Para ello pulse el menú "Herramientas".
   
4. ${check} Pulse la opción "VCSGis" del desplegable anterior.

5. ${check} Seleccione la opción "Administración".

6. ${check} Pulse del desplegable la opción "Crear tabla de recursos".

7. ${check} Se presenta un cuadro de diálogo titulado "Crear tabla de recursos".
     
8. ${check} En el campo "Copia de trabajo" seleccione ```${WCNAME}``` (WCNAME). Esta copia de trabajo tiene 
   que disponer de la capa, ```${TABLE1_NAME}``` (${TABLE1_LINK}), a la cual se desea asignar el recurso.

9. ${check} En el campo "Nombre de tabla" especifique el nombre ```CBASE_RESOURCES``` puesto que la 
   capa ```${TABLE1_NAME}``` (${TABLE1_LINK}) presenta la categoría ```${CATEGORY}``` (CATEGORY)

10. ${check} Pulse el botón "Aceptar".

11. ${check} Con la tabla de recursos ```CBASE_RESOURCES``` ya creada hay que introducir esta el fichero
    ```${LEYENDA_NAME}``` (${LEYENDA_LINK}). Abra la tabla de recursos ```CBASE_RESOURCES```. Siga los pasos de 
    [Abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?BBDD=${REPONAME}&TABLENAME=$CBASE_RESOURCES)

12. ${check} Una vez abierta la tabla y estando esta activa se procede a añadir en esta un nuevo registro. Para ello 
    seleccione "Tabla" en el menú de gvSIG Desktop.

13. ${check} Seleccione del despeglable anterior la opción "Show form". 

14. ${check} Como resultado se genera una nueva ventana que muestra el formulario asociado a la tabla de recursos.

15. ${check} Para registrar cambios en esta hay que iniciar la edición. Para iniciar la edición pulse el icono con la
   etiqueta "Comenzar edición". Los iconos se muestran en la zona inferior de la ventana y el de comenzar edición se
   encuentra en la zona media de estos.

16. ${check} La acción anterior habilita una serie de iconos.

17. ${check} Pulse el icono con la etiqueta "Nuevo" recientemente habilitado.

19. ${check} Como consecuencia de lo anterior, algunos de los campos de la página actual del formulario se muestran
    sin datos a la espera de la nueva información.

19. ${check} Indroduce el nombre del nuevo recurso, ```${LEYENDA_NAME}.gvsleg``` en el campo correspondiente.

20. ${check} Localiza el campo "Recurso" y de los dos iconos adyacentes a este pulse el que presenta una flecha
   ascendente de color azul.

   [IconoSubirRecurso]!(../iconoSubirRecurso.png)










   

10. ${check} Pulse el icono con la etiqueta "Guardar".

11. ${check} Para terminar el proceso y trás guardar cambios hay que terminar la edición. Para terinar la edición pulse 
    el icono con la etiqueta "Terminar edición". Este se encuentra la zona media de los iconos. 

12. ${check} Cierre el formulario.

13. ${check} Cierre la tabla en cuestión

13. ${check} Siga los pasos de 
    [Añadir capa a la copia de trabajo](../../PROC/003/VC00PROC003.html?WCNAME=${WCNAME}&LAYER=${TABLE2_NAME}&FIELDFORLABEL=${TABLE2_FIELDFORLABEL}&CATEGORY=${CATEGORY}) 

14. ${check} Debera haber aparecido en la vista una capa 
    ```${TABLE2_NAME}```(${TABLE2_LINK}) con el identificativo de una capa de base de datos H2.

15. ${check} Elimine de la vista la capa ```${TABLE2_NAME}``` cargada 
    a partir del fichero ${TABLE2_LINK} con el identificativo de una capa "normal".

16. ${check} Pulse la opción de menú "Herramientas".

17. ${check} Del desplegable surgido en la acción anterior seleccione la opción "VCSGis".

18. ${check} Del desplegable surgido en la acción anterior pulse la opción "Mostrar cambios"

19. ${check} Se visualiza la ventana que muestra los cambios entre el repositorio y la copia de trabajo
   de título  "VCSGis Cambios".

20. ${check} Seleccione la copia de trabajo ```${WCNAME}``` (WCNAME).

21. ${check} Se muestra el contenido de la pestaña "Copia de trabajo" donde podrá apreciar,
    a la izquierda, un selector en forma de árbol (selector de entidades) que contiene la categoría que le 
    puso a la capa cuando la añadió y, bajo ésta, la capa añadida a la copia de trabajo.
    A la derecha se habrá mostrado una tabla vacía (tabla de cambios) y sobre ésta los botones de "Refrescar",
    "Revertir", "Commit", "Resaltar", "Centrar", "Zoom", "Limpiar geometrías resaltadas" y "Mostrar formulario".

22. ${check} Pulse la casilla de verificación asociada a la capa ```${TABLE2_NAME}``` (TABLE2_NAME).

23. ${check} En la tabla de cambios se muestran los cambios necesarios para insertar esta capa en el repositorio, 
    habilitandose también los botones de "Refrescar", "Revertir" y "Commit".

24. ${check} Introduzca en el campo "Fecha de entra en vigor" la fecha "3/05/2021"

25. ${check} Introduzca en el campo "Comentario" el texto "Adición de la capa de ${TABLE2_NAME}"

26. ${check} Pulse el botón de "Commit"

27. ${check} Una vez termine el proceso, cuyo progreso se puede ver en la barra de estado de este diálogo,
    se habrá vaciado la tabla de cambios y se habrán deshabilitado los botones de "Refrescar", "Revertir" y "Commit".
    
28. ${check} Cierre la ventana de cambios.

29. ${check} Minimice la aplicación gvSIG Desktop ```cliente````.

30. ${check} Active la aplicación gvSIG Desktop ```servidor```. A partir de ahora va a configurar el servidor para 
    registrar el plan topológico.

31. ${check} Abra la tabla ```VCSGISREPO_TOPOLOGYPLANS``` de este. Siga los pasos de 
    [Abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?BBDD=${REPONAME}&TABLENAME=VCSGISREPO_TOPOLOGYPLANS)

32. ${check} Una vez abierta la tabla y estando esta activa se procede a añadir en esta un nuevo registro. Para ello 
    seleccione "Tabla" en el menú de gvSIG Desktop.

33. ${check} Seleccione del despeglable anterior la opción "Show form". 

34. ${check} Como resultado se genera una nueva ventana que muestra el formulario asociado a la tabla 
    de planes topológicos.

35. ${check} Para registrar cambios en esta hay que iniciar la edición. Para iniciar la edición pulse el icono con la
   etiqueta "Comenzar edición". Los iconos se muestran en la zona inferior de la ventana y el de comenzar edición se
   encuentra en la zona media de estos.

36. ${check} La acción anterior habilita una serie de iconos.

37. ${check} Pulse el icono con la etiqueta "Nuevo" recientemente habilitado.

38. ${check} Como consecuencia de lo anterior, algunos de los campos de la página actual del formulario se muestran
    sin datos a la espera de la nueva información.

39. ${check} En la pestaña "General" de la ventana se indroduce el nombre del nuevo plan topológico,
    ```${TPNAME}``` en el campo correspondiente, Nombre.

40. ${check} En la pestaña "General" de la ventana se indroduce la descripción del nuevo plan topológico,
    ```${TPDESCRIPTION}```, en el campo correspondiente, Descripción.

41. ${check} En la pestaña "Plan" de la ventana se indroduce el plan topológico en formatao JSON del 
    nuevo plan topológico: 

    ```
    {"name":"provinciasDebenTenerPoblaciones","dataSets":[
      {"name":"esp_provincias","fullName":"esp_provincias.csv"},
      {"name":"esp_poblaciones","fullName":"esp_poblaciones.csv"}
    ],
    "rules":[
      {"__factoryId":"ContainsPoint","dataSet2":"esp_poblaciones",
      "dataSet1":"esp_provincias","tolerance":0}
    ],
    "tolerance":0
    }
    ```
    Este se obtiene de la opción "Copy topology plan to clipboard" de la 
    ventana "Plan de topología" del módulo de topología.

42. ${check} Pulse el icono con la etiqueta "Guardar".

43. ${check} Para terminar el proceso y trás guardar cambios hay que terminar la edición. Para terinar 
    la edición pulse el icono con la etiqueta "Terminar edición". Este se encuentra la zona media de los iconos. 

44. ${check} Cierre el formulario.

45. ${check} Cierre la tabla en cuestión

46. ${check} Tras lo anterior, la ventana "Servidor VCSGis" queda activa y visible.


### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
