1. ${check} Si acaba de ejecutar el caso de pruebas (hace menos de 1 hora) VC00TP00CP001,
    "Cargar un plan topológico en el repositorio"
    y no ha cerrado gvSIG, continúe con el paso 2. Si no, ejecútelo antes de continuar.

2. ${check} Cierre gvSIG.

3. ${check} Compruebe que no exista el fichero:
   * ```${TMPFOLDER}/${WCNAME}.mv.db``` (TMPFOLDER/WCNAME.mv.db). 
   
   En caso de que exista elimínelo.

4. ${check} Abra gvSIG

5. ${check} Inicialice una nueva copia de trabajo para ello siga los pasos de 
   [Inicializacion de una copia de trabajo (repositorio local en H2 con autorización)](../../PROC/008/procVC00PROC008.md.html?TMPFOLDER=${TMPFOLDER}&REPONAME=${REPONAME}&WCNAME=${WCNAME2})

6. ${check} Asegúrese de que la vista que se ha creado al arrancar gvSIG se encuentra en "EPSG:4326",
   de no ser asi cámbie la proyección de la vista.

7. ${check} Seleccione la opción de menu "Herramientas/VCSGis/Obtener copia local (checkout)" que nos presentara 
   la ventana de titulo "Obtener copia local (checkout)".

8. ${check} Siga los pasos de [Obtención de una copia local (checkout)](../../PROC/006/procVC00PROC006.html?WCNAME=${WCNAME}&TABLENAME=${TABLE1_NAME}&USER=${USER}&PASSWORD=${PASSWORD})

8. ${check} Siga los pasos de [Obtención de una copia local (checkout)](../../PROC/005/procVC00PROC005.html?WCNAME=${WCNAME}&TABLENAME=${TABLE2_NAME})

9. ${check} Cierre el cuadro de diálogo "Obtener copia local (checkout)".

10. ${check} En la vista se habrá añadido las capas: 
    * ```${TABLE1_NAME}``` (TABLE1_NAME).
    * ```${TABLE2_NAME}``` (TABLE2_NAME).

11. MODIFICAR Y COMMITAR

CIERRA VETANA DE CAMBIOS inspecctor de errores Y SE DEjar LA VISTA EN PRIMER PLANO Y ACTIVA

