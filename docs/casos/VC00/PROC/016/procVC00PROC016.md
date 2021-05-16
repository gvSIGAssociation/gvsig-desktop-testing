---
title: Exportar una capa a una fecha concreta sin autenticación
proccode: procVC00PROC016
srcpath: "casos/VC00/PROC/016/procVC00PROC016"
---

{% include es/header.md %}

{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo" %}

{% include parameter.html name="TABLENAME" value="esp_provincias" %}

{% include parameter.html name="DATE" value="01/01/2021" %}

{% include parameter.html name="EXPORTTABLENAME" value="ESP_PROVINCIAS_20210101_000000_0" %}

## {{ page.title }}

### Descripción

Exportar una capa en el estado en que estuviese en una fecha concreta

### Datos de entrada

1. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia de trabajo donde se descargará la capa.

2. ${check} **TABLENAME**=```${TABLENAME}```. Nombre de la tabla a descargar

5. ${check} **DATE**=```${DATE}```. Fecha

6. ${check} **EXPORTTABLENAME**=```${EXPORTTABLENAME}```. Nombre de la tabla exportada


### Pasos

1. ${check} Al iniciarse este procedimiento deberá estar abierta la ventana de exportación con título "Exportar".

2. ${check} Asímismo, deberá estar abierta una vista de gvSIG.

3. ${check} En el cuadro desplegable "Copia de trabajo" seleccione ```${WORKINGCOPY}```(WORKINGCOPY).

8. ${check} En la lista de tabla habrá aparecido la tabla ```${TABLENAME}```(TABLENAME)

9. ${check} Selecciónela.

10. ${check} Se habrán habilitado los siguientes controles:
  * "Fecha de entrada en vigor"
  * "Revisión"
  * "No añadir la capa al proyecto"
  * "Añadir capa a la vista" (deberá estar seleccionado) y un cuadro desplegable de vistas en el que esté seleccionada la vista del paso 2
  * "Añadir la tabla al proyecto

11. ${check} Seleccione la opción "Fecha de entrada en vigor"

12. ${check} Se habrá habilitado, tanto el cuadro de texto como el botón de selección de fecha adjunto.

13. ${check} Pulse en el botón de selección de fecha e introduzca la fecha ```${DATE}```(DATE)

14. ${check} En el cuadro de texto "Nombre de la tabla" aparecerá un nombre propuesto calculado a partir de el nombre de la tabla a exportar y la fecha seleccionada ```${EXPORTTABLENAME}```(EXPORTTABLENAME).

15. ${check} Pulse el botón "Exportar"

12. ${check} El cuadro de diálogo habrá mostrado el proceso de descarga en su barra de estado.

13. ${check} Se habrán deshabilitado todos los controles relacionados con la adición de la capa al proyecto.

15. ${check} Se habrá añadido a la vista seleccionada la capa ```${EXPORTTABLENAME}```(EXPORTTABLENAME).

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
