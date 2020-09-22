## HE00IN00CP001 Definir Formato de Título y Subtítulo 

[Primero compruebo si hay una peticion abierta](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues?utf8=%E2%9C%93&set_filter=1&f%5B%5D=status_id&op%5Bstatus_id%5D=o&f%5B%5D=subject&op%5Bsubject%5D=%7E&v%5Bsubject%5D%5B%5D=HE00IN00CP001&f%5B%5D=&c%5B%5D=tracker&c%5B%5D=status&c%5B%5D=priority&c%5B%5D=subject&c%5B%5D=assigned_to&c%5B%5D=updated_on&group_by=)

### Descripcion

Cargamos el fichero de datos y la seleccion de atributos para realizar un informe. Se probará que se personalizan correctamente los campos de título y subtítulo del informe.

### Prerrequisitos

1. Tener instalado *gvSIG desktop 2.5.1.* 
2. Tener acceso a la tabla de datos [FB_datos1.csv](https://github.com/carloskr/gvsig-desktop-testing/blob/master/data/HE00IN00/IN00_datos1.csv)
3. Tener arrancada la aplicacion con una vista nueva y vacia activa

### Pasos

1. Añadiremos la capa *.csv* teniendo la precaución de seleccionar "," como opción de separador
2. Mostrar la tabla de atributos en la vista
3. Seleccionar menu *Tabla*/Busqueda por atributos
4. Abriremos la opcion "Informes/Definida por usuario"
5. Abrimos las propiedades de "título" con el icono a la derecha de la caja de "Título"
6. Cambiamos tipo y tamaño de letra, color de texto y color de fondo y pulsamos "Aceptar"
7. Repetimos los pasos 5 y 6 con "subtítulo"
8. Pulsaremos en el boton "Aceptar"
 

### Resultados esperados

Como resultado del paso 8 se debe obtener una previsualización del informe con los textos de título y subtítulo formateados de acuerdo con lo especificado en los pasos 5 y 6

### Reportar fallo

En caso de que resultados sean incorrectos, puedes informar del problema en redmine de gvSIG desktop. Puedes encontrarlo en: https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues 

[Abro una nueva publicacion con este test](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues/new?issue[subject]=HE00IN00CP001+Definir Formato+de+Título+y+Subtítulo)