---
title: Añadir capa a una copia de trabajo asociada a un repositorio local en H2
testcode: VC00PROC003
srcpath: "casos/VC00/PROC/003/procVC00PROC003.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Este procedimiento describe como añadir añadir una capa ya cargada en el proyecto
a una copia de trabajo ya creada. Desde donde se invoque al procedimiento debera
haberse inicializado correctamente la copia de trabajo y haber indicado al usuario
como mostrar la ventana de "Añadir a la copia de trabajo".

### Datos de entrada

1. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia de trabajo que se va a crear asi como 
   de la conexion a la base de datos de la copia de trabajo. 

2. ${check} **LAYER**=```${LAYER}```. Nombre de la copia de trabajo que se va a crear asi como 
   de la conexion a la base de datos de la copia de trabajo. 

3. ${check} **FIELDFORLABEL**=```${FIELDFORLABEL}```. Nombre del campo de la capa a añadir
   a usar en "Campo para etiqueta". 

4. ${check} **CATEGORY**=```${CATEGORY}```. Categoria a la que se asociara la capa al 
   añadirla a la copia local. 

### Pasos

1. ${check} Al iniciarse este procedimiento debera estar abierta la venta de añadir a la copia de 
   trabajo de titulo "Añadir a la copia de trabajo" y debera estar activa.

2. ${check} En el desplegable del campo "Copia de trabajo" debera existir una 
   entrada ```${WCNAME}``` (WCNAME). Si existe la selccionaremos. Si no existe
   abortaremos el procedimiento.
   
4. ${check} Activaremos la pestaña "Capas" y en el arbol que presenta seleccionaremos
    la opcion ```${LAYER}``` (LAYER). Si esta no existe abortaremos el procedimiento.

5. ${check} Debera aparecer marcado el check "Añadir la nueva capa a la vista".

6. ${check} Debera aparecer en el desplegable de vistas "Sin titulo".

7. ${check} Debera aparecer en el valor del campo "nombre" ```${LAYER}``` (LAYER).

8. ${check} En el desplegable del  campo "Campo para etiqueta" seleccionaremos 
   la opcion ```${FIELDFORLABEL}``` (FIELDFORLABEL). 
   Si esta no existe abortaremos el procedimiento.

9. ${check} En el campo "Categoria" introduciremos el valor  ```${CATEGORY}``` (CATEGORY).

10. ${check} Pulsaremos el boton "Añadir a la copia de trabajo".

11. ${check} Se debera cerrar la ventana sin presentar ningun mensaje de error,
    ni en ventanas ni en la barra de mensajes de gvSIG desktop.

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
