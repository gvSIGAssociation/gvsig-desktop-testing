---
title: Añadir tabla a una copia de trabajo
proccode: VC00PROC014
srcpath: "casos/VC00/PROC/014/procVC00PROC014.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Este procedimiento describe como añadir una tabla ya cargada en el proyecto
a una copia de trabajo ya creada. Desde donde se invoque al procedimiento debera
haberse inicializado correctamente la copia de trabajo y haber indicado al usuario
como mostrar la ventana de "Añadir a la copia de trabajo".

### Datos de entrada

1. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia de trabajo que se va a crear asi como 
   de la conexion a la base de datos de la copia de trabajo. 

1. ${check} **TABLE**=```${TABLE}```. Nombre de la tabla a añadir a la copia de trabajo ```${WORKINGCOPY}``` (WORKINGCOPY).

1. ${check} **FIELDFORLABEL**=```${FIELDFORLABEL}```. Nombre del campo de la tabla a añadir
   a usar en "Campo para etiqueta". 

1. ${check} **CATEGORY**={% include var_tag.html var="CATEGORY" %}. Categoria a la que se asociara la tabla al 
   añadirla a la copia local. 

1. ${check} **USER**={% include var_tag.html var="USER" %}.

1. ${check} **PASSWORD**={% include var_tag.html var="PASSWORD" %}.

### Pasos

1. ${check} Al iniciarse este procedimiento debera estar abierta la ventana de añadir a la copia de 
   trabajo de titulo "Añadir a la copia de trabajo" y debera estar activa.

2. ${check} En el desplegable del campo "Copia de trabajo" debera existir una 
   entrada ```${WORKINGCOPY}``` (WORKINGCOPY). Si existe seleccionela. Si no existe
   termine el procedimiento.
   
3. ${check} Se habrá presentado la ventana de título "Inicio de sesión de usuario".

4. ${check} Introduzca en el campo de texto "Usuario" el valor ```${USER}``` (USER) {% include var_copy.html var="USER"%}
 
6. ${check} Introduzca en el campo de texto "Contraseña" el valor ```${PASSWORD}``` (PASSWORD) {% include var_copy.html var="PASSWORD"%}

7. Pulse "Aceptar".

5. ${check} Devuelta a la ventana "Añadir a la copia de trabajo", active la pestaña "Tablas" y seleccione
    la opción ```${TABLE}``` (TABLE). Si esta no existe aborte el caso de prueba.

6. ${check} Debera aparecer marcado el check "Añadir la tabla nueva el proyecto".

7. ${check} Debera aparecer en el valor del campo "nombre" ```${TABLE}``` (TABLE).

8. ${check} En el desplegable del  campo "Campo para etiqueta" introduzca 
   la opción ```${FIELDFORLABEL}``` (FIELDFORLABEL). 
   Si esta no existe aborte el caso de prueba.

9. ${check} En el campo para "Etiqueta" no especifique nada.

10. ${check} En el campo "Categoria" introduzca el valor ```${CATEGORY}``` (CATEGORY) {% include var_copy.html var="CATEGORY"%}.

11. ${check} Pulse el boton "Añadir a la copia de trabajo".

12. ${check} Se debera cerrar la ventana sin presentar ningun mensaje de error,
    ni en ventanas ni en la barra de mensajes de gvSIG desktop.

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
