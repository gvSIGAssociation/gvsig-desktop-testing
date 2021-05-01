
## [Procedure VC00LB00PR000] Creacion de una conexion a base de datos H2

### Descripción

Crea una conexion a una base de datos H2, si la conexion ya existe se eliminara y se volvera a crear.

Datos de entrada:
* **NAME**, nombre de la conexion a crear.
* **PATHNAME**, ruta completa en la que crear la base de datos H2

Antes de pasar el caso de prueba compruebe [aquí](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues?utf8=%E2%9C%93&set_filter=1&f%5B%5D=status_id&op%5Bstatus_id%5D=o&f%5B%5D=subject&op%5Bsubject%5D=%7E&v%5Bsubject%5D%5B%5D=VC00LB00PR000&f%5B%5D=&c%5B%5D=tracker&c%5B%5D=status&c%5B%5D=priority&c%5B%5D=subject&c%5B%5D=assigned_to&c%5B%5D=updated_on&group_by=)
 que no exista abierta una incidencia sobre él.

### Pasos

1. Estaremos viendo la ventana de creacion de conexiones a base de datos, de titulo "XXX" y estara activa.
2. Comprobaremos si existe la conexion <NAME>. Para miraremos si ya existe en el desplegable 
   del campo ????? un valor con el nombre <NAME>.
3. Si existe lo seleccionaremos y pulsaremos el boton inferior que dice "Mas...", seleccionando la
   opcion ???
4. Escribiremos el nombre <NAME> en la caja de texto ????
5. Indicaremos como conector el de H2. Para ello seleccionaremos el valor ???? en el desplegable "???".
6. Pulsaremos en el boton asociado al campo '???' y en el dialogo de seleccion de fichero introduciremos 
   el valor <PATHNAME>, pulsando acceptar en ese dialogo.
7. Deberemos estar de vuelta al dialgo de creacion de conexion a base de datos.
8. Pulsaremos el boton "??aceptar??", que cerrara la ventana.
   

### Resultado esperado

Si se pueden realizar los pasos tal como se han descrito y al cerrar la ventana no aparece ninguna ventana con 
un mensaje de error ni tampoco en la barra de mensajes de la aplicacion, es que la accion se ha realizado correctamente.

### Reportar fallo

En caso de que los resultados obtenidos no sean los correctos puede reportar
una incidencia en el *redmine* de *gvSIG deskop* que localizará en 
https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues .

[Comprobar si hay abierta una incidencia sobre este caso de prueba](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues?utf8=%E2%9C%93&set_filter=1&f%5B%5D=status_id&op%5Bstatus_id%5D=o&f%5B%5D=subject&op%5Bsubject%5D=%7E&v%5Bsubject%5D%5B%5D=VC00LB00PR000&f%5B%5D=&c%5B%5D=tracker&c%5B%5D=status&c%5B%5D=priority&c%5B%5D=subject&c%5B%5D=assigned_to&c%5B%5D=updated_on&group_by=)

[Abrir una indicendia sobre este caso de prueba](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues/new?issue[subject]=VC00LB00PR000+Creacion+de+una+conexion+a+base+de+datos+H2)



