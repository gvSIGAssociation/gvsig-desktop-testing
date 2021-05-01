---
title: Añadir capa a copia de trabajo
testcode: VC00AD00CP000
srcpath: "casos/VC00/AD00/CP000/testVC00AD00CP000.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Crearemos una copia local asociada a un repositorio local basado en H2 y añadiremos a la copia local 
una capa. En el proceso se creara la conexion a la base de datos que va a usarse para acceder al repositorio y
otra para acceder a la copia local.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada:

1. <input type="checkbox"> **TMPFOLDER**="/tmp". Carpeta en la que se disponga de acceso para escritura donde
   se crearan los archivos necesarios durante la ejecucion del test.
2. <input type="checkbox"> **REPONAME**="Repositorio". Nombre de la conexion a crear asociada al repositorio.
3. <input type="checkbox"> **WCNAME**="WorkingCopy". Nombre de la conexion a crear asociada a la copia local. 
4. <input type="checkbox"> Tabla **[EUROPA_OCCIDENTAL](../../data/europa_occidental.csv)**. Capa a usar en
   este test. 

### Prerrequisitos

1. {%include check.html%} Un gvSIG desktop instalado y funcional cuya version sea la indicada en el plan de pruebas.
2. {%include check.html%} El complemento de VCSGis debe estar instalado y activo.
3. {%include check.html%} Tendremos descargada la tabla [TABLA_EUROPA_OCCIDENTAL](../../data/europa_occidental.csv) en una ruta conocida en nuestro equipo.

### Pasos

1. Antes de iniciar gvSIG desktop comprobaremos que no existan los ficheros:
   * */tmp/Repositorio.mv.db* (*TMPFOLDER*/*REPONAME*.mv.db).
   * */tmp/WorkingCopy.mv.db* (*TMPFOLDER*/*WCNAME*.mv.db).
   
   En caso de que existan los eliminaremos.
   
2. Iniciaremos gvSIG desktop.

3. Nos cercioraremos que la vista que se ha creado al arrancar gvSIG se encuentra en "EPSG:4326", de no ser
   asi cambiaremos la proyección de la vista.

4. Seleccionaremos la opcion de menu "Herramientas/VCSGis/Administración/Inicializar repositorio" que nos
   presentara la ventana de titulo "Inicializar repositorio".

5. Seguiremos los pasos de [Creacion de un repositorio en H2](../../PROC/001/procVC00PROC001.md) usando:
   * TMPFOLDER="/tmp" (*TMPFOLDER*)
   * REPONAME="Repositorio" (*REPONAME*)

6. Tras la creacion del repositorio, seleccionaremos la opcion de menu "Herramientas/VCSGis/Inicializar copia de trabajo" que nos
   presentara la ventana de titulo "Inicializar copia de trabajo".

7. Seguiremos los pasos de [Creacion de una copia de trabajo asociada a un repositorio local en H2](../../PROC/002/procVC00PROC002.md) 
   usando:
   * TMPFOLDER="/tmp" (*TMPFOLDER*)
   * REPONAME="Repositorio" (*REPONAME*)
   * REPONAME="WorkingCopy" (*WCNAME*)
   
8. Una vez creada la copia de tranajo, procederemos a cargar la capa [EUROPA_OCCIDENTAL](../../data/europa_occidental.csv) en
   la vista que hay creada en el proyecto. Para eso abriremos el dialogo de añadir capa desde el menu vista, "Vista/Añadir capa".

9. Seleccionaremos la pestaña "Archivo" y pulsaremos en el boton de "Añadir".

10. Nos presentara el cuadro de dialogo para seleccionar un fichero. Seleccionaremos el correspondiente 
    a [EUROPA_OCCIDENTAL](../../data/europa_occidental.csv) y pulsaremos en el boton "Abrir".

11. De vuelta en el dialogo de "Añadir capa" pulsaremos el boton "Aceptar" para cargarla en la vista.

12. Seleccionaremos la opcion de menu "Herramientas/VCSGis/Añadir a la copia de trabajo" que nos
    presentara la ventana de titulo Añadir a la copia de trabajo".

13. Seguiremos los pasos de [Añadir capa a la copia de trabajo](../../PROC/003/VC00PROC003.md) usando: 
   * REPONAME="WorkingCopy" (*WCNAME*)
   * LAYER="europa_accidental" ([EUROPA_OCCIDENTAL](../../data/europa_occidental.csv))

14. Debera haber aparecido en la vista una capa "europa_occidental" ([EUROPA_OCCIDENTAL](../../data/europa_occidental.csv))
    con el identificativo de una capa de base de datos H2.

15. Eliminaremos de la vista la capa "europa_occidental" cargada a partir del 
    fichero ([EUROPA_OCCIDENTAL](../../data/europa_occidental.csv)).

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

