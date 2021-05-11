---
title: Exportar una revision concreta de una capa (repositorio remoto con autorización).
proccode: VC00EX00CP002
srcpath: "casos/VC00/EX00/CP002/testVC00EX00CP002.md"
---

**--- EN CONSTRUCCIÓN ---**

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="REPONAME" value="Repositorio" %}

{% include parameter.html name="WCNAME2" value="CopiaDeTrabajo2" %}

{% include parameter.html name="TABLENAME" value="esp_provincias" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}

{% include parameter.html name="REVISION0" value="0" %}

{% include parameter.html name="REVISION1" value="3" %}

{% include parameter.html name="EXPORTTABLENAME0" value="ESP_PROVINCIAS_R0_XXXXXXXX_XXXXXX_XXX" %}

{% include parameter.html name="EXPORTTABLENAME1" value="ESP_PROVINCIAS_R3_XXXXXXXX_XXXXXX_XXX" %}

## {{ page.title }}

### Descripción

Este caso de prueba verifica que se puede exportar una capa de un repositorio en una copia de trabajo. Para ello:
* Inicializa una nueva copia de trabajo
* Exporta una capa del repositorio sobre la copia de trabajo.

Si la base de datos que se va a utilizar asociada a la copia de 
trabajo existe se eliminará y se volverá a crear, asi como la conexión.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. ${check} **TMPFOLDER**="/tmp". Carpeta en la que se disponga de acceso para escritura donde
   se crearan los archivos necesarios durante la ejecucion del test.

2. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexion a crear asociada al repositorio.

3. ${check} **WORKINGCOPY**=```${WCNAME2}``` a usar en este test. 

4. ${check} **TABLENAME**=```${TABLENAME}``` a usar en este test. 

5. ${check} **USER**=```${USER}```. Identificador de usuario.

6. ${check} **PASSWORD**=```${PASSWORD}```. Contraseña de usuario.

7. ${check} **REVISION0**=```0```. Primera revisión a exportar

8. ${check} **REVISION1**=```3```. Segunda revisión a exportar

[//]: # (9. ${check} **EXPORTTABLENAME0**=```ESP_PROVINCIAS_R0_XXXXXXXX_XXXXXX_XXX```. Nombre de la primera tabla exportada)

[//]: # (10. ${check} **EXPORTTABLENAME1**=```ESP_PROVINCIAS_R3_XXXXXXXX_XXXXXX_XXX```. Nombre de la segunda tabla exportada)

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya version sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} El caso de prueba [VC00TP00CP003, "Subir cambios en una capa con un plan topológico (que sí pasen el plan)"](../../TP00/CP003/testVC00TP00CP003.md),
   ha pasado sin errores. 

### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas 
   [VC00TP00CP003, "Subir cambios en una capa con un plan topológico (que sí pasen el plan)"](../../TP00/CP003/testVC00TP00CP003.md), 
   continúe con el siguiente paso, si no, ejecútelo antes de continuar. 
   
2. ${check} Cierre gvSIG.

3. ${check} **--- FIXME  Eliminar cualquier rastro de ${WCNAME2} ---**

4. ${check} Abra gvSIG

5. ${check} Inicialice una nueva copia de trabajo para ello seleccione la opción de menu "Herramientas/VCSGis/Inicializar copia de trabajo" y siga los pasos de [Inicializacion de una copia de trabajo (repositorio remoto en H2 con autorización)](../../PROC/008/procVC00PROC008.html?TMPFOLDER=${TMPFOLDER}&REPONAME=${REPONAME}&WCNAME=${WCNAME2})

6. ${check} Asegúrese de que la vista que se ha creado al arrancar gvSIG se encuentra en "EPSG:4326", de no ser asi cámbie la proyección de la vista.

7. ${check} Seleccione la opción de menu "Herramientas/VCSGis/Exportar" que nos presentara la ventana de titulo "Exportar".

8. ${check} Siga los pasos de [Exportar una revisión concreta de una capa desde repositorio](../../PROC/017/procVC00PROC017.html?WCNAME=${WCNAME2}&TABLENAME=${TABLENAME}&USER=${USER}&PASSWORD=${PASSWORD}&REVISION=${REVISION0}&EXPORTTABLENAME=${EXPORTTABLENAME0})

9. ${check} Cierre el cuadro de diálogo "Exportar".

10. ${check} En la vista se habrá añadido la capa ```${EXPORTTABLENAME0}```(EXPORTTABLENAME0) en el estado de la revisión ${REVISION0}.

11. ${check} Elimine la capa ```${TABLENAME}```(TABLENAME) de la vista pulsando con el botón secundario del ratón sobre la capa en el TOC y seleccionando "Eliminar capa".

12. Aparecerá un diálogo de confirmación que le preguntará "¿Está seguro de que desea borrar las capas activas?". Pulse el botón "Sí".

12. ${check} Seleccione la opción de menú "Herramientas/VCSGis/Obtener copia local (checkout)" que presentará la ventana de titulo "Obtener copia local (checkout)".

13. ${check} Siga los pasos de [Exportar una revisión concreta de una capa desde repositorio](../../PROC/018/procVC00PROC018.html?WCNAME=${WCNAME2}&TABLENAME=${TABLENAME}&USER=${USER}&PASSWORD=${PASSWORD}&REVISION=${REVISION1}&EXPORTTABLENAME=${EXPORTTABLENAME1})

14. ${check} Cierre el cuadro de diálogo "Exportar".

15. ${check} En la vista se habrá añadido la capa ```${EXPORTTABLENAME1}```(EXPORTTABLENAME1) en el estado de la revisión ${REVISION1}.

16. ${check} Cierre la vista.

17. ${check} Solo debe quedar abierta la ventana del "Gestor de proyecto".

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
