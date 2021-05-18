---
title: Subir cambios en una capa con un plan topológico asociado (que no pasen el plan)
proccode: VC00TP00CP0002
srcpath: "casos/VC00/TP00/CP002/testVC00TP00CP002.md"
---

{% include es/header.md %}

{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo" %}

{% include parameter.html name="TPNAME" value="ProvinciasDebenTenerPoblaciones" %}

{% include parameter.html name="LAYER1_NAME" value="esp_provincias" %}

{% include parameter.html name="LAYER2_NAME" value="esp_poblaciones" %}


## {{ page.title }}

### Descripción

Este proceso prueba que no es posible hacer un commit de una capa con un plan topológico asociado sin que los
datos a "commitar" cumplan dicho plan topologico.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia nueva de trabajo sobre la cual se realizará un checkout.

1. ${check} **TPNAME**=```${TPNAME}```. Nombre del plan topológico a asignar.

1. ${check} **LAYER1_NAME**=```${LAYER1_NAME}```. Capa se va a editar y no se va a poder commitar
   por tener asignado un plan de topología que no va a cumplir tras la edición.

1. ${check} **LAYER2_NAME**=```${LAYER2_NAME}```. 

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya versión sea la indicada en el plan de pruebas.

1. ${check} El complemento de VCSGis debe estar instalado y activo.

1. ${check} El complemento de Topología debe estar instalado y activo.

1. ${check} El caso de prueba [VC00TP00CP001, "Asociar un plan topológico a una capa"](../../TP00/CP001/testVC00TP00CP001.md),
   ha pasado sin errores.

### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas (hace menos de 1 hora) 
   [VC00TP00CP001, "Asociar un plan topológico a una capa"](../../TP00/CP001/testVC00TP00CP001.md)
    y no ha cerrado gvSIG, continúe con el paso 2. Si no, ejecútelo antes de continuar.

2. ${check} Si no esta activa, active la aplicación gvSIG desktop  ```Cliente```.

3. ${check} La vista "Sin titulo" deberá estar activa y cargada la capa ```${LAYER2_NAME}``` (LAYER2_NAME).
   
4. ${check} Cargue la capa ``${LAYER1_NAME}``` (LAYER1_NAME) siguiendo los pasos de 
    [añadir capa de base de datos](../../PROC/022/procVC00PROC022.html?CONNAME=${WORKINGCOPY}&TABLENAME=${LAYER1_NAME}) 

5. ${check} Seleccione la capa ```${LAYER1_NAME}``` (LAYER1_NAME) en el ToC.

6. ${check} Seleccione la opción de menú "Capa/Comenzar edición".

7. ${check} Seleccione la provincia de "Valencia" y desplácela fuera del área de la península ibérica hasta
    asegurarse de que no solape con ningún punto de la capa de ```${LAYER2_NAME}``` (LAYER2_NAME).

8. ${check} Si no lo está seleccione la capa ```${LAYER1_NAME}``` (LAYER1_NAME) en el ToC.

9. ${check} Seleccione la opción de menú "Capa/Terminar edicion" (end_editingJList).

10. ${check} Aparecerá una ventana de titulo "Terminar edición".

11. ${check} Seleccione la opción "Guardar".

12. ${check} Seleccione la opción de menú "Herramientas/VCSGis/Mostrar cambios".

13. ${check} Se presentará una ventana de título  "VCSGis Cambios".

14. ${check} Seleccione la copia de trabajo ```${WORKINGCOPY}``` (WORKINGCOPY).

15. ${check} Se muestra el contenido de la pestaña "Copia de trabajo" donde podrá apreciar,
    a la izquierda, un selector en forma de árbol (selector de entidades) que contiene la categoría que le 
    puso a la capa cuando la añadió y, bajo ésta, la capa añadida a la copia de trabajo.
    A la derecha se habrá mostrado una tabla vacía (tabla de cambios) y sobre ésta los botones de "Refrescar",
    "Revertir", "Commit", "Resaltar", "Centrar", "Zoom", "Limpiar geometrías resaltadas" y "Mostrar formulario".

16. ${check} Pulse la casilla de verificación asociada a la capa ```${LAYER1_NAME}``` (LAYER1_NAME).

17. ${check} En la tabla de cambios se muestran los cambios que se deben subir al repositorio, 
    habilitándose también los botones de "Refrescar", "Revertir" y "Commit".

18. ${check} Introduzca en el campo "Fecha de entra en vigor" la fecha <code id="EFECTIVEDATE" class="language-plaintext highlighter-rouge">3/05/2021</code> {% include var_copy.html var="EFECTIVEDATE"%}

19. ${check} Introduzca en el campo "Comentario" el texto <code id="COMMENT" class="language-plaintext highlighter-rouge">Modificación de la capa de ${LAYER1_NAME}</code> {% include var_copy.html var="COMMENT"%}

20. ${check} Pulse el botón de "Commit"

21. ${check} Se mostrará una ventana de titulo "Inspector de errores del Plan de topología (${TPNAME})".
    
22. ${check} Se mostrará una ventana que indica que es imposible realizar la 
    acción de commit puesto que hay elementos  de la capa ```${LAYER1_NAME}``` (LAYER1_NAME) que no cumplen el 
    plan topológico ```${TPNAME}``` (TPNAME).
    
23. ${check} Pulse el botón de "Aceptar"

24. ${check} Cierre la ventana titulada "Inspector de errores del Plan de topología (${TPNAME})".

25. ${check} Cierre la ventana titulada "Mostrar cambios".

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
