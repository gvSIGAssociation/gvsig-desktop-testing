{{testcode="VC00AD00CP000"}}

{% include es/header.md page="casos/VC00/AD00/CP000/testVC00AD00CP000.md"%}

## Añadir capa a copia de trabajo

### Descripción

Crearemos una copia local asociada a un repositorio local basado en H2 y añadiremos a la copia local 
una capa. En el proceso se creara la conexion a la base de datos que va a usarse para acceder al repositorio y
otra para acceder a la copia local.

{% include es/checkifthereisalreadyabug.md testcode="VC00AD00CP000"%}

### Datos de entrada:

1. **TMPFOLDER**="/tmp". Carpeta en la que se disponga de acceso para escritura donde
   se crearan los archivos necesarios durante la ejecucion del test.
4. **REPONAME**="Repositorio". Nombre de la conexion a crear asociada al repositorio.
5. **WCNAME**="workingcopy". Nombre de la conexion a crear asociada a la copia local. 
6. **[LAYER](../../data/layer.csv)**. Capa a usar en este test del juego de datos de test asociado a este plan. 

### Prerrequisitos

1. Un gvSIG desktop instalado y funcional cuya version sea la indicada en el plan de pruebas.
2. El complemento de VCSGis debe estar instalado y activo.
3. Tendremos descargada el fichero LAYER en una ruta conocida en nuestro equipo.

### Pasos

1. Antes de iniciar gvSIG desktop comprobaremos que no existan los ficheros "*TMPFOLDER*/*REPONAME*.mv.db" y
   "*TMPFOLDER*/*WCNAME*.mv.db" y en caso de que existan los eliminaremos.
2. Iniciaremos gvSIG desktop.
3. Seleccionaremos la opcion de menu "Herramientas/VCSGis/Administracion/?crear-repositorio?" que nos
   presentara la ventana de titulo "??????".
4. Seguiremos los pasos de [Crear repositorio local en H2](../../LB00/PR000_create_dbconnection/definition.md) 
   usando *TMPFOLDER* y *REPONAME*
5. Seleccionaremos la opcion de menu "Herramientas/VCSGis/?crear-copia-local?" que nos
   presentara la ventana de titulo "??????".
6. Seguiremos los pasos de [Creacion de una copia local de un repositorio local en H2](../../LB00/PR001_create_repo_h2/definition.md) 
   usando *TMPFOLDER*, *REPONAME* y *WCNAME*
7. El proyecto debera tener una vista creada. En ella cargaremos la capa *LAYER*. Para eso abriremos el dialogo de añadir capa desde el menu vista.
8. Seleccionaremos la pestaña fichero y pulsaremos en el boton de "añadir".
9. Seleccionaremos el fichero *LAYER* y pincharemos en el boton aceptar, volviendo al dialogo de añadir capa.
10. Seleccionaremos en la lista la entrada correspondiente al fichero *LAYER* y punsaremos el boton "CRS vista".
11. Pulsaremos en el boton aceptar del dialogo de añadir capa.
12. Seleccionaremos la opcion de menu "Herramientas/VCSGis/Administracion/?add??" que nos
    presentara la ventana de titulo "??????".
13. Seguiremos los pasos de [Añadir capa al repositorio](../../LB00/PR003_add_layer/definition.md) 
    usando *WCNAME* y *LAYER*

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md testcode="VC00AD00CP000" testtitle="Add+layer+to+working+copy" %}

