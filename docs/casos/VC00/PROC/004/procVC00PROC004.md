---
title: Crear un repositorio sobre una base de datos H2 (con autorización)
proccode: VC00PROC004
srcpath: "casos/VC00/PROC/004/procVC00PROC004.md"
---

**EN CONSTRUCCION**

{% include es/header.md %}

{% include parameter.html name="CONFIGTABLENAME" value="VCSGISREPO_CONFIG" %}

{% include parameter.html name="USERSTABLENAME" value="VCSGISREPO_USERS" %}


## {{ page.title }}

### Descripción

Este proceso crea e inicializa un repositorio VCSGis sobre una base de datos nueva de H2.
Una vez creado el repositorio se activará la autenticación y autorización sobre el y se crearán
dos usuarios:
* "sara", de clave "sara1", con todos los permisos activados (opción por defecto).
* "pedro", de clave "pedro1", sin permiso de "commit".

En el proceso se creará la conexión a la base de datos que va a usarse para acceder al repositorio.

### Datos de entrada

1. ${check} **TMPFOLDER**=```${TMPFOLDER}```. Carpeta en la que se crearán los archivos que se precisen 
   durante la ejecución del test. Deberemos tener permiso de escritura en ella.

2. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexión a crear y del repositorio.


### Pasos
1. ${check} Para inicial el proceso de crear el repositorio diríjase a la pestaña "Herramientas".

2. ${check} Seleccione del despeglable la opción "VCSGis". 

3. ${check} Seleccione la opción "Administración".

4. ${check} Pulse la opción "Inicializar repositorio".

5. ${check} Cuando se inicia este procedimiento se debe ver la ventana de creación de repositorio,
   con título "Inicializar repositorio" y esta estará activa.

6. ${check} Pulse el botón asociado al campo "Conexión" para crear la conexion a la base de datos. Este se situa en
   adyacente al desplegable que indica las diferentes conexiones.

7. ${check} Siga los pasos de [Creación de una conexión a base de datos H2](../../PROC/000/procVC00PROC000.html?NAME=${REPONAME}&PATHNAME=${TMPFOLDER}/${REPONAME}) 

8. ${check} Una vez creada la conexión a la base de datos, de nuevo en la ventana de título "Inicializar repositorio",
   pulse el botón "Inicializar repositorio". 
   
9. ${check}Tras lo anterior, se cierra la ventana de inicialización del repositorio
   y no debe aparecer ningun mensaje de error, ni en ventanas, ni en la barra de mensajes de gvSIG desktop.
   
10. ${check} Abra el explorador de archivos del sistema y compruebe que se ha creado el archivo 
   ```${TMPFOLDER}/${REPONAME}.mv.db``` (TMPFOLDER/REPONAME.mv.db) en el sistema de archivos.

11. ${check} Una vez creado el repositorio tiene que realizarse la configuración de este. Para inicial el proceso 
   de configuración del repositorio diríjase a la pestaña "Archivo".

12. ${check} Seleccione la opción "Connect to database workspase".

13. ${check} Tras lo anterior, se muestra una ventana de diálogo titulada "Connect".

14. ${check} En el desplegable "Conection" seleccione la conexión llamada ```${REPONAME}```.

15. ${check} Pulse el botón "Connect".

16. ${check} Tras lo anterior, se cierra la ventana que realiza la conexión al espacio de trabajo de la base de datos
   y no debe aparecer ningun mensaje de error, ni en ventanas, ni en la barra de mensajes de gvSIG desktop.

17. ${check} Abra la tabla de configuración del repositorio, ```${CONFIGTABLENAME}```. Siga los pasos de 
    [Abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?BBDD=${REPONAME}&TABLENAME=${CONFIGTABLENAME})

18. ${check} Vamos a crear un registro para activar la autenticación. Siga los pasos de 
    [Alta de una variable](../../PROC/009/procVC00PROC009.html?VARIABLE=AUTHENTICATION&VALUE=true)

19. ${check} Vamos a crear un registro para activar la autorización. Siga los pasos de 
    [Alta de una variable](../../PROC/009/procVC00PROC009.html?VARIABLE=AUTHORIZATION&VALUE=true)

20. ${check} Abra la tabla de usuarios del repositorio, ```${USERSTABLENAME}```. Siga los pasos de 
    [Abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?BBDD=${REPONAME}&TABLENAME=${USERSTABLENAME})

21. ${check} Vamos a dar de alta el usuario "pedro" con todos los permisos excepto el de "commit". Siga los pasos de 
    [Alta de un usuario](../../PROC/010/procVC00PROC010.html?NAME=pedro&PASSWORD=pedro1&OPERATIONS=add,entities,update,checkout,history,topologyplan,users)

22. ${check} Vamos a dar de alta el usuario "sara" con todos los permisos. Siga los pasos de 
    [Alta de un usuario](../../PROC/010/procVC00PROC010.html?NAME=sara&PASSWORD=sara1&OPERATIONS=add,entities,commit,update,checkout,history,topologyplan,users)

23. ${check} Reinicie gvSIG Desktop para que los cambios tengan efecto.


### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
