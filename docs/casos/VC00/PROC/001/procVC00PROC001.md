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

# Datos de entrada

1. **TMPFOLDER**, una carpeta en la que se disponga de acceso para escritura.
2. **NAME**, nombre de la conexion a crear.

### Pasos

1. Estaremos viendo la ventana de creacion de repositorio, con titulo "XXXX", y estara activa.
2. Pulsaremos en el boton asociado al campo "????" para crear la conexion a la base de datos.
3. Seguiremos los pasos de [VC00LB00PR000 Creacion de una conexion a base de datos H2](../../LB00/PR000_create_dbconnection/definition.md) 
   usando NAME y PATHNAME="<TMPFOLDER>/<NAME>.mv.db"
4. Una vez creada la conexion pulsaremos en el boton "?????"
5. Comprobaremos que se ha creado el archivo "<TMPFOLDER>/<NAME>.mv.db" en el sistema de archivos.

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

Si se produce un error reportelo en el test que esta ejecutando.



