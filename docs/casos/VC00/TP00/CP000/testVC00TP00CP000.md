---
title: Cargar un plan topológico en el repositorio
proccode: VC00TP00CP0000
srcpath: "casos/VC00/TP00/CP000/testVC00TP00CP000.md"
---

**EN CONSTRUCCION**

{% include es/header.md %}

{% include parameter.html name="DATANAME1" value="esp_provincias" %}

{% include parameter.html name="DATANAME2" value="esp_poblaciones" %}

{% include parameter.html name="DATANAME1LINK" value="<a href='../../data/esp_provincias.csv'>ESP_PROVINCIAS</a>" %}

{% include parameter.html name="DATANAME2LINK" value="<a href='../../data/esp_poblaciones.csv'>ESP_POBLACIONES</a>" %}

{% include parameter.html name="NAME" value="tp1" %}

{% include parameter.html name="DESCRIPTION" value="plan topológico número 1" %}




## {{ page.title }}

### Descripción

Este proceso carga un plan topológico en el repositorio.

### Datos de entrada

1. ${check} Archivo de datos 1 ```${DATANAME1}``` (${DATANAME1LINK}). Capa numero 1 a usar en este test. 

2. ${check} Archivo de datos 2 ```${DATANAME2}``` (${DATANAME2LINK}). Capa numero 2 a usar en este test. 

3. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexión y del repositorio.

4. ${check} **NAME**=```${NAME}```. Nombre del nuevo plan topológico a registrar.

5. ${check} **DESCRIPTION**=```${DESCRIPTION}```. Descripción del nuevo plan topológico a registrar.

6. ${check} **TOPOLOGYPLAN**=```${TOPOLOGYPLAN}```. Plan topológico a registrar en formato JSON proveniente 
    de los archivos de datos.




### Pasos

1. ${check} Una vez creado el repositorio sobre el cual se va a aplicar el plan topológico se abre la 
   tabla ```VCSGISREPO_TOPOLOGYPLANS``` de este. Siga los pasos de 
    [Abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?BBDD=${REPONAME}&TABLENAME=VCSGISREPO_TOPOLOGYPLANS)

2. ${check} Una vez abierta la tabla y estando esta activa se procede a añadir en esta un nuevo registro. Para ello 
    seleccione "Tabla" en el menú de gvSIG Desktop.

3. ${check} Seleccione del despeglable anterior la opción "Show form". 

4. ${check} Como resultado se genera una nueva ventana que muestra el formulario asociado a la tabla de planes topológicos.

5. ${check} Para registrar cambios en esta hay que iniciar la edición. Para iniciar la edición pulse el icono con la
   etiqueta "Comenzar edición". Los iconos se muestran en la zona inferior de la ventana y el de comenzar edición se
   encuentra en la zona media de estos.

6. ${check} La acción anterior habilita una serie de iconos.

7. ${check} Pulse el icono con la etiqueta "Nuevo" recientemente habilitado.

8. ${check} Como consecuencia de lo anterior, algunos de los campos de la página actual del formulario se muestran
    sin datos a la espera de la nueva información.

9. ${check} Indroduce el nombre del nuevo plan topológico, ```${NAME}``` en el campo correspondiente, Nombre.

10. ${check} Indroduce la descripción del nuevo plan topológico, ```${DESCRIPTION}```, en el campo correspondiente, Descripción.

11. ${check} Indroduce el plan topológico en formatao JSON del nuevo plan topológico, ```${TOPOLOGYPLAN}```,
     en el campo correspondiente, Serialized topology plan in JSON .

11. ${check} Pulse el icono con la etiqueta "Guardar".

12. ${check} Para terminar el proceso y trás guardar cambios hay que terminar la edición. Para terinar la edición pulse 
    el icono con la etiqueta "Terminar edición". Este se encuentra la zona media de los iconos. 

13. ${check} Cierre el formulario.

14. ${check} Cierre la tabla en cuestión


### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
