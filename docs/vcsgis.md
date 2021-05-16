{% include es/header.md %}

{% include parameter.html name="VERSION" value="2.6.0-3222" %}

{% include parameter.html name="VERSION_FOLDER" value="2_6_0_3222" %}


# Plan de pruebas sobre VCSGis

Para pasar los planes de prueba es necesario disponer de una version portable de gvSIG desktop 2.6.0-3222.
La distribucion usada para ejecutar el plan de pruebas se puede localizar en:
* Para Linux [gvSIG-desktop-${VERSION}-devel-lin-x86_64.zip](${VERSION_FOLDER}/gvSIG-desktop-${VERSION}-devel-lin-x86_64.zip)
* Para Windows [gvSIG-desktop-${VERSION}-devel-win-x86_64.zip](${VERSION_FOLDER}/gvSIG-desktop-${VERSION}-devel-win-x86_64.zip)

Antes de pasar el plan de pruebas "basico" de VCSGis es recomendable que tenga en cuenta las siguientes cosas:
1. Para su ejecucion se recomienda crear una estructura de carpetas como la siguiente:
   * gvSIG-desktop-${VERSION}-devel-lin-x86_64
     * Servidor
     * Cliente 

   Y dentro de las capetas "Servidor" y "Cliente" se descomprimira el zip con la portable de forma que dentro
   de cada uno de ellas este directamente el fichero que arranca gvSIG desktop ("gvSIG.sh").

2. Identificar una carpeta donde guardar los archivos temporales que se precisen 
   durante la ejecucion del plan de pruebas, y tener claro cual es. A lo largo del plan se
   haran referencias a ella.

3. Descargar los archivos que van a ser necesarios durante la ejecucion del plan de pruebas
   a una carpeta en disco de forma que sean facilmente localizables cuando se requieran
   en la ejecucion del plan. Estos archivos son:
   * [esp_poblaciones.csv](casos/VC00/data/esp_poblaciones.csv)
   * [esp_provincias.csv](casos/VC00/data/esp_provincias.csv)
   * [esp_provincias.gvsleg](casos/VC00/data/esp_provincias.gvsleg)
   * [origen_coordenadas.csv](casos/VC00/data/origen_coordenadas.csv)
   * [reservas.csv](casos/VC00/data/reservas.csv)

Se puede acceder al plan de pruebas desde:

* [Plan de pruebas](casos/VC00/plans/planVC00PLAN003.md)

Puede acceder al PDF con el estado de ejecucion del plan de pruebas desde:
* [Estado ejecucion del plan de pruebas](2_6_0_3222/Estado_ejecucion_del_plan_de_pruebas.pdf)

A los videos grabados de cada uno de los casos de prueba se puede acceder desde los siguientes enlaces:
1. [```VC00CR00CP003``` Iniciar servidor](${VERSION_FOLDER}/VC00CR00CP003.mp4).
1. [```VC00CW00CP002``` Crear copia de trabajo](${VERSION_FOLDER}/VC00CW00CP002.mp4).
1. [```VC00AD00CP002``` Añadir capa a la copia de trabajo (add)](${VERSION_FOLDER}/VC00AD00CP002.mp4).
1. [```VC00SY00CP002``` Subir capa al repositorio (commit)](${VERSION_FOLDER}/VC00SY00CP002.mp4).
1. [```VC00CO00CP002``` Obtener copia de trabajo de una capa (checkout)](${VERSION_FOLDER}/VC00CO00CP002.mp4).
1. [```VC00RE00CP003``` Asociar leyenda a una capa](${VERSION_FOLDER}/VC00RE00CP003.mp4).
1. [```VC00TP00CP000``` Cargar un plan topologico en el repositorio](${VERSION_FOLDER}/VC00TP00CP000.mp4).
1. [```VC00TP00CP001``` Asociar un plan topologico a una capa](${VERSION_FOLDER}/VC00TP00CP001.mp4).
1. [```VC00TP00CP002``` Subir cambios en una capa con un plan topologico asociado (que no pasen el plan)](${VERSION_FOLDER}/VC00TP00CP002.mp4).
1. [```VC00TP00CP003``` Subir cambios en una capa con un plan topologico asociado (que sí pasen el plan)](${VERSION_FOLDER}/VC00TP00CP003.mp4).
1. [```VC00CO00CP005``` Obtener una revision concreta de una capa](${VERSION_FOLDER}/VC00CO00CP005.mp4).
1. [```VC00EX00CP005``` Exportar una capa a una fecha dada](${VERSION_FOLDER}/VC00EX00CP005.mp4).
1. [```VC00EX00CP002``` Exportar una capa a una revision dada](${VERSION_FOLDER}/VC00EX00CP002.mp4).
1. [```VC00MO00CP003``` Definir y descargar un modelo de datos](${VERSION_FOLDER}/VC00MO00CP003.mp4).
1. [```VC00HI00CP003``` Importar historial](${VERSION_FOLDER}/VC00HI00CP003.mp4).

<div style="display:none;"  markdown="1">

Notas para descargar la web:
* Para descargar la web de los casos de prueba:
  ```
  wget -m --convert-links --page-requisites --no-parent  https://gvsigassociation.github.io/gvsig-desktop-testing/
  wget -m --convert-links --page-requisites --no-parent  https://gvsigassociation.github.io/gvsig-desktop-testing/vcsgis.html
  cd gvsigassociation.github.io/gvsig-desktop-testing
  rm index.html
  mv vcsgis.html index.html
  
  ```
* Una vez descargado, el raiz de la web estara en la carpeta ```gvsigassociation.github.io/gvsig-desktop-testing```.

* Dejar en "casos" solo la carpeta "VC00".
* 
* Crear la carpteta de la version (2_6_0_3222) en el raiz de la web.

</div>


{% include es/footer.html %}


