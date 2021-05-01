---
title: Creacion de una copia de trabajo de un repositorio local en H2
testcode: VC00CW00CP000
srcpath: "casos/VC00/CW00/CP000/testVC00CW00CP000.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Crearemos una copia local asociada a un repositorio local basado en H2.
En el proceso se creara la conexion a la base de datos que va a usarse para acceder al repositorio y
otra para acceder a la copia local.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. **TMPFOLDER**, una carpeta en la que se disponga de acceso para escritura, por defecto "/tmp"
2. **REPONAME**, nombre de la conexion a crear asociada al repositorio, por defecto "Repositorio"
2. **WCNAME**, nombre de la conexion a crear asociada a la copia local, por defecto "workingcopy"

### Prerrequisitos

1. Un gvSIG desktop instalado y funcional cuya version sea la indicada en el plan de pruebas.
2. El complemento de VCSGis debe estar instalado y activo.

### Pasos

1. Antes de iniciar gvSIG desktop comprobaremos que no existan los ficheros "<TMPFOLDER>/<REPONAME>.mv.db" y
   "<TMPFOLDER>/<WCNAME>.mv.db" y en caso de que existan los eliminaremos.
2. Iniciaremos gvSIG desktop.
3. Una vez iniciado seleccionaremos la opcion de menu "Herramientas/VCSGis/Administracion/????" que nos
   presentara la ventana de titulo "??????".
4. Seguiremos los pasos de [VC00LB00PR002 Creacion de una copia local de un repositorio local en H2](../../LB00/PR002_create_dbconnection/definition.md) 
   usando TMPFOLDER, REPONAME y WCNAME

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

