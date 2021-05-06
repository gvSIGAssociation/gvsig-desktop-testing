---
title: Alta de una variable
proccode: VC00PROC009
srcpath: "casos/VC00/PROC/009/procVC00PROC009.md"
---

**EN CONSTRUCCION**

{% include es/header.md %}

## {{ page.title }}

### Descripción

Este proceso registra en la tabla de variables una nueva entrada o variable, ```${VARIABLE}```,
además de su valor correspondiente, ```${VALUE}```.

### Datos de entrada

1. ${check} **VARIABLE**=```${VARIABLE}```. Nombre de la nueva variable a registrar.

2. ${check} **VALUE**=```${VALUE}```. Valor de a nueva variable.


### Pasos

1. ${check} Una vez abierta la tabla y estando esta activa se procede a añadir en esta un nuevo registro. Para ello 
    seleccione "Tabla" en el menú de gvSIG Desktop.

2. ${check} Seleccione del despeglable anterior la opción "Show form". 

3. ${check} Como resultado se genera una nueva ventana que muestra el formulario asociado a la tabla de variables.

4. ${check} Para registrar cambios en esta hay que iniciar la edición. Para iniciar la edición pulse el icono con la
   etiqueta "Comenzar edición". Los iconos se muestran en la zona inferior de la ventana y el de comenzar edición se
   encuentra en la zona media de estos.

5. ${check} La acción anterior habilita una serie de iconos.

6. ${check} Pulse el icono con la etiqueta "Nuevo" recientemente habilitado.

7. ${check} Como consecuencia de lo anterior, algunos de los campos de la página actual del formulario se muestran
    sin datos a la espera de la nueva información.

8. ${check} Indroduce el nombre del nuevo registro, ```${VARIABLE}``` en el campo correspondiente.

9. ${check} Indroduce el valor del nuevo registro, ```${VALUE}```, en el campo correspondiente.

10. ${check} Pulse el icono con la etiqueta "Guardar".

11. ${check} Para terminar el proceso y trás guardar cambios hay que terminar la edición. Para terinar la edición pulse 
    el icono con la etiqueta "Terminar edición". Este se encuentra la zona media de los iconos. 

12. ${check} Como consecuencia de lo anterior se despliega una ventana, pulse en la opción "Guardar".

13. ${check} Cierre el formulario.

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
