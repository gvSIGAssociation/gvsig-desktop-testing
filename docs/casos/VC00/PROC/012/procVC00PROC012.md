---
title: Obtención de una revisión de una tabla desde repositorio sin autenticación
proccode: procVC00PROC005
srcpath: "casos/VC00/PROC/012/procVC00PROC012"
---

{% include es/header.md %}

{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo" %}

{% include parameter.html name="TABLENAME" value="esp_provincias" %}

{% include parameter.html name="REVISION" value="0" %}

{% include parameter.html name="OVERWRITE" value="si" %}

## {{ page.title }}

### Descripción

Obtiene una copia local de una revisiónde una capa existente en 

### Datos de entrada

1. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia de trabajo donde se descargará la capa.

2. ${check} **TABLENAME**=```${TABLENAME}```. Nombre de la tabla a descargar

3. ${check} **REVISION**=```${REVISION}```. Revision de la tabla a descargar

### Pasos

1. ${check} Al iniciarse este procedimiento deberá estar abierta la ventana de obtención de una copia local con título "Obtener copia local (checkout)".

2. ${check} Asímismo, deberá estar abierta una vista de gvSIG.

3. ${check} En el cuadro desplegable "Copia de trabajo" seleccione ```${WORKINGCOPY}```(WORKINGCOPY).

4. ${check} En la lista de tabla habrá aparecido la tabla ```${TABLENAME}```(TABLENAME)

5. ${check} Selecciónela.

6. ${check} Se habrán habilitado los siguientes controles:
  * Sobrescribir tabla
  * "No añadir la capa al proyecto"
  * "Añadir capa a la vista" (deberá estar seleccionado) y un cuadro desplegable de vistas en el que esté seleccionada la vista del paso 2
  * "Añadir la tabla al proyecto

7. ${check} La casilla de verificación "Sobreescribir tabla" ${OVERWRITE} estará seleccionado.

8. ${check} Pulse el botón de seleccionar revisión. Se mostrará un diálogo de selección de revisiones de la tabla.

9. ${check} Seleccione la revisión ```${REVISION}```(REVISION)

10. ${check} Pulse el botón "Aceptar"

11. ${check} En el cuadro de texto "Revisión" habrá aparecido el número de revisión seguido de su fecha.

12. ${check} Pulse el botón "Obtener copia local (checkout)"

13. ${check} El cuadro de diálogo habrá mostrado el proceso de descarga en su barra de estado.

14. ${check} Y se habrá añadido a la vista seleccionada la capa ```${TABLENAME}```(TABLENAME) en el estado en que estaba en la revisión seleccionada.

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}

