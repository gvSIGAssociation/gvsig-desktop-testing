---
title: Exportar una capa a una fecha dada (repositorio remoto con autorización).
proccode: VC00EX00CP005
srcpath: "casos/VC00/EX00/CP005/testVC00EX00CP005.md"
---

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="REPOURL" value="http://127.0.0.1:9810" %}

{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo2" %}

{% include parameter.html name="TABLENAME" value="esp_provincias" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}

{% include parameter.html name="DATE0" value="3/5/21" %}

{% include parameter.html name="DATE1" value="5/5/21" %}

{% include parameter.html name="EXPORTTABLENAME0" value="ESP_PROVINCIAS_20210503_000000_0" %}

{% include parameter.html name="EXPORTTABLENAME1" value="ESP_PROVINCIAS_20210505_000000_0" %}


## {{ page.title }}

### Descripción

Este caso de prueba verifica que se puede exportar una capa de un repositorio en una copia de trabajo. Para ello:
* Inicializa una nueva copia de trabajo
* Exporta una capa del repositorio sobre la copia de trabajo.

Si la base de datos que se va a utilizar asociada a la copia de 
trabajo existe se eliminará y se volverá a crear, así como la conexión.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. ${check} **TMPFOLDER**="/tmp". Carpeta en la que se disponga de acceso para escritura donde
   se crearán los archivos necesarios durante la ejecucion del test.

1. ${check} **REPOURL**=```${REPOURL}```. Dirección donde esta el servidor del repositorio a usar.

1. ${check} **WORKINGCOPY**=```${WORKINGCOPY}``` a usar en este test. 

1. ${check} **TABLENAME**=```${TABLENAME}``` a usar en este test. 

1. ${check} **USER**=```${USER}```. Identificador de usuario.

1. ${check} **PASSWORD**=```${PASSWORD}```. Contraseña de usuario.

1. ${check} **DATE0**=```3/5/21```. Primera fecha a exportar

1. ${check} **DATE1**=```5/5/21```. Segunda fecha a exportar

[//]: # (9. ${check} **EXPORTTABLENAME0**=```ESP_PROVINCIAS_20210503_000000_0```. Nombre de la primera tabla exportada)

[//]: # (10. ${check} **EXPORTTABLENAME1**=```ESP_PROVINCIAS_20210505_000000_0```. Nombre de la segunda tabla exportada)

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya versión sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} El caso de prueba [VC00TP00CP003, "Subir cambios en una capa con un plan topológico (que sí pasen el plan)"](../../TP00/CP003/testVC00TP00CP003.md),
   ha pasado sin errores. 

### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas 
   [VC00TP00CP003, "Subir cambios en una capa con un plan topológico (que sí pasen el plan)"](../../TP00/CP003/testVC00TP00CP003.md), 
   continúe con el siguiente paso, si no, ejecútelo antes de continuar. 
   
2. ${check} Compruebe que no exista el fichero:
   * ```${TMPFOLDER}/${WORKINGCOPY}.mv.db``` (TMPFOLDER/WORKINGCOPY.mv.db).
   En caso de que exista debera:
   * ${check} Cerrar gvSIG desktop ```Cliente```.
   * ${check} Elimínar el fichero ```${TMPFOLDER}/${WORKINGCOPY}.mv.db``` (TMPFOLDER/WORKINGCOPY.mv.db).
   * ${check} Iniciar gvSIG desktop ```Cliente```.

3. ${check} Elimine el registro de la copia de trabajo ```${WORKINGCOPY}``` en caso de que existise.
   Para ello siga los pasos indicados en 
   [eliminar copia local del registro](../../PROC/019/procVC00PROC019.html?&WORKINGCOPY=${WORKINGCOPY})

4. ${check} Compruebe que la vista que se ha creado al arrancar gvSIG se encuentra en "EPSG:4326", de no ser así cambie la proyección de la vista.
   
5. ${check} Inicialice una nueva copia de trabajo para ello seleccione la opción de 
   menú "Herramientas/VCSGis/Inicializar copia de trabajo" y siga los pasos de 
   [inicialización de una copia de trabajo](../../PROC/008/procVC00PROC008.html?TMPFOLDER=${TMPFOLDER}&REPOURL=${REPOURL}&WORKINGCOPY=${WORKINGCOPY})

7. ${check} Seleccione la opción de menu "Herramientas/VCSGis/Exportar" que presentará la ventana de titulo "Exportar".

8. ${check} Siga los pasos de [exportar una capa a una fecha concreta](../../PROC/015/procVC00PROC015.html?WORKINGCOPY=${WORKINGCOPY}&TABLENAME=${TABLENAME}&USER=${USER}&PASSWORD=${PASSWORD}&DATE=${DATE0}&EXPORTTABLENAME=${EXPORTTABLENAME0})

9. ${check} Cierre el cuadro de diálogo "Exportar".

10. ${check} En la vista se habrá añadido la capa ```${EXPORTTABLENAME0}```(EXPORTTABLENAME0) en el estado de la revisión ${REVISION0}.

11. ${check} Elimine la capa ```${EXPORTTABLENAME0}```(EXPORTTABLENAME0) de la vista pulsando con el botón secundario del ratón sobre la capa en el TOC y seleccionando "Eliminar capa".

12. ${check} Aparecerá un diálogo de confirmación que le preguntará "¿Está seguro de que desea borrar las capas activas?". Pulse el botón "Sí".

12. ${check} Seleccione la opción de menu "Herramientas/VCSGis/Exportar" que presentara la ventana de titulo "Exportar".

13. ${check} Siga los pasos de [Exportar una capa a una fecha concreta](../../PROC/016/procVC00PROC016.html?WORKINGCOPY=${WORKINGCOPY}&TABLENAME=${TABLENAME}&USER=${USER}&PASSWORD=${PASSWORD}&DATE=${DATE1}&EXPORTTABLENAME=${EXPORTTABLENAME1})

14. ${check} Cierre el cuadro de diálogo "Exportar".

15. ${check} En la vista se habrá añadido la capa ```${EXPORTTABLENAME1}```(EXPORTTABLENAME1) en el estado de la revisión ${REVISION1}.


### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}


