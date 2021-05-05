---
title: Obtención de una copia local (checkout) desde repositorio con autenticación
proccode: procVC00PROC006
srcpath: "casos/VC00/PROC/006/procVC00PROC006"
---

{% include es/header.md %}

{% include parameter.html name="WCNAME2" value="CopiaDeTrabajo2" %}

{% include parameter.html name="TABLENAME" value="esp_provincias" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}

## {{ page.title }}

### Descripción

Obtiene una copia local de una capa existente en 

### Datos de entrada

1. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia de trabajo donde se descargará la capa.

2. ${check} **TABLENAME**=```${TABLENAME}```. Nombre de la tabla a descargar

3. ${check} **USER**=```${USER}```. Nombre de la tabla a descargar

4. ${check} **PASSWORD**=```${PASSWORD}```. Nombre de la tabla a descargar


### Pasos

1. ${check} Al iniciarse este procedimiento deberá estar abierta la ventana de obtención de una copia local con título "Obtener copia local (checkout)".

2. ${check} Asímismo, deberá estar abierta una vista de gvSIG.

3. ${check} En el cuadro desplegable "Copia de trabajo" seleccione ```${WCNAME}```(WCNAME).

4. ${check} Se mostrará el cuadro de diálogo con título "Inicio de sessión de usuario"

5. ${check} En el cuadro de texto "Usuario" introduzca ```${USER}```(USER)

6. ${check} En el cuadro de texto "Contraseña" introduzca ```${PASSWORD}```(PASSWORD)

7. ${check} Pulse el botón "Aceptar"

8. ${check} En la lista de tabla habrá aparecido la tabla ```${TABLENAME}```(TABLENAME)

9. ${check} Selecciónela.

10. ${check} Se habrán habilitado los siguientes controles:
  * "No añadir la capa al proyecto"
  * "Añadir capa a la vista" (deberá estar seleccionado) y un cuadro desplegable de vistas en el que esté seleccionada la vista del paso 2
  * "Añadir la tabla al proyecto

11. ${check} Pulse el botón "Obtener copia local (checkout)"

12. ${check} El cuadro de diálogo habrá mostrado el proceso de descarga en su barra de estado.

13. ${check} Se habrán deshabilitado todos los controles mencionados en el punto 10. 

14. ${check} Se habrá habilitado la casilla de verificación "Sobreescribir tabla".

15. ${check} Y se habrá añadido a la vista seleccionada la capa ```${TABLENAME}```(TABLENAME).

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}