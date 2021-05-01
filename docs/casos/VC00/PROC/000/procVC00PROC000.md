---
title: Creacion de una conexion a base de datos H2
testcode: VC00PROC000
srcpath: "casos/VC00/PROC/000/procVC00PROC000.md"
---

{% include es/header.md %}

## {{ page.title }}

### Descripción

Crea una conexion a una base de datos H2, si la conexion ya existe se eliminara y se volvera a crear.

{% include es/checkifthereisalreadyabug.md %}

# Datos de entrada

* **NAME**, nombre de la conexion a crear.
* **PATHNAME**, ruta completa en la que crear la base de datos H2

### Pasos

1. Estaremos viendo la ventana de creacion de conexiones a base de datos, de titulo "XXX" y estara activa.
2. Comprobaremos si existe la conexion *NAME*. Para miraremos si ya existe en el desplegable 
   del campo ????? un valor con el nombre *NAME*.
3. Si existe lo seleccionaremos y pulsaremos el boton inferior que dice "Mas...", seleccionando la
   opcion ???
4. Escribiremos el nombre *NAME* en la caja de texto ????
5. Indicaremos como conector el de H2. Para ello seleccionaremos el valor ???? en el desplegable "???".
6. Pulsaremos en el boton asociado al campo '???' y en el dialogo de seleccion de fichero introduciremos 
   el valor *PATHNAME*, pulsando acceptar en ese dialogo.
7. Deberemos estar de vuelta al dialgo de creacion de conexion a base de datos.
8. Pulsaremos el boton "??aceptar??", que cerrara la ventana.
   
### Resultado esperado

{% include es/expectedresult.md %}

### Reportar fallo

{% include es/reportbug.md %}




