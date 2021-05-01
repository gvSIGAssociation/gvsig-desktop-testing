---
title: Añadir capa a copia de trabajo
testcode: VC00AD00CP000
srcpath: "casos/VC00/AD00/CP000/testVC00AD00CP000.md"
---

{% include es/header.md %}

{% include parameter.html name="tmpfolder" value="/tmp" %}
{% include parameter.html name="reponame" value="Repositorio" %}
{% include parameter.html name="wcname" value="CopiaDeTrabajo" %}
{% include parameter.html name="tablelink" value="<a href='../../data/europa_occidental.csv'>EUROPA_OCCIDENTAL</a>" %}
{% include parameter.html name="tablename" value="europa_occidental" %}

## {{ page.title }}

### Descripción

Crearemos una copia local asociada a un repositorio local basado en H2 y añadiremos a la copia local 
una capa. En el proceso se creara la conexion a la base de datos que va a usarse para acceder al repositorio y
otra para acceder a la copia local.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada:

1. ${check} **TMPFOLDER**="${tmpfolder}". Carpeta en la que se creara los archivos que se precisen 
   durante la ejecucion del test. Deberemos tener  permiso de escritura en ella.

2. ${check} **REPONAME**="${reponame}". Nombre de la conexion a crear asociada al repositorio.

3. ${check} **WCNAME**="${wcname}". Nombre de la copia de trabajo que se va a crear asi como 
   de la conexion a la base de datos de la copia de trabajo. 

4. ${check} Tabla *${tablename}* (${tablelink}). Capa a usar en este test. 

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya version sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} Tendremos descargada la tabla ${tablename} (${tablelink}) en 
   una ruta conocida en nuestro equipo.

### Pasos

1. ${check} Antes de iniciar gvSIG desktop comprobaremos que no existan los ficheros:
   * */${tmpfolder}/${reponame}.mv.db* (*TMPFOLDER*/*REPONAME*.mv.db).
   * */${tmpfolder}/${wcname}.mv.db* (*TMPFOLDER*/*WCNAME*.mv.db).
   
   En caso de que existan los eliminaremos.
   
2. ${check} Iniciaremos gvSIG desktop.

3. ${check} Nos cercioraremos que la vista que se ha creado al arrancar gvSIG se encuentra 
   en "EPSG:4326", de no ser asi cambiaremos la proyección de la vista.

4. ${check} Seleccionaremos la opcion de menu "Herramientas/VCSGis/Administración/Inicializar repositorio" 
   que nos presentara la ventana de titulo "Inicializar repositorio".

5. ${check} Seguiremos los pasos de [Creacion de un repositorio en H2](../../PROC/001/procVC00PROC001.html?TMPFOLDER=${tmpfolder}&REPONAME=${reponame})

7. ${check} Tras la creacion del repositorio, seleccionaremos la opcion de menu 
   "Herramientas/VCSGis/Inicializar copia de trabajo" que nos presentara la ventana de 
   titulo "Inicializar copia de trabajo".

7. ${check} Seguiremos los pasos de [Creacion de una copia de trabajo asociada a un repositorio local en H2](../../PROC/002/procVC00PROC002.html?TMPFOLDER=${tmpfolder}&REPONAME=${reponame}&WCNAME=${wcname}) 
   
8. ${check} Una vez creada la copia de tranajo, procederemos a cargar la 
   capa ${tablelink} en la vista que hay creada 
   en el proyecto. Para eso abriremos el dialogo de añadir capa desde el menu vista, "Vista/Añadir capa".

9. ${check} Seleccionaremos la pestaña "Archivo" y pulsaremos en el boton de "Añadir".

10. ${check} Nos presentara el cuadro de dialogo para seleccionar un fichero. 
    Seleccionaremos el correspondiente a ${tablelink} 
    y pulsaremos en el boton "Abrir".

11. ${check} De vuelta en el dialogo de "Añadir capa" pulsaremos el boton "Aceptar" 
    para cargarla en la vista.

12. ${check} Seleccionaremos la opcion de menu "Herramientas/VCSGis/Añadir a la copia de trabajo" 
    que nos presentara la ventana de titulo Añadir a la copia de trabajo".

13. ${check} Seguiremos los pasos de [Añadir capa a la copia de trabajo](../../PROC/003/VC00PROC003.html?WCNAME=${wcname}&LAYER=${tablename}) 

14. ${check} Debera haber aparecido en la vista una capa 
    "${tablename}" (${tablelink})
    con el identificativo de una capa de base de datos H2.

15. ${check} Eliminaremos de la vista la capa "${tablename}" cargada 
    a partir del fichero ${tablelink}.

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
