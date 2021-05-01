---
title: Añadir capa a copia de trabajo
testcode: VC00AD00CP000
srcpath: "casos/VC00/AD00/CP000/testVC00AD00CP000.md"
tmpfolder: "/tmp"
reponame: "Repositorio"
wcname: "CopiaDeTrabajo"
tablelink: "[EUROPA_OCCIDENTAL](../../data/europa_occidental.csv)"
tablename: "europa_occidental"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Crearemos una copia local asociada a un repositorio local basado en H2 y añadiremos a la copia local 
una capa. En el proceso se creara la conexion a la base de datos que va a usarse para acceder al repositorio y
otra para acceder a la copia local.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada:

1. {%include check.html%}  **TMPFOLDER**="{{page.tmpfolder}}". Carpeta en la que se disponga de acceso para escritura donde
   se crearan los archivos necesarios durante la ejecucion del test.
2. {%include check.html%}  **REPONAME**="{{page.reponame}}". Nombre de la conexion a crear asociada al repositorio.
3. {%include check.html%}  **WCNAME**="{{page.wcname}}". Nombre de la conexion a crear asociada a la copia local. 
4. {%include check.html%}  Tabla **{{page.tablename}}** ({{page.tablelink}}). Capa a usar en este test. 

### Prerrequisitos

1. {%include check.html%} Un gvSIG desktop instalado y funcional cuya version sea la indicada en el plan de pruebas.
2. {%include check.html%} El complemento de VCSGis debe estar instalado y activo.
3. {%include check.html%} Tendremos descargada la tabla ({{page.tablename}} (({{page.tablelink}}) en 
   una ruta conocida en nuestro equipo.

### Pasos

1. {%include check.html%} Antes de iniciar gvSIG desktop comprobaremos que no existan los ficheros:
   * */{{page.tmpfolder}}/{{page.reponame}}.mv.db* (*TMPFOLDER*/*REPONAME*.mv.db).
   * */{{page.tmpfolder}}/{{page.wcname}}.mv.db* (*TMPFOLDER*/*WCNAME*.mv.db).
   
   En caso de que existan los eliminaremos.
   
2. {%include check.html%} Iniciaremos gvSIG desktop.

3. {%include check.html%} Nos cercioraremos que la vista que se ha creado al arrancar gvSIG se encuentra 
   en "EPSG:4326", de no ser asi cambiaremos la proyección de la vista.

4. {%include check.html%} Seleccionaremos la opcion de menu "Herramientas/VCSGis/Administración/Inicializar repositorio" 
   que nos presentara la ventana de titulo "Inicializar repositorio".

5. {%include check.html%} Seguiremos los pasos de [Creacion de un repositorio en H2](../../PROC/001/procVC00PROC001.html?TMPFOLDER={{page.tmpfolder}}&REPONAME={{page.reponame}}) usando:
   * TMPFOLDER="{{page.tmpfolder}}" (*TMPFOLDER*)
   * REPONAME="{{page.reponame}}" (*REPONAME*)

6. {%include check.html%} Tras la creacion del repositorio, seleccionaremos la opcion de menu 
   "Herramientas/VCSGis/Inicializar copia de trabajo" que nos presentara la ventana de 
   titulo "Inicializar copia de trabajo".

7. {%include check.html%} Seguiremos los pasos de 
   [Creacion de una copia de trabajo asociada a un repositorio local en H2](../../PROC/002/procVC00PROC002.md) 
   usando:
   * TMPFOLDER="{{page.tmpfolder}}" (*TMPFOLDER*)
   * REPONAME="{{page.reponame}}" (*REPONAME*)
   * WCNAME="{{page.wcname}}" (*WCNAME*)
   
8. {%include check.html%} Una vez creada la copia de tranajo, procederemos a cargar la 
   capa [EUROPA_OCCIDENTAL](../../data/europa_occidental.csv) en la vista que hay creada 
   en el proyecto. Para eso abriremos el dialogo de añadir capa desde el menu vista, "Vista/Añadir capa".

9. {%include check.html%} Seleccionaremos la pestaña "Archivo" y pulsaremos en el boton de "Añadir".

10. {%include check.html%} Nos presentara el cuadro de dialogo para seleccionar un fichero. 
    Seleccionaremos el correspondiente a ({{page.tablelink}} 
    y pulsaremos en el boton "Abrir".

11. {%include check.html%} De vuelta en el dialogo de "Añadir capa" pulsaremos el boton "Aceptar" 
    para cargarla en la vista.

12. {%include check.html%} Seleccionaremos la opcion de menu "Herramientas/VCSGis/Añadir a la copia de trabajo" 
    que nos presentara la ventana de titulo Añadir a la copia de trabajo".

13. {%include check.html%} Seguiremos los pasos de [Añadir capa a la copia de trabajo](../../PROC/003/VC00PROC003.md) usando: 
   * WCNAME="{{page.wcname}}" (*WCNAME*)
   * LAYER="{{page.tablename}}" ({{page.tablelink}})

14. {%include check.html%} Debera haber aparecido en la vista una capa 
    "{{page.tablename}}" (({{page.tablelink}})
    con el identificativo de una capa de base de datos H2.

15. {%include check.html%} Eliminaremos de la vista la capa "({{page.tablename}}" cargada 
    a partir del fichero (({{page.tablelink}}).

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

