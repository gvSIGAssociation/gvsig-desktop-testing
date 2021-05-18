---
title: Descargar capa a la copia de trabajo (repositorio remoto con autorización).
proccode: VC00CO00CP002
srcpath: "casos/VC00/CO00/CP002/testVC00CO00CP002.md"
---

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="REPOURL" value="http://127.0.0.1:9810" %}

{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo2" %}

{% include parameter.html name="TABLENAME" value="esp_provincias" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}


## {{ page.title }}

### Descripción

Este caso de prueba verifica que se puede obtener una capa de un repositorio en una copia de trabajo nueva. Para ello:
* Inicializa una nueva copia de trabajo
* Descarga una capa (checkout) del repositorio sobre la copia de trabajo.

Si la base de datos que se va a utilizar asociada a la copia de 
trabajo existe se eliminará y se volverá a crear, así como la conexión.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. ${check} **TMPFOLDER**="/tmp". Carpeta en la que se disponga de acceso para escritura donde
   se crearán los archivos necesarios durante la ejecución del test.

2. ${check} **REPOURL**=```${REPOURL}```. Dirección donde está el servidor del repositorio a utilizar.

3. ${check} **WORKINGCOPY**=```${WORKINGCOPY}``` a usar en este test. 

4. ${check} **TABLENAME**=```${TABLENAME}``` a usar en este test. 

5. ${check} **USER**=```${USER}```. Identificador de usuario.

6. ${check} **PASSWORD**=```${PASSWORD}```. Contraseña de usuario.

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya versión sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} El caso de prueba [VC00SY00CP001 Commitar una capa nueva](../../SY00/CP001/testVC00SY00CP001.md),
   ha pasado sin errores. 

### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas 
   [VC00SY00CP001 commitar una capa nueva](../../SY00/CP001/testVC00SY00CP001.md), 
   continúe con el siguiente paso, si no, ejecútelo antes de continuar. 
   
2. ${check} Compruebe que no exista el fichero:
   * ```${TMPFOLDER}/${WORKINGCOPY}.mv.db``` (TMPFOLDER/WORKINGCOPY.mv.db).
   En caso de que exista deberá:
   * ${check} Cerrar gvSIG desktop ```Cliente```.
   * ${check} Elimínar el fichero ```${TMPFOLDER}/${WORKINGCOPY}.mv.db``` (TMPFOLDER/WORKINGCOPY.mv.db).
   * ${check} Iniciar gvSIG desktop ```Cliente```.

3. ${check} Elimine el registro de la copia de trabajo ```${WORKINGCOPY}``` en caso de que existise.
   Para ello siga los pasos indicados en 
   [eliminar copia local del registro](../../PROC/019/procVC00PROC019.html?&WORKINGCOPY=${WORKINGCOPY})

4. ${check} Compruebe que la vista que se ha creado al arrancar gvSIG se encuentra en "EPSG:4326", de no ser así cámbie la proyección de la vista.

5. ${check} Inicialice una nueva copia de trabajo para ello seleccione la opción de 
   menú "Herramientas/VCSGis/Inicializar copia de trabajo" y siga los pasos de 
   [inicialización de una copia de trabajo](../../PROC/008/procVC00PROC008.html?TMPFOLDER=${TMPFOLDER}&REPOURL=${REPOURL}&WORKINGCOPY=${WORKINGCOPY})

6. ${check} Seleccione la opción de menu "Herramientas/VCSGis/Obtener copia local (checkout)" que 
   presentará la ventana de titulo "Obtener copia local (checkout)".

7. ${check} Siga los pasos de 
   [obtención de una copia local (checkout) desde repositorio con autenticación](../../PROC/006/procVC00PROC006.html?WORKINGCOPY=${WORKINGCOPY}&TABLENAME=${TABLENAME}&USER=${USER}&PASSWORD=${PASSWORD})

8. ${check} Cierre el cuadro de diálogo "Obtener copia local (checkout)".

9. ${check} En la vista se habrá añadido la capa ```${TABLENAME}```(TABLENAME).

9. ${check} Elimine la capa ```${TABLENAME}```(TABLENAME) de la vista pulsando con el botón secundario del ratón sobre el nombre de la capa en el TOC y seleccionado la opcíón "Eliminar capa"

10. ${check} Se le preguntará si está seguro de que desea borrar las capas activas". Pulse el botón "Sí"

11. ${check} Cierre la vista.

12. ${check} Solo debe quedar abierta la ventana del "Gestor de proyecto"

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
