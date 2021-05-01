
## [Test VC00AD00CP000] Añadir capa a copia de trabajo

### Descripción

Crearemos una copia local asociada a un repositorio local basado en H2 y añadiremos a la copia local 
una capa. En el proceso se creara la conexion a la base de datos que va a usarse para acceder al repositorio y
otra para acceder a la copia local.

Antes de pasar el caso de prueba compruebe [aquí](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues?utf8=%E2%9C%93&set_filter=1&f%5B%5D=status_id&op%5Bstatus_id%5D=o&f%5B%5D=subject&op%5Bsubject%5D=%7E&v%5Bsubject%5D%5B%5D=VC00AD00CP000&f%5B%5D=&c%5B%5D=tracker&c%5B%5D=status&c%5B%5D=priority&c%5B%5D=subject&c%5B%5D=assigned_to&c%5B%5D=updated_on&group_by=)
 que no exista abierta una incidencia sobre él.

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

Si se pueden realizar los pasos tal como se han descrito y al cerrar la ventana no aparece ninguna ventana con 
un mensaje de error ni tampoco en la barra de mensajes de la aplicacion, es que la accion se ha realizado correctamente.

### Reportar fallo

En caso de que los resultados obtenidos no sean los correctos puede reportar
una incidencia en el [redmine de gvSIG deskop](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues). 



Pulse [aqui](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues?utf8=%E2%9C%93&set_filter=1&f%5B%5D=status_id&op%5Bstatus_id%5D=o&f%5B%5D=subject&op%5Bsubject%5D=%7E&v%5Bsubject%5D%5B%5D=VC00AD00CP000&f%5B%5D=&c%5B%5D=tracker&c%5B%5D=status&c%5B%5D=priority&c%5B%5D=subject&c%5B%5D=assigned_to&c%5B%5D=updated_on&group_by=) para comprobar si hay abierta una incidencia sobre este caso de prueba.

Pulse [aqui](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues/new?issue[subject]=VC00AD00CP000+Add+layer+to+working+copy) para abrir una indicendia sobre este caso de prueba.

Recuerde adjuntar los ficheros de *log* generados durante la ejecución del test que a ha fallado al ticket.


