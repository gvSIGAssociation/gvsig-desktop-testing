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

{% include parameter.html name="REPOURL" value="??????????????????????" %}

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

2. ${check} Si no esta activa activaremos la aplicación gvSIG Desktop ```Cliente```.

3. Seleccione la opción "Mostrar/Gestor de proyecto".

4. ${check} Seleccione el tipo de documento "Tabla".

5. ${check} Pulse el botón "Nuevo".

6. ${check} Se mostrara la ventana de diálogo titulada "Nueva tabla". 

7. ${check} Seleccione la pestaña "Archivo".

8. ${check} Pulse en el boton "Añadir".

9. ${check} Se mostrara el diálogo para seleccionar un fichero. 
    Seleccione el fichero correspondiente a ```${TABLE_NAME}``` (${TABLE_LINK}) y pulse el boton "Abrir" que cerrara este dialogo.

10. ${check} De vuelta en el dialogo de "Nueva tabla" pulse el botón "Aceptar".

12. ${check} Pulse el botón "Aceptar" situado en la zona inferior del cuadro de diálogo.

13. ${check} Añada la tabla ```${TABLE_NAME}``` (${TABLE_LINK}) a la copia de trabajo, para ello siga los pasos de 
    [añadir tabla a una copia de trabajo](../../PROC/014/procVC00PROC014.html?WORKINGCOPY=${WORKINGCOPY}&TABLE=${TABLE_NAME}&FIELDFORLABEL=${TABLE_FIELDFORLABEL}&CATEGORY=${TABLE_CATEGORY})
    
14. ${check} Seleccione la opción de menu "Herramientas/VCSGis/Mostrar cambios".
15. 
16. ${check} Siga los pasos de 
    [commit de una tabla](../../PROC/021/VC00PROC021.html?WORKINGCOPY=${WORKINGCOPY}&TABLENAME=${TABLE_NAME}&EFECTIVEDATE=${TABLE_EFECTIVEDATE}&COMMENT=${TABLE_COMMENT}) 
    para subir la capa al reposiorio.

23. ${check} Cierre la ventana titulada "Mostrar cambios".

24. ${check} Minimice la aplicación gvSIG Desktop ```Cliente```.

25. ${check} Active la aplicación gvSIG Desktop ```Servidor```. 
    Vamos a configurar el servidor para registrar el modelo de datos.

26. ${check} Abra la tabla ```VCSGISREPO_ENTITIES``` de este, para ello siga los pasos de 
    [abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?CONNAME=${REPONAME}&TABLENAME=VCSGISREPO_ENTITIES)

27. ${check} Una vez abierta la tabla y estando esta activa seleccione la opcion de menu "Tabla/Show form". 

29. ${check} Se mostrara una ventana con el formulario asociado a la tabla  ```VCSGISREPO_ENTITIES```.

11. ${check} Pulse el boton "Comenzar edición" del formulario. 

32. ${check} Con ayuda de los botones "Anterior" y "Siguiente" de formulario localice la entidad ```esp_provincias```.

33. ${check} En el campo "Data Models" introduzca en el valor ```${MODEL}``` (MODEL). 

10. ${check} Pulse el boton "Guardar" del formulario.
 
32. ${check} Con ayuda de los botones "Anterior" y "Siguiente" de formulario localice la entidad ```esp_poblaciones```.

33. ${check} En el campo "Data Models" introduzca en el valor ```${MODEL}``` (MODEL). 

10. ${check} Pulse el boton "Guardar" del formulario.

32. ${check} Con ayuda de los botones "Anterior" y "Siguiente" de formulario localice la entidad ```${TABLE_NAME}```.

33. ${check} En el campo "Data Models" introduzca en el valor ```${MODEL}``` (MODEL). 

10. ${check} Pulse el boton "Guardar" del formulario.

11. ${check} Pulse el boton "Terminar edición" del formulario. 

12. ${check} Se presentrara una ventana, pulse en la opción "Si" para terminar edición y guardar los cambios.

13. ${check} Cierre el formulario de ```VCSGISREPO_ENTITIES```.

39. ${check} Cierre la tabla ```VCSGISREPO_ENTITIES```

41. ${check} Minimice la aplicación gvSIG Desktop ```Servidor```.

25. ${check} Active la aplicación gvSIG Desktop ```Cliente```. 

43. ${check} Inicialice una nueva copia de trabajo para ello siga los pasos de 
   [Inicializacion de una copia de trabajo](../../PROC/008/procVC00PROC008.html?TMPFOLDER=${TMPFOLDER}&REPOURL=${REPOURL}&WORKINGCOPY=${WORKINGCOPY2})

45. ${check} Seleccione la opción de menú "Herramientas/VCSGis/Conectar a modelo de datos" 

46. ${check} Se muestra la ventana con el título "Conectar a modelo de datos".

47. ${check} En el desplegable del campo "Copia de trabajo" seleccione el valor ```${WORKINGCOPY2}``` (WORKINGCOPY2).

48. ${check} Se mostrará el cuadro de diálogo con título "Inicio de sessión de usuario"

47. ${check} En el cuadro de texto "Usuario" introduzca ${USER} (USER) {% include var_copy.html var="USER"%}

49. ${check} En el cuadro de texto "Contraseña" introduzca ${PASSWORD} (PASSWORD) {% include var_copy.html var="PASSWORD"%}

51. ${check} Pulse el botón "Aceptar"

52. ${check} Devuelta al dialogo de "Conectar a modelo de datos", en el desplegable del 
    campo "Modelo de datos" seleccione ```${MODEL}``` (MODEL).

53. ${check} La lista inferior se rellenará con las diferentes tablas que componen ese modelo de datos.

54. ${check} Pulse el botón "Conectar a modelo de datos".

55. ${check} Tras la carga del modelo, pulse el botón "Cerrar". 

3. Seleccione la opción "Mostrar/Gestor de proyecto".

4. ${check} Seleccione el tipo de documento "Tabla".

5. ${check} Pulse el botón "Nuevo".

6. ${check} Se mostrara la ventana de diálogo titulada "Nueva tabla". 

6. ${check} Seleccione la pestaña "VCSGis".

47. ${check} En el desplegable del campo "Copia de trabajo" seleccione el valor ```${WORKINGCOPY2}``` (WORKINGCOPY2).

56. ${check} La lista de tablas debera rellenarse con las tablas del repositorio.

56. ${check} Obserbaremos que las tablas:
    * esp_provincias
    * esp_poblaciones
    * origen_coordenadas
    
    Deberan aparecer marcadas como disponibles en la copia de trabajo.
    
56. ${check} Pulse el boton cancelar para cerrar el dialogo de "Nueva tabla".

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
