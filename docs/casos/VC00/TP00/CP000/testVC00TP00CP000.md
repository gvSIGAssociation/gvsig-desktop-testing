---
title: Cargar un plan topológico en el repositorio
proccode: VC00TP00CP000
srcpath: "casos/VC00/TP00/CP000/testVC00TP00CP000.md"
---

{% include es/header.md %}

{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo" %}

{% include parameter.html name="REPONAME" value="RepositorioAuth" %}

{% include parameter.html name="TPNAME" value="ProvinciasDebenTenerPoblaciones" %}

{% include parameter.html name="TPDESCRIPTION" value="Las provincias deben tener alguna población" %}

{% include parameter.html name="TABLE2_NAME" value="esp_poblaciones" %}

{% include parameter.html name="TABLE2_LINK" value="<a href='../../data/esp_poblaciones.csv'>ESP_POBLACIONES</a>" %}

{% include parameter.html name="TABLE2_CATEGORY" value="Cartografia base" %}

{% include parameter.html name="TABLE2_FIELDFORLABEL" value="POB_NOMBRE" %}

{% include parameter.html name="TABLE2_EFECTIVEDATE" value="3/05/2021" %}

{% include parameter.html name="TABLE2_COMMENT" value="Adición de la capa de esp_poblaciones" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}

## {{ page.title }}

### Descripción

Este caso de pruebas acaba cargando en el repositorio dos capas y registrando en él un plan topologico que las usa.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexión y del repositorio.

1. ${check} **TPNAME**={% include var_tag.html var="TPNAME" %}. Nombre del nuevo plan topológico a registrar.

1. ${check} **TPDESCRIPTION**={% include var_tag.html var="TPDESCRIPTION" %}. Descripción del nuevo plan topológico a registrar.

4. ${check} **TABLE2_NAME**=```${TABLE2_NAME}``` (${TABLE2_LINK}). Capa a usar en este test. 

3. ${check} **TABLE2_FIELDFORLABEL**=```${TABLE2_FIELDFORLABEL}```. Nombre del campo de la tabla ```${TABLE2_NAME}```
   a usar en etiquetas. 

4. ${check} **TABLE2_CATEGORY**=```${TABLE2_CATEGORY}```. Categoría a asociar a la tabla ```${TABLE2_NAME}``` cuando la añadamos a la copia local.

4. ${check} **TABLE2_EFECTIVEDATE**=```${TABLE2_EFECTIVEDATE}```. Fecha a indicar al hacer commit de la  tabla ```${TABLE2_NAME}```.

4. ${check} **TABLE2_COMMENT**=```${TABLE2_COMMENT}```. Comentario a indicar al hacer commit de la tabla ```${TABLE2_NAME}```.

5. ${check} **USER**=```${USER}```. Usuario a utilizar cuando sea requerido por la aplicación.

7. ${check} **PASSWORD**=```${PASSWORD}```. Clave del usuario a utilizar cuando sea requerido por la aplicación.

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya versión sea la indicada en el plan de pruebas.

1. ${check} El complemento de VCSGis debe estar instalado y activo.

1. ${check} El complemento de Topología debe estar instalado y activo.

1. ${check} Se acaba de pasar uno de los casos de prueba "commitar una capa nueva" o "Asociar leyenda a una capa" del
   plan de pruebas.

### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas "commitar una capa nueva" o "Asociar leyenda a una capa" (hace menos de 1 hora) y 
   aún tiene abierto gvSIG desktop ```Servidor``` continúe con el paso 2. Si no, ejecute uno de estos dos antes de continuar.

2. ${check} **Active la aplicación gvSIG Desktop ```Cliente```**.

3. ${check} Compruebe que no exista el fichero:
   * ```${TMPFOLDER}/${WORKINGCOPY}.mv.db``` (TMPFOLDER/WORKINGCOPY.mv.db).
   En caso de que exista debera:
   * ${check} Cerrar gvSIG desktop ```Cliente```.
   * ${check} Elimínar el fichero ```${TMPFOLDER}/${WORKINGCOPY}.mv.db``` (TMPFOLDER/WORKINGCOPY.mv.db).
   * ${check} Iniciar gvSIG desktop ```Cliente```.

4. ${check} Elimine el registro de la copia de trabajo ```${WORKINGCOPY}``` en caso de que existiese.
   Para ello siga los pasos indicados en 
   [eliminar copia local del registro](../../PROC/019/procVC00PROC019.html?&WORKINGCOPY=${WORKINGCOPY})

5. ${check} Proceda a cargar la capa ```${TABLE2_NAME}``` (${TABLE2_LINK}) en la vista que hay creada 
   en el proyecto. Seleccione la opción de menú "Vista/Añadir capa".

6. ${check} Se presentará el diálogo de "Añadir capa". Seleccione la pestaña "Archivo" y pulse en el botón "Añadir".

7. ${check} Se presenta un cuadro de diálogo para seleccionar un fichero. 
    Seleccione el correspondiente a ```${TABLE2_NAME}``` (${TABLE2_LINK}).
     
8. ${check} Pulse en el botón "Abrir".

9. ${check} De vuelta en el diálogo de "Añadir capa" pulse el botón "Aceptar" 
    para cargarla en la vista.

10. ${check} Seleccione la opción de menu "Herramientas/VCSGis/Añadir a la copia de trabajo".
    Se presentará la ventana de titulo "Añadir a la copia de trabajo".

13. ${check} Siga los pasos de 
    [añadir capa a la copia de trabajo](../../PROC/003/procVC00PROC003.html?WORKINGCOPY=${WORKINGCOPY}&LAYER=${TABLE2_NAME}&FIELDFORLABEL=${TABLE2_FIELDFORLABEL}&CATEGORY=${TABLE2_CATEGORY}&USER=${USER}&PASSWORD=${PASSWORD}) 
    para añadir la capa a la copia de trabajo.

13. ${check} En la ventana de titulo "Añadir a la copia de trabajo" pulse el botón "Cerrar" para cerrarla.

15. ${check} Deberá haber aparecido en la vista una capa 
    ```${TABLE2_NAME}``` con el identificativo de una capa de base de datos H2.

15. ${check} Elimine de la vista la capa ```${TABLE2_NAME}``` cargada 
    a partir del fichero ${TABLE2_LINK} dejando la que tiene el indicativo de H2.

12. ${check} Seleccione la opción de menú "Herramientas/VCSGis/Mostrar cambios".

14. ${check} Siga los pasos de 
    [commit de una capa](../../PROC/021/procVC00PROC021.html?WORKINGCOPY=${WORKINGCOPY}&TABLENAME=${TABLE2_NAME}&EFECTIVEDATE=${TABLE2_EFECTIVEDATE}&COMMENT=${TABLE2_COMMENT}&USER=${USER}&PASSWORD=${PASSWORD}) 
    para subir la capa al reposiorio.

2. ${check} **Active la aplicación gvSIG Desktop ```Servidor```**. Se va a proceder a registrar en el servidor un plan topológico.

3. ${check} Abra la tabla ```VCSGISREPO_TOPOLOGYPLANS```, para ello siga los pasos de 
    [abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?CONNAME=${REPONAME}&TABLENAME=VCSGISREPO_TOPOLOGYPLANS)

4. ${check} Una vez abierta la tabla y estando esta activa seleccione la opción de menu "Tabla/Show form".

5. ${check} Se mostrará la ventana con el formulario asociado a la tabla de planes topológicos.

6. ${check} Pulse el botón "Comenzar edición" del formulario. 

7. ${check} Pulse el botón "Nuevo" del formulario.

8. ${check} En el campo "Nombre" de la pestaña "General" introduzca el valor ```${TPNAME}``` {% include var_copy.html var="TPNAME"%}.

9. ${check} En el campo "Descripción" la pestaña "General" introduzca el valor ```${TPDESCRIPTION}``` {% include var_copy.html var="TPDESCRIPTION"%}.

10. ${check} En la pestaña "Plan" debe introducir el plan topológico en formato Json. Introduzca el valor: 
    <PRE id="DROP_TABLES" class="language-plaintext highlighter-rouge">
    {"name":"provinciasDebenTenerPoblaciones","dataSets":[
      {"name":"esp_provincias","fullName":"esp_provincias.csv"},
      {"name":"esp_poblaciones","fullName":"esp_poblaciones.csv"}
    ],
    "rules":[
      {"__factoryId":"ContainsPoint","dataSet2":"esp_poblaciones",
      "dataSet1":"esp_provincias","tolerance":0}
    ],
    "tolerance":0
    }
    </PRE>
    {% include var_copy.html var="DROP_TABLES"%}

    Esta secuencia Json se obtiene de la opción "Copy topology plan to clipboard" de la 
    ventana "Plan de topología" del módulo de topología.

11. ${check} Pulse el botón "Guardar" del formulario.

12. ${check} Pulse el botón "Terminar edición" del formulario. 

13. ${check} Se presentrará una ventana, pulse en la opción "Si" para terminar edición y guarda los cambios.

14. ${check} Cierre el formulario.

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
