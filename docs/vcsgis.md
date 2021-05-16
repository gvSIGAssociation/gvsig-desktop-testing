# Plan de pruebas sobre VCSGis

Para pasar los planes de prueba es necesario disponer de una version portable de gvSIG desktop 2.6.0-3222.
La distribucion usada para ejecutar el plan de pruebas se puede localizar en:
* Para Linux [gvSIG-desktop-2.6.0-3222-devel-lin-x86_64.zip](dist/gvSIG-desktop-2.6.0-3222-devel-lin-x86_64.zip)
* Para Windows [gvSIG-desktop-2.6.0-3222-devel-win-x86_64.zip](dist/gvSIG-desktop-2.6.0-3222-devel-win-x86_64.zip)

Antes de pasar el plan de pruebas "basico" de VCSGis es recomendable que tenga en cuenta las siguientes cosas:
1. Para su ejecucion se recomienda crear una estructura de carpetas como la siguiente:
   * gvSIG-desktop-2.6.0-3222-devel-lin-x86_64
     * Servidor
     * Cliente 

   Y dentro de las capetas "Servidor" y "Cliente" se ha descomprimido el zip con la portable de forma que dentro
   de cada uno de ellas haya este el fichero "gvSIG.sh" que arranca la aplicacion.

2. Identificar una carpeta donde guardar los archivos temporales que se precisen 
   durante la ejecucion del plan de pruebas, y tener claro cual es. A lo largo del plan se
   le indicaran referencias a ella.

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

Y a los videos grabados de casa uno de los casos de prueba desde los siguientes enlaces:
1. [```VC00CR00CP003``` Iniciar servidor](videos/VC00CR00CP003.mp4).
1. [```VC00CW00CP002``` Crear copia de trabajo](videos/VC00CW00CP002.mp4).
1. [```VC00AD00CP002``` Añadir capa a la copia de trabajo (add)](videos/VC00AD00CP002.mp4).
1. [```VC00SY00CP002``` Subir capa al repositorio (commit)](videos/VC00SY00CP002.mp4).
1. [```VC00CO00CP002``` Obtener copia de trabajo de una capa (checkout)](videos/VC00CO00CP002.mp4).
1. [```VC00RE00CP003``` Asociar leyenda a una capa](videos/VC00RE00CP003.mp4).
1. [```VC00TP00CP000``` Cargar un plan topologico en el repositorio](videos/VC00TP00CP000.mp4).
1. [```VC00TP00CP001``` Asociar un plan topologico a una capa](videos/VC00TP00CP001.mp4).
1. [```VC00TP00CP002``` Subir cambios en una capa con un plan topologico asociado (que no pasen el plan)](videos/VC00TP00CP002.mp4).
1. [```VC00TP00CP003``` Subir cambios en una capa con un plan topologico asociado (que sí pasen el plan)](videos/VC00TP00CP003.mp4).
1. [```VC00CO00CP005``` Obtener una revision concreta de una capa](videos/VC00CO00CP005.mp4).
1. [```VC00EX00CP005``` Exportar una capa a una fecha dada](videos/VC00EX00CP005.mp4).
1. [```VC00EX00CP002``` Exportar una capa a una revision dada](videos/VC00EX00CP002.mp4).
1. [```VC00MO00CP003``` Definir y descargar un modelo de datos](videos/VC00MO00CP003.mp4).
1. [```VC00HI00CP003``` Importar historial](videos/VC00HI00CP003.mp4).

