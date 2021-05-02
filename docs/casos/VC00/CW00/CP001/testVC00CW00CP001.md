---
title: Inicializacion de una copia de trabajo (repositorio local en H2 con autorización)
testcode: VC00CW00CP001
srcpath: "casos/VC00/CW00/CP001/testVC00CW00CP001.md"
---

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="REPONAME" value="Repositorio" %}

{% include parameter.html name="WCNAME" value="CopiaDeTrabajo" %}

## {{ page.title }}

### Descripción

Inicializa una copia de trabajo asociada a un repositorio local basado en H2.
En el proceso se creara la conexion a la base de datos que va a usarse para acceder al repositorio y
otra para acceder a la copia de trabajo.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. ${check} **TMPFOLDER**=```${TMPFOLDER}```. Carpeta en la que se creara los archivos que se precisen 
   durante la ejecucion del test. Deberemos tener  permiso de escritura en ella.

2. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexion a crear asociada al repositorio.

3. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia de trabajo que se va a crear asi como 
   de la conexion a la base de datos de la copia de trabajo. 

### Prerrequisitos

1. Un gvSIG desktop instalado y funcional cuya version sea la indicada en el plan de pruebas.
2. El complemento de VCSGis debe estar instalado y activo.
3. Antes de pasar este caso de prueba deben de haber pasado los siguientes casos de prueba:
   * [VC00CR00CP001](../../CR00/CP001/testVC00CR00CP001.md) 

### Pasos
1. ${check} Antes de iniciar gvSIG desktop comprobaremos que no existan los ficheros:
   * ```${TMPFOLDER}/${REPONAME}.mv.db``` (*TMPFOLDER*/*REPONAME*.mv.db).
   * ```${TMPFOLDER}/${WCNAME}.mv.db``` (*TMPFOLDER*/*WCNAME*.mv.db).
   
   En caso de que existan los eliminaremos.
   
2. ${check} Iniciaremos gvSIG desktop.

4. ${check} Seleccionaremos la opcion de menu "Herramientas/VCSGis/Administración/Inicializar repositorio" 
   que nos presentara la ventana de titulo "Inicializar repositorio".

5. ${check} Seguiremos los pasos de [Inicializar un repositorio en H2 (con autorización)](../../PROC/004/procVC00PROC004.html?TMPFOLDER=${TMPFOLDER}&REPONAME=${REPONAME})

7. ${check} Tras la creacion del repositorio, seleccionaremos la opcion de menu 
   "Herramientas/VCSGis/Inicializar copia de trabajo" que nos presentara la ventana de 
   titulo "Inicializar copia de trabajo".

7. ${check} Seguiremos los pasos de [Inicialización de una copia de trabajo asociada a un repositorio local en H2](../../PROC/002/procVC00PROC002.html?TMPFOLDER=${TMPFOLDER}&REPONAME=${REPONAME}&WCNAME=${WCNAME}) 

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
