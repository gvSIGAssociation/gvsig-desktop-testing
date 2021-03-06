---
title: Obtener una revision concreta de una capa (repositorio remoto con autorización).
proccode: VC00CO00CP005
srcpath: "casos/VC00/CP005/testVC00CO00CP005.md"
---

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="REPOURL" value="http://127.0.0.1:9810" %}

{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo2" %}

{% include parameter.html name="TABLENAME" value="esp_provincias" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}

{% include parameter.html name="REVISION0" value="0" %}

{% include parameter.html name="REVISION1" value="3" %}

## {{ page.title }}

### Descripción

Este caso de prueba verifica que se puede obtener una capa de un repositorio en una copia de trabajo nueva. Para ello:
* Inicializa una nueva copia de trabajo
* Descarga una capa (checkout) del repositorio sobre la copia de trabajo.

Si la base de datos que se va a utilizar asociada a la copia de 
trabajo existe se eliminará y se volverá a crear, asi como la conexión.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. ${check} **TMPFOLDER**="/tmp". Carpeta en la que se disponga de acceso para escritura donde
   se crearan los archivos necesarios durante la ejecucion del test.

2. ${check} **REPOURL**=```${REPOURL}```. Direccion donde esta el servidor del repopsiyotio a usar.

3. ${check} **WORKINGCOPY**=```${WORKINGCOPY}``` a usar en este test. 

4. ${check} **TABLENAME**=```${TABLENAME}``` a usar en este test. 

5. ${check} **USER**=```${USER}```. Identificador de usuario.

6. ${check} **PASSWORD**=```${PASSWORD}```. Contraseña de usuario.

7. ${check} **REVISION0**=```0```. Primera revisión a descargar

8. ${check} **REVISION1**=```3```. Segunda revisión a descargar

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya version sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} El caso de prueba [VC00TP00CP003, "Subir cambios en una capa con un plan topológico (que sí pasen el plan)"](../../TP00/CP003/testVC00TP00CP003.md),
   ha pasado sin errores. 

### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas 
   [VC00TP00CP003, subir cambios en una capa con un plan topológico (que sí pasen el plan)](../../TP00/CP003/testVC00TP00CP003.md), 
   continúe con el siguiente paso, si no, ejecútelo antes de continuar. 
   
2. ${check} Compruebe que no exista el fichero:
   * ```${TMPFOLDER}/${WORKINGCOPY}.mv.db``` (TMPFOLDER/WORKINGCOPY.mv.db).
   En caso de que exista debera:
   * ${check} Cerrar gvSIG desktop ```Cliente```.
   * ${check} Elimínar el fichero ```${TMPFOLDER}/${WORKINGCOPY}.mv.db``` (TMPFOLDER/WORKINGCOPY.mv.db).
   * ${check} Iniciar gvSIG desktop ```Cliente```.

3. ${check} Elimine el registro de la copia de trabajo ```${WORKINGCOPY}``` en caso de que existiese.
   Para ello siga los pasos indicados en 
   [eliminar copia local del registro](../../PROC/019/procVC00PROC019.html?&WORKINGCOPY=${WORKINGCOPY})

4. ${check} Compruebe que la vista que se ha creado al arrancar gvSIG se encuentra en "EPSG:4326", de no ser asi cambie la proyección de la vista.

5. ${check} Inicialice una nueva copia de trabajo para ello seleccione la opción de 
   menu "Herramientas/VCSGis/Inicializar copia de trabajo" y siga los pasos de 
   [inicializacion de una copia de trabajo](../../PROC/008/procVC00PROC008.html?TMPFOLDER=${TMPFOLDER}&REPOURL=${REPOURL}&WORKINGCOPY=${WORKINGCOPY})

7. ${check} Seleccione la opción de menu "Herramientas/VCSGis/Obtener copia local (checkout)" que nos presentara la ventana de titulo "Obtener copia local (checkout)".

8. ${check} Siga los pasos de [obtención de una revisión de una capa desde repositorio](../../PROC/013/procVC00PROC013.html?WORKINGCOPY=${WORKINGCOPY}&TABLENAME=${TABLENAME}&USER=${USER}&PASSWORD=${PASSWORD}&REVISION=${REVISION0}&OVERWRITE=no)

9. ${check} Cierre el cuadro de diálogo "Obtener copia local (checkout)".

10. ${check} En la vista se habrá añadido la capa ```${TABLENAME}```(TABLENAME) en el estado de la revisión ${REVISION0}.

11. ${check} Elimine la capa ```${TABLENAME}```(TABLENAME) de la vista pulsando con el botón secundario del ratón sobre la capa en el TOC y seleccionando "Eliminar capa".

12. Aparecerá un diálogo de confirmación que le preguntará "¿Está seguro de que desea borrar las capas activas?". Pulse el botón "Sí".

12. ${check} Seleccione la opción de menú "Herramientas/VCSGis/Obtener copia local (checkout)" que presentará la ventana de titulo "Obtener copia local (checkout)".

13. ${check} Siga los pasos de [obtención de una revisión de una capa desde repositorio](../../PROC/012/procVC00PROC012.html?WORKINGCOPY=${WORKINGCOPY}&TABLENAME=${TABLENAME}&USER=${USER}&PASSWORD=${PASSWORD}&REVISION=${REVISION1}&OVERWRITE=sí)

14. ${check} Cierre el cuadro de diálogo "Obtener copia local (checkout)".

15. ${check} En la vista se habrá añadido la capa ```${TABLENAME}```(TABLENAME) en el estado de la revisión ${REVISION1}.

16. ${check} Cierre la vista.

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}

