---
title: Añadir capa a copia de trabajo (repositorio remoto en H2 con autorización)
testcode: VC00AD00CP002
srcpath: "casos/VC00/AD00/CP002/testVC00AD00CP002.md"
---

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="REPONAME" value="Repositorio" %}

{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo" %}

{% include parameter.html name="TABLELINK" value="<a href='../../data/esp_provincias.csv'>ESP_PROVINCIAS</a>" %}

{% include parameter.html name="TABLENAME" value="esp_provincias" %}

{% include parameter.html name="FIELDFORLABEL" value="PRO_NAME" %}

{% include parameter.html name="CATEGORY" value="Cartografia base" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}

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

3. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia de trabajo que se va a crear asi como 
   de la conexion a la base de datos de la copia de trabajo. 

4. ${check} Tabla ```${TABLENAME}``` (${TABLELINK}). Capa a usar en este test. 

3. ${check} **FIELDFORLABEL**=```${FIELDFORLABEL}```. Nombre del campo de la tabla ```${TABLENAME}```
   a usar en etiquetas. 

4. ${check} **CATEGORY**=```${CATEGORY}```. Con la que vamos a añadir la tabla ```${TABLENAME}```
   a la copia local.

5. ${check} **USER**=```${USER}``` y **PASSWORD**=```${USER}``` a utilizar cuando se requiera autenticar al
   usuario que esta realizando la opracion.

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional para ser usado como ```Servidor``` de la versión indicada
   en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} Tendremos descargada la tabla ```${TABLENAME}``` (${TABLELINK}) en 
   una ruta conocida en nuestro equipo.

### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas 
   [VC00CW00CP002, Inicializacion de una copia de trabajo](../../CW00/CP002/testVC00CW00CP002.md)
   (hace menos de 1 hora) y no ha cerrado gvSIG, continúe con el paso 2. 
   Si no, ejecútelo antes de continuar.

2. ${check} En este punto deberemos tener abierta la aplicación gvSIG Desktop ```Cliente```.

3. ${check} Comprobaremos  que la vista que se ha creado al arrancar gvSIG se encuentra 
   en "EPSG:4326", de no ser así cambie la proyección de la vista asignandole esta.

4. ${check} Procederemos a cargar la capa ${TABLELINK} en la vista que hay creada 
   en el proyecto. Para eso abriremos el dialogo de añadir capa desde el menu vista, "Vista/Añadir capa".

5. ${check} Seleccionaremos la pestaña "Archivo" y pulsaremos en el boton de "Añadir".

6. ${check} Nos presentara el cuadro de dialogo para seleccionar un fichero. 
   Seleccionaremos el correspondiente a ${TABLELINK} 
   y pulsaremos en el boton "Abrir".

7. ${check} De vuelta en el dialogo de "Añadir capa" pulsaremos el boton "Aceptar" 
   para cargarla en la vista.

8. ${check} Seleccione la opción de menú "Herramientas/VCSGis/Añadir a la copia de trabajo" 
   que mostrará la ventana de título "Añadir a la copia de trabajo".

9. ${check} Siga los pasos de [añadir capa a la copia de trabajo](../../PROC/003/procVC00PROC003.html?WORKINGCOPY=${WORKINGCOPY}&LAYER=${TABLENAME}&FIELDFORLABEL=${FIELDFORLABEL}&CATEGORY=${CATEGORY}&USER=${USER}&PASSWORD=${PASSWORD}) 

10. ${check} Deberá haber aparecido en la vista una capa 
    ```${TABLENAME}``` (${TABLELINK})
    con el icono identificativo de una capa de base de datos H2.

11. ${check} Elimine de la vista la capa ```${TABLENAME}``` cargada 
    a partir del fichero ${TABLELINK} dejando la de H2.

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
