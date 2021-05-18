---
title: Iniciar un servidor VCSGis contra un repositorio en una base de datos Oracle (con autorización)
testcode: VC00CR00CP003
srcpath: "casos/VC00/CR00/CP003/testVC00CR00CP003.md"
---

{% include es/header.md %}

{% include parameter.html name="REPONAME" value="RepositorioAuth" %}

{% include parameter.html name="SERVER" value="127.0.0.1" %}

{% include parameter.html name="PORT" value="1521" %}

{% include parameter.html name="DATABASE" value="orcl" %}

{% include parameter.html name="USER" value="P1" %}

{% include parameter.html name="PASSWORD" value="oracle" %}

{% include parameter.html name="MODE" value="Servicio" %}

## {{ page.title }}

### Descripción

Inicializa un repositorio VCSGis sobre una base de datos de Oracle e inicia el servidor 
de VCSGis que hay empotrado en gvSIG desktop.
Como resultado de ejecutar el caso de prueba en el repositorio quedará activas la autenticación
y la autorización, y se habrán creado dos usuarios:
* "sara", de clave "sara1", con todos los permisos activados (opción por defecto).
* "pedro", de clave "pedro1", sin permiso de "commit".

Durante la ejecución del caso de prueba se creará la conexion a la base de datos que va a usarse 
para acceder al repositorio.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. ${check} **REPONAME**={% include var_tag.html var="REPONAME" %}. Nombre de la conexión a crear asociada al repositorio.

2. ${check} **SERVER**=```${SERVER}```. Dirección o nombre del servidor donde esta ejecutándose la instancia de Oracle.

3. ${check} **PORT**=```${PORT}```. Puerto TCP en el que esta escuchando el servicio de Oracle.

4. ${check} **DATABASE**=```${DATABASE}```. Nombre de la base de datos a la que se conectará.

5. ${check} **USER**=```${USER}```. Nombre del usuario de Oracle que se conectará.

6. ${check} **PASSWORD**=```${PASSWORD}```. Clave del usuario.

7. ${check} **MODE**=```${MODE}```. Modo de la conexion, deberá ser "SID" o "Servicio".


### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional para ser usado como ```Servidor``` de la versión indicada
   en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} Disponer de una herramienta de administración de Oracle como puede ser el "Oracle SQL Developer".

### Pasos

1. ${check} Compruebe que no esté iniciado gvSIG desktop a partir de la portable 
   para el ```Servidor```. Si lo está ciérrelo.
   
2. ${check} Compruebe que en la base de datos de Oracle en la que se va a crear el repositorio no existen las tablas 
   que va a crear la inicializacion del repositorio. Para ello puede utilizar la herramienta *"Oracle SQL Developer"* y ejecutar las siguientes sentencias, para eliminarlas, en caso de que existan:
   <PRE id="DROP_TABLES" class="language-plaintext highlighter-rouge">
   DROP TABLE "GVSIGD_CONFIG";
   DROP TABLE "GVSIGD_REPOSITORY";
   DROP TABLE "GVSIGD_RESOURCES";
   DROP TABLE "VCSGISREPO_CONFIG";
   DROP TABLE "VCSGISREPO_DATA";
   DROP TABLE "VCSGISREPO_ENTITIES";
   DROP TABLE "VCSGISREPO_HOOKS";
   DROP TABLE "VCSGISREPO_REVISIONS";
   DROP TABLE "VCSGISREPO_TOPOLOGYPLANS";
   DROP TABLE "VCSGISREPO_USERS";
   </PRE>
   {% include var_copy.html var="DROP_TABLES"%}
   
3. ${check} Inicie gvSIG desktop a partir de la portable para el ```Servidor```.

4. ${check} Una vez iniciado seleccione la opción de menú "Herramientas/VCSGis/Administracion/Inicializar repositorio" que
   presenta la ventana de título "Inicializar repositorio".
   
5. ${check} Pulse el botón asociado al campo "Conexión" para crear la conexión a la base de datos que se sitúa
   junto al desplegable con las diferentes conexiones.

6. ${check} Siga los pasos de 
   [crear una conexión a base de datos](../../PROC/020/procVC00PROC020.html?NAME=${REPONAME}&SERVER=${SERVER}&PORT=${PORT}&DATABASE=${DATABASE}&USER=${USER}&PASSWORD=${PASSWORD}&MODE=${MODE}) 

7. ${check} Una vez creada la conexión a la base de datos, de nuevo en la ventana de título "Inicializar repositorio",
   pulse el botón "Inicializar repositorio". 
   
8. ${check} Una vez que se haya terminado la inicialización del repositorio se cerrará la ventana "Inicializar repositorio"
   y no debe aparecer ningún mensaje de error, ni en ventanas, ni en la barra de mensajes de gvSIG desktop.
   
9. ${check} Compruebe que se han creado las tablas en la base de datos de Oracle, usando, por ejemplo, el *"Oracle SQL Developer"*. 
   Deben haberse creado las siguientes tablas:
   * GVSIGD_CONFIG
   * GVSIGD_REPOSITORY
   * GVSIGD_RESOURCES
   * VCSGISREPO_CONFIG
   * VCSGISREPO_DATA
   * VCSGISREPO_ENTITIES
   * VCSGISREPO_HOOKS
   * VCSGISREPO_REVISIONS
   * VCSGISREPO_TOPOLOGYPLANS
   * VCSGISREPO_USERS

   Las tablas deben estar creadas y las siguientes deben tener registros:
   * GVSIGD_REPOSITORY (7)
   * GVSIGD_RESOURCES (7)
   * VCSGISREPO_CONFIG (1)
  
10. ${check} En la aplicación de gvSIG desktop seleccione la opción de menu "Archivo/Connect to database workspase" 
    que mostrará una ventana de diálogo titulada "Connect".

11. ${check} En el desplegable "Conection" seleccione la conexión llamada ```${REPONAME}```.

12. ${check} Pulse el botón "Connect". Se conectará al espacio de trabajo asociado a la conexión y cerrará la ventana.
     No debe aparecer ningún mensaje de error, ni en ventanas, ni en la barra de mensajes de gvSIG desktop.
   
13. ${check} Siga los pasos de [activar autenticación y autorización en el repositorio](../../PROC/004/procVC00PROC004.html?REPONAME=${REPONAME})

14. ${check} Pulse la opción de menú "Herramientas/VCSGis/Administración/Servidor VCSGis". Al hacerlo aparecerá 
    una ventana de título "Servidor VCSGis".

15. ${check} En el desplegable asociado al campo "Base de datos" deberá existir la opción ```${REPONAME}```, selecciónela.

16. ${check} Pulse en el botón "Reiniciar" y maximice la ventana.

17. ${check} En el cuadro de texto "Mensajes" habrá aparecido algo como:
    ```
    2021-05-17 11:57:40.251 - Creating server...
    2021-05-17 11:57:40.42 - Starting server with repository jdbc:oracle:thin:@//127.0.0.1:1521/orcl...

    ```
    Pueden cambiar las fechas y las rutas que aparezcan.

18.  No cierre la aplicación si va a seguir ejecutando los casos de prueba de este plan. Iconice la ventana de la aplicacion gvSIG desktop ```Servidor```.

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}

