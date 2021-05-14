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

2. ${check} **VALUE**=```${VALUE}```. Valor de a nueva variable.


### Pasos

1. ${check} Para iniciar el proceso debará estar abierta la tabla de variables del repositorio.

2. ${check} Seleccione la opción de menú "Tabla/Show form". 

3. ${check} Se mostrará una ventana con el formulario asociado a la tabla de variables.

4. ${check} Para dar de alta un registro hay que iniciar la edición. Pulse el icono con la
   etiqueta "Comenzar edición". Los iconos se muestran en la zona inferior de la ventana y el de comenzar edición se
   encuentra en la zona media de estos. Al hacerlo se habilitaran otros iconos.

6. ${check} Pulse el icono con la etiqueta "Nuevo". Al hacerlo algunos de los campos del formulario se muestrarán
    sin datos.

8. ${check} Indroduzca el valor del nombre, ```${VARIABLE}``` en el campo "Nombre"  {% include var_copy.html var="VARIABLE"%}.

9. ${check} Indroduzca el valor, ```${VALUE}```, en el campo "Valor".

10. ${check} Pulse el icono con la etiqueta "Guardar".

11. ${check} Pulse el icono con la etiqueta "Terminar edición". 

12. ${check} Se presentrara una ventana, pulse en la opción "Si". Dicha opción termina edición y guarda los cambios.

13. ${check} Cierre el formulario.

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
