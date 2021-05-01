---
title: Creacion de un repositorio en H2
testcode: VC00PROC001
srcpath: "casos/VC00/PROC/001/procVC00PROC001.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Crea un repositorio VCSGis sobre una base de datos nueva de H2.
En el proceso se creara la conexion a la base de datos que va a usarse para acceder al repositorio.

### Datos de entrada

1. ${check} **TMPFOLDER**="${TMPFOLDER}". Carpeta en la que se creara los archivos que se precisen 
   durante la ejecucion del test. Deberemos tener  permiso de escritura en ella.

2. ${check} **REPONAME**="${REPONAME}". Nombre de la conexion a crear.


### Pasos

1. ${check} Cuando iniciemos este procedimiento deberems estar viendo
   la ventana de creacion de repositorio, con titulo "Inicializar repositorio" y estara activa.

2. ${check} Pulsaremos en el boton asociado al campo "Conexión" para crear la conexion a la base de datos.

3. ${check} Seguiremos los pasos de [Creacion de una conexion a base de datos H2](../../PROC/000/procVC00PROC000.html?NAME=${REPONAME}&PATHNAME=${TMPFOLDER}/${REPONAME}) 

5. ${check} Una vez creada la conexion a la base de datos, habremos vuelto a la ventana de titulo "Inicializar repositorio".
   Pulsaremos el boton "Inicializar repositorio".

5. ${check} Se cerrara la ventana de inicializacion del repositorio y no debe aparecer ningun mensaje de error, ni en
   ventanas ni en la barra de mensajes de gvSIG desktop.
   
7. ${check} Abriremos el explorador de archivos del sistema y comprobaremos que se ha creado el archivo 
   "${TMPFOLDER}/${REPONAME}.mv.db" (TMPFOLDER/REPONAME.mv.db)
   en el sistema de archivos.

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

Si se produce un error reportelo en el test que esta ejecutando.

{% include es/footer.html %}
