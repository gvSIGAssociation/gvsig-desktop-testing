---
title: Asociar leyenda a una capa (repositorio remoto con autorización)
proccode: VC00RE00CP0003
srcpath: "casos/VC00/RE00/CP003/testVC00RE00CP003.md"
---

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="REPONAME" value="RepositorioAuth" %}

{% include parameter.html name="REPOURL" value="http://127.0.0.1:9810" %}

{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo" %}

{% include parameter.html name="WORKINGCOPY2" value="CopiaDeTrabajo2" %}

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
de una capa, añadiendo a la tabla de recursos recién creada una leyenda para la capa.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexión asciada al repositorio.

1. ${check} **REPOURL**=```${REPOURL}```. Dirección y puerto del servidor VCSGis que se esté usando.

1. ${check} **TMPFOLDER**={% include var_tag.html var="TMPFOLDER" %}. Carpeta en la que se crearán los archivos que se precisen 
   durante la ejecución del test. Deberá tener permiso de escritura en ella. 

1. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia de trabajo sobre la que se realiza el 
   proceso de registrar el recurso.

1. ${check} **WORKINGCOPY2**=```${WORKINGCOPY2}```. Nombre de la copia de trabajo sobre la que se hará un chekout
   de la capa ${TABLE_NAME} para comprobar que se ha asociado correctamente la leyenda a la capa.

1. ${check} **TABLE_NAME**=```${TABLE_NAME}```. Nombre de la tabla del repositorio a la que le se va a asociar una
   leyenda por defecto.

1. ${check} **RESOURCES_TABLE_NAME**={% include var_tag.html var="RESOURCES_TABLE_NAME" %}. Nombre de la tabla de recursos que se va a crear.

1. ${check} **RESOURCES_TABLE_EFECTIVEDATE**={% include var_tag.html var="RESOURCES_TABLE_EFECTIVEDATE" %}. Fecha a indicar como fecha efectiva 
   en el momento de realizar el commit de la tabla de recursos.

1. ${check} **RESOURCES_TABLE_COMMENT**={% include var_tag.html var="RESOURCES_TABLE_COMMENT" %}. Comentario a indicar en el momento
   de realizar el commit de la tabla de recursos.

1. ${check} **RESOURCE_NAME**={% include var_tag.html var="RESOURCE_NAME" %}. Nombre del recurso a dar de alta en la nueva tabla de recursos.

1. ${check} **LEGEND_NAME**=```${LEGEND_NAME}```, (${LEGEND_LINK}). Nombre del fichero en el que está almacenada la leyenda.


### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya versión sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} El caso de prueba 
   [VC00SY00CP002, "Commitar una capa nueva"](../../SY00/CP002/testVC00SY00CP002.md),
   ha pasado sin errores.
   
### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas 
   [VC00SY00CP002 "commitar una capa nueva"](../../SY00/CP002/testVC00SY00CP002.md)
    (hace menos de 1 hora) y aún tiene abierto gvSIG desktop  ```Servidor``` 
    continúe con el paso 2. Si no, ejecútelo antes de continuar.

2. ${check} Si no esta activa, active la aplicación gvSIG desktop  ```Cliente```. 

3. ${check} Para crear la tabla de recursos seleccione la opción de menú "Herramientas/VCSGis/Administración/Crear tabla de recursos".

4. ${check} Se presenta un cuadro de diálogo titulado "Crear tabla de recursos".
     
5. ${check} En el desplegable del campo "Copia de trabajo" seleccione la opción ```${WORKINGCOPY}``` (WORKINGCOPY). 

6. ${check} En el campo "Nombre de tabla" introduzca el nombre ```${RESOURCES_TABLE_NAME}``` {% include var_copy.html var="RESOURCES_TABLE_NAME"%}.

7. ${check} Pulse el botón "Crear tabla de recursos".

8. ${check} Abra la tabla de recursos que se acaba de crear, para ello siga los pasos de 
    [abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?CONNAME=${WORKINGCOPY}&TABLENAME=${RESOURCES_TABLE_NAME})

9. ${check} Una vez abierta la tabla y estando esta activa se procede a añadir en ésta un nuevo registro. Para ello 
   seleccione la opción de menú "Tabla/Show form". 

10. ${check} Como resultado se abrirá una ventana que muestra el formulario asociado a la tabla de recursos.

11. ${check} Inicie edición pulsando en el botón "Comenzar edición" del formulario. 

12. ${check} La acción anterior habilita una serie de botones. Pulse el botón "Nuevo" del formulario.

13. ${check} Se habilitarán los campos del formulario. Indroduzca el valor ```${RESOURCE_NAME}``` (RESOURCE_NAME) 
    en el campo "Nombre" {% include var_copy.html var="RESOURCE_NAME"%}.

14. ${check} Pulse el botón de cargar datos asociado al campo "Recurso". Podra identificarlo por contener
    una flecha hacia arriba ![IconoSubirRecurso](iconoSubirRecurso.png) .

15. ${check} Se presenta un cuadro de diálogo para seleccionar un fichero. 
    Seleccione el correspondiente a ```${LEGEND_NAME}``` (${LEGEND_LINK}).
    y pulse en el botón "Abrir".

16. ${check} De vuelta en el formulario de la tabla de recursos, el campo "Recurso" tiene
    que estar relleno con el tamaño del archivo ```${LEGEND_NAME}```.

17. ${check} Pulse el botón "Guardar" del formulario.

18. ${check} Termine edición pulsando en el botón "Terminar edición" del formulario. 
    Al hacerlo se le preguntará si desea guardar los cambios, pulse en el botón "aceptar".

19. ${check} Cierre el formulario.

20. ${check} Cierre la tabla ```${RESOURCES_TABLE_NAME}```.

21. ${check} Añada la tabla de recursos ```${RESOURCES_TABLE_NAME}``` a la copia de trabajo, para eso seleccione la opción de menú "Herramientas/VCSGis/Añadir a la copia de trabajo" y siga los pasos de 
    [añadir tabla a una copia de trabajo](../../PROC/014/procVC00PROC014.html?WORKINGCOPY=${WORKINGCOPY}&TABLE=${RESOURCES_TABLE_NAME}&FIELDFORLABEL=${RESOURCES_TABLE_FIELDFORLABEL}&CATEGORY=${RESOURCES_TABLE_CATEGORY}&USER=${USER}&PASSWORD=${PASSWORD})

22. ${check} Cierre la ventana "Añadir a la copia de trabajo".

23. ${check} Pulse la opción "Herramientas/VCSGis/Mostrar cambios".

24. ${check} Siga los pasos de 
    [commit de una tabla](../../PROC/021/procVC00PROC021.html?WORKINGCOPY=${WORKINGCOPY}&TABLENAME=${RESOURCES_TABLE_NAME}&EFECTIVEDATE=${RESOURCES_TABLE_EFECTIVEDATE}&COMMENT=${RESOURCES_TABLE_COMMENT}) 
    para subir la tabla al reposiorio.

25. ${check} Active la aplicación gvSIG Desktop ```servidor```. A partir de ahora va a configurar el servidor para 
    asociar la tabla de recursos a la capa ```${TABLE_NAME}```.

26. ${check} Abra la tabla ```VCSGISREPO_ENTITIES```, para ello siga los pasos de 
    [abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?CONNAME=${REPONAME}&TABLENAME=VCSGISREPO_ENTITIES) 

27. ${check} Seleccione la opción de menu "Table/Show form". 

28. ${check} Como resultado se genera una nueva ventana que muestra el formulario asociado a la tabla 
    de entidades.

29. ${check} Pulse el botón "Comenzar edición" del formulario.

30. ${check} Seleccione con ayuda de los botones "Anterior" y "Siguiente"  del formulario el registro de la 
    entidad ```${TABLE_NAME}```.

31. ${check} Introduzca el valor ```${RESOURCES_TABLE_NAME}``` en el campo "Resources" {% include var_copy.html var="RESOURCES_TABLE_NAME"%}.

32. ${check} Pulse el botón "Guardar" del formulario.

33. ${check} Pulse el botón "Terminar edición" del formulario.

34. ${check} Cierre el formulario.

35. ${check} Cierre la tabla ```VCSGISREPO_ENTITIES```.

36. ${check} Minimice la aplicación gvSIG Desktop ```Servidor````.

37. ${check} Compruebe si exite el fichero 
    * ```${TMPFOLDER}/${WORKINGCOPY2}.mv.db``` (TMPFOLDER/WORKINGCOPY2.mv.db).
    En caso de que exista, cierre la aplicacion gvSIG Desktop ```Cliente```, elimínelo y abra de nuevo gvSIG desktop ```Cliente```.

38. ${check} Asegúrese de que la vista que se ha creado al arrancar gvSIG se encuentra en "EPSG:4326", 
   de no ser asi cámbie la proyección de la vista.

39. ${check} Elimine el registro de la copia de trabajo ```${WORKINGCOPY2}``` en caso de que existise.
   Para ello seleccione la opción de menú "Herramientas/VCSGis/Administración/Registrar copia de trabajo" y siga los pasos indicados en 
   [eliminar copia local del registro](../../PROC/019/procVC00PROC019.html?&WORKINGCOPY=${WORKINGCOPY2})

40. ${check} Inicialice una nueva copia de trabajo, para ello seleccione la opción de menú "Herramientas/VCSGis/Inicializar copia de trabajo" y siga los pasos de 
   [inicializacion de una copia de trabajo ](../../PROC/008/procVC00PROC008.html?TMPFOLDER=${TMPFOLDER}&REPOURL=${REPOURL}&WORKINGCOPY=${WORKINGCOPY2})

41. ${check} Seleccione la opción de menú "Herramientas/VCSGis/Obtener copia local (checkout)"

42. ${check} Se presentará la ventana con el título "Obtener copia local (checkout)".

43. ${check} Siga los pasos de 
    [obtención de una copia local (checkout)](../../PROC/006/procVC00PROC006.html?WORKINGCOPY=${WORKINGCOPY2}&TABLENAME=${TABLE_NAME}&USER=${USER}&PASSWORD=${PASSWORD})

44. ${check} Cierre el cuadro de diálogo "Obtener copia local (checkout)".

45. ${check} En la vista se habrá añadido la capa```${TABLE_NAME}``` (TABLE_NAME) con la 
    leyenda ```${LEGEND_NAME}```.

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
