---
title: Subir cambios en una capa con un plan topológico (que no pasen el plan)
proccode: VC00TP00CP0002
srcpath: "casos/VC00/TP00/CP002/testVC00TP00CP002.md"
---

**EN CONSTRUCCION**

{% include es/header.md %}

{% include parameter.html name="REPONAME" value="Repositorio" %}

{% include parameter.html name="TPNAME" value="ProvinciasDebenTenerPoblaciones" %}

{% include parameter.html name="ENTITIE1" value="esp_provincias" %}

{% include parameter.html name="ENTITIE2" value="esp_provincias" %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="WCNAME" value="CopiaDeTrabajo2" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}


## {{ page.title }}

### Descripción

Este proceso prueba que no es posible hacer un commit de una capa, ${ENTITIE},que no cumple un plan 
topológico, ${TPNAME}, asignado previamente en el repositorio, ${REPONAME}.

### Datos de entrada

1. ${check} **TMPFOLDER**=```${TMPFOLDER}```. Carpeta en la que se crearán los archivos que se precisen 
   durante la ejecución del test. Deberemos tener permiso de escritura en ella. 
   
2. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexión y del repositorio.

3. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia nueva de trabajo sobre la cual se realizará un checkout.

4. ${check} **TPNAME**=```${TPNAME}```. Nombre del plan topológico a asignar.

5. ${check} **ENTITIE1**=```${ENTITIE1}```. Capa o entidad del repositorio a la cual se le asigna el 
   plan topológico ${TPNAME}.

6. ${check} **ENTITIE2**=```${ENTITIE2}```. Capa o entidad del repositorio necesaria para 
    aplicar el plan topológico ${TPNAME}.

7. ${check} **USER**=```${USER}```. Nombre del usuario que realizará las operaciones con las tablas del repositorio.

8. ${check} **PASSWORD**=```${PASWORD}```. Contraseña del usuario que realizará las operaciones con las 
   tablas del repositorio.


### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas (hace menos de 1 hora) VC00TP00CP001,
    "Cargar un plan topológico en el repositorio"
    y no ha cerrado gvSIG, continúe con el paso 2. Si no, ejecútelo antes de continuar.

2. ${check} Cierre gvSIG.

3. ${check} Compruebe que no exista el fichero:
   * ```${TMPFOLDER}/${WCNAME}.mv.db``` (TMPFOLDER/WCNAME.mv.db). 
   
   En caso de que exista elimínelo.

4. ${check} Abra gvSIG

5. ${check} Inicialice una nueva copia de trabajo para ello siga los pasos de 
   [Inicializacion de una copia de trabajo (repositorio local en H2 con autorización)](../../PROC/008/procVC00PROC008.md.html?TMPFOLDER=${TMPFOLDER}&REPONAME=${REPONAME}&WCNAME=${WCNAME})

6. ${check} Asegúrese de que la vista que se ha creado al arrancar gvSIG se encuentra en "EPSG:4326",
   de no ser asi cámbie la proyección de la vista.

7. ${check} Seleccione la opción de menú "Herramientas"

8. ${check} Del desplegable surgido en la acción anterior seleccione la opción "VCSGis".

9. ${check} Del desplegable surgido en la acción anterior pulse la opción "Obtener copia local (checkout)" 

10. ${check} Tras lo anterior, se muestra la venanacon el título "Obtener copia local (checkout)".

11. ${check} Siga los pasos de [Obtención de una copia local (checkout)](../../PROC/006/procVC00PROC006.html?WCNAME=${WCNAME}&TABLENAME=${ENTITIE1}&USER=${USER}&PASSWORD=${PASSWORD})

12. ${check} Siga los pasos de [Obtención de una copia local (checkout)](../../PROC/005/procVC00PROC005.html?WCNAME=${WCNAME}&TABLENAME=${ENTITIE2})

13. ${check} Cierre el cuadro de diálogo "Obtener copia local (checkout)".

14. ${check} En la vista se habrá añadido las capas: 
    * ```${ENTITIE1}``` (ENTITIE1).
    * ```${ENTITIE2}``` (ENTITIE2).

11. MODIFICAR Y COMMITAR

CIERRA VETANA DE CAMBIOS inspecctor de errores Y SE DEjar LA VISTA EN PRIMER PLANO Y ACTIVA

