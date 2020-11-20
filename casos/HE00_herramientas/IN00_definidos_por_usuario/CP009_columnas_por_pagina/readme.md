## HE00IN00CP009 Columnas por página

[Primero compruebo si hay una peticion abierta](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues?utf8=%E2%9C%93&set_filter=1&f%5B%5D=status_id&op%5Bstatus_id%5D=o&f%5B%5D=subject&op%5Bsubject%5D=%7E&v%5Bsubject%5D%5B%5D=HE00IN00CP009&f%5B%5D=&c%5B%5D=tracker&c%5B%5D=status&c%5B%5D=priority&c%5B%5D=subject&c%5B%5D=assigned_to&c%5B%5D=updated_on&group_by=)

### Descripcion

Cargamos el fichero de datos y abriremos la seleccion de atributos para realizar un informe. Cuando se cambia el valor del campo "Columnas por página" cambia el número de columnas en el informe.

### Prerrequisitos

1. Tener instalado *gvSIG desktop 2.5.1.* 
2. Tener acceso a la tabla de datos [IN00_datos1.csv](https://github.com/carloskr/gvsig-desktop-testing/blob/master/data/HE00IN00/IN00_datos1.csv)
3. Tener arrancada la aplicacion con una vista nueva y vacia activa

### Pasos

1. Añadiremos la capa *.csv* teniendo la precaución de seleccionar "," como opción de separador
2. Mostrar la tabla de atributos en la vista
3. Seleccionar menu *Tabla*/Busqueda por atributos
4. Pasaremos a la pestaña "Columnas"
5. En el desplegable seleccionaremos el campo "PARCELA" y pulsaremos en el "+" de color verde de la derecha
6. Volveremos a la pestaña "Informe"
7. Nos aseguraremos que el valor del campo "Columnas por página" es 1
8. Pulsaremos el botón "Aplicar" y se generará el informe
9. En el informe pulsaremos el botón "Ancho de página"
10. Cerraremos el informe.
11. En el campo "Columnas por página" sustituiremos el valor 1 por el valor 3
12. Pulsaremos el botón "Aplicar" y se generará el informe
13. En el informe pulsaremos el botón "Ancho de página"
14. Cerraremos el informe.
 

### Resultados esperados

- Como resultado del paso 9, debemos obtener un informe con una tabla con una única columna.
- Como resultado del paso 13, debemos obtener un informe con una tabla con tres columnas.


### Reportar fallo

En caso de que resultados sean incorrectos, puedes informar del problema en redmine de gvSIG desktop. Puedes encontrarlo en: https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues 

[Abro una nueva publicacion con este test](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues/new?issue[subject]=HE00IN00CP009+columnas+por+pagina)