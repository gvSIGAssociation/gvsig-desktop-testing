---
title: Obtención de una copia local (checkout) desde repositorio con autenticación
proccode: procVC00PROC006
srcpath: "casos/VC00/PROC/006/procVC00PROC006.md"
---

{% include es/header.md %}

{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo" %}

{% include parameter.html name="TABLENAME" value="esp_provincias" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}

## {{ page.title }}

### Descripción

Obtiene una copia local de una capa existente en 

### Datos de entrada

1. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia de trabajo donde se descargará la capa.

1. ${check} **TABLENAME**=```${TABLENAME}```. Nombre de la tabla a descargar

1. ${check} **USER**={% include var_tag.html var="USER" %}.

1. ${check} **PASSWORD**={% include var_tag.html var="PASSWORD" %}.



### Pasos

1. ${check} Al iniciarse este procedimiento deberá estar abierta la ventana de 
   obtención de una copia local con título "Obtener copia local (checkout)".

2. ${check} Asímismo, deberá estar abierta una vista de gvSIG.

3. ${check} En el cuadro desplegable "Copia de trabajo" seleccione ```${WORKINGCOPY}```(WORKINGCOPY).

{%include es/conditional_login.md %}

8. ${check} En la lista de tablas habrá aparecido la tabla ```${TABLENAME}```(TABLENAME), selecciónela.

9. ${check} Se habrán habilitado los siguientes controles:
   * "No añadir la capa al proyecto", que no estara seleccionado.
   * "Añadir capa a la vista" (deberá estar seleccionado) y un cuadro desplegable de vistas en el que estara seleccionada una vista.
   * "Añadir la tabla al proyecto, que no estara seleccionado.

10. ${check} Pulse el botón "Obtener copia local (checkout)"

11. ${check} El cuadro de diálogo habrá mostrado el proceso de descarga en su barra de estado.

12. ${check} Se habrán deshabilitado todos los controles mencionados en el punto 9. 

13. ${check} Se habrá habilitado la casilla de verificación "Sobreescribir tabla", pero no estara seleccionada.

14. ${check} Y se habrá añadido a la vista seleccionada la capa ```${TABLENAME}```(TABLENAME).

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
