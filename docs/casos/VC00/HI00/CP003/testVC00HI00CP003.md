---
title: Importar historial (repositorio remoto en H2 con autorización)
proccode: VC00HI00CP0003
srcpath: "casos/VC00/HI00/CP003/testVC00HI00CP003.md"
---


**EN CONSTRUCCION**

{% include es/header.md %}

{% include parameter.html name="TABLE_NAME" value="reservas" %}

{% include parameter.html name="TABLE_LINK" value="<a href='../../data/reservas.csv'>RESERVAS</a>" %}

{% include parameter.html name="CATEGORY" value="Historial" %}

{% include parameter.html name="WCNAME" value="CopiaDeTrabajo" %}

{% include parameter.html name="REPONAME" value="RepositorioAuth" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="FIELDFORLABEL" value="extinca" %}

{% include parameter.html name="IDENTIFICADOR" value="extinca" %}

{% include parameter.html name="CONTADOR" value="id" %}

{% include parameter.html name="REVISION" value="revisiondate" %}



## {{ page.title }}

### Descripción

Este proceso define un modelo de datos, ```${MODEL}``` (MODEL), con las capas ```esp_provincias``` y ```esp_poblaciones``` y la tabla ```${TABLE_NAME}``` (TABLE_LINK). Tras definirlo
se procede a descargar dicho modelo en la copia de trabajo ```${WCNAME2}``` (WCNAME2).

### Datos de entrada

1. ${check} **TMPFOLDER**=```${TMPFOLDER}```. Carpeta en la que se crearán los archivos que se precisen 
   durante la ejecución del test. Deberemos tener permiso de escritura en ella. 

2. ${check} Archivo de datos: ```${TABLE_NAME}``` (${TABLE_LINK}). Tabla de datos a añadir al modelo ```${MODEL}``` (MODEL). 

3. ${check} **FIELDFORLABEL**=```${FIELDFORLABEL}```. Nombre del campo de la tabla a añadir
   a usar en "Campo para etiqueta".

4. ${check} **CATEGORY**=```${CATEGORY}```. Categoria a asignar la tabla.

5. ${check} **IDENTIFICADOR**=```${IDENTIFICADOR}```. Campo del identificador del elemento.

6. ${check} **CONTADOR**=```${CONTADOR}```. Campo contador.

7. ${check} **REVISION**=```${REVISION}```. Campo que indica la fecha de revisión del elemento.

8. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexión y del repositorio.

9. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia de trabajo sobre la que se realiza el 
   proceso de registrar el modelo.

10. ${check} **USER**=```${USER}```. Identificador de usuario.

11. ${check} **PASSWORD**=```${PASSWORD}```. Contraseña de usuario.

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya versión sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} El caso de prueba 
   [VC00CW00CP002, "Inicializacion de una copia de trabajo (repositorio remoto en H2 con autorización)"](../../CW00/CP002/testVC00WC00CP002.md),
   ha pasado sin errores.
   
### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas (hace menos de 1 hora) VC00CW00CP002,
    "Inicializacion de una copia de trabajo (repositorio remoto en H2 con autorización)"
    y no ha cerrado gvSIG, continúe con el paso 2. Si no, ejecútelo antes de continuar.

2. ${check} Asegúrese de estar en la aplicación gvSIG Desktop ```cliente```.

3. ${check} La copia de trabajo ```${WCNAME}``` (WCNAME) no dispone de información por lo que se busca cargar en ella un historial.

4. ${check} Para ello hay que cargar la tabla de historial en gvSIG Desktop. Seleccione la opción "Mostrar/Gestor de proyecto".

5. ${check}Marque la opción "Tabla".

6. ${check} Pulse el botón "Nuevo". Solo tiene que estas ese habilitado.

7. ${check} Como resultado de lo anterior se muestra una ventana de diálogo titulada "Nueva Tabla". 

8. ${check} De las pestañas situadas en la zona superior de la ventana seleccione la opción "Archivo".

9. ${check} De los botones situados en la zona derecha de la ventana seleccione la opción "Añadir".

10. ${check} Se presenta un cuadro de diálogo para seleccionar un fichero. 
    Seleccione el correspondiente a ```${TABLE_NAME}``` (${TABLE_LINK}).

11. ${check} Pulse el botón "Aceptar" situado en la zona inferior del cuadro de diálogo.

12. ${check} Ejecute la opción "Herramientas/VCSGis/Importar historial".

13. ${check} Se visualiza la ventana que los parámetros necesarios para realizar la importación
   de título  "Importar historial".

14. ${check} En el desplegable del campo "Copia de trabajo" debera existir una 
   entrada ```${WCNAME}``` (WCNAME). Si existe seleccionela. Si no existe
   termine el procedimiento.
   
15. ${check} Se habrá presentado la ventana de título "Inicio de sesión de usuario".

16. ${check} Introduzca en el campo de texto "Usuario" el valor ```${USER}``` (USER) y en el "Contraseña" ```${PASSWORD}``` (PASSWORD).

17. ${check} Active la pestaña "Tablas" y seleccione
    la opción ```${TABLE_NAME}``` (TABLE_LINK). Si esta no existe termine el procedimiento.

18. ${check} Debera aparecer marcado el check "Añadir la tabla nueva el proyecto".

19. ${check} Debera aparecer en el valor del campo "nombre" ```${TABLE}``` (TABLE).

20. ${check} En el desplegable del  campo "Campo para etiqueta" introduzca 
   la opción ```${FIELDFORLABEL}``` (FIELDFORLABEL). 
   Si esta no existe termine el procedimiento.

21. ${check} En el campo para "Etiqueta" no especifique nada.

22. ${check} En el campo "Categoria" introduzca el valor ```${CATEGORY}``` (CATEGORY).

23. ${check} En el campo "Campo del intedificador" introduzca el valor ```${IDENTIFICADOR}``` (IDENTIFICADOR).

24. ${check} En el campo "Campo contador" introduzca el valor ```${CONTADOR}``` (CONTADOR).

25. ${check} Marque la opción "Usar fecha de revisión".

26. ${check} Seleccione en el campo "Campo de fecha de revisión" el valor ```${REVISION}``` (REVISION).

27. ${check} Pulse el boton "Importar historial".

28. ${check} Tras la importación del historial, pulse el botón "Cerrar". Una vez ejecutado lo anterior la copia de trabajo ```${WCNAME}``` (WCNAME) dispone del
    historial. Hay que especificar que el proceso de importación también realiza commits por lo que el repositorio también dispone del historial.

29. ${check} La vista "Sin título" se queda activa y vacía.



### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
