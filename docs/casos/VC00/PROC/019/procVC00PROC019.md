---
title: Eliminar copia local del registro
proccode: VC00PROC019
srcpath: "casos/VC00/PROC/019/procVC00PROC019.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Este proceso elimina una copia de trabajo del registro de copias de trabajo.

### Datos de entrada

1. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia de trabajo a eliminar.


### Pasos

5. ${check} Seleccione la opción de menú "Herramientas/VCSGis/Administración/Registrar copia de trabajo".

6. ${check} Se mostrará la venta de la gestion de registro de copia de trabajo, con el titulo "Registrar copia de trabajo".

7. ${check} Si en la lista aparece una de nombre ```${WORKINGCOPY}```, la seleccionaremos y pulsaremos el boton "Eliminar".

8. ${check} Cerraremos la ventana "Registrar copia de trabajo" pulsando en el aspa de arriba a la derecha,


### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
