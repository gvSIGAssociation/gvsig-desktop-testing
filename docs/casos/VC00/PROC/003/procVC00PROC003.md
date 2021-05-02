---
title: Añadir capa a una copia de trabajo asociada a un repositorio local en H2
testcode: VC00PROC003
srcpath: "casos/VC00/PROC/003/procVC00PROC003.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción



### Datos de entrada

1. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia de trabajo que se va a crear asi como 
   de la conexion a la base de datos de la copia de trabajo. 

2. ${check} **LAYER**=```${LAYER}```. Nombre de la copia de trabajo que se va a crear asi como 
   de la conexion a la base de datos de la copia de trabajo. 

### Pasos

1. ${check} Al iniciarse este procedimiento debera estar abierta la venta de añadir a la copia de 
   trabajo de titulo "Añair a la copia de trabajo" y debera estar activa.

2. ${check} En el desplegable del campo "Copia de trabajo" debera existir una 
   entrada ```${WCNAME}``` (WCNAME). Si existe la selccionaremos. Si no existe
   abortaremos el procedimiento.
   
4. ${check} Activaremos la pestaña "Capas" y en el arbol que presenta seleccionaremos
    la opcion ```${LAYER}``` (LAYER). Si esta no existe abortaremos el procedimiento.

3. ${check} En el desplegable de "Conexion" seleccionaremos ```${REPONAME}``` (REPONAME). 
   Si no esta esta opcion en el desplegable abortamos test, marcandolo como fallido.

4. ${check} Marcaremos la opcion de "Base de datos personal (H2Spatial)

5. ${check} Pulsaremos el boton asociado al campo "Fichero" y no aparecera el dialogo de seleccionar
   fichero.
   
6. ${check} Seleccionaremos el fichereo ```${TMPFOLDER}/${WCNAME}``` y pulsaremos el boton "Abrir".
   Se cerrar el dialogo de seleccion de fichero y volveremos al dialogo de "Inicializar copia de trbajo".
   
7. ${check} En el campo "Nombre" debera haber aparecido el valor ```${WCNAME}```.

8. ${check} Pulsaremos el boton "Inicializar copia de trabajo".

9. ${check} Se debera cerrar la ventana sin presentar ningun mensaje de error,
   ni en ventanas ni en la barra de mensajes de gvSIG desktop.

10. ${check} Abriremos un explorador de archivos del sistema y comprobaremos que se ha creado el archivo 
    ```${TMPFOLDER}/${WCNAME}.mv.db``` (TMPFOLDER/WCNAME.mv.db)
    en el sistema de archivos.

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
