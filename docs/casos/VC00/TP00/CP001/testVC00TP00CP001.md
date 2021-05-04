---
title: Asociar un plan topológico a una capa
proccode: VC00TP00CP0001
srcpath: "casos/VC00/TP00/CP001/testVC00TP00CP001.md"
---

**EN CONSTRUCCION**

{% include es/header.md %}


{% include parameter.html name="TPNAME" value="tp1" %}

{% include parameter.html name="ENTITIE" value="esp_provincias" %}


## {{ page.title }}

### Descripción

Este proceso asigna el plan topológico ${TPNAME} a la entidad o capa del repositorio ${ENTITIE}.

### Datos de entrada

1. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexión y del repositorio.

2. ${check} **TPNAME**=```${TPNAME}```. Nombre del plan topológico a asignar.

3. ${check} **ENTITIE**=```${ENTITIE}```. Capa o entidad del repositorio a la cual se le asigna el plan topológico.


### Pasos
1. ${check} Si acaba de ejecutar el caso de pruebas (hace menos de 1 hora) VC00TP00CP000,
    "Cargar un plan topológico en el repositorio"
    y no ha cerrado gvSIG, continúe con el paso 2. Si no, ejecútelo antes de continuar.
    
2. ${check} Abra la tabla ```VCSGISREPO_ENTITIES``` de este. Siga los pasos de 
    [Abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?BBDD=${REPONAME}&TABLENAME=VCSGISREPO_ENTITIES)

2. ${check} Una vez abierta la tabla y estando esta activa se procede a asignar el plan a a entidad. Para ello 
    seleccione "Tabla" en el menú de gvSIG Desktop.

3. ${check} Seleccione del despeglable anterior la opción "Show form". 

4. ${check} Como resultado se genera una nueva ventana que muestra el formulario asociado a la tabla de planes topológicos.

5. ${check} Para registrar cambios en esta hay que iniciar la edición. Para iniciar la edición pulse el icono con la
   etiqueta "Comenzar edición". Los iconos se muestran en la zona inferior de la ventana y el de comenzar edición se
   encuentra en la zona media de estos.

6. ${check} La acción anterior habilita una serie de iconos.

7. ${check} Seleccione con ayuda de los iconos "Anterior" y "Siguiente" la página del formulario de la entidad ${ENTITIE}.

8. ${check} Localice el campo "Topology plan" y pulse el icono adyacente a este con etiqueta "Select item to list".

9. ${check} Tras lo anterior, se despliega una ventana con los diferentes planes topológicos disponibles 
    en el repositorio ${REPONAME}.

10. ${check} Seleccione el plan topológico ${TPNAME}.

11. ${check} Como consecuencia de la última acción el campo "Topology plan" presentara el valor ${TPNAME}.

12. ${check} Localice el campo "Topology plan mode" y seleccione la opción "Mandatory" del desplegable.

13. ${check} Pulse el icono con la etiqueta "Guardar".

14. ${check} Para terminar el proceso y trás guardar cambios hay que terminar la edición. Para terminar la edición pulse 
    el icono con la etiqueta "Terminar edición". Este se encuentra la zona media de los iconos. 

15. ${check} Cierre el formulario.

16. ${check} Cierre la tabla en cuestión


### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
