---
title: Descargar capa a la copia de trabajo (con autorización).
proccode: VC00CO00CP001
srcpath: "casos/VC00/CP001/testVC00CO00CP001.md"
---

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="REPONAME" value="Repositorio" %}

{% include parameter.html name="WCNAME2" value="CopiaDeTrabajo2" %}

{% include parameter.html name="TABLENAME" value="esp_provincias" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}


## {{ page.title }}

**EN CONSTRUCCION**

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

2. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexion a crear asociada al repositorio.

3. ${check} **WORKINGCOPY**=```${WCNAME2}``` a usar en este test. 

4. ${check} **TABLENAME**=```${TABLENAME}``` a usar en este test. 

5. ${check} **USER**=```${USER}```. Identificador de usuario.

6. ${check} **PASSWORD**=```${PASSWORD}```. Contraseña de usuario.

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya version sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} El caso de prueba [VC00SY00CP001, "Commitar una capa nueva (con autorización)"](../../SY00/CP001/testVC00SY00CP001.md),
   ha pasado sin errores. 

### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas 
   [VC00SY00CP001, "Commitar una capa nueva (con autorización)"](../../SY00/CP001/testVC00SY00CP001.md), 
   continúe con el paso 2.
   Si no, ejecútelo antes de continuar. 
   
2. ${check} Cierre gvSIG.

3. ${check} Compruebe que no exista el fichero:
   * ```${TMPFOLDER}/${WCNAME2}.mv.db``` (*TMPFOLDER*/*WCNAME2*.mv.db).
   En caso de que exista elimínelo.

4. ${check} Abra gvSIG

5. ${check} Inicialice una nueva copia de trabajo para ello siga los pasos de [Inicializacion de una copia de trabajo (repositorio local en H2 con autorización)](../../PROC/002/procVC00PROC002.md.html?TMPFOLDER=${TMPFOLDER}&REPONAME=${REPONAME}&WCNAME=${WCNAME2})

6. ${check} Asegúrese de que la vista que se ha creado al arrancar gvSIG se encuentra en "EPSG:4326", de no ser asi cámbie la proyección de la vista.

7. ${check} Seleccione la opción de menu "Herramientas/VCSGis/Obtener copia local (checkout)" que nos presentara la ventana de titulo "Obtener copia local (checkout)".

8. ${check} Siga los pasos de [Obtención de una copia local (checkout) desde repositorio local con autenticación](../../PROC/006/procVC00PROC006.html?WCNAME=${WCNAME2}&TABLENAME=${TABLENAME}&USER=${USER}&PASSWORD=${PASSWORD})

9. ${check} Cierre el cuadro de diálogo "Obtener copia local (checkout)".

10. ${check} En la vista se habrá añadido la capa ```${TABLENAME}```(TABLENAME).

11. Cierre la vista.

12. Solo debe quedar abierta la ventana del "Gestor de proyecto"

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
