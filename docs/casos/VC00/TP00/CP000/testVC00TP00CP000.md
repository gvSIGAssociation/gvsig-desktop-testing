---
title: Cargar un plan topológico en el repositorio
proccode: VC00TP00CP0000
srcpath: "casos/VC00/TP00/CP000/testVC00TP00CP000.md"
---

**EN CONSTRUCCION**

{% include es/header.md %}

{% include parameter.html name="REPONAME" value="RepositorioAuth" %}

{% include parameter.html name="TPNAME" value="ProvinciasDebenTenerPoblaciones" %}

{% include parameter.html name="TPDESCRIPTION" value="Las provincias deben tener alguna población" %}

{% include parameter.html name="TABLE2_NAME" value="esp_poblaciones" %}

{% include parameter.html name="TABLE2_LINK" value="<a href='../../data/esp_poblaciones.csv'>ESP_POBLACIONES</a>" %}

{% include parameter.html name="TABLE2_CATEGORY" value="Cartografia base" %}

{% include parameter.html name="TABLE2_FIELDFORLABEL" value="POB_NOMBRE" %}

{% include parameter.html name="TABLE2_EFECTIVEDATE" value="3/05/2021" %}

{% include parameter.html name="TABLE2_COMMENT" value="Adición de la capa de esp_poblaciones" %}


## {{ page.title }}

### Descripción

Este caso de pruebas acaba cargando en el repositorio dos capas y registrando en el un plan topologico que usa ambas capas.

### Datos de entrada

1. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexión y del repositorio.

1. ${check} **TPNAME**={% include var_tag.html var="TPNAME" %}. Nombre del nuevo plan topológico a registrar.

1. ${check} **TPDESCRIPTION**={% include var_tag.html var="TPDESCRIPTION" %}. Descripción del nuevo plan topológico a registrar.

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya versión sea la indicada en el plan de pruebas.

1. ${check} El complemento de VCSGis debe estar instalado y activo.

1. ${check} El complemento de Topología debe estar instalado y activo.

1. ${check} Se acaba de pasar uno de los casos de prueba "commitar una capa nueva" o "Asociar leyenda a una capa" del
   plan de pruebas.

### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas "commitar una capa nueva" o "Asociar leyenda a una capa" (hace menos de 1 hora) y 
   aun tiene abierto gvSIG desktop Servidor continúe con el paso 2. Si no, ejecúte uno de estos dos antes de continuar.

2. ${check} **Active la aplicación gvSIG Desktop ```Cliente```**.

3. ${check} Proceda a cargar la capa ```${TABLE2_NAME}``` (${TABLE2_LINK}) en la vista que hay creada 
   en el proyecto. Seleccione la opcion de menú "Vista/Añadir capa".

5. ${check} Se presentara el dialogo de "Añadir capa". Seleccione la pestaña "Archivo" y pulse en el boton "Añadir".

7. ${check} Se presenta un cuadro de diálogo para seleccionar un fichero. 
    Seleccione el correspondiente a ```${TABLE2_NAME}``` (${TABLE2_LINK}).
     
8. ${check} Pulse en el boton "Abrir".

9. ${check} De vuelta en el dialogo de "Añadir capa" pulse el botón "Aceptar" 
    para cargarla en la vista.

10. ${check} Seleccione la opción de menu "Herramientas/VCSGis/Añadir a la copia de trabajo".
    Se preentara la ventana de titulo "Añadir a la copia de trabajo".

13. ${check} Siga los pasos de 
    [añadir capa a la copia de trabajo](../../PROC/003/procVC00PROC003.html?WORKINGCOPY=${WORKINGCOPY}&LAYER=${TABLE2_NAME}&FIELDFORLABEL=${TABLE2_FIELDFORLABEL}&TABLE2_CATEGORY=${CATEGORY}) 
    para añadir la capa a la copia de trabajo.

14. ${check} Debera haber aparecido en la vista una capa 
    ```${TABLE2_NAME}``` con el identificativo de una capa de base de datos H2.

15. ${check} Elimine de la vista la capa ```${TABLE2_NAME}``` cargada 
    a partir del fichero ${TABLE2_LINK} dejando la que tiene el indicativo de H2.

12. ${check} Seleccione la opcion de menu "Herramientas/VCSGis/Mostrar cambios".

14. ${check} Siga los pasos de 
    [commit de una capa](../../PROC/021/procVC00PROC021.html?WORKINGCOPY=${WORKINGCOPY}&TABLENAME=${TABLE2_NAME}&EFECTIVEDATE=${TABLE2_EFECTIVEDATE}&COMMENT=${TABLE2_COMMENT}) 
    para subir la capa al reposiorio.

2. ${check} **Active la aplicación gvSIG Desktop ```Servidor```**. Vamos a registrar el servidor un plan topológico.

3. ${check} Abra la tabla ```VCSGISREPO_TOPOLOGYPLANS```, para ello siga los pasos de 
    [abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?CONNAME=${REPONAME}&TABLENAME=VCSGISREPO_TOPOLOGYPLANS)

4. ${check} Una vez abierta la tabla y estando esta activa seleccione la opcion de menu "Tabla/Show form".

5. ${check} Se mostrara la ventana con el formulario asociado a la tabla de planes topológicos.

6. ${check} Pulse el boton "Comenzar edición" del formulario. 

7. ${check} Pulse el boton "Nuevo" del formulario.

8. ${check} En el campo "Nombre" de la pestaña "General" introduzca el valor ```${TPNAME}``` {% include var_copy.html var="TPNAME"%}.

9. ${check} En el campo "Descripcion" la pestaña "General" introduzca el valor ```${TPDESCRIPTION}``` {% include var_copy.html var="TPDESCRIPTION"%}.

10. ${check} En la pestaña "Plan" debe introducir el plan topológico en formatao Json. Introduzca el valor: 
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

11. ${check} Pulse el boton "Guardar" del formulario.

12. ${check} Pulse el boton "Terminar edición" del formulario. 

13. ${check} Se presentrara una ventana, pulse en la opción "Si" para terminar edición y guarda los cambios.

14. ${check} Cierre el formulario.


### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
