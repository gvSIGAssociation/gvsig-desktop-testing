## HE00IN00CP008 Formato página

[Primero compruebo si hay una peticion abierta](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues?utf8=%E2%9C%93&set_filter=1&f%5B%5D=status_id&op%5Bstatus_id%5D=o&f%5B%5D=subject&op%5Bsubject%5D=%7E&v%5Bsubject%5D%5B%5D=HE00IN00CP008&f%5B%5D=&c%5B%5D=tracker&c%5B%5D=status&c%5B%5D=priority&c%5B%5D=subject&c%5B%5D=assigned_to&c%5B%5D=updated_on&group_by=)

### Descripcion

Cargamos el fichero de datos y abriremos la seleccion de atributos para realizar un informe. Se probará que cuando se selecciona el formato de página de la lista cambia el tamaño y/o orientación de las páginas del informe.

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
7. En la lista Asociada a "Formato página" seleccionaremos "A4 vertical"
8. Pulsaremos el botón "Aplicar" y se generará el informe
9. En el informe pulsaremos el botón "Ancho de página"
10. Cerraremos el informe.
11. En la lista Asociada a "Formato página" seleccionaremos "A4 horizontal"
12. Pulsaremos el botón "Aplicar" y se generará el informe
13. En el informe pulsaremos el botón "Ancho de página"
14. Cerraremos el informe.
15. En la lista Asociada a "Formato página" seleccionaremos "Legal vertical"
16. Pulsaremos el botón "Aplicar" y se generará el informe
17. En el informe pulsaremos el botón "Ancho de página"
18. Cerraremos el informe.
19. En la lista Asociada a "Formato página" seleccionaremos "Legal horizontal"
20. Pulsaremos el botón "Aplicar" y se generará el informe
21. En el informe pulsaremos el botón "Ancho de página"
22. Cerraremos el informe.
23. En la lista Asociada a "Formato página" seleccionaremos "Carta vertical"
24. Pulsaremos el botón "Aplicar" y se generará el informe
25. En el informe pulsaremos el botón "Ancho de página"
26. Cerraremos el informe.
27. En la lista Asociada a "Formato página" seleccionaremos "Carta horizontal"
28. Pulsaremos el botón "Aplicar" y se generará el informe
29. En el informe pulsaremos el botón "Ancho de página"
 

### Resultados esperados

- Como resultado del paso 9, debemos obtener un informe con disposición vertical compuesto por 9 páginas.
- Como resultado del paso 13, debemos obtener un informe con disposición horizontal compuesto por 13 páginas.
- Como resultado del paso 17, debemos obtener un informe con disposición vertical compuesto por 7 páginas.
- Como resultado del paso 21, debemos obtener un informe con disposición horizontal compuesto por 12 páginas.
- Como resultado del paso 25, debemos obtener un informe con disposición vertical compuesto por 9 páginas.
- Como resultado del paso 25, debemos obtener un informe con disposición horizontal compuesto por 12 páginas.


### Reportar fallo

En caso de que resultados sean incorrectos, puedes informar del problema en redmine de gvSIG desktop. Puedes encontrarlo en: https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues 

[Abro una nueva publicacion con este test](https://redmine.gvsig.net/redmine/projects/gvsig-desktop/issues/new?issue[subject]=HE00IN00CP008+formato+pagina)