---
title: Inicializar un repositorio en H2 con la autorización acivada
proccode: VC00PROC004
srcpath: "casos/VC00/PROC/004/procVC00PROC004.md"
---

**EN CONSTRUCCION**

{% include es/header.md %}

## {{ page.title }}

### Descripción

Este proceso inicializa un repositorio VCSGis sobre una base de datos nueva de H2.
Una vez creado el repositorio se activara la autenticacion y autorizacion sobre el y se crearan
dos usuarios:
* "sara", de clave "sara1", con todos los permisos activados (opcion por defecto).
* "pedro", de clave "pedro1", sin permiso de "commit".

En el proceso se creara la conexion a la base de datos que va a usarse para acceder al repositorio.

### Datos de entrada

1. ${check} **TMPFOLDER**=```${TMPFOLDER}```. Carpeta en la que se creara los archivos que se precisen 
   durante la ejecucion del test. Deberemos tener  permiso de escritura en ella.

2. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexion a crear.


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
   ```${TMPFOLDER}/${REPONAME}.mv.db``` (TMPFOLDER/REPONAME.mv.db)
   en el sistema de archivos.
   
 **FIXME**:Continuar aqui con la explicacion de:
   * Conectarse al espacio de trabajo de base de datos
   * Abrir la tabla de configuracion del repositorio y activar la autentcacion y autorizacion (usar VC00PROC009, alta de una variable)
   * Abrir la tabla de usuarios del repo y dar de alta los dos usuarios (usar VC00PROC010, alta de un usuario)
   * acabar cerrando gvSIG y volviendo a abrirlo.

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
