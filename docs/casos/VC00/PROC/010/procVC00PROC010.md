---
title: Alta de un usuario
proccode: VC00PROC010
srcpath: "casos/VC00/PROC/010/procVC00PROC010.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Este proceso registra en la tabla de usuarios un nuevo usuario. Le indicaremos su nombre, clave y las operaciones
que tendrá pemitidas realizar.

### Datos de entrada

1. ${check} **NAME**=```${NAME}```. Nombre del nuevo usuario.

2. ${check} **PASSWORD**=```${PASSWORD}```. Contraseña del nuevo usuario.

3. ${check} **OPERATIONS**=```${OPERATIONS}```. Operaciones que puede realizar el nuevo usuario sobre la base de datos.


### Pasos

1. ${check} Para iniciarse este proceso debera estar abierta la tabla de usuarios del repositorio.

2. ${check} Seleccione la opción de menú "Tabla/Show form". 

3. ${check} Se mostrará una ventana con el formulario asociado a la tabla de variables.

4. ${check} Para dar de alta un registro hay que iniciar la edición. Pulse el icono con la
   etiqueta "Comenzar edición". Los iconos se muestran en la zona inferior de la ventana y el de comenzar edición se
   encuentra en la zona media de estos. Al hacerlo se habilitaran otros iconos.

6. ${check} Pulse el icono con la etiqueta "Nuevo". Al hacerlo algunos de los campos del formulario se muestrarán
    sin datos.

8. ${check} Indroduzca el nombre del usuario, ```${NAME}```, en el campo "Identifier".

9. ${check} Indroduzca la clave del usuario, ```${PASSWORD}```, en el campo "Contraseña".

10. ${check} Indroduzca las operaciones permitidas del usuario, ```${OPERATIONS}```,
    en el campo  "Allowed operations".

10. ${check} Pulse el icono con la etiqueta "Guardar".

11. ${check} Pulse el icono con la etiqueta "Terminar edición". 

12. ${check} Se presentrara una ventana, pulse en la opción "Guardar".

13. ${check} Cierre el formulario.

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
