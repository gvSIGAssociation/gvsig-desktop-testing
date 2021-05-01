---
title: Creacion de una copia de trabajo asociada a un repositorio local en H2
testcode: VC00PROC002
srcpath: "casos/VC00/PROC/002/procVC00PROC002.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Este procedimiento crea una copia de trabajo asociada a un repositorio local.

### Datos de entrada

1. **TMPFOLDER**, una carpeta en la que se disponga de acceso para escritura
2. **REPONAME**, nombre de la conexion a crear asociada al repositorio
2. **WCNAME**, nombre de la conexion a crear asociada a la copia local

### Pasos

1. Estaremos viendo la ventana de creacion de copias de trabajo, con titulo "????" y estara activa.,/Administracion/????" que nos
2. Seleccionaremos el repo local <REPONAME> usando el desplegable. Si no esta en el desplegable abortamos test.
3. Introduciremos el nombre de la copia de trabajo <WCNAME>
4. Seleccionaremos la ruta a la copia local "<TMPFOLDER>/<WCNAME>"
5. Pulsaremos en ?aceptar?
6. Comprobaremos que se ha creado el archivo "<TMPFOLDER>/<WCNAME>.mv.db" en el sistema de archivos.

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

Si se produce un error reportelo en el test que esta ejecutando.

{% include es/header.md %}
