
## [Test VC00CW00CP000] Creacion de una copia local de un repositorio local en H2

### Descripción

Crearemos una copia local asociada a un repositorio local basado en H2.
En el proceso se creara la conexion a la base de datos que va a usarse para acceder al repositorio y
otra para acceder a la copia local.

Datos de entrada:

1. **TMPFOLDER**, una carpeta en la que se disponga de acceso para escritura, por defecto "/tmp"
2. **REPONAME**, nombre de la conexion a crear asociada al repositorio, por defecto "Repositorio"
2. **WCNAME**, nombre de la conexion a crear asociada a la copia local, por defecto "workingcopy"


Antes de pasar el caso de prueba compruebe [aquí](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues?utf8=%E2%9C%93&set_filter=1&f%5B%5D=status_id&op%5Bstatus_id%5D=o&f%5B%5D=subject&op%5Bsubject%5D=%7E&v%5Bsubject%5D%5B%5D=VC00CW00CP000&f%5B%5D=&c%5B%5D=tracker&c%5B%5D=status&c%5B%5D=priority&c%5B%5D=subject&c%5B%5D=assigned_to&c%5B%5D=updated_on&group_by=)
 que no exista abierta una incidencia sobre él.

### Prerrequisitos

1. Un gvSIG desktop instalado, version 2.6.0-3220 o superior
2. El complemento de VCSGis debe estar instalado y activo.


### Pasos

1. Antes de iniciar gvSIG desktop comprobaremos que no existan los ficheros "<TMPFOLDER>/<REPONAME>.mv.db" y
   "<TMPFOLDER>/<WCNAME>.mv.db" y en caso de que existan los eliminaremos.
2. Iniciaremos gvSIG desktop.
3. Una vez iniciado seleccionaremos la opcion de menu "Herramientas/VCSGis/Administracion/????" que nos
   presentara la ventana de titulo "??????".
4. Seguiremos los pasos de [VC00LB00PR002 Creacion de una copia local de un repositorio local en H2](../../LB00/PR002_create_dbconnection/definition.md) 
   usando TMPFOLDER, REPONAME y WCNAME

### Resultado esperado

Si se pueden realizar los pasos tal como se han descrito y al cerrar la ventana no aparece ninguna ventana con 
un mensaje de error ni tampoco en la barra de mensajes de la aplicacion, es que la accion se ha realizado correctamente.

### Reportar fallo

En caso de que los resultados obtenidos no sean los correctos puede reportar
una incidencia en el *redmine* de *gvSIG deskop* que localizará en 
https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues .

[Comprobar si hay abierta una incidencia sobre este caso de prueba](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues?utf8=%E2%9C%93&set_filter=1&f%5B%5D=status_id&op%5Bstatus_id%5D=o&f%5B%5D=subject&op%5Bsubject%5D=%7E&v%5Bsubject%5D%5B%5D=VC00CW00CP000&f%5B%5D=&c%5B%5D=tracker&c%5B%5D=status&c%5B%5D=priority&c%5B%5D=subject&c%5B%5D=assigned_to&c%5B%5D=updated_on&group_by=)

[Abrir una indicendia sobre este caso de prueba](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues/new?issue[subject]=VC00CW00CP000+Creacion+de+un+repositorio+de+H2)



