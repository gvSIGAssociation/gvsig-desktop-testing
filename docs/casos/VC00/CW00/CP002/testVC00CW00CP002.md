---
title: Inicializacion de una copia de trabajo (repositorio remoto en H2 con autorización)
testcode: VC00CW00CP002
srcpath: "casos/VC00/CW00/CP002/testVC00CW00CP002.md"
---

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="REPONAME" value="Repositorio" %}

{% include parameter.html name="WCNAME" value="CopiaDeTrabajo" %}

## {{ page.title }}

### Descripción

Inicializa una copia de trabajo asociada a un repositorio remoto basado en H2.
En el proceso se creara la conexion a la base de datos que va a usarse para acceder 
a la copia de trabajo.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. ${check} **TMPFOLDER**=```${TMPFOLDER}```. Carpeta en la que se creara los archivos que se precisen 
   durante la ejecucion del test. Deberemos tener  permiso de escritura en ella.

1. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia de trabajo que se va a crear asi como 
   de la conexion a la base de datos de la copia de trabajo. 

### Prerrequisitos

1. Un gvSIG desktop instalado y funcional cuya version sea la indicada en el plan de pruebas.
2. El complemento de VCSGis debe estar instalado y activo.
3. Antes de pasar este caso de prueba deben de haber pasado los siguientes casos de prueba:
   * [VC00CR00CP002 Iniciar un servidor VCSGis contra un repositorio en una base de datos H2 (con autorización)](../../CR00/CP002/VC00CR00CP002.html?TMPFOLDER=${TMPFOLDER}&REPONAME=${REPONAME}).

### Pasos

1. ${check} seguiremos los pasos indicados en el caso de prueba:
   * [VC00CR00CP002 Iniciar un servidor VCSGis contra un repositorio en una base de datos H2 (con autorización)](../../CR00/CP002/VC00CR00CP002.html?TMPFOLDER=${TMPFOLDER}&REPONAME=${REPONAME}).

3. ${check} Antes de iniciar gvSIG desktop comprobaremos que no existan los ficheros:
   * ```${TMPFOLDER}/${WCNAME}.mv.db``` (*TMPFOLDER*/*WCNAME*.mv.db).
   
   En caso de que existan los eliminaremos.
   
2. ${check} Iniciaremos gvSIG desktop a partir de la portabla para el ```Cliente```.

4. ${check} Seleccionaremos la opcion de menu "Herramientas/VCSGis/Administración/Inicializar repositorio" 
   que nos presentara la ventana de titulo "Inicializar repositorio".

5. ${check} Seguiremos los pasos de [Inicializar un repositorio en H2 (con autorización)](../../PROC/004/procVC00PROC004.html?TMPFOLDER=${TMPFOLDER}&REPONAME=${REPONAME})

7. ${check} Tras la creacion del repositorio, seleccionaremos la opcion de menu 
   "Herramientas/VCSGis/Inicializar copia de trabajo" que nos presentara la ventana de 
   titulo "Inicializar copia de trabajo".

7. ${check} Seguiremos los pasos de [Inicialización de una copia de trabajo asociada a un repositorio remoto](../../PROC/002/procVC00PROC002.html?TMPFOLDER=${TMPFOLDER}&REPONAME=${REPONAME}&WCNAME=${WCNAME}) 

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
