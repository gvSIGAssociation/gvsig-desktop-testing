
## [Procedure VC00LB00PR002] Creacion de una copia local de un repositorio local en H2

### Descripción

Este procedimiento crea una copia de trabajo asociada a un repositorio local.

Datos de entrada:

1. **TMPFOLDER**, una carpeta en la que se disponga de acceso para escritura
2. **REPONAME**, nombre de la conexion a crear asociada al repositorio
2. **WCNAME**, nombre de la conexion a crear asociada a la copia local


Antes de pasar el caso de prueba compruebe [aquí](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues?utf8=%E2%9C%93&set_filter=1&f%5B%5D=status_id&op%5Bstatus_id%5D=o&f%5B%5D=subject&op%5Bsubject%5D=%7E&v%5Bsubject%5D%5B%5D=VC00LB00PR002&f%5B%5D=&c%5B%5D=tracker&c%5B%5D=status&c%5B%5D=priority&c%5B%5D=subject&c%5B%5D=assigned_to&c%5B%5D=updated_on&group_by=)
 que no exista abierta una incidencia sobre él.


### Pasos

1. Estaremos viendo la ventana de creacion de copias de trabajo, con titulo "????" y estara activa.,/Administracion/????" que nos
2. Seleccionaremos el repo local <REPONAME> usando el desplegable. Si no esta en el desplegable abortamos test.
3. Introduciremos el nombre de la copia de trabajo <WCNAME>
4. Seleccionaremos la ruta a la copia local "<TMPFOLDER>/<WCNAME>"
5. Pulsaremos en ?aceptar?
6. Comprobaremos que se ha creado el archivo "<TMPFOLDER>/<WCNAME>.mv.db" en el sistema de archivos.

### Resultado esperado

Si se pueden realizar los pasos tal como se han descrito y al cerrar la ventana no aparece ninguna ventana con 
un mensaje de error ni tampoco en la barra de mensajes de la aplicacion, es que la accion se ha realizado correctamente.

### Reportar fallo

En caso de que los resultados obtenidos no sean los correctos puede reportar
una incidencia en el *redmine* de *gvSIG deskop* que localizará en 
https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues .

[Comprobar si hay abierta una incidencia sobre este caso de prueba](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues?utf8=%E2%9C%93&set_filter=1&f%5B%5D=status_id&op%5Bstatus_id%5D=o&f%5B%5D=subject&op%5Bsubject%5D=%7E&v%5Bsubject%5D%5B%5D=VC00LB00PR002&f%5B%5D=&c%5B%5D=tracker&c%5B%5D=status&c%5B%5D=priority&c%5B%5D=subject&c%5B%5D=assigned_to&c%5B%5D=updated_on&group_by=)

[Abrir una indicendia sobre este caso de prueba](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues/new?issue[subject]=VC00LB00PR002+Creacion+de+una+copia+local+de+un+repositorio+local+en+H2)



