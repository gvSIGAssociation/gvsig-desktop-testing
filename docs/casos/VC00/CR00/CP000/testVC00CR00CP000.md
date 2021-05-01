---
title: Creacion de un repositorio en una base de datos H2
testcode: VC00CR00CP000
srcpath: "casos/VC00/CR00/CP000/testVC00CR00CP000.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Crea un repositorio VCSGis sobre una base de datos nueva de H2.
En el proceso se creara la conexion a la base de datos que va a usarse para acceder al repositorio.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. **TMPFOLDER**="/tmp". Carpeta en la que se disponga de acceso para escritura donde
   se crearan los archivos necesarios durante la ejecucion del test.

### Prerrequisitos

1. Un gvSIG desktop instalado y funcional cuya version sea la indicada en el plan de pruebas.
2. El complemento de VCSGis debe estar instalado y activo.

### Pasos

1. Antes de iniciar gvSIG desktop comprobaremos que no existe el fichero "*TMPFOLDER*/Repositorio.mv.db", 
   y en caso de exista lo eliminaremos.
2. Iniciaremos gvSIG desktop.
3. Una vez iniciado seleccionaremos la opcion de menu "Herramientas/VCSGis/Administracion/????" que nos
   presentara la ventana de titulo "??????".
5. Seguiremos los pasos de [VC00LB00PR001 Creacion de un repositorio de H2](../../LB00/PR0001_create_repo_h2/definition.md) 
   usando NAME="Repositorio" y PATHNAME="*TMPFOLDER*/Repositorio.mv.db"

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}



