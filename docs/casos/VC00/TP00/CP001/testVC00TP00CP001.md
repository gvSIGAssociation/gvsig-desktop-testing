---
title: Asociar un plan topológico a una capa
proccode: VC00TP00CP0001
srcpath: "casos/VC00/TP00/CP001/testVC00TP00CP001.md"
---

{% include es/header.md %}

{% include parameter.html name="REPONAME" value="RepositorioAuth" %}

{% include parameter.html name="TPNAME" value="ProvinciasDebenTenerPoblaciones" %}

{% include parameter.html name="LAYER_NAME" value="esp_provincias" %}


## {{ page.title }}

### Descripción

Este proceso asigna el plan topológico a una capa existente en el repositorio.
Tanto la capa como el plan topológico deben estar dados de alta en el repositorio previamente.

{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada

1. ${check} **REPONAME**=```${REPONAME}```. Nombre de la conexión y del repositorio.

1. ${check} **TPNAME**=```${TPNAME}```. Nombre del plan topológico a asignar.

1. ${check} **LAYER_NAME**=```${LAYER_NAME}```. Capa a la cual se le va a asignar el plan topológico.

### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya versión sea la indicada en el plan de pruebas.

1. ${check} El complemento de VCSGis debe estar instalado y activo.

1. ${check} El complemento de Topología debe estar instalado y activo.

1. ${check} El caso de prueba [VC00TP00CP000, "Cargar un plan topológico en el repositorio"](../../TP00/CP000/testVC00TP00CP000.md),
   ha pasado sin errores.
   
### Pasos

1. ${check} Si acaba de ejecutar el caso de pruebas (hace menos de 1 hora)  "Cargar un plan topológico en el repositorio"
    y no ha cerrado gvSIG, continúe con el paso 2. Si no, ejecútelo antes de continuar.

2. ${check} Asegúrese de estar en la aplicación gvSIG Desktop ```Servidor```.

3. ${check} Consulte en el "Gestor de proyecto" si tiene cargada la tabla "VCSGISREPO_ENTITIES. 
   * Si la tiene cargada, selecciónela y pulse el botón "Abrir...".
   * Si no la tiene cargada, ábrala siguiendo los pasos de 
    [abrir tabla de base de datos](../../PROC/011/procVC00PROC011.html?CONNAME=${REPONAME}&TABLENAME=VCSGISREPO_ENTITIES)

4. ${check} Una vez abierta la tabla y estando ésta activa seleccione la opción de menú "Tabla/Refrescar"

4. ${check} Seleccione la opción de menú "Tabla/Show form"

6. ${check} Como resultado se presentará una ventana que muestra el formulario asociado a la tabla 
   de entidades del repositorio.

11. ${check} Pulse el botón "Comenzar edición" del formulario. 

9. ${check} Con ayuda de los botones "Anterior" y "Siguiente" del formulario seleccione la entidad ```${LAYER_NAME}``` (LAYER_NAME).

10. ${check} Localice el campo "Topology plan" y pulse el botón  "Select item to list" asociado a ese campo.

11. ${check} Se presentará una ventana con los diferentes planes topológicos disponibles en el repositorio.

12. ${check} Seleccione el plan topológico ```${TPNAME}``` (TPNAME) si no aparece el plan topologico indicado en la
    lista aborte la ejecución del plan de prueba.

13. ${check} Pulse el botón "Aceptar", que cerrará el dialogo de selección de plan topológico y le devolverá
    al formulario de entidades.

13. ${check} Se habrá presentado en el campo  "Topology plan" el valor ```${TPNAME}``` (TPNAME).

14. ${check} Localice el campo "Topology plan mode" y seleccione la opción ```Mandatory``` del desplegable.

10. ${check} Pulse el botón "Guardar" del formulario.

11. ${check} Pulse el botón "Terminar edición" del formulario. 

12. ${check} Se presentrará una ventana, pulse en la opción "Sí" para terminar edición y guardar los cambios.

13. ${check} Cierre el formulario de entidades.

18. ${check} Cierre la tabla en de entidades

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
