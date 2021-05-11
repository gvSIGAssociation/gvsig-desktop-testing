---
title: Iniciar un servidor VCSGis contra un repositorio en una base de datos H2 (con autorización)
testcode: VC00CR00CP002
srcpath: "casos/VC00/CR00/CP002/testVC00CR00CP002.md"
---

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="REPONAME" value="RepositorioAuth" %}

## {{ page.title }}

### Descripción

Inicializa un repositorio VCSGis sobre una base de datos nueva de H2 e inicia el servidor 
de VCSGis que hay empotrado en gvSIG desktop.
Como resultado de ejecutar el caso de prueba en el repositorio quedará activa la autenticación
y autorización, y tendremos creados dos usuarios:
* "sara", de clave "sara1", con todos los permisos activados (opción por defecto).
* "pedro", de clave "pedro1", sin permiso de "commit".

Durante la ejecución del caso de prueba se creara la conexion a la base de datos que va a usarse 
para acceder al repositorio.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. ${check} **TMPFOLDER**=```${TMPFOLDER}```. Carpeta en la que se crearan los archivos que se precisen 
   durante la ejecución del caso de prueba. Deberemos tener permiso de escritura en ella.

2. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexión a crear asociada al repositorio.

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional para ser usado como ```Servidor``` de la versión indicada
   en el plan de pruebas.

3. ${check} El complemento de VCSGis debe estar instalado y activo.

### Pasos

1. ${check} Comprobaremos que no este iniciado gvSIG desktop a partir de la portable 
   para el ```Servidor```. Si lo esta deberiamos cerrarlo.
   
2. ${check} Antes de iniciar gvSIG desktop comprobaremos que no exista el fichero:
   * ```${TMPFOLDER}/${REPONAME}.mv.db``` (TMPFOLDER/REPONAME.mv.db).
   
   En caso de que exista lo eliminaremos.
   
3. ${check} Iniciaremos gvSIG desktop a partir de la portable para el ```Servidor```.

4. ${check} Una vez iniciado seleccionaremos la opción de menú "Herramientas/VCSGis/Administracion/Inicializar repositorio" que nos
   presenta la ventana de título "Inicializar repositorio".

5. ${check} Seguiremos los pasos de [Inicializar un repositorio en H2](../../PROC/004/procVC00PROC004.html?TMPFOLDER=${TMPFOLDER}&REPONAME=${REPONAME})

6. ${check} Pulsaremos la opción de menú "Herramientas/VCSGis/Administración/Servidor VCSGis". Al hacerlo aparecerá 
   una ventana de título "Servidor VCSGis".

7. ${check} En el desplegable asociado al campo "Base de datos" debera existir la opción ```${REPONAME}```, la seleccionaremos.

8. ${check} Pulsaremos en el boton "Reiniciar" y maximizaremos la ventana.

9. ${check} En el cuadro de texto "Mensajes" habrá aparecido algo como:
   ```
   2021-05-04 09:23:50.839 - Creating server...
   2021-05-04 09:23:50.939 - Starting server with repository jdbc:h2:file:${TMPFOLDER}/${REPONAME};MODE=PostgreSQL;SCHEMA=PUBLIC;ALLOW_LITERALS=ALL...

   ```
   
   Pueden cambiar las fechas y las rutas que aparezcan.

10.  Iconice la ventana de la aplicacion gvSIG desktop usada como ```Servidor```.

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}

