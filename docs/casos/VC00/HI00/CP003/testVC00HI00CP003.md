---
title: Importar historial (repositorio remoto con autorización)
proccode: VC00HI00CP0003
srcpath: "casos/VC00/HI00/CP003/testVC00HI00CP003.md"
---


{% include es/header.md %}

{% include parameter.html name="WORKINGCOPY" value="CopiaDeTrabajo" %}

{% include parameter.html name="TABLE_NAME" value="reservas" %}

{% include parameter.html name="TABLE_LINK" value="<a href='../../data/reservas.csv'>RESERVAS</a>" %}

{% include parameter.html name="CATEGORY" value="Señalizacion vertical" %}

{% include parameter.html name="FIELDFORLABEL" value="extinca" %}

{% include parameter.html name="IDENTIFICADOR" value="extinca" %}

{% include parameter.html name="CONTADOR" value="id" %}

{% include parameter.html name="REVISION" value="revisiondate" %}

{% include parameter.html name="USER" value="sara" %}

{% include parameter.html name="PASSWORD" value="sara1" %}


## {{ page.title }}

### Descripción

Este caso de prueba verifica que la herramienta de importacion de historial y consulta de revisiones funcionan
correctamente. Hay que tener en cuenta que el diseño de la herramienta de carga de historial esta limitado a
cargar los datos obtenidos a partir del INCA.


{% include es/checkifthereisalreadyabug.md %}


### Datos de entrada

1. ${check} **WORKINGCOPY**=```${WORKINGCOPY}```. Nombre de la copia de trabajo sobre la que se va a trabajar.

1. ${check} **TABLE_NAME**=```${TABLE_NAME}``` (${TABLE_LINK}). Tabla de datos que contiene los datos del 
   historico a cargar. 

1. ${check} **CATEGORY**=```${CATEGORY}```. Categoria a asignar la tabla al subirla al repositorio.

1. ${check} **FIELDFORLABEL**=```${FIELDFORLABEL}```. Nombre del campo a usar cuando se requiera etiquetar 
   un registro de la tabla```${TABLE_NAME}``` (TABLE_NAME).

1. ${check} **IDENTIFICADOR**=```${IDENTIFICADOR}```.

1. ${check} **CONTADOR**=```${CONTADOR}```.

1. ${check} **REVISION**=```${REVISION}```. Campo que indica la fecha de revisión del elemento.

1. ${check} **USER**={% include var_tag.html var="USER" %}.

1. ${check} **PASSWORD**={% include var_tag.html var="PASSWORD" %}.


### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya versión sea la indicada en el plan de pruebas.

1. ${check} El complemento de VCSGis debe estar instalado y activo.

1. ${check} El caso de prueba 
   "Inicializacion de una copia de trabajo" del plan de pruebas que esta ejecutando
   ha pasado sin errores.
   
### Pasos

1. ${check} Si acaba de ejecutar algunos de los sieguientes casos de prueba de su plan de pruebas:
    * Crear copia de trabajo.
    * Subir capa al repositorio (commit).
    * Asociar leyenda a una capa.
    * Cargar un plan topologico en el repositorio.
    * Asociar un plan topologico a una capa.
    * Subir cambios en una capa con un plan topologico asociado (que sí pasen el plan).
    * Obtener una revision concreta de una capa.
    * Exportar una capa a una fecha dada.
    * Exportar una capa a una revision dada.
    * Definir y descargar un modelo de datos.

   Y ha pasado correctamente continue con el paso 2.
   Si no, ejecúte alguno de estos antes de continuar.

2. ${check} Si no esta activa activaremos la aplicación gvSIG Desktop ```Cliente```.

3. ${check} Seleccione la opción "Mostrar/Gestor de proyecto".

4. ${check} Seleccione el tipo de documento "Tabla".

5. ${check} Pulse el botón "Nuevo".

6. ${check} Se mostrara la ventana de diálogo titulada "Nueva tabla". 

7. ${check} Seleccione la pestaña "Archivo".

8. ${check} Pulse en el boton "Añadir".

9. ${check} Se mostrara el diálogo para seleccionar un fichero. 
    Seleccione el fichero correspondiente a ```${TABLE_NAME}``` (${TABLE_LINK}) y pulse el boton "Abrir" que cerrara este dialogo.

10. ${check} De vuelta en el dialogo de "Nueva tabla" pulse el botón "Aceptar".

11. ${check} Seleccione la opción de menú "Herramientas/VCSGis/Importar historial".

12. ${check} Se presentara una ventana de título  "Importar historial".

13. ${check} En el desplegable del campo "Copia de trabajo" seleccione el valor ```${WORKINGCOPY}``` (WORKINGCOPY).
    Si no existe aborte el caso de prueba.

14. ${check} Si le aparece un dialogo con título "Inicio de sessión de usuario":
    * ${check} En el cuadro de texto "Usuario" introduzca ```${USER}```(USER) {% include var_copy.html var="USER"%}
    * ${check} En el cuadro de texto "Contraseña" introduzca ```${PASSWORD}```(PASSWORD) {% include var_copy.html var="PASSWORD"%}
    * ${check} Pulse el botón "Aceptar"

15. ${check} En la ventana de título  "Importar historial" active la pestaña "Tablas" y seleccione
    la opción ```${TABLE_NAME}``` (TABLE_LINK). Si esta no existe aborte el caso de prueba.

16. ${check} Debera aparecer marcado el check "Añadir la tabla nueva el proyecto".

17. ${check} Debera aparecer el campo "nombre" con en el valor ```${TABLE_NAME}``` (TABLE_NAME).

18. ${check} En el desplegable del campo "Campo para etiqueta" seleccione el valor ```${FIELDFORLABEL}``` (FIELDFORLABEL). 
   Si no existe aborte el caso de prueba.

19. ${check} En el campo para "Etiqueta" no especifique nada.

20. ${check} En el campo "Categoria" introduzca el valor ```${CATEGORY}``` (CATEGORY) {% include var_copy.html var="CATEGORY"%}.

21. ${check} En el desplegable del campo "Campo del intedificador" seleccione el valor ```${IDENTIFICADOR}``` (IDENTIFICADOR).
    Si no existe aborte el caso de prueba.

22. ${check} En el desplegable del campo "Campo contador" seleccione el valor ```${CONTADOR}``` (CONTADOR).
    Si no existe aborte el caso de prueba.

23. ${check} Seleccione la opción "Usar fecha de revisión".

24. ${check} En el desplegable del campo "Campo de fecha de revisión" seleccione el valor ```${REVISION}``` (REVISION).

25. ${check} Pulse el boton "Importar historial".

26. ${check} Tras la importación del historial, pulse el botón "Cerrar". 

27. ${check} Seleccione la opcion de menu "Herramientas/VCSGis/Mostrar revisiones".

28. ${check} Se presentara una ventana de título  "Revisiones".

30. ${check} En el desplegable del campo "Copia de trabajo" seleccione el valor ```${WORKINGCOPY}``` (WORKINGCOPY).
    Si no existe aborte el caso de prueba.

31. ${check} En el desplegable del campo "Tabla" seleccione el valor ```${TABLE_NAME}``` (TABLE_NAME).
    Si no existe aborte el caso de prueba.
    
32. ${check} En la tabla de la parte inferior del dialogo deberan haber aperecido XXX lineas.

33. ${check} Cierre el dialogo de titulo "Revisiones".

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
