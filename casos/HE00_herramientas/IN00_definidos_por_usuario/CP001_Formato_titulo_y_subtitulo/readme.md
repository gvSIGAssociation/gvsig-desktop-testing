## HE00IN00CP001 Definir Formato de Título y Subtítulo 

[Primero compruebo si hay una peticion abierta](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues?utf8=%E2%9C%93&set_filter=1&f%5B%5D=status_id&op%5Bstatus_id%5D=o&f%5B%5D=subject&op%5Bsubject%5D=%7E&v%5Bsubject%5D%5B%5D=HE00IN00CP001&f%5B%5D=&c%5B%5D=tracker&c%5B%5D=status&c%5B%5D=priority&c%5B%5D=subject&c%5B%5D=assigned_to&c%5B%5D=updated_on&group_by=)

### Descripcion

Cargamos el fichero de datos y la seleccion de atributos para realizar un informe. Se probará que se personalizan correctamente los campos de título y subtítulo del informe.

### Prerrequisitos

1. Tener instalado *gvSIG desktop 2.5.1.* 
2. Tener acceso a la tabla de datos [IN00_datos1.csv](https://github.com/carloskr/gvsig-desktop-testing/blob/master/data/HE00IN00/IN00_datos1.csv)
3. Tener arrancada la aplicacion con una vista nueva y vacia activa

### Pasos

1. Añadiremos la capa *.csv* teniendo la precaución de seleccionar "," como opción de separador
2. Mostrar la tabla de atributos en la vista
3. Seleccionar menu *Tabla*/Busqueda por atributos
4. Abriremos la opcion "Informes/Definida por usuario"
5. Abriremos las propiedades del título con el icono a la derecha de la caja de "Título"
6. En la pestaña "General" cambiaremos el tipo de letra a *Comic Sans* y el tamaño de letra a 24
7. Cambiaremos también el color del texto a color rojo *RGB: FF0000* y el color de fondo a color cyan *RGB: 00FFFF*
8. En la pestaña "Border" seleccionaremos *Top*/Edit border estableciendo Width = 5 y el color a *RGB: FF00FF* haciendo igual con *Botton*/Edit border
9. Pulsaremos en el botón "Aceptar" para cerrar las opciones de título
10. Escribiremos "Subtítulo" dentro de la caja del mismo nombre.
11. Abriremos las propiedades de "subtítulo" con el icono a la derecha de la caja de "Subtítulo"
12. En la pestaña "General" cambiaremos el tipo de letra a *Verdana* y el tamaño de letra a 18
13. Cambiaremos también el color del texto a color verde *RGB: 00FF00* y el color de fondo a color amarillo *RGB: FFFF00*
14. En la pestaña "Border" seleccionaremos *Botton*/Edit border estableciendo Width = 3 y el color a *RGB: FF00FF* 
15. Pulsaremos en el boton "Aceptar" para cerrar las opciones de subtítulo
16. Pulsaremos en el boton "Aceptar" para cerrar el *Report Builder* y generar el informe
 

### Resultados esperados

- Como resultado de los pasos 6 y 7, el título debe aparecer en el informe con tipo de letra *Comic Sans*, tamaño 24 en color rojo sobre fondo de color cyan
- Como resultado del paso 8, el título debe tener un borde superior y otro inferior de 5 puntos de ancho y de color púrpura
- Como resultado de los pasos 12 y 13, el subtítulo debe aparecer en el informe con tipo de letra *Verdana*, tamaño 18 en color verde sobre fondo de color amarillo
- Como resultado del paso 14, el título debe tener un borde inferior de 3 puntos de ancho y de color púrpura

### Reportar fallo

En caso de que resultados sean incorrectos, puedes informar del problema en redmine de gvSIG desktop. Puedes encontrarlo en: https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues 

[Abro una nueva publicacion con este test](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues/new?issue[subject]=HE00IN00CP001+Definir Formato+de+Título+y+Subtítulo)