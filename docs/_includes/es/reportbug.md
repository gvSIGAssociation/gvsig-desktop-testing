En caso de que los resultados obtenidos no sean los correctos puede reportar
una incidencia en el [redmine de gvSIG deskop](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues?set_filter=1). 

Pulse [aquí](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues?utf8=%E2%9C%93&set_filter=1&f%5B%5D=status_id&op%5Bstatus_id%5D=o&f%5B%5D=subject&op%5Bsubject%5D=%7E&v%5Bsubject%5D%5B%5D={{include.testcode | default: page.testcode}}&f%5B%5D=&c%5B%5D=tracker&c%5B%5D=status&c%5B%5D=priority&c%5B%5D=subject&c%5B%5D=assigned_to&c%5B%5D=updated_on&group_by=) 
para comprobar si hay abierta una incidencia sobre este caso de prueba.

Pulse [aquí](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues/new?issue[subject]={{include.testcode | default: page.testcode}}+{{include.testtitle| default: page.title| escape | replace: " ", "+" }}) para abrir una indicendia sobre este caso de prueba.
Indique en la descripción del ticket en qué paso del caso de prueba se ha producido el problema, y describa lo mas
inequivocamente posible qué ha observado para decidir que no ha pasado éste. En caso de que el problema se produzca en un procedimiento dentro del caso de prueba, indique, además del paso dentro del caso de prueba, en qué paso del procedimiento se ha producido el problema.
**Recuerde adjuntar los ficheros de *log*** generados durante la ejecución del test que ha fallado al ticket.

