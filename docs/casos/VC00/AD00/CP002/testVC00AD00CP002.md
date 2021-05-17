---
title: Añadir capa a copia de trabajo (repositorio remoto con autorización)
testcode: VC00AD00CP002
srcpath: "casos/VC00/AD00/CP002/testVC00AD00CP002.md"
---

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

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
basada en un repositotio remoto con la autorización activada.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada:

1. ${check} **TMPFOLDER**=```${TMPFOLDER}```. Carpeta en la que se crearán los archivos que se precisen 
   durante la ejecucion del test. Deberemos tener permiso de escritura en ella.

1. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia de trabajo que se va a crear así como 
   de la conexión a la base de datos de la copia de trabajo. 

1. ${check} **TABLENAME**=```${TABLENAME}``` (${TABLELINK}). Capa a usar en este test. 

1. ${check} **FIELDFORLABEL**=```${FIELDFORLABEL}```. Nombre del campo de la tabla ```${TABLENAME}```
   a usar en etiquetas. 

1. ${check} **CATEGORY**=```${CATEGORY}```. Categoría a aosciar a la tabla ```${TABLENAME}``` al añadirla
   a la copia local.

1. ${check} **USER**=```${USER}```. Usuario a utilizar cuando sea requerido por la aplicación.

1. ${check} **PASSWORD**=```${PASSWORD}```. Clave del usuario a utilizar cuando sea requerido por la aplicación.

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional para ser usado como ```Servidor``` de la versión indicada
   en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} Descargada la tabla ```${TABLENAME}``` (${TABLELINK}) en 
   una ruta conocida en nuestro equipo.

### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas 
   [VC00CW00CP002, Inicializacion de una copia de trabajo](../../CW00/CP002/testVC00CW00CP002.md)
   (hace menos de 1 hora) y no ha cerrado gvSIG, continúe con el paso 2. 
   Si no, ejecútelo antes de continuar.

2. ${check} En este punto deberemos tener abierta la aplicación gvSIG Desktop ```Cliente```.

3. ${check} Compruebe que la vista que se ha creado al arrancar gvSIG se encuentra 
   en "EPSG:4326", de no ser así cambie la proyección de la vista asignándole ésta.

4. ${check} Proceda a cargar la capa ${TABLELINK} en la vista que hay creada 
   en el proyecto. Para eso abra el diálogo de añadir capa desde el menú vista, "Vista/Añadir capa".

5. ${check} Seleccione la pestaña "Archivo" y pulse en el botón "Añadir".

6. ${check} Se presentará el cuadro de diálogo de selección de fichero. 
   Seleccione el correspondiente a ${TABLELINK} 
   y pulse en el botón "Abrir".

7. ${check} De vuelta en el diálogo de "Añadir capa" pulse el botón "Aceptar" 
   para cargarla en la vista.

8. ${check} Seleccione la opción de menú "Herramientas/VCSGis/Añadir a la copia de trabajo" 
   que mostrará la ventana de título "Añadir a la copia de trabajo".

9. ${check} Siga los pasos de [añadir capa a la copia de trabajo](../../PROC/003/procVC00PROC003.html?WORKINGCOPY=${WORKINGCOPY}&LAYER=${TABLENAME}&FIELDFORLABEL=${FIELDFORLABEL}&CATEGORY=${CATEGORY}&USER=${USER}&PASSWORD=${PASSWORD}) 

9. ${check} En la ventana de título "Añadir a la copia de trabajo" pulse el boton "Cerrar" para cerrar este ventana.

11. ${check} Deberá haber aparecido en la vista una capa 
    ```${TABLENAME}``` (${TABLELINK})
    con el icono identificativo de una capa de base de datos H2.

11. ${check} Elimine de la vista la capa ```${TABLENAME}``` cargada 
    a partir del fichero ${TABLELINK} dejando la de H2.

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
