---
title: Añadir capa a una copia de trabajo 
proccode: VC00PROC003
srcpath: "casos/VC00/PROC/003/procVC00PROC003.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Este procedimiento describe como añadir una capa ya cargada en el proyecto
a una copia de trabajo ya creada. Desde donde se invoque al procedimiento debera
haberse inicializado correctamente la copia de trabajo y haber indicado al usuario
como mostrar la ventana de "Añadir a la copia de trabajo".

### Datos de entrada

1. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia de trabajo que se va a crear asi como 
   de la conexion a la base de datos de la copia de trabajo. 

2. ${check} **LAYER**=```${LAYER}```. Nombre de la capa a añadir a la copia de trabajo.

3. ${check} **FIELDFORLABEL**=```${FIELDFORLABEL}```. Nombre del campo de la capa a añadir
   a usar en "Campo para etiqueta". 

4. ${check} **CATEGORY**={% include var_tag.html var="CATEGORY" %}. Categoria a la que se asociara la capa al 
   añadirla a la copia de trabajo. 

5. ${check} **USER**=```${USER}``` y **PASSWORD**=```${PASSWORD}``` a utilizar cuando se requiera autenticar al
   usuario que esta realizando la opracion.

### Pasos

1. ${check} Al iniciarse este procedimiento debera estar abierta la ventana de añadir a la copia de 
   trabajo de titulo "Añadir a la copia de trabajo" y debera estar activa.

2. ${check} En el desplegable del campo "Copia de trabajo" debera existir una 
   entrada ```${WORKINGCOPY}``` (WORKINGCOPY). Si existe seleccionela. Si no existe
   aborte el caso de prueba.
   
6. ${check} Active la pestaña "Capas" y en el árbol que presenta seleccione
    la opción ```${LAYER}``` (LAYER). Si esta no existe aborte el caso de prueba.

3. ${check} Si se presenta la ventana de título "Inicio de sesión de usuario":
   * ${check} Introduzca en el campo de texto "Usuario" el valor ```${USER}``` (USER)  {% include var_copy.html var="USER"%}
   * ${check} Introduzca en el campo de texto "Contraseña" el valor ```${PASSWORD}``` (PASSWORD)  {% include var_copy.html var="USER"%}.
   * ${check} Pulse el botón "Aceptar".
   * ${check} Se cerrara la venta de inicio de sesión y le devolverá a la ventana en la que estuviese trabajando.

7. ${check} Debera aparecer marcado el check "Añadir la nueva capa a la vista".

8. ${check} Debera aparecer en el desplegable de vistas "Sin titulo".

9. ${check} Debera aparecer en el valor del campo "nombre" ```${LAYER}``` (LAYER).

10. ${check} En el desplegable del  campo "Campo para etiqueta" seleccione 
   la opción ```${FIELDFORLABEL}``` (FIELDFORLABEL). 
   Si esta no existe aborte el procedimiento.

11. ${check} En el campo "Categoría" introduzca el valor  ```${CATEGORY}``` (CATEGORY) {% include var_copy.html var="CATEGORY"%}.

12. ${check} Pulse el boton "Añadir a la copia de trabajo".

13. ${check} En la parte inferior de la ventana se indicara el progreso de la carga.

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
