---
title: Añadir tabla a una copia de trabajo
proccode: VC00PROC014
srcpath: "casos/VC00/PROC/014/procVC00PROC014.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Este procedimiento describe como añadir una tabla ya cargada en el proyecto
a una copia de trabajo ya creada. Desde donde se invoque al procedimiento deberá
haberse inicializado correctamente la copia de trabajo y haber indicado al usuario
como mostrar la ventana de "Añadir a la copia de trabajo".

### Datos de entrada

1. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia de trabajo que se va a crear así como 
   de la conexión a la base de datos de la copia de trabajo. 

1. ${check} **TABLE**=```${TABLE}```. Nombre de la tabla a añadir a la copia de trabajo ```${WORKINGCOPY}``` (WORKINGCOPY).

1. ${check} **FIELDFORLABEL**=```${FIELDFORLABEL}```. Nombre del campo de la tabla a añadir
   a usar en "Campo para etiqueta". 

1. ${check} **CATEGORY**={% include var_tag.html var="CATEGORY" %}. Categoría a la que se asociará la tabla al 
   añadirla a la copia local. 

1. ${check} **USER**={% include var_tag.html var="USER" %}.

1. ${check} **PASSWORD**={% include var_tag.html var="PASSWORD" %}.

### Pasos

1. ${check} Al iniciarse este procedimiento deberá estar abierta la ventana de añadir a la copia de 
   trabajo de titulo "Añadir a la copia de trabajo" y deberá estar activa.

2. ${check} En el desplegable del campo "Copia de trabajo" deberá existir una 
   entrada ```${WORKINGCOPY}``` (WORKINGCOPY). Si existe selecciónela. Si no existe
   termine el procedimiento.
   
5. ${check} De vuelta en la ventana "Añadir a la copia de trabajo", active la pestaña "Tablas" y seleccione
    la opción ```${TABLE}``` (TABLE). Si ésta no existe aborte el caso de prueba.

{%include es/conditional_login.md %}   

6. ${check} Deberá aparecer marcada la casilla de verificación "Añadir la tabla nueva el proyecto".

7. ${check} Deberá aparecer en el valor del campo "nombre" ```${TABLE}``` (TABLE).

8. ${check} En el desplegable del  campo "Campo para etiqueta" introduzca 
   la opción ```${FIELDFORLABEL}``` (FIELDFORLABEL). 
   Si ésta no existe aborte el caso de prueba.

9. ${check} En el campo "Etiqueta" no especifique nada.

10. ${check} En el campo "Categoría" introduzca el valor ```${CATEGORY}``` (CATEGORY) {% include var_copy.html var="CATEGORY"%}.

11. ${check} Pulse el botón "Añadir a la copia de trabajo".

12. ${check} Deberá haber terminado el proceso sin presentar ningún mensaje de error,
    ni en ventanas ni en la barra de mensajes de gvSIG desktop.

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
