---
title: Inicialización de una copia de trabajo (repositorio remoto con autorización)
testcode: VC00CW00CP002
srcpath: "casos/VC00/CW00/CP002/testVC00CW00CP002.md"
---

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo" %}

{% include parameter.html name="REPOURL" value="http://127.0.0.1:9810" %}

## {{ page.title }}

### Descripción

Inicializa una copia de trabajo asociada a un repositorio remoto en el que está activa la autorización.
En el proceso se creará la conexión a la base de datos que va a usarse para acceder 
a la copia de trabajo.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. ${check} **TMPFOLDER**=```${TMPFOLDER}```. Carpeta en la que se crearán los archivos que se precisen 
   durante la ejecución del test. Deberá tener permiso de escritura en ella.

1. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia de trabajo que se va a crear así como de la conexión a la base de datos de la copia de trabajo. 

### Prerrequisitos

1. Un gvSIG desktop instalado y funcional cuya versión sea la indicada en el plan de pruebas.

2. El complemento de VCSGis debe estar instalado y activo.

3. Antes de pasar este caso de prueba deben de haber pasado el caso de prueba "Iniciar servidor" del plan de pruebas.

### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas "Iniciar servidor" del plan de pruebas pasa el paso 2, en caso
   contrario ejecútelo antes de continuar.

2. ${check} Compruebe que no exista el fichero:
   * ```${TMPFOLDER}/${WORKINGCOPY}.mv.db``` (*TMPFOLDER*/*WCNAME*.mv.db).
   En caso de que exista elimínelo.
   
3. ${check} Inicie gvSIG desktop a partir de la portable para el ```Cliente```.

4. ${check} Seleccione la opción de menú "Herramientas/VCSGis/Inicializar copia de trabajo".

5. ${check} Siga los pasos de [inicialización de una copia de trabajo](../../PROC/008/procVC00PROC008.html?TMPFOLDER=${TMPFOLDER}&REPOURL=${REPOURL}&WORKINGCOPY=${WORKINGCOPY}) 

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
