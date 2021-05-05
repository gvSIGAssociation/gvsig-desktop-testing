---
title: Inicialización de una copia de trabajo (repositorio local en H2)
proccode: VC00PROC002
srcpath: "casos/VC00/PROC/002/procVC00PROC002.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Este procedimiento inicializa una copia de trabajo asociada a un repositorio local. La conexion al repositorio
debera estar creada cuando se ejecute este procedimiento.

### Datos de entrada

1. ${check} **TMPFOLDER**=```${TMPFOLDER}```. Carpeta en la que se creara los archivos que se precisen 
   durante la ejecucion del test. Deberemos tener  permiso de escritura en ella.

2. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexion a usar para seleccionar el repositorio.

3. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia de trabajo que se va a crear asi como 
   de la conexion a la base de datos de la copia de trabajo. 

### Pasos

1. ${check} Al iniciarse este procedimiento debera estar abierta la venta de inicializacion de copias de 
   trabajo de titulo "Inicializar copia de trabajo" y debera estar activa.

2. ${check} Marcaremos la opcion de "Servidor de base de datos".

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

{% include es/expectedresult.md %}

### Reportar fallo

Si se produce un error reportelo en el test que esta ejecutando.

{% include es/footer.html %}
