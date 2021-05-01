---
title: Creacion de un repositorio en H2
testcode: VC00PROC001
srcpath: "casos/VC00/PROC/001/procVC00PROC001.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Crea un repositorio VCSGis sobre una base de datos nueva de H2.
En el proceso se creara la conexion a la base de datos que va a usarse para acceder al repositorio.

### Datos de entrada

1. {%include check.html%} **TMPFOLDER**="<span id="TMPFOLDER"></span><script>
const query=window.location.search;
const params=new URLSearchParams(query);
const param=params.get("TMPFOLDER");
document.getElementById('TMPFOLDER').innerHTML = param;
</script>" una carpeta en la que se disponga de acceso para escritura.

2. {%include check.html%} **REPONAME**="<span id="REPONAME"></span><script>
const query=window.location.search;
const params=new URLSearchParams(query);
const param=params.get("REPONAME");
document.getElementById('REPONAME').innerHTML = param;
</script>". Nombre de la conexion a crear.

### Pasos

1. {%include check.html%} Cuando iniciemos este procedimiento deberems estar viendo
   la ventana de creacion de repositorio, con titulo "Inicializar repositorio" y estara activa.

2. {%include check.html%} Pulsaremos en el boton asociado al campo "Conexión" para crear la conexion a la base de datos.

3. {%include check.html%} Seguiremos los pasos de [Creacion de una conexion a base de datos H2](../../PROC/000/procVC00PROC000.md) 
   usando: 
   * CONNAME="<span id="REPONAME"></span><script>
const query=window.location.search;
const params=new URLSearchParams(query);
const param=params.get("REPONAME");
document.getElementById('REPONAME').innerHTML = param;
</script>" (REPONAME)
   * PATHNAME="<span id="TMPFOLDER"></span><script>
const query=window.location.search;
const params=new URLSearchParams(query);
const param=params.get("TMPFOLDER");
document.getElementById('TMPFOLDER').innerHTML = param;
</script>/{%include arg.html name="REPONAME"%}.mv.db" (TMPFOLDER/REPONAME.mv.db)

4. {%include check.html%} Una vez creada la conexion a la base de datos, habremos vuelto a la ventana de titulo "Inicializar repositorio".
   Pulsaremos el boton "Inicializar repositorio".

5. {%include check.html%} Se cerrara la ventana de inicializacion del repositorio y no debe aparecer ningun mensaje de error, ni en
   ventanas ni en la barra de mensajes de gvSIG desktop.
   
7. {%include check.html%} Iremo al explorador de archivos del sistema y comprobaremos que se ha creado el archivo 
   {%include arg.html name="TMPFOLDER"%}/{%include arg.html name="REPONAME"%}.mv.db" (TMPFOLDER/REPONAME.mv.db)
   en el sistema de archivos.

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

Si se produce un error reportelo en el test que esta ejecutando.
