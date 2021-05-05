---
title: Añadir capa a copia de trabajo (repositorio remoto en H2 con autorización)
testcode: VC00AD00CP002
srcpath: "casos/VC00/AD00/CP002/testVC00AD00CP002.md"
---

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="REPONAME" value="Repositorio" %}

{% include parameter.html name="WCNAME" value="CopiaDeTrabajo" %}

{% include parameter.html name="TABLELINK" value="<a href='../../data/esp_provincias.csv'>ESP_PROVINCIAS</a>" %}

{% include parameter.html name="TABLENAME" value="esp_provincias" %}

{% include parameter.html name="FIELDFORLABEL" value="COM_NAME" %}

{% include parameter.html name="CATEGORY" value="Cartografia base" %}

## {{ page.title }}

### Descripción

Este caso de prueba verifica que se pueda añadir una capa local a una copia de trabajo
basada en un repositotio remoto en H2 con la autorización activada.
Para ello:
* Inicializa un repositorio remoto de H2.
* Inicializa una copia de trabajo
* Añade una capa a la copia de trabajo creada.

Si las bases de datos que vamos a utilizar asociadas al repositorio o la copia de 
trabajo existen se eliminaran y se volveran a crear, asi como las conexiones a 
base de datos que se vayan a utilizar.


{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada:

1. ${check} **TMPFOLDER**=```${TMPFOLDER}```. Carpeta en la que se crearán los archivos que se precisen 
   durante la ejecucion del test. Deberemos tener permiso de escritura en ella.

2. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexion a crear asociada al repositorio.

3. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia de trabajo que se va a crear asi como 
   de la conexion a la base de datos de la copia de trabajo. 

4. ${check} Tabla ```${TABLENAME}``` (${TABLELINK}). Capa a usar en este test. 

3. ${check} **FIELDFORLABEL**=```${FIELDFORLABEL}```. Nombre del campo de la tabla ```${TABLENAME}```
   a usar en etiquetas. 

4. ${check} **CATEGORY**=```${CATEGORY}```. Con la que vamos a añadir la tabla ```${TABLENAME}```
   a la copia local.

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya version sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} Tendremos descargada la tabla ```${TABLENAME}``` (${TABLELINK}) en 
   una ruta conocida en nuestro equipo.

### Pasos

1. ${check} Antes de iniciar gvSIG desktop compruebe que no existan los ficheros:
   * ```${TMPFOLDER}/${REPONAME}.mv.db``` (*TMPFOLDER*/*REPONAME*.mv.db).
   * ```${TMPFOLDER}/${WCNAME}.mv.db``` (*TMPFOLDER*/*WCNAME*.mv.db).
   
   En caso de que existan elimínelos.
   
2. ${check} Inicie gvSIG desktop.

3. ${check} Cerciórese de que la vista que se ha creado al arrancar gvSIG se encuentra 
   en "EPSG:4326", de no ser así cambie la proyección de la vista.

4. ${check} Seleccione la opcion de menu "Herramientas/VCSGis/Administración/Inicializar repositorio" 
   que presentara la ventana de titulo "Inicializar repositorio".

5. ${check} Siga los pasos de [Inicializar un repositorio en H2 (con autorización)](../../PROC/004/procVC00PROC004.html?TMPFOLDER=${TMPFOLDER}&REPONAME=${REPONAME})

6. ${check} Siga los pasos de [Iniciar un servidor de repositorio](../../PROC/007/procVC00PROC007.html?TMPFOLDER=REPONAME=${REPONAME})

7. ${check} Seleccione la opción de menú 
   "Herramientas/VCSGis/Inicializar copia de trabajo" que presentará la ventana de 
   titulo "Inicializar copia de trabajo".

7. ${check} Siga los pasos de [Inicialización de una copia de trabajo asociada a un repositorio remoto en H2.](../../PROC/008/procVC00PROC008.html?TMPFOLDER=${TMPFOLDER}&REPONAME=${REPONAME}&WCNAME=${WCNAME}) 
   
8. ${check} Cargue la capa ${TABLELINK} en la vista que se ha abierto por defecto en el proyecto. 
Para ello abra el diálogo de añadir capa desde el menú vista, "Vista/Añadir capa".

9. ${check} Seleccione la pestaña "Archivo" y pulse el botón de "Añadir".

10. ${check} Se mostrará el cuadro de diálogo para seleccionar un fichero. 
    Seleccione el correspondiente a ${TABLELINK} 
    y pulse el boton "Abrir".

11. ${check} De vuelta en el diálogo de "Añadir capa" pule el boton "Aceptar" 
    para cargarla en la vista.

12. ${check} Seleccione la opción de menú "Herramientas/VCSGis/Añadir a la copia de trabajo" 
    que mostrará la ventana de título "Añadir a la copia de trabajo".

13. ${check} Siga los pasos de [Añadir capa a la copia de trabajo](../../PROC/003/VC00PROC003.html?WCNAME=${WCNAME}&LAYER=${TABLENAME}&FIELDFORLABEL=${FIELDFORLABEL}&CATEGORY=${CATEGORY}) 

14. ${check} Deberá haber aparecido en la vista una capa 
    ```${TABLENAME}``` (${TABLELINK})
    con el identificativo de una capa de base de datos H2.

15. ${check} Elimine de la vista la capa ```${TABLENAME}``` cargada 
    a partir del fichero ${TABLELINK}.

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
