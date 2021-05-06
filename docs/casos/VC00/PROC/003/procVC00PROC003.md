---
title: Añadir capa a una copia de trabajo asociada a un repositorio local en H2
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

1. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia de trabajo que se va a crear asi como 
   de la conexion a la base de datos de la copia de trabajo. 

2. ${check} **LAYER**=```${LAYER}```. Nombre de la capa a añadir a la copia de trabajo ```${WCNAME}``` (WCNAME).

3. ${check} **FIELDFORLABEL**=```${FIELDFORLABEL}```. Nombre del campo de la capa a añadir
   a usar en "Campo para etiqueta". 

4. ${check} **CATEGORY**=```${CATEGORY}```. Categoria a la que se asociara la capa al 
   añadirla a la copia local. 

### Pasos

1. ${check} Al iniciarse este procedimiento debera estar abierta la ventana de añadir a la copia de 
   trabajo de titulo "Añadir a la copia de trabajo" y debera estar activa.

2. ${check} En el desplegable del campo "Copia de trabajo" debera existir una 
   entrada ```${WCNAME}``` (WCNAME). Si existe seleccionela. Si no existe
   termine el procedimiento.

3. ${check} Se habrá presentado la ventana de título "Inicio de sesión de usuario".

4. ${check} Introduzca en el campo de texto "Usuario" el valor ```${USER}``` (USER) y en el "Contraseña" ```${PASSWORD}``` (PASSWORD).
 
5. ${check} Active la pestaña "Capas" y en el árbol que presenta seleccione
    la opción ```${LAYER}``` (LAYER). Si esta no existe termine el procedimiento.

6. ${check} Debera aparecer marcado el check "Añadir la nueva capa a la vista".

7. ${check} Debera aparecer en el desplegable de vistas "Sin titulo".

8. ${check} Debera aparecer en el valor del campo "nombre" ```${LAYER}``` (LAYER).

9. ${check} En el desplegable del  campo "Campo para etiqueta" seleccione 
   la opción ```${FIELDFORLABEL}``` (FIELDFORLABEL). 
   Si esta no existe aborte el procedimiento.

10. ${check} En el campo "Categoría" introduzca el valor  ```${CATEGORY}``` (CATEGORY).

11. ${check} Pulse el boton "Añadir a la copia de trabajo".

12. ${check} Se debera cerrar la ventana sin presentar ningun mensaje de error,
    ni en ventanas ni en la barra de mensajes de gvSIG desktop.

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
