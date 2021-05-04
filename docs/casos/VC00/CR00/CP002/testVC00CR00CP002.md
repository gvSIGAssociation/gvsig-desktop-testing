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
En el repositorio estara activa la autenticacion y autorizacion sobre el y existiran
dos usuarios:
* "sara", de clave "sara1", con todos los permisos activados (opcion por defecto).
* "pedro", de clave "pedro1", sin permiso de "commit".

Durante la ejecucion del caso de prueba se creara la conexion a la base de datos que va a usarse 
para acceder al repositorio.

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
   
2. ${check} Iniciaremos gvSIG desktop a partir de la version portabla ```Servidor```.

3. ${check} Una vez iniciado seleccionaremos la opcion de menu "Herramientas/VCSGis/Administracion/Inicializar repositorio" que nos
   presentara la ventana de titulo "Inicializar repositorio".

4. ${check} Seguiremos los pasos de [Inicializar un repositorio en H2 con autorizacion activada](../../PROC/004/procVC00PROC004.html?TMPFOLDER=${TMPFOLDER}&REPONAME=${REPONAME})

5. Pulsaremos la opcion de menu "HerramientasVCSGis/Administración/Servidor VCSGis". Al hacerlo aparecera 
   una ventana de titulo "Servidor VCSGis".

6. En el desplegable asociado al campo "Base de datos" debera existir la opcion ```${REPONAME}```, la seleccionaremos.

7. Pulsaremos en el boton "Reiniciar" y maximizaremos la ventana.

8. En el cuadro de texto "Mensajes" habra aparecido algo como:
   ```
   2021-05-04 09:23:50.839 - Creating server...
   2021-05-04 09:23:50.939 - Starting server with repository jdbc:h2:file:/home/jjdelcerro/dbs/test1;MODE=PostgreSQL;SCHEMA=PUBLIC;ALLOW_LITERALS=ALL...

   ```
   
   Pueden cambiar las fechas y las rutas que aparezcan.
   
### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}

