---
title: Asociar leyenda a una capa (repositorio remoto en H2 con autorización)
proccode: VC00RE00CP0003
srcpath: "casos/VC00/RE00/CP003/testVC00RE00CP003.md"
---

**EN CONSTRUCCION**

{% include es/header.md %}

{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo" %}

{% include parameter.html name="TABLE_NAME" value="esp_provincias" %}

{% include parameter.html name="TABLE_LINK" value="<a href='../../data/esp_provincias.csv'>ESP_PROVINCIAS</a>" %}

{% include parameter.html name="RESOURCES_TABLE_NAME" value="RES_CARTOGRAFIA_BASE" %}

{% include parameter.html name="RESOURCES_CATEGORY" value="Cartografia base" %}





{% include parameter.html name="WCNAME2" value="CopiaDeTrabajo3" %}

{% include parameter.html name="REPONAME" value="Repositorio" %}

{% include parameter.html name="LEGEND_NAME" value="esp_provincias.gvsleg" %}

{% include parameter.html name="LEGEND_LINK" value="<a href='../../data/esp_provincias.gvsleg'>ESP_PROVINCIAS.GVSLEG</a>" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="FIELDFORLABEL" value="Nombre" %}


## {{ page.title }}

### Descripción

Este proceso crea una tabla de recursos, la sube al repositorio y la asocia como tabla de recursos 
de una capa, añadiendo a la tabla de recursos recien creada una leyenda para la capa.

### Datos de entrada

1. ${check} **TMPFOLDER**=```${TMPFOLDER}```. Carpeta en la que se crearán los archivos que se precisen 
   durante la ejecución del test. Deberemos tener permiso de escritura en ella. 

2. ${check} Archivo de datos: ```${TABLE_NAME}``` (${TABLE_LINK}). Capa a usar en este test. 

3. ${check} Archivo con leyenda  ```${LEGEND_NAME}``` (${LEGEND_LINK}) a usar como la keyenda por defecto
   para la capa ```${TABLE_NAME}``` (${TABLE_LINK}). 

5. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia de trabajo sobre la que se realiza el 
   proceso de registrar el recurso.

6. ${check} **WCNAME2**=```${WCNAME2}```. Nombre de la copia de trabajo sobre la que se realiza el checkout 
   de la capa con la leyenda asignada.

7. ${check} **FIELDFORLABEL**=```${FIELDFORLABEL}```. Nombre del campo de la tabla a añadir
   a usar en "Campo para etiqueta".

8. ${check} **CATEGORY**=```${CATEGORY}```. Categoria a asignar la capa al hacer checkout.

9. ${check} **USER**=```${USER}```. Identificador de usuario.

10. ${check} **PASSWORD**=```${PASSWORD}```. Contraseña de usuario.

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya versión sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} El caso de prueba 
   [VC00SY00CP002, "Commitar una capa nueva"](../../SY00/CP002/testVC00SY00CP002.md),
   ha pasado sin errores.
   
### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas 
   [VC00SY00CP002 "commitar una capa nueva"](../../SY00/CP002/testVC00SY00CP002.md)
    (hace menos de 1 hora) y aun tiene abierto gvSIG desktop  ```Servidor``` 
    continúe con el paso 2. Si no, ejecútelo antes de continuar.

3. ${check} Active la aplicación gvSIG desktop  ```Cliente``` 

3. ${check} Vamos a crear la tabla de recursos. Seleccione la opción de menú "Herramientas/VCSGis/Administración/Crear tabla de recursos".

7. ${check} Se presenta un cuadro de diálogo titulado "Crear tabla de recursos".
     
8. ${check} En el desplegable del campo "Copia de trabajo" seleccione la opción ```${WORKINGCOPY}``` (WORKINGCOPY). 

9. ${check} En el campo "Nombre de tabla" especifique el nombre ```${RESOURCES_TABLE_NAME}```.

10. ${check} Pulse el botón "Aceptar".

11. ${check} Vamos a guardar la leyenda en la tabla de recursos.  Siga los pasos de 
    [abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?CONNAME=${WORKINGCOPY}&TABLENAME=${RESOURCES_TABLE_NAME})

12. ${check} Una vez abierta la tabla y estando esta activa se procede a añadir en esta un nuevo registro. Para ello 
    seleccione la opción de menú "Tabla/Show form". 

14. ${check} Como resultado se abrira una ventana que muestra el formulario asociado a la tabla de recursos.

15. ${check} Iniciaremos edicón pulsando en el boton con la etiqueta "Comenzar edición". 
    Los botones se muestran en la zona inferior de la ventana y el de comenzar edición se encuentra en la zona media de estos.

16. ${check} La acción anterior habilita una serie de botones. Pulse el boton con la etiqueta "Nuevo".

18. ${check} Se habilitaran los campos del formulario y se mostraran sin datos.

19. ${check} Indroduzca el valor ```${LEGEND_NAME}``` (LEGEND_NAME) en el campo "Nombre".

19. ${check} Pulse el boton de cargar datos asociado al campo "Recurso". Podra identificarlo por contener
    una flecha hacia arriba ![IconoSubirRecurso](iconoSubirRecurso.png) .

21. ${check} Se presenta un cuadro de diálogo para seleccionar un fichero. 
    Seleccione el correspondiente a ```${LEGEND_NAME}``` (${LEGEND_LINK}).
    y pulse en el boton "Abrir".

23. ${check} De vuelta en el formulario de la tabla de recursos el campo "Recurso" tiene
    que estar relleno con el tamaño del archivo ```${LEGEND_NAME}```.

24. ${check} Pulse el icono con la etiqueta "Guardar".

25. ${check} Termine edicion pulsando en el boton con la "Terminar edición". 
    Este se encuentra la zona media de los iconos.  Al hacerlo se le preguntara si desea
    guardar los cambios, pulse en "aceptar".

26. ${check} Cierre el formulario.

27. ${check} Cierre la tabla ${RESOURCES_TABLE_NAME}.




28. ============FIXME==========    ${check} Añada la tabla de recursos ```${RESOURCES_TABLE_NAME}``` a la copia de trabajo. Siga los pasos de 
    [añadir tabla a una copia de trabajo](../../PROC/014/procVC00PROC014.html?WCNAME=${WCNAME}&TABLE=CBASE_RESOURCE&FIELDFORLABEL=${FIELDFORLABEL}&CATEGORY=${CATEGORY})

29. ${check} Pulse la opción "Herramientas/VCSGis/Mostrar cambios".

30. ${check} Se visualiza la ventana que muestra los cambios entre el repositorio y la copia de trabajo
   de título  "VCSGis Cambios".

31. ${check} Seleccione la copia de trabajo ```${WCNAME}``` (WCNAME).

32. ${check} Se muestra el contenido de la pestaña "Copia de trabajo" donde podrá apreciar,
    a la izquierda, un selector en forma de árbol (selector de entidades) que contiene la categoría que le 
    puso a la capa cuando la añadió y, bajo ésta, la capa añadida a la copia de trabajo.
    A la derecha se habrá mostrado una tabla vacía (tabla de cambios) y sobre ésta los botones de "Refrescar",
    "Revertir", "Commit", "Resaltar", "Centrar", "Zoom", "Limpiar geometrías resaltadas" y "Mostrar formulario".

33. ${check} Pulse la casilla de verificación asociada a la tabla ```CBASE_RESOURCE```.

34. ${check} En la tabla de cambios se muestran los cambios necesarios para insertar esta capa en el repositorio, 
    habilitandose también los botones de "Refrescar", "Revertir" y "Commit".

35. ${check} Introduzca en el campo "Fecha de entra en vigor" la fecha "3/05/2021"

36. ${check} Introduzca en el campo "Comentario" el texto "Añadir tabla de recursos: ```CBASE_RESOURCE```"

37. ${check} Pulse el botón de "Commit"

38. ${check} Cierre la ventana titulada "Mostrar cambios".

39. ${check} Cierre la aplicación gvSIG Desktop ```cliente````.

40. ${check} Active la aplicación gvSIG Desktop ```servidor```. A partir de ahora va a configurar el servidor para 
    registrar el recurso a la capa ```${TABLE_NAME}``` (${TABLE_LINK}).

41. ${check} Abra la tabla ```VCSGISREPO_ENTITIES``` de este. Siga los pasos de 
    [Abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?BBDD=${REPONAME}&TABLENAME=$VCSGISREPO_ENTITIES) 

42. ${check} Una vez abierta la tabla y estando esta activa se procede a asignar el recurso a la entidad. Para ello 
    seleccione "Tabla" en el menú de gvSIG Desktop.

43. ${check} Seleccione del despeglable anterior la opción "Show form". 

44. ${check} Como resultado se genera una nueva ventana que muestra el formulario asociado a la tabla 
    de entidades.

45. ${check} Para registrar cambios en esta hay que iniciar la edición. Para iniciar la edición pulse el icono con la
    etiqueta "Comenzar edición". Los iconos se muestran en la zona inferior de la ventana y el de comenzar edición se
    encuentra en la zona media de estos.

46. ${check} La acción anterior habilita una serie de iconos.

47. ${check} Seleccione con ayuda de los iconos "Anterior" y "Siguiente" la página del formulario de la 
    entidad ```${TABLE_NAME}``` (${TABLE_LINK}).

48. ${check} Localice el campo "Resources" y rellenelo con el nombre de la tabla de recursos ```CBASE_RESOURCES```.

49. ${check} Pulse el icono con la etiqueta "Guardar".

50. ${check} Para terminar el proceso y trás guardar cambios hay que terminar la edición. Para terminar la edición pulse 
    el icono con la etiqueta "Terminar edición". Este se encuentra la zona media de los iconos. 

51. ${check} Cierre el formulario.

52. ${check} Cierre la tabla en cuestión

53. ${check} Minimice la aplicación gvSIG Desktop ```servidor````.

3. ${check} Compruebe que no exista el fichero:
   * ```${TMPFOLDER}/${WORKINGCOPY2}.mv.db``` (TMPFOLDER/WORKINGCOPY2.mv.db).
   En caso de que exista elimínelo.

4. ${check} Abra gvSIG desktop ```Cliente```.

59. ${check} Asegúrese de que la vista que se ha creado al arrancar gvSIG se encuentra en "EPSG:4326", 
   de no ser asi cámbie la proyección de la vista.

5. ${check} Eliminaremos el registro de la copia de trabajo ```${WORKINGCOPY2}``` en caso de que existise.
   Para ello siga los pasos indicados en 
   [eliminar copia local del registro](../../PROC/019/procVC00PROC019.html?&WORKINGCOPY=${WORKINGCOPY2})

58. ${check} Inicialice una copia de trabajo. Siga los pasos de 
   [Inicializacion de una copia de trabajo ](../../PROC/008/procVC00PROC008.html?TMPFOLDER=${TMPFOLDER}&REPOURL=${REPOURL}&WORKINGCOPY=${WORKINGCOPY2})

60. ${check} Seleccione la opción de menú "Herramientas"

61. ${check} Del desplegable surgido en la acción anterior seleccione la opción "VCSGis".

62. ${check} Del desplegable surgido en la acción anterior pulse la opción "Obtener copia local (checkout)" 

63. ${check} Tras lo anterior, se muestra la ventana con el título "Obtener copia local (checkout)".

64. ${check} Siga los pasos de 
    [Obtención de una copia local (checkout)](../../PROC/006/procVC00PROC006.html?WCNAME=${WCNAME2}&TABLENAME=${TABLE_NAME}&USER=${USER}&PASSWORD=${PASSWORD})

65. ${check} Cierre el cuadro de diálogo "Obtener copia local (checkout)".

66. ${check} En la vista se habrá añadido la capa```${TABLE_NAME}``` (TABLE_NAME) con la 
    leyenda ```${LEYENDA_NAME}```.



### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
