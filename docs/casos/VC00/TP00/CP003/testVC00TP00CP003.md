---
title: Subir cambios en una capa con un plan topológico (que sí pasen el plan)
proccode: VC00TP00CP0003
srcpath: "casos/VC00/TP00/CP003/testVC00TP00CP003.md"
---

{% include es/header.md %}


{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo" %}

{% include parameter.html name="TPNAME" value="ProvinciasDebenTenerPoblaciones" %}

{% include parameter.html name="LAYER1_NAME" value="esp_provincias" %}

{% include parameter.html name="LAYER1_EFECTIVEDATE" value="5/05/2021" %}

{% include parameter.html name="LAYER2_NAME" value="esp_poblaciones" %}

## {{ page.title }}

### Descripción

Este caso de prueba comprueba que se pueden subir cambios a una capa que tiene asignado un plan de topología
cuando la capa cumple dicho plan topológico.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada
  
1. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia nueva de trabajo sobre la cual se realizará un checkout.

1. ${check} **TPNAME**=```${TPNAME}```. Nombre del plan topológico a asignar.

1. ${check} **LAYER1_NAME**=```${LAYER1_NAME}```. Capa que se va editar y commitar.

1. ${check} **LAYER1_EFECTIVEDATE**={% include var_tag.html var="LAYER1_EFECTIVEDATE" %}. Fecha a usar al realizar el commit de las modificaciones en la capa ```${LAYER1_NAME}```.

1. ${check} **LAYER2_NAME**=```${LAYER2_NAME}```. 


### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya versión sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} El complemento de Topología debe estar instalado y activo.

4. ${check} El caso de prueba 
   [VC00TP00CP002, "Subir cambios en una capa con un plan topológico (que no pasen el plan)"](../../TP00/CP002/testVC00TP00CP002.md),
   ha pasado sin errores.

### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas (hace menos de 1 hora) VC00TP00CP002,
    "Subir cambios en una capa con un plan topológico (que no pasen el plan)"
    y no ha cerrado gvSIG, continúe con el paso 2. Si no, ejecútelo antes de continuar.

2. ${check} Si no esta activa, active la aplicación gvSIG desktop  ```Cliente```.

3. ${check} La vista "Sin titulo" deberá estar activa y cargadas las capas ```${LAYER1_NAME}``` (LAYER1_NAME) y ```${LAYER2_NAME}``` (LAYER2_NAME).

4. ${check} Seleccione la capa ```${LAYER1_NAME}``` (LAYER1_NAME) en el ToC.

5. ${check} Seleccione la opción de menú "Capa/Comenzar edicion".

6. ${check} Seleccione la provincia de "Valencia" y desplácela dentro del área de la península ibérica hasta
    asegurarse de que solape con algún punto de la capa de ```${LAYER2_NAME}``` (LAYER2_NAME).

7. ${check} Si ya solapa, seleccione la capa ```${LAYER1_NAME}``` (LAYER1_NAME) en el ToC.

8. ${check} Seleccione la opción de menú "Capa/Terminar edicion" (end_editingJList).

9. ${check} Aparecerá una ventana de titulo "Terminar edición".

10. ${check} Seleccione la opción "Guardar".

11. ${check} Seleccione la opción de menú "Herramientas/VCSGis/Mostrar cambios".

12. ${check} Se presentará una ventana de título  "VCSGis Cambios".

13. ${check} Seleccione la copia de trabajo ```${WORKINGCOPY}``` (WORKINGCOPY).

14. ${check} Se muestra el contenido de la pestaña "Copia de trabajo" donde podrá apreciar,
    a la izquierda, un selector en forma de árbol (selector de entidades) que contiene la categoría que le 
    puso a la capa cuando la añadió y, bajo ésta, la capa añadida a la copia de trabajo.
    A la derecha se habrá mostrado una tabla vacía (tabla de cambios) y sobre ésta los botones de "Refrescar",
    "Revertir", "Commit", "Resaltar", "Centrar", "Zoom", "Limpiar geometrías resaltadas" y "Mostrar formulario".

15. ${check} Pulse la casilla de verificación asociada a la capa ```${LAYER1_NAME}``` (LAYER1_NAME).

16. ${check} En la tabla de cambios se muestran los cambios a commitar de esta capa en el repositorio, 
    habilitándose también los botones de "Refrescar", "Revertir" y "Commit".

17. ${check} Introduzca en el campo "Fecha de entra en vigor" la fecha ${LAYER1_EFECTIVEDATE} {% include var_copy.html var="LAYER1_EFECTIVEDATE"%}

18. ${check} Introduzca en el campo "Comentario" el texto <code id="COMMENT" class="language-plaintext highlighter-rouge">Modificación de la capa de ${LAYER1_NAME}</code> {% include var_copy.html var="COMMENT"%}

19. ${check} Pulse el botón de "Commit"

20. ${check} Se mostrará una ventana de titulo "Inspector de errores del Plan de topología (${TPNAME})" y se cerrará automaticamente.

21. ${check} Cierre la ventana titulada "Mostrar cambios".

22. ${check} Deje la vista "Sin título" en primer plano y activa.

    
### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
