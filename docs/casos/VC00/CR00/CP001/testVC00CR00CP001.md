---
title: Inicializacion de un repositorio en una base de datos H2
testcode: VC00CR00CP000
srcpath: "casos/VC00/CR00/CP000/testVC00CR00CP000.md"
---

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}
{% include parameter.html name="REPONAME" value="RepositorioAuth" %}

## {{ page.title }}

### Descripción

Inicializa un repositorio VCSGis sobre una base de datos nueva de H2.
Una vez creado el repositorio se activara la autenticacion y autorizacion sobre el y se crearan
dos usuarios:
* "sara", de clave "sara1", con todos los permisos activados (opcion por defecto).
* "pedro", de clave "pedro1", sin permiso de "commit".

En el proceso se creara la conexion a la base de datos que va a usarse para acceder al repositorio.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. ${check} **TMPFOLDER**=```${TMPFOLDER}```. Carpeta en la que se creara los archivos que se precisen 
   durante la ejecucion del test. Deberemos tener  permiso de escritura en ella.

2. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexion a crear asociada al repositorio.

### Prerrequisitos

1. Un gvSIG desktop instalado y funcional cuya version sea la indicada en el plan de pruebas.
2. El complemento de VCSGis debe estar instalado y activo.

### Pasos

1. ${check} Antes de iniciar gvSIG desktop comprobaremos que no existan los ficheros:
   * ```${TMPFOLDER}/${REPONAME}.mv.db``` (TMPFOLDER/REPONAME.mv.db).
   
   En caso de que exista lo eliminaremos.
   
2. ${check} Iniciaremos gvSIG desktop.

3. ${check} Una vez iniciado seleccionaremos la opcion de menu "Herramientas/VCSGis/Administracion/Inicializar repositorio" que nos
   presentara la ventana de titulo "Inicializar repositorio".

4. ${check} Seguiremos los pasos de [Inicializar un repositorio en H2 con autorizacion activada](../../PROC/004/procVC00PROC004.html?TMPFOLDER=${TMPFOLDER}&REPONAME=${REPONAME})

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}

