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
Como resultado de ejecutar el caso de prueba en el repositorio quedará activa la autenticación
y autorización, y tendremos creados dos usuarios:
* "sara", de clave "sara1", con todos los permisos activados (opción por defecto).
* "pedro", de clave "pedro1", sin permiso de "commit".

Durante la ejecución del caso de prueba se creara la conexion a la base de datos que va a usarse 
para acceder al repositorio.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexión a crear asociada al repositorio.

2. ${check} **SERVER**=```${SERVER}```. Direccion o nombre del servidor donde esta ejecutandose la instancia de Oracle.

3. ${check} **PORT**=```${PORT}```. Puerto TCP en el que esta escuchando el servicio de Oracle.

4. ${check} **DATABASE**=```${DATABASE}```. Nombre de la base de datos a la que nos vamos a conectar.

5. ${check} **USER**=```${USER}```. Nombre del usuario de Oracle con el que nos vamos a conectar.

6. ${check} **PASSWORD**=```${PASSWORD}```. Clave del usuario.

7. ${check} **MODE**=```${MODE}```. Mode de la conexion, debera ser "SID" o "Servicio".


### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional para ser usado como ```Servidor``` de la versión indicada
   en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} Disponer de una herramienta de administracion de Oracle como puede ser el "Oracle SQL Developer".

### Pasos

1. ${check} Comprobaremos que no este iniciado gvSIG desktop a partir de la portable 
   para el ```Servidor```. Si lo esta deberiamos cerrarlo.
   
2. Comprobaremos que en la base de datos de Oracle en la que vayamos a crear el repositorio no existen las tablas 
   que va a crear la inicializacion del repositorio. Para ello puede utilizar la herramienta *"Oracle SQL Developer"*.
   Puede ejecutar las siguientes sentencias para eliminarlas en caso de que existan:
   ```
   BEGIN  EXECUTE  immediate 'DROP TABLE "GVSIGD_CONFIG"'; EXCEPTION WHEN OTHERS THEN NULL; END;
   BEGIN  EXECUTE  immediate 'DROP TABLE "GVSIGD_REPOSITORY"'; EXCEPTION WHEN OTHERS THEN NULL; END;
   BEGIN  EXECUTE  immediate 'DROP TABLE "GVSIGD_RESOURCES"'; EXCEPTION WHEN OTHERS THEN NULL; END;
   BEGIN  EXECUTE  immediate 'DROP TABLE "VCSGISREPO_CONFIG"'; EXCEPTION WHEN OTHERS THEN NULL; END;
   BEGIN  EXECUTE  immediate 'DROP TABLE "VCSGISREPO_DATA"'; EXCEPTION WHEN OTHERS THEN NULL; END;
   BEGIN  EXECUTE  immediate 'DROP TABLE "VCSGISREPO_ENTITIES"'; EXCEPTION WHEN OTHERS THEN NULL; END;
   BEGIN  EXECUTE  immediate 'DROP TABLE "VCSGISREPO_HOOKS"'; EXCEPTION WHEN OTHERS THEN NULL; END;
   BEGIN  EXECUTE  immediate 'DROP TABLE "VCSGISREPO_REVISIONS"'; EXCEPTION WHEN OTHERS THEN NULL; END;
   BEGIN  EXECUTE  immediate 'DROP TABLE "VCSGISREPO_TOPOLOGYPLANS"'; EXCEPTION WHEN OTHERS THEN NULL; END;
   BEGIN  EXECUTE  immediate 'DROP TABLE "VCSGISREPO_USERS"'; EXCEPTION WHEN OTHERS THEN NULL; END;
   ```
   
3. ${check} Iniciaremos gvSIG desktop a partir de la portable para el ```Servidor```.

4. ${check} Una vez iniciado seleccionaremos la opción de menú "Herramientas/VCSGis/Administracion/Inicializar repositorio" que nos
   presenta la ventana de título "Inicializar repositorio".
   
5. ${check} Pulse el botón asociado al campo "Conexión" para crear la conexion a la base de datos. Este se situa
   junto al desplegable con las diferentes conexiones.

6. ${check} Siga los pasos de 
   [crear una conexión a base de datos](../../PROC/000/procVC00PROC020.html?NAME=${REPONAME}&SERVER=${SERVER}&PORT=${PORT}&DATABASE=${DATABASE}&USER=${USER}&PASSWORD=${PASSWORD}&MODE=${MODE}) 

7. ${check} Una vez creada la conexión a la base de datos, de nuevo en la ventana de título "Inicializar repositorio",
   pulse el botón "Inicializar repositorio". 
   
8. ${check} Una vez se haya terminado la inicialización del repositorio se cerrara la ventana "Inicializar repositorio"
   y no debe aparecer ningun mensaje de error, ni en ventanas, ni en la barra de mensajes de gvSIG desktop.
   
9. ${check} Compruebe que se han creado las tablas en la base de datos de Oracle, usando, por ejemplo, el *"Oracle SQL Developer"*. 
   Se tienen que haber creado las siguientes tablas:
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
   Las tablas deben estar creadas y las siguientes deben tener filas:
   * GVSIGD_REPOSITORY (7)
   * GVSIGD_RESOURCES (7)
   * VCSGISREPO_CONFIG (1)
  
10. ${check} En la aplicación de gvSIG desktop seleccione la opción de menu "Archivo/Connect to database workspase" 
    que mostrará una ventana de diálogo titulada "Connect".

11. ${check} En el desplegable "Conection" seleccione la conexión llamada ```${REPONAME}```.

12. ${check} Pulse el botón "Connect". Se conectara al espacio de trabajo asociado a la conexión y cerrara la ventana.
     No debe aparecer ningun mensaje de error, ni en ventanas, ni en la barra de mensajes de gvSIG desktop.
   
13. ${check} Seguiremos los pasos de [activar autenticación y autorización en el repositorio](../../PROC/004/procVC00PROC004.html?REPONAME=${REPONAME})

14. ${check} Pulsaremos la opción de menú "Herramientas/VCSGis/Administración/Servidor VCSGis". Al hacerlo aparecerá 
    una ventana de título "Servidor VCSGis".

15. ${check} En el desplegable asociado al campo "Base de datos" debera existir la opción ```${REPONAME}```, la seleccionaremos.

16. ${check} Pulsaremos en el boton "Reiniciar" y maximizaremos la ventana.

17. ${check} En el cuadro de texto "Mensajes" habrá aparecido algo como:
    ```
    2021-05-04 09:23:50.839 - Creating server...
    2021-05-04 09:23:50.939 - Starting server with repository jdbc:h2:file:${TMPFOLDER}/${REPONAME};MODE=PostgreSQL;SCHEMA=PUBLIC;ALLOW_LITERALS=ALL...
 
    ```
    Pueden cambiar las fechas y las rutas que aparezcan.

18.  No cierre la aplicacion si va a seguir ejecutando casos de prueba de este plan. Iconice la ventana de la aplicacion gvSIG desktop ```Servidor```.

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}

