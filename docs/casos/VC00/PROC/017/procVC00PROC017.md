---
title: Exportar una revisión concreta de una capa con autenticación
proccode: procVC00PROC017
srcpath: "casos/VC00/PROC/017/procVC00PROC017"
---

**--- EN CONSTRUCCIÓN ---**

{% include es/header.md %}

{% include parameter.html name="WCNAME2" value="CopiaDeTrabajo2" %}

{% include parameter.html name="TABLENAME" value="esp_provincias" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}

{% include parameter.html name="REVISION" value="0" %}

{% include parameter.html name="EXPORTTABLENAME" value="ESP_PROVINCIAS_R0_XXXXXXX_XXXXXX_XXX" %}

## {{ page.title }}

### Descripción

Exportar una capa en el estado en que estuviese en una revisión concreta

### Datos de entrada

1. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia de trabajo donde se descargará la capa.

2. ${check} **TABLENAME**=```${TABLENAME}```. Nombre de la tabla a descargar

3. ${check} **USER**=```${USER}```. Nombre de usuario

4. ${check} **PASSWORD**=```${PASSWORD}```. Contraseña de usuario

5. ${check} **REVISION**=```${REVISION}```. Fecha

6. ${check} **EXPORTTABLENAME**=```${EXPORTTABLENAME}```. Nombre de la tabla exportada


### Pasos

1. ${check} Al iniciarse este procedimiento deberá estar abierta la ventana de exportación con título "Exportar".

2. ${check} Asímismo, deberá estar abierta una vista de gvSIG.

3. ${check} En el cuadro desplegable "Copia de trabajo" seleccione ```${WCNAME}```(WCNAME).

4. ${check} Se mostrará el cuadro de diálogo con título "Inicio de sessión de usuario"

5. ${check} En el cuadro de texto "Usuario" introduzca ```${USER}```(USER)

6. ${check} En el cuadro de texto "Contraseña" introduzca ```${PASSWORD}```(PASSWORD)

7. ${check} Pulse el botón "Aceptar"

8. ${check} En la lista de tabla habrá aparecido la tabla ```${TABLENAME}```(TABLENAME)

9. ${check} Selecciónela.

10. ${check} Se habrán habilitado los siguientes controles:
  * "Fecha de entrada en vigor"
  * "Revisión"
  * "No añadir la capa al proyecto"
  * "Añadir capa a la vista" (deberá estar seleccionado) y un cuadro desplegable de vistas en el que esté seleccionada la vista del paso 2
  * "Añadir la tabla al proyecto

11. ${check} Pulse sobre "Revisión"

12. ${check} Se habrá habilitado el botón de selección de revisión que está a la derecha.

13. ${check} Pulse en el botón de selección de revisión

14. ${check} Seleccione la revisión ```${REVISION}```(REVISION)

15. ${check} Pulse el botón "Aceptar"

15. ${check} Se habrá cerrado el selector de revisiones. Habrá aparecido la revisión y su fecha en el cuadro de texto.

14. ${check} En el cuadro de texto "Nombre de la tabla" aparecerá un nombre propuesto calculado a partir de el nombre en mayúsculas de la tabla a exportar ${TABLENAME}```(TABLENAME)``` y de la revisión seleccionada ```${EXPORTTABLENAME}```(EXPORTTABLENAME) (este nombre dependerá de en qué momento se creó la revisión).

15. ${check} Pulse el botón "Exportar"

12. ${check} El cuadro de diálogo habrá mostrado el proceso de descarga en su barra de estado.

13. ${check} Se habrán deshabilitado todos los controles relacionados con la adición de la capa al proyecto.

15. ${check} Se habrá añadido a la vista seleccionada la capa ```${EXPORTTABLENAME}```(EXPORTTABLENAME).

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
