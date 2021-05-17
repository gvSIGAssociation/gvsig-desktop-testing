---
title: Inicialización de una copia de trabajo (repositorio remoto)
proccode: VC00PROC008
srcpath: "casos/VC00/PROC/008/procVC00PROC008.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Este procedimiento inicializa una copia de trabajo asociada a un repositorio remoto. 
El servidor deberá estar iniciado al ejecutar este procedimiento.


### Datos de entrada

1. ${check} **TMPFOLDER**=```${TMPFOLDER}```. Carpeta en la que se crearán los archivos que se precisen 
   durante la ejecucion del test. Debe tener permiso de escritura en ella.
   
2. ${check} **REPOURL**=```${REPOURL}```. Url en la que se está ejecutando el 
   servidor de VCSGis a usar en la copia de trabajo.

3. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia de trabajo que se va a crear así como 
   de la conexión a la base de datos de la copia de trabajo. 

### Pasos

1. ${check} Al iniciarse este procedimiento deberá estar abierta la venta de inicialización de copias de 
   trabajo de título "Inicializar copia de trabajo" y deberá estar activa.

2. ${check} Marque la opción de "Repositorio remoto".

3. ${check} En el campo "URL" introduzca el valor ```${REPOURL}``` (REPOURL). 

4. ${check} Marque la opción de "Base de datos personal (H2Spatial)

5. ${check} Pulse el botón asociado al campo "Fichero" y aparecerá el diálogo de selección de ficheros.
   
6. ${check} Navegue a la carpeta ```${TMPFOLDER}``` (TMPFOLDER), indique como nombre 
   de fichero  ```${WORKINGCOPY}``` (WORKINGCOPY) y pulse el botón "Abrir".
   Se cerrará el diálogo de selección de fichero y volverá al diálogo de "Inicializar copia de trabajo".
   
7. ${check} En el campo "Nombre" deberá haber aparecido el valor ```${WORKINGCOPY}```.

8. ${check} Pulse el botón "Inicializar copia de trabajo".

9. ${check} Se deberá cerrar la ventana sin presentar ningún mensaje de error,
   ni en ventanas ni en la barra de mensajes de gvSIG desktop.

10. ${check} Abra un explorador de archivos del sistema y compruebe que se ha creado el archivo 
    ```${TMPFOLDER}/${WORKINGCOPY}.mv.db``` (TMPFOLDER/WORKINGCOPY.mv.db)
    en el sistema de archivos.

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

Si se produce un error repórtelo en el test que está ejecutando.

{% include es/footer.html %}
