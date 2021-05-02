---
title: ------------FIXME------------
proccode: VC00...FIXME...
srcpath: "casos/VC00/...FIXME..."
---

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="TABLELINK" value="EUROPA_OCCIDENTAL" %}

{% include parameter.html name="TABLENAME" value="europa_occidental" %}

## {{ page.title }}

### Descripción

**------------FIXME------------**

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. ${check} **TMPFOLDER**="/tmp". Carpeta en la que se disponga de acceso para escritura donde
   se crearan los archivos necesarios durante la ejecucion del test.

4. ${check} Tabla ```${TABLENAME}``` (${TABLELINK}). Capa a usar en este test. 

3. ${check} **------------FIXME------------**. 

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya version sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} Tendremos descargada el fichero ```${TABLENAME}``` (${TABLELINK}) en una ruta conocida en nuestro equipo.

4. ${check} **------------FIXME------------**

### Pasos

1. ${check} **------------FIXME------------**

2. ${check} **------------FIXME------------**

3. ${check} **------------FIXME------------**

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
