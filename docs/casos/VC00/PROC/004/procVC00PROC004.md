---
title: Activar autenticación y autorización en el repositorio
proccode: VC00PROC004
srcpath: "casos/VC00/PROC/004/procVC00PROC004.md"
---

{% include es/header.md %}

{% include parameter.html name="CONFIGTABLENAME" value="VCSGISREPO_CONFIG" %}

{% include parameter.html name="USERSTABLENAME" value="VCSGISREPO_USERS" %}


## {{ page.title }}

### Descripción

Este proceso activará la autenticación y autorización sobre un repostotio y se crearán
dos usuarios:
* "sara", de clave "sara1", con todos los permisos activados (opción por defecto).
* "pedro", de clave "pedro1", sin permiso de "commit".

### Datos de entrada

1. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexión a crear y del repositorio.

### Pasos

1. ${check} Abra la tabla de configuración del repositorio, ```${CONFIGTABLENAME}```, 
   para ello siga los pasos indicados en 
   [abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?CONNAME=${REPONAME}&TABLENAME=${CONFIGTABLENAME})
    
2. ${check} Cree un registro en la tabla ```${CONFIGTABLENAME}``` que active la autenticación en el repositorio, 
   para ello siga los pasos indicados en 
   [alta de una variable](../../PROC/009/procVC00PROC009.html?VARIABLE=AUTHENTICATION&VALUE=true)

3. ${check} Cree un registro en la tabla ```${CONFIGTABLENAME}``` que active la autorizacion en el repositorio, 
   para ello siga los pasos indicados en 
   [alta de una variable](../../PROC/009/procVC00PROC009.html?VARIABLE=AUTHENTICATION&VALUE=true)

4. ${check} Cierre la ventana de la tabla ```${CONFIGTABLENAME}```.

5. ${check} Abra la tabla de configuración del repositorio, ```${USERSTABLENAME}```, 
    para ello siga los pasos indicados en 
    [abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?CONNAME=${REPONAME}&TABLENAME=${USERSTABLENAME})

6. ${check} Cree un registro en la tabla ```${USERSTABLENAME}``` con la información del usuario "pedro", 
   para ello siga los pasos indicados en 
   [alta de un usuario](../../PROC/010/procVC00PROC010.html?NAME=pedro&PASSWORD=pedro1&OPERATIONS=add,entities,update,checkout,history,topologyplans,users)

7. ${check} Cree un registro en la tabla ```${USERSTABLENAME}``` con la información del usuario "sara", 
   para ello siga los pasos indicados en 
   [Alta de un usuario](../../PROC/010/procVC00PROC010.html?NAME=sara&PASSWORD=sara1&OPERATIONS=add,entities,commit,update,checkout,history,topologyplans,users)

8. ${check} Cierre la ventana de la tabla ```${USERSTABLENAME}```.

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
