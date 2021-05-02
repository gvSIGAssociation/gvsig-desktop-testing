---
title: Descargar capa a la copia de trabajo (sin autenticación).
proccode: VC00CO00CP000
srcpath: "casos/VC00/CP000/testVC00CO00CP000.md"
---

{% include es/header.md %}

{% include parameter.html name="TMPFOLDER" value="/tmp" %}

{% include parameter.html name="REPONAME" value="Repositorio" %}

{% include parameter.html name="WCNAME2" value="CopiaDeTrabajo2" %}

{% include parameter.html name="TABLENAME" value="europa_occidental" %}

## {{ page.title }}

### Descripción

**------------FIXME------------**

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. ${check} **TMPFOLDER**="/tmp". Carpeta en la que se disponga de acceso para escritura donde
   se crearan los archivos necesarios durante la ejecucion del test.

4. ${check} Tabla ```${TABLENAME}``` a usar en este test. 

4. ${check} **------------FIXME------------**. 

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya version sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} El caso de prueba [VC00CI00CP000, "Commitar una capa nueva (sin autenticación)"](../../CI00/CP000/testVC00CI00CP000.md) 
   (**FIXME** ¿pasar parametros?),
   ha pasado sin errores. 

4. ${check} **------------FIXME------------**

### Pasos

1. ${check} Si acabamos de pasar el caso de pruebas 
   [VC00CI00CP000, "Commitar una capa nueva (sin autenticación)"](../../CI00/CP000/testVC00CI00CP000.md) (**FIXME** ¿pasar parametros?), 
   continuaremos con el paso 2. 
   Si no lo pasaremos antes de continuar. 
      
1. ${check} **------------FIXME------------**
   * ¿Cerrar gvSIG si esta abierto?
   * Inicializar ws 2 (procVC00PROC???)
   * crear o abrir vista
   * checkout (crear procVC00PROC???)

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
