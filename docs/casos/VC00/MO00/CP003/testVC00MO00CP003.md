---
title: Definir y descargar un modelo de datos (repositorio remoto con autorización)
proccode: VC00MO00CP0003
srcpath: "casos/VC00/MO00/CP003/testVC00MO00CP003.md"
---

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo" %}

{% include parameter.html name="WORKINGCOPY2" value="CopiaDeTrabajo2" %}

{% include parameter.html name="REPONAME" value="RepositorioAuth" %}

{% include parameter.html name="REPOURL" value="http://127.0.0.1:9810" %}

{% include parameter.html name="TABLE_NAME" value="origen_coordenadas" %}

{% include parameter.html name="TABLE_LINK" value="<a href='../../data/origen_coordenadas.csv'>ORIGEN_COORDENADAS</a>" %}

{% include parameter.html name="TABLE_CATEGORY" value="Cartografia base" %}

{% include parameter.html name="TABLE_FIELDFORLABEL" value="COD_ORIGENCOORDENADAS" %}

{% include parameter.html name="TABLE_EFECTIVEDATE" value="6/05/2021" %}

{% include parameter.html name="TABLE_COMMIT" value="Añadida tabla origen_coordenadas" %}

{% include parameter.html name="MODEL_NAME" value="Modelo1" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}


## {{ page.title }}

### Descripción

Este caso de prueba declara en el repostorio un modelo de datos formado por las tablas:
   * esp_provincias
   * esp_poblaciones
   * origen_coordenadas
   
Posteriormente se crea una nueva copia de trabajo y se conecta al modelo creado, se abre el formulario 
asociado a la tabla esp_poblaciones y se comprueba que las relaciones entra las tres tablas se muestran
correctamente.

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

1. ${check} Si acaba de ejecutar algunos de los sieguientes casos de prueba de su plan de pruebas:
    * Subir cambios en una capa con un plan topologico asociado (que sí pasen el plan).
    * Obtener una revision concreta de una capa.
    * Exportar una capa a una fecha dada.
    * Exportar una capa a una revision dada.

   Y ha pasado correctamente continue con el paso 2.
   Si no, ejecúte alguno de estos antes de continuar.

2. ${check} Compruebe que no exista el fichero:
   * ```${TMPFOLDER}/${WORKINGCOPY2}.mv.db``` (TMPFOLDER/WORKINGCOPY2.mv.db).
   En caso de que exista debera:
   * ${check} Cerrar gvSIG desktop ```Cliente```.
   * ${check} Elimínar el fichero ```${TMPFOLDER}/${WORKINGCOPY2}.mv.db``` (TMPFOLDER/WORKINGCOPY2.mv.db).
   * ${check} Iniciar gvSIG desktop ```Cliente```.
   * ${check} Asegúrese de que la vista que se ha creado al arrancar gvSIG se encuentra en "EPSG:4326", 
     de no ser asi cámbie la proyección de la vista.

3. ${check} Si no esta activa activaremos la aplicación gvSIG Desktop ```Cliente```.

4. Seleccione la opción "Mostrar/Gestor de proyecto".

5. ${check} Seleccione el tipo de documento "Tabla".

6. ${check} Pulse el botón "Nuevo".

7. ${check} Se mostrara la ventana de diálogo titulada "Nueva tabla". 

8. ${check} Seleccione la pestaña "Archivo".

9. ${check} Pulse en el boton "Añadir".

10. ${check} Se mostrara el diálogo para seleccionar un fichero. 
    Seleccione el fichero correspondiente a ```${TABLE_NAME}``` (${TABLE_LINK}) y pulse el boton "Abrir" que cerrara este dialogo.

11. ${check} De vuelta en el dialogo de "Nueva tabla" pulse el botón "Aceptar".

12. ${check} Pulse el botón "Aceptar" situado en la zona inferior del cuadro de diálogo.

13. ${check} Añada la tabla ```${TABLE_NAME}``` (${TABLE_LINK}) a la copia de trabajo, para ello siga los pasos de 
    [añadir tabla a una copia de trabajo](../../PROC/014/procVC00PROC014.html?WORKINGCOPY=${WORKINGCOPY}&TABLE=${TABLE_NAME}&FIELDFORLABEL=${TABLE_FIELDFORLABEL}&CATEGORY=${TABLE_CATEGORY})
    
14. ${check} Seleccione la opción de menu "Herramientas/VCSGis/Mostrar cambios".

15. ${check} Siga los pasos de 
    [commit de una tabla](../../PROC/021/VC00PROC021.html?WORKINGCOPY=${WORKINGCOPY}&TABLENAME=${TABLE_NAME}&EFECTIVEDATE=${TABLE_EFECTIVEDATE}&COMMENT=${TABLE_COMMENT}) 
    para subir la capa al reposiorio.

16. ${check} Cierre la ventana titulada "Mostrar cambios".

17. ${check} Minimice la aplicación gvSIG Desktop ```Cliente```.

18. ${check} Active la aplicación gvSIG Desktop ```Servidor```. 
    Vamos a configurar el servidor para registrar el modelo de datos.

19. ${check} Abra la tabla ```VCSGISREPO_ENTITIES``` de este, para ello siga los pasos de 
    [abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?CONNAME=${REPONAME}&TABLENAME=VCSGISREPO_ENTITIES)

20. ${check} Una vez abierta la tabla y estando esta activa seleccione la opcion de menu "Tabla/Show form". 

21. ${check} Se mostrara una ventana con el formulario asociado a la tabla  ```VCSGISREPO_ENTITIES```.

22. ${check} Pulse el boton "Comenzar edición" del formulario. 

23. ${check} Con ayuda de los botones "Anterior" y "Siguiente" de formulario localice la entidad ```esp_provincias```.

24. ${check} En el campo "Data Models" introduzca en el valor ```${MODEL}``` (MODEL). 

25. ${check} Pulse el boton "Guardar" del formulario.
 
26. ${check} Con ayuda de los botones "Anterior" y "Siguiente" de formulario localice la entidad ```esp_poblaciones```.

27. ${check} En el campo "Data Models" introduzca en el valor ```${MODEL}``` (MODEL). 

28. ${check} Pulse el boton "Guardar" del formulario.

29. ${check} Con ayuda de los botones "Anterior" y "Siguiente" de formulario localice la entidad ```${TABLE_NAME}```.

30. ${check} En el campo "Data Models" introduzca en el valor ```${MODEL}``` (MODEL). 

31. ${check} Pulse el boton "Guardar" del formulario.

32. ${check} Pulse el boton "Terminar edición" del formulario. 

33. ${check} Se presentrara una ventana, pulse en la opción "Si" para terminar edición y guardar los cambios.

34. ${check} Cierre el formulario de ```VCSGISREPO_ENTITIES```.

35. ${check} Cierre la tabla ```VCSGISREPO_ENTITIES```

36. ${check} Minimice la aplicación gvSIG Desktop ```Servidor```.

37. ${check} Active la aplicación gvSIG Desktop ```Cliente```. 

38. ${check} Inicialice una nueva copia de trabajo para ello siga los pasos de 
   [Inicializacion de una copia de trabajo](../../PROC/008/procVC00PROC008.html?TMPFOLDER=${TMPFOLDER}&REPOURL=${REPOURL}&WORKINGCOPY=${WORKINGCOPY2})

39. ${check} Seleccione la opción de menú "Herramientas/VCSGis/Conectar a modelo de datos" 

40. ${check} Se muestra la ventana con el título "Conectar a modelo de datos".

41. ${check} En el desplegable del campo "Copia de trabajo" seleccione el valor ```${WORKINGCOPY2}``` (WORKINGCOPY2).

41. ${check} Se mostrará el cuadro de diálogo con título "Inicio de sessión de usuario"

42. ${check} En el cuadro de texto "Usuario" introduzca ${USER} (USER) {% include var_copy.html var="USER"%}

44. ${check} En el cuadro de texto "Contraseña" introduzca ${PASSWORD} (PASSWORD) {% include var_copy.html var="PASSWORD"%}

45. ${check} Pulse el botón "Aceptar"

46. ${check} Devuelta al dialogo de "Conectar a modelo de datos", en el desplegable del 
    campo "Modelo de datos" seleccione ```${MODEL}``` (MODEL).

47. ${check} La lista inferior se rellenará con las diferentes tablas que componen ese modelo de datos.

48. ${check} Pulse el botón "Conectar a modelo de datos".

49. ${check} Tras la carga del modelo, pulse el botón "Cerrar". 

50. Seleccione la opción "Mostrar/Gestor de proyecto".

51. ${check} Seleccione el tipo de documento "Tabla".

52. ${check} Pulse el botón "Nuevo".

53. ${check} Se mostrara la ventana de diálogo titulada "Nueva tabla". 

53. ${check} Abra la tabla ```esp_poblaciones```, para ello siga los pasos de 
    [abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?CONNAME=${WORKINGCOPY2}&TABLENAME=esp_poblaciones)

54. ${check} Una vez abierta la tabla y estando esta activa seleccione la opcion de menu "Tabla/Show form". 

55. ${check} Se mostrara una ventana con el formulario asociado a la tabla  ```esp_poblaciones```.

56. ${check} En el formulario debera obserbar que el campo "ZZZZZZ" es un desplegable con los 
    valores de la tabla ${TABLE_LINK}.
    
57. ${check} En el formulario debera obserbar que el campo "ZZZZZZ" es un enlace con los datos 
    de la tabla ```esp_provincias```, y en su caja de texto aparece el nombre de una provincia.
    
58. ${check} Cierre el formulario de ```esp_poblaciones```.

59. ${check} Cierre la tabla ```esp_poblaciones```

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
