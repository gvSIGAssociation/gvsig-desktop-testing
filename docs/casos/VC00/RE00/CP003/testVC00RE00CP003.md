---
title: Asociar leyenda a una capa (repositorio remoto con autorización)
proccode: VC00RE00CP0003
srcpath: "casos/VC00/RE00/CP003/testVC00RE00CP003.md"
---

**EN CONSTRUCCION**

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="REPONAME" value="RepositorioAuth" %}

{% include parameter.html name="REPOURL" value="127.0.0.1:9810" %}

{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo" %}

{% include parameter.html name="WORKINGCOPY2" value="CopiaDeTrabajo" %}

{% include parameter.html name="TABLE_NAME" value="esp_provincias" %}

{% include parameter.html name="RESOURCES_TABLE_NAME" value="res_cartografia_base" %}

{% include parameter.html name="RESOURCES_TABLE_FIELDFORLABEL" value="Nombre" %}

{% include parameter.html name="RESOURCES_TABLE_CATEGORY" value="Cartografia base" %}

{% include parameter.html name="RESOURCES_TABLE_EFECTIVEDATE" value="3/05/2021" %}

{% include parameter.html name="RESOURCES_TABLE_COMMENT" value="Añadir tabla de recursos res_cartografia_base" %}

{% include parameter.html name="LEGEND_NAME" value="esp_provincias.gvsleg" %}

{% include parameter.html name="LEGEND_LINK" value="<a href='../../data/esp_provincias.gvsleg'>ESP_PROVINCIAS.GVSLEG</a>" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}

{% include parameter.html name="RESOURCE_NAME" value="esp_provincias.gvsleg" %}

## {{ page.title }}

### Descripción

Este proceso crea una tabla de recursos, la sube al repositorio y la asocia como tabla de recursos 
de una capa, añadiendo a la tabla de recursos recien creada una leyenda para la capa.

### Datos de entrada

1. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexion asciada al repositorio.

1. ${check} **REPOURL**=```${REPOURL}```. Direccion y puerto del servidor VCSGis que estamos usando.

1. ${check} **TMPFOLDER**={% include var_tag.html var="TMPFOLDER" %}. Carpeta en la que se crearán los archivos que se precisen 
   durante la ejecución del test. Deberemos tener permiso de escritura en ella. 

1. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia de trabajo sobre la que se realiza el 
   proceso de registrar el recurso.

1. ${check} **WORKINGCOPY2**=```${WORKINGCOPY2}```. Nombre de la copia de trabajo sobre la que haremos un chekout
   de la capa ${TABLE_NAME} para comprobar que se ha asociado correctamente la leyenda a la capa.

1. ${check} **TABLE_NAME**=```${TABLE_NAME}```. Nombre de la tabla del repositorio a la que le vamos a asociar una
   leyenda por defecto.

1. ${check} **RESOURCES_TABLE_NAME**={% include var_tag.html var="RESOURCES_TABLE_NAME" %}. Nombre de la tabla de recursos que vamos a crear.

1. ${check} **RESOURCES_TABLE_EFECTIVEDATE**={% include var_tag.html var="RESOURCES_TABLE_EFECTIVEDATE" %}. Fecha a indicar como fecha efectiva 
   en el momento de realizar el commit de la tabla de recursos.

1. ${check} **RESOURCES_TABLE_COMMENT**={% include var_tag.html var="RESOURCES_TABLE_COMMENT" %}. Comentario a indicar en el momento
   de realizar el commit de la tabla de recursos.

1. ${check} **RESOURCE_NAME**={% include var_tag.html var="RESOURCE_NAME" %}. Nombre del recurso a dar de alta en la nueva tabla de recursos.

1. ${check} **LEGEND_NAME**=```${LEGEND_NAME}```, (${LEGEND_LINK}). Nombre del fichero en el que tenemos almacenada la leyenda.


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

2. ${check} Si no esta activa, active la aplicación gvSIG desktop  ```Cliente``` 

3. ${check} Vamos a crear la tabla de recursos. Seleccione la opción de menú "Herramientas/VCSGis/Administración/Crear tabla de recursos".

4. ${check} Se presenta un cuadro de diálogo titulado "Crear tabla de recursos".
     
5. ${check} En el desplegable del campo "Copia de trabajo" seleccione la opción ```${WORKINGCOPY}``` (WORKINGCOPY). 

6. ${check} En el campo "Nombre de tabla" introduzca el nombre ```${RESOURCES_TABLE_NAME}``` {% include var_copy.html var="RESOURCES_TABLE_NAME"%}.

7. ${check} Pulse el botón "Aceptar".

8. ${check} Abriremos la tabla de recursos que acabamos de crear, para ello siga los pasos de 
    [abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?CONNAME=${WORKINGCOPY}&TABLENAME=${RESOURCES_TABLE_NAME})

9. ${check} Una vez abierta la tabla y estando esta activa se procede a añadir en esta un nuevo registro. Para ello 
   seleccione la opción de menú "Tabla/Show form". 

10. ${check} Como resultado se abrira una ventana que muestra el formulario asociado a la tabla de recursos.

11. ${check} Iniciaremos edicón pulsando en el boton "Comenzar edición" del formulario. 

12. ${check} La acción anterior habilita una serie de botones. Pulse el boton "Nuevo" del formulario.

13. ${check} Se habilitaran los campos del formulario. Indroduzca el valor ```${RESOURCE_NAME}``` (RESOURCE_NAME) 
    en el campo "Nombre" {% include var_copy.html var="RESOURCE_NAME"%}.

14. ${check} Pulse el boton de cargar datos asociado al campo "Recurso". Podra identificarlo por contener
    una flecha hacia arriba ![IconoSubirRecurso](iconoSubirRecurso.png) .

15. ${check} Se presenta un cuadro de diálogo para seleccionar un fichero. 
    Seleccione el correspondiente a ```${LEGEND_NAME}``` (${LEGEND_LINK}).
    y pulse en el boton "Abrir".

16. ${check} De vuelta en el formulario de la tabla de recursos el campo "Recurso" tiene
    que estar relleno con el tamaño del archivo ```${LEGEND_NAME}```.

17. ${check} Pulse el boton "Guardar" del formulario.

18. ${check} Termine edicion pulsando en el boton "Terminar edición" del formulario. 
    Al hacerlo se le preguntara si desea guardar los cambios, pulse en "aceptar".

19. ${check} Cierre el formulario.

20. ${check} Cierre la tabla ${RESOURCES_TABLE_NAME}.

21. ${check} Añada la tabla de recursos ```${RESOURCES_TABLE_NAME}``` a la copia de trabajo, para eso siga los pasos de 
    [añadir tabla a una copia de trabajo](../../PROC/014/procVC00PROC014.html?WORKIONGCOPY=${WORKIONGCOPY}&TABLE=${RESOURCES_TABLE_NAME}&FIELDFORLABEL=${RESOURCES_TABLE_FIELDFORLABEL}&CATEGORY=${RESOURCES_TABLE_CATEGORY}&USER=${USER}&PASSWORD=${PASSWORD})

22. ${check} Pulse la opción "Herramientas/VCSGis/Mostrar cambios".

23. ${check} Se visualiza la ventana que muestra los cambios entre el repositorio y la copia de trabajo
    de título  "VCSGis Cambios".

24. ${check} Seleccione la copia de trabajo ```${WORKINGCOPY}``` (WORKINGCOPY).

25. ${check} Se muestra el contenido de la pestaña "Copia de trabajo" donde podrá apreciar,
    a la izquierda, un selector en forma de árbol (selector de entidades) que contiene la categoría que le 
    puso a la capa cuando la añadió y, bajo ésta, la capa añadida a la copia de trabajo.
    A la derecha se habrá mostrado una tabla vacía (tabla de cambios) y sobre ésta los botones de "Refrescar",
    "Revertir", "Commit", "Resaltar", "Centrar", "Zoom", "Limpiar geometrías resaltadas" y "Mostrar formulario".

26. ${check} Marque la casilla de verificación asociada a la tabla ```${RESOURCES_TABLE_NAME}```.

27. ${check} En la tabla de cambios se muestran los cambios necesarios para insertar esta capa en el repositorio, 
    habilitandose también los botones de "Refrescar", "Revertir" y "Commit".

28. ${check} Introduzca en el campo "Fecha de entrada en vigor" la 
    fecha ```${RESOURCES_TABLE_EFECTIVEDATE}``` {% include var_copy.html var="RESOURCES_TABLE_EFECTIVEDATE"%}.

29. ${check} Introduzca en el campo "Comentario" el 
    texto ```${RESOURCES_TABLE_COMMENT}``` {% include var_copy.html var="RESOURCES_TABLE_COMMENT"%}.

30. ${check} Pulse el botón de "Commit"

31. ${check} Cierre la ventana titulada "Mostrar cambios".

32. ${check} Active la aplicación gvSIG Desktop ```servidor```. A partir de ahora va a configurar el servidor para 
    asociar la tabla de recursos a la capa ```${TABLE_NAME}```.

33. ${check} Abra la tabla ```VCSGISREPO_ENTITIES```, para ello siga los pasos de 
    [abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?CONNAME=${REPONAME}&TABLENAME=VCSGISREPO_ENTITIES) 

34. ${check} Seleccione la opcion de menu  "Table/Show form". 

35. ${check} Como resultado se genera una nueva ventana que muestra el formulario asociado a la tabla 
    de entidades.

36. ${check} pulse el boton "Comenzar edición" del formulario.

37. ${check} Seleccione con ayuda de los botones "Anterior" y "Siguiente"  del formulario el registro de la 
    entidad ```${TABLE_NAME}```.

38. ${check} Introduzca el valor ```${RESOURCES_TABLE_NAME}``` en el campo "Resources" {% include var_copy.html var="RESOURCES_TABLE_NAME"%}.

39. ${check} Pulse el boton "Guardar" del formulario.

40. ${check} Pulse el boton "Terminar edición" del formulario.

41. ${check} Cierre el formulario.

42. ${check} Cierre la tabla ```VCSGISREPO_ENTITIES```.

43. ${check} Minimice la aplicación gvSIG Desktop ```Servidor````.

44. ${check} Compruebe si exite el fichero 
    * ```${TMPFOLDER}/${WORKINGCOPY2}.mv.db``` (TMPFOLDER/WORKINGCOPY2.mv.db).
    En caso de que exista, cierre la aplicacion gvSIG Desktop ```Cliente````, eliminelo y abra de nuevo gvSIG desktop ```Cliente```.

45. ${check} Asegúrese de que la vista que se ha creado al arrancar gvSIG se encuentra en "EPSG:4326", 
   de no ser asi cámbie la proyección de la vista.

46. ${check} Eliminaremos el registro de la copia de trabajo ```${WORKINGCOPY2}``` en caso de que existise.
   Para ello siga los pasos indicados en 
   [eliminar copia local del registro](../../PROC/019/procVC00PROC019.html?&WORKINGCOPY=${WORKINGCOPY2})

47. ${check} Inicialice una nueva copia de trabajo, para ello siga los pasos de 
   [inicializacion de una copia de trabajo ](../../PROC/008/procVC00PROC008.html?TMPFOLDER=${TMPFOLDER}&REPOURL=${REPOURL}&WORKINGCOPY=${WORKINGCOPY2})

48. ${check} Seleccione la opción de menú "Herramientas/VCSGis/Obtener copia local (checkout)"

49. ${check} Se presentara la ventana con el título "Obtener copia local (checkout)".

50. ${check} Siga los pasos de 
    [obtención de una copia local (checkout)](../../PROC/006/procVC00PROC006.html?WORKINGCOPY=${WORKINGCOPY2}&TABLENAME=${TABLE_NAME}&USER=${USER}&PASSWORD=${PASSWORD})

51. ${check} Cierre el cuadro de diálogo "Obtener copia local (checkout)".

52. ${check} En la vista se habrá añadido la capa```${TABLE_NAME}``` (TABLE_NAME) con la 
    leyenda ```${LEYENDA_NAME}```.



### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
