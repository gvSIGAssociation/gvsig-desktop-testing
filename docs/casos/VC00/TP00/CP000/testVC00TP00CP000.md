---
title: Cargar un plan topológico en el repositorio
proccode: VC00TP00CP0000
srcpath: "casos/VC00/TP00/CP000/testVC00TP00CP000.md"
---

**EN CONSTRUCCION**

{% include es/header.md %}

{% include parameter.html name="TABLE1_NAME" value="esp_provincias" %}

{% include parameter.html name="TABLE2_NAME" value="esp_poblaciones" %}

{% include parameter.html name="TABLE1_LINK" value="<a href='../../data/esp_provincias.csv'>ESP_PROVINCIAS</a>" %}

{% include parameter.html name="TABLE2_LINK" value="<a href='../../data/esp_poblaciones.csv'>ESP_POBLACIONES</a>" %}

{% include parameter.html name="TPNAME" value="ProvinciasDebenTenerPoblaciones" %}

{% include parameter.html name="TPDESCRIPTION" value="Las provincias deben tener alguna población" %}

{% include parameter.html name="TABLE2_FIELDFORLABEL" value="esp_poblaciones" %}

{% include parameter.html name="CATEGORY" value="Cartografia base" %}

{% include parameter.html name="WCNAME" value="CopiaDeTrabajo" %}

{% include parameter.html name="REPONAME" value="Repositorio" %}


## {{ page.title }}

### Descripción

Este proceso carga un plan topológico en el repositorio.

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

2. ${check} Active la aplicación gvSIG Desktop ```Servidor```. Vamos a registrar el servidor un plan topológico.

3. ${check} Abra la tabla ```VCSGISREPO_TOPOLOGYPLANS``` de este para ello siga los pasos de 
    [abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?CONNAME=${REPONAME}&TABLENAME=VCSGISREPO_TOPOLOGYPLANS)

4. ${check} Una vez abierta la tabla y estando esta activa seleccione la opcion de menu "Tabla/Show form".

5. ${check} Se mostrara la ventana con el formulario asociado a la tabla de planes topológicos.

6. ${check} Pulse el boton "Comenzar edición" del formulario. 

7. ${check} Pulse el boton "Nuevo" del formulario.

8. ${check} En el campo "Nombre" de la pestaña "General" d introduzca el valor ```${TPNAME}``` {% include var_copy.html var="TPNAME"%}.

9. ${check} En el campo "Descripcion" la pestaña "General" introduzca el valor ```${TPDESCRIPTION}``` {% include var_copy.html var="TPDESCRIPTION"%}.

10. ${check} En la pestaña "Plan" introduzca el plan topológico en formatao Json. Introduzca el valor: 
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

13. ${check} Se presentrara una ventana, pulse en la opción "Si". Dicha opción termina edición y guarda los cambios.

14. ${check} Cierre el formulario.


### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
