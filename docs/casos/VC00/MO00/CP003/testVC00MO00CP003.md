---
title: Definir y descargar un modelo de datos (repositorio remoto en H2 con autorización)
proccode: VC00MO00CP0003
srcpath: "casos/VC00/MO00/CP003/testVC00MO00CP003.md"
---

**EN CONSTRUCCION**

{% include es/header.md %}

{% include parameter.html name="TABLE_NAME" value="origen_coordenadas" %}

{% include parameter.html name="TABLE_LINK" value="<a href='../../data/origen_coordenadas.csv'>ORIGEN_COORDENADAS</a>" %}

{% include parameter.html name="CATEGORY" value="Cartografia base" %}

{% include parameter.html name="WCNAME" value="CopiaDeTrabajo" %}

{% include parameter.html name="WCNAME2" value="CopiaDeTrabajo2" %}

{% include parameter.html name="REPONAME" value="RepositorioAuth" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="FIELDFORLABEL" value="COD_ORIGENCOORDENADAS" %}

{% include parameter.html name="MODEL" value="MD1" %}



## {{ page.title }}

### Descripción

Este proceso define un modelo de datos, ```${MODEL}``` (MODEL), con las capas ```esp_provincias``` y ```esp_poblaciones``` y la tabla ```${TABLE_NAME}``` (TABLE_LINK). Tras definirlo
se procede a descargar dicho modelo en la copia de trabajo ```${WCNAME2}``` (WCNAME2).

### Datos de entrada

1. ${check} **TMPFOLDER**=```${TMPFOLDER}```. Carpeta en la que se crearán los archivos que se precisen 
   durante la ejecución del test. Deberemos tener permiso de escritura en ella. 

2. ${check} Archivo de datos: ```${TABLE_NAME}``` (${TABLE_LINK}). Tabla de datos a añadir al modelo ```${MODEL}``` (MODEL). 

3. ${check} **FIELDFORLABEL**=```${FIELDFORLABEL}```. Nombre del campo de la tabla a añadir
   a usar en "Campo para etiqueta".

4. ${check} **CATEGORY**=```${CATEGORY}```. Categoria a asignar la tabla.

5. ${check} **MODEL**= ```${MODEL}```. Nombre del modelo de datos

6. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexión y del repositorio.

7. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia de trabajo sobre la que se realiza el 
   proceso de registrar el modelo.

8. ${check} **WCNAME2**=```${WCNAME2}```. Nombre de la copia de trabajo sobre que se descargará el modelo.

9. ${check} **USER**=```${USER}```. Identificador de usuario.

10. ${check} **PASSWORD**=```${PASSWORD}```. Contraseña de usuario.

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya versión sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} El caso de prueba 
   [VC00TP00CP0003, "Subir cambios en una capa con un plan topológico (que sí pasen el plan)"](../../TP00/CP003/testVC00TP00CP003.md),
   ha pasado sin errores.
   
### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas (hace menos de 1 hora) VC00TP00CP0003,
    Subir cambios en una capa con un plan topológico (que sí pasen el plan)"
    y no ha cerrado gvSIG, continúe con el paso 2. Si no, ejecútelo antes de continuar.

2. ${check} Asegúrese de estar en la aplicación gvSIG Desktop ```cliente``` y cierrela.

3. **FIXME** ${check} Antes de iniciar  de nuevo la aplicación gvSIG desktop ```cliente``` compruebe que no exista el fichero:
   * ```${TMPFOLDER}/${WCNAME2}.mv.db``` (TMPFOLDER/WCNAME2.mv.db).
   
   En caso de que exista eliminela.
   
4. ${check} Inicie gvSIG Desktop ```cliente```.
    
5. ${check} La copia de trabajo ```${WCNAME}``` (WCNAME) solo dispone de las capas ```esp_provincias``` y ```esp_poblaciones```, las cuales junto a la 
   tabla ```${TABLE_NAME}``` (TABLE_LINK) conforman el modelo ```${MODEL}``` (MODEL). Por lo que hay que proceder a cargar la tabla ```${TABLE_NAME}``` (TABLE_LINK) en
   la copia de trabajo. Para ello seleccione la opción "Mostrar/Gestor de proyecto" del menú de gvSIG Desktop.

6. ${check} Marque la opción "Tabla".

7. ${check} Pulse el botón "Nuevo". Solo tiene que estas ese habilitado.

8. ${check} Como resultado de lo anterior se muestra una ventana de diálogo titulada "Nueva Tabla". 

9. ${check} De las pestañas situadas en la zona superior de la ventana seleccione la opción "Archivo".

10. ${check} De los botones situados en la zona derecha de la ventana seleccione la opción "Añadir".

11. ${check} Se presenta un cuadro de diálogo para seleccionar un fichero. 
    Seleccione el correspondiente a ```${TABLE_NAME}``` (${TABLE_LINK}).

12. ${check} Pulse el botón "Aceptar" situado en la zona inferior del cuadro de diálogo.

13. ${check} Añada la tabla ```${TABLE_NAME}``` (${TABLE_LINK}) a la copia de trabajo. Siga los pasos de 
    [Añadir tabla a una copia de trabajo](../../PROC/014/procVC00PROC014.html?WCNAME=${WCNAME}&TABLE=${TABLE_NAME}&FIELDFORLABEL=${FIELDFORLABEL}&CATEGORY=${CATEGORY})
    
14. ${check} Una vez añadida a la copia de trabajo hay que subirla al repositorio ```${REPONAME}``` (REPONAME). Pulse la opción "Herramientas/VCSGis/Mostrar cambios".

15. ${check} Se visualiza la ventana que muestra los cambios entre el repositorio y la copia de trabajo
   de título  "VCSGis Cambios".

16. ${check} Seleccione la copia de trabajo ```${WCNAME}``` (WCNAME).

17. ${check} Se muestra el contenido de la pestaña "Copia de trabajo" donde podrá apreciar,
    a la izquierda, un selector en forma de árbol (selector de entidades) que contiene la categoría que le 
    puso a la capa cuando la añadió y, bajo ésta, la capa añadida a la copia de trabajo.
    A la derecha se habrá mostrado una tabla vacía (tabla de cambios) y sobre ésta los botones de "Refrescar",
    "Revertir", "Commit", "Resaltar", "Centrar", "Zoom", "Limpiar geometrías resaltadas" y "Mostrar formulario".

18. ${check} Pulse la casilla de verificación asociada a la tabla ```${TABLE_NAME}``` (${TABLE_LINK}).

19. ${check} En la tabla de cambios se muestran los cambios necesarios para insertar esta capa en el repositorio, 
    habilitandose también los botones de "Refrescar", "Revertir" y "Commit".

20. ${check} Introduzca en el campo "Fecha de entra en vigor" la fecha "6/05/2021"

21. ${check} Introduzca en el campo "Comentario" el texto "Añadir tabla ```${TABLE_NAME}``` del modelo ```${MODEL}```"

22. ${check} Pulse el botón de "Commit"

23. ${check} Cierre la ventana titulada "Mostrar cambios".

24. ${check} Minimice la aplicación gvSIG Desktop ```cliente```.

25. ${check} Active la aplicación gvSIG Desktop ```servidor```. A partir de ahora va a configurar el servidor para 
    registrar el modelo de datos las diferentes capas.

26. ${check} Abra la tabla ```VCSGISREPO_ENTITIES``` de este. Siga los pasos de 
    [Abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?BBDD=${REPONAME}&TABLENAME=VCSGISREPO_ENTITIES)

27. ${check} Una vez abierta la tabla y estando esta activa se procede a asignar el modelo de datos ```${MODEL}``` (MODEL) alas diferentes entidades  que lo conforman.
    Para ello seleccione "Tabla" en el menú de gvSIG Desktop.

28. ${check} Seleccione del despeglable anterior la opción "Show form". 

29. ${check} Como resultado se genera una nueva ventana que muestra el formulario asociado a la tabla 
   de entidades del repositorio.

30. ${check} Para registrar cambios en esta hay que iniciar la edición. Para iniciar la edición pulse el icono con la
   etiqueta "Comenzar edición". Los iconos se muestran en la zona inferior de la ventana y el de comenzar edición se
   encuentra en la zona media de estos.

31. ${check} La acción anterior habilita una serie de iconos.

32. ${check} Seleccione con ayuda de los iconos "Anterior" y "Siguiente" la página del formulario de la entidad ```esp_provincias```.

33. ${check} Localice el campo "Data Models" e introduzca en el el valor ```${MODEL}``` (MODEL). 

34. ${check} Pulse el icono con la etiqueta "Guardar".

35. ${check} Repita los pasos 32, 33, y 34 con las entidades ```esp_poblaciones``` y ```${TABLE_NAME}```.

36. ${check} Para terminar el proceso y trás guardar cambios hay que terminar la edición. Para terminar la edición pulse 
    el icono con la etiqueta "Terminar edición". Este se encuentra la zona media de los iconos. 

37. ${check} Como consecuencia de lo anterior se despliega una ventana, pulse en la opción "Guardar".

38. ${check} Cierre el formulario.

39. ${check} Cierre la tabla en cuestión

40. ${check} Tras lo anterior, la ventana "Servidor VCSGis" queda activa y visible.

41. ${check} Minimice la aplicación gvSIG Desktop ```servidor```.

42. ${check} Una vez asignado el modelo, carge este en una nueva copia de trabajo. Para ello abra la aplicación gvSIG Desktop ```cliente```.

43. ${check} Inicialice una nueva copia de trabajo para ello siga los pasos de 
   [Inicializacion de una copia de trabajo (repositorio remoto en H2 con autorización)](../../PROC/008/procVC00PROC008.html?TMPFOLDER=${TMPFOLDER}&REPONAME=${REPONAME}&WCNAME=${WCNAME2})

44. ${check} Asegúrese de que la vista que se ha creado al arrancar gvSIG se encuentra en "EPSG:4326", 
   de no ser asi cámbie la proyección de la vista.

45. ${check} Seleccione la opción de menú "Herramientas/VCSGis/Conectar a modelo de datos" 

46. ${check} Se muestra la ventana con el título "Conectar a modelo de datos".

47. ${check} En el campo "Copia de trabajo" seleccione la opción ```${WCNAME2}``` (WCNAME2).

48. ${check} Se mostrará el cuadro de diálogo con título "Inicio de sessión de usuario"

49. ${check} En el cuadro de texto "Usuario" introduzca ```${USER}```(USER)

50. ${check} En el cuadro de texto "Contraseña" introduzca ```${PASSWORD}```(PASSWORD)

51. ${check} Pulse el botón "Aceptar"

52. ${check} En el campo "Modelo de datos" seleccione ```${MODEL}``` (MODEL).

53. ${check} El área inferior se rellenará con los diferentes elementos que componen ese modelo de datos.

54. ${check} Pulse el botón "Conectar a modelo de datos".

55. ${check} Tras la carga del modelo, pulse el botón "Cerrar". Una vez ejecutado lo anterior la copiad e trabajo ```${WCNAME2}``` (WCNAME2) disponede los elementos
    que conforman el modelo de datos ```${MODEL}``` (MODEL).

56. ${check} La vista "Sin título" se queda activa y vacía.



### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
