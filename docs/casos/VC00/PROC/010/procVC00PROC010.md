---
title: Alta de un usuario
proccode: VC00PROC010
srcpath: "casos/VC00/PROC/010/procVC00PROC010.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Este proceso registra en la tabla de usuarios un nuevo usuario, ```${NAME}```, además de su contraseña, ```${PASSWORD}```,
y las operaciones que puede realizar sobre los datos, ```${OPERATIONS}```.

### Datos de entrada

1. ${check} **NAME**=```${NAME}```. Nombre del nuevo usuario a registrar.

2. ${check} **PASSWORD**=```${PASSWORD}```. Contraseña del nuevo usuario a registrar.

3. ${check} **OPERATIONS**=```${OPERATIONS}```. Operaciones que puede realizar el nuevo usuario sobre la base de datos.


### Pasos

1. ${check} Una vez abierta la tabla y estando esta activa se procede a añadir en esta un nuevo registro o usuario. Para ello 
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

8. ${check} Indroduce el nombre del nuevo usuario, ```${NAME}```, en el campo correspondiente, Idetifier.

9. ${check} Indroduce la contraseña del nuevo usuario, ```${PASSWORD}```, en el campo correspondiente, Contraseña.

10. ${check} Indroduce las operaciones permitidas del nuevo usuario, ```${OPERATIONS}```,
    en el campo correspondiente, Allowed operatios.

11. ${check} Pulse el icono con la etiqueta "Guardar".

12. ${check} Para terminar el proceso y trás guardar cambios hay que terminar la edición. Para terinar la edición pulse 
    el icono con la etiqueta "Terminar edición". Este se encuentra la zona media de los iconos. 

13. ${check} Cierre el formulario.

14. ${check} Cierre la tabla en cuestión


### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
