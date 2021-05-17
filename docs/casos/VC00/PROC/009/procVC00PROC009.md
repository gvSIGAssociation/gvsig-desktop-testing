---
title: Alta de una variable
proccode: VC00PROC009
srcpath: "casos/VC00/PROC/009/procVC00PROC009.md"
---

**EN CONSTRUCCION**

{% include es/header.md %}

## {{ page.title }}

### Descripción

Este proceso da de alta una entrada en la tabla de variables del repositorio.

### Datos de entrada

1. ${check} **VARIABLE**={% include var_tag.html var="VARIABLE" %}. Nombre de la nueva variable a dar ed alta.

2. ${check} **VALUE**={% include var_tag.html var="VALUE" %}. Valor de a nueva variable.


### Pasos

1. ${check} Para iniciar el proceso debará estar abierta la tabla de variables del repositorio.

2. ${check} Seleccione la opción de menú "Tabla/Show form". 

3. ${check} Se mostrará una ventana con el formulario asociado a la tabla de variables.

11. ${check} Pulse el boton "Comenzar edición" del formulario. 

12. ${check} Pulse el boton "Nuevo" del formulario.

8. ${check} Indroduzca en el campo "Nombre" el valor ```${VARIABLE}``` {% include var_copy.html var="VARIABLE"%}.

9. ${check} Indroduzca en el campo "Valor" el valor  ```${VALUE}``` {% include var_copy.html var="VALUE"%}.

10. ${check} Pulse el boton "Guardar" del formulario.

11. ${check} Pulse el boton "Terminar edición" del formulario. 

12. ${check} Se presentará una ventana, pulse en la opción "Sí" para terminar edición y guardar los cambios.

13. ${check} Cierre el formulario.

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
