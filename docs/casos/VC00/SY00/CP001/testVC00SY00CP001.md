---
title: Commitar una capa nueva (con autorización)
testcode: VC00CI00CP001
srcpath: casos/VC00/testVC00CI00CP001.md
---


**------------- FIXME (paco) --------------**



{% include es/header.md %}

{% include parameter.html name="WCNAME" value="CopiaDeTrabajo" %}

{% include parameter.html name="TABLENAME" value="europa_occidental" %}


## {{ page.title }}

### Descripción


{% include es/checkifthereisalreadyabug.md %}

### Datos de entrada:

1. ${check} **WCNAME**=```${WCNAME}```. Nombre de la copia de trabajo que se va a crear asi como 
   de la conexion a la base de datos de la copia de trabajo. 

2. ${check} Tabla ```${TABLENAME}``` (${TABLELINK}). Capa a usar en este test. 


### Prerrequisitos

1. ${check} Un gvSIG desktop instalado y funcional cuya version sea la indicada en el plan de pruebas.

2. ${check} El complemento de VCSGis debe estar instalado y activo.

3. ${check} El caso de prueba [VC00AD00CP001, "Añadir capa a copia de trabajo (con autorizacion)"](../../AD00/CP001/testVC00AD00CP001.md),
   ha pasado sin errores.

### Pasos

1. ${check} Si acabamos de pasar el caso de pruebas 
   [VC00AD00CP001, "Añadir capa a copia de trabajo (con autorizacion)"](../../AD00/CP001/testVC00AD00CP001.md), 
   continuaremos con el paso 2. 
   Si no lo pasaremos antes de continuar. 
   
2. ${check} Pulsaremos en la opcion de menu "Herramientas/VCSGis/?Mostrar cambios?".

3. ${check} Se habra presentado la ventana ver los cambios entre el repositorio y la copia de trabajo
   de titulo XXXX.

4. ${check} seleccionaremos la copia de trabajo .... **-----------FIXME------------** 

5. ${check} Activaremos la pestaña .... **-----------FIXME------------** 

6. ${check} .... **-----------FIXME------------** 

### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}

{% include es/footer.html %}
