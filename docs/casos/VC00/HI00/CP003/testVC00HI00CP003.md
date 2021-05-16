---
title: Importar historial (repositorio remoto con autorización)
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

Este proceso importa el historial ```${TABLE_NAME}``` (TABLE_LINK) en la copia de trabajo ```${WCNAME}``` (WCNAME).

### Datos de entrada

1. ${check} **TMPFOLDER**=```${TMPFOLDER}```. Carpeta en la que se crearán los archivos que se precisen 
   durante la ejecución del test. Deberemos tener permiso de escritura en ella. 

2. ${check} Archivo de datos: ```${TABLE_NAME}``` (${TABLE_LINK}). Tabla de datos que contiene el historial. 

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

2. ${check} Si no esta activa activaremos la aplicación gvSIG Desktop ```Cliente```.

3. Seleccione la opción "Mostrar/Gestor de proyecto".

5. ${check} Seleccione el tipo de documento "Tabla".

6. ${check} Pulse el botón "Nuevo".

7. ${check} Se mostrara la ventana de diálogo titulada "Nueva tabla". 

8. ${check} Seleccione la pestaña "Archivo".

9. ${check} Pulse en el boton "Añadir".

10. ${check} Se mostrara el diálogo para seleccionar un fichero. 
    Seleccione el fichero correspondiente a ```${TABLE_NAME}``` (${TABLE_LINK}) y pulse el boton "Abrir" que cerrara este dialogo.

11. ${check} De vuelta en el dialogo de "Nueva tabla" pulse el botón "Aceptar".

12. ${check} Seleccione la opción de menú "Herramientas/VCSGis/Importar historial".

13. ${check} Se presentara una ventana de título  "Importar historial".

14. ${check} En el desplegable del campo "Copia de trabajo" seleccione el valor ```${WORKINGCOPY}``` (WORKINGCOPY).
    Si no existe aborte el caso de prueba.

4. ${check} Si le aparece un dialogo con título "Inicio de sessión de usuario":
   * ${check} En el cuadro de texto "Usuario" introduzca ```${USER}```(USER) {% include var_copy.html var="USER"%}
   * ${check} En el cuadro de texto "Contraseña" introduzca ```${PASSWORD}```(PASSWORD) {% include var_copy.html var="PASSWORD"%}
   * ${check} Pulse el botón "Aceptar"

17. ${check} En la ventana de título  "Importar historial" active la pestaña "Tablas" y seleccione
    la opción ```${TABLE_NAME}``` (TABLE_LINK). Si esta no existe aborte el procedimiento.

18. ${check} Debera aparecer marcado el check "Añadir la tabla nueva el proyecto".

19. ${check} Debera aparecer el campo "nombre" con en el valor ```${TABLE_NAME}``` (TABLE_NAME).

20. ${check} En el desplegable del campo "Campo para etiqueta" seleccione el valor ```${FIELDFORLABEL}``` (FIELDFORLABEL). 
   Si no existe aborte el caso de prueba.

21. ${check} En el campo para "Etiqueta" no especifique nada.

22. ${check} En el campo "Categoria" introduzca el valor ```${CATEGORY}``` (CATEGORY) {% include var_copy.html var="CATEGORY"%}.

23. ${check} En el desplegable del campo "Campo del intedificador" seleccione el valor ```${IDENTIFICADOR}``` (IDENTIFICADOR).
    Si no existe aborte el caso de prueba.

24. ${check} En el desplegable del campo "Campo contador" seleccione el valor ```${CONTADOR}``` (CONTADOR).
    Si no existe aborte el caso de prueba.

25. ${check} Seleccione la opción "Usar fecha de revisión".

26. ${check} En el desplegable del campo "Campo de fecha de revisión" seleccione el valor ```${REVISION}``` (REVISION).

27. ${check} Pulse el boton "Importar historial".

28. ${check} Tras la importación del historial, pulse el botón "Cerrar". 

30. ${check} Seleccione la opcion de menu "Herramientas/VCSGis/Mostrar revisiones".

13. ${check} Se presentara una ventana de título  "Revisiones".

13. ${check} Se presentara una ventana de título  "Importar historial".

14. ${check} En el desplegable del campo "Copia de trabajo" seleccione el valor ```${WORKINGCOPY}``` (WORKINGCOPY).
    Si no existe aborte el caso de prueba.

14. ${check} En el desplegable del campo "Tabla" seleccione el valor ```${TABLE_NAME}``` (TABLE_NAME).
    Si no existe aborte el caso de prueba.
    
14. ${check} En la tabla de la parte inferior del dialogo deberan haber aperecido XXX lineas.

14. ${check} Cierre el dialogo de titulo "Revisiones".

### Resultado esperado

{% include es/expectedresult_proc.md %}

### Reportar fallo

{% include es/reportbug_proc.md %}

{% include es/footer.html %}
