---
title: Plan de prueba "basico" (repositorio remoto en H2 con autorizacion)
plancode: VC00PLAN002
srcpath: "casos/VC00/plans/planVC00PLAN002.md"
---

{% include es/header.md %}

# {{ page.title }}

<div class="noprint"  markdown="1">
<style scoped>
@media print{
   .noprint{
       display:none;
   }
}
</style>
## Descripción
   
Este *plan de prueba* contiene *casos de prueba* para verificar la funcionalidad basica de VCSGis sobre 
un repositorio remoto en H2 con la autenticacion y autorizacion de usuarios activada.

Comprueba:

1. Que se crea un repositorio.
1. Que se crea una copia de trabajo.
1. Que se pueden añdir a la copia de trabajo capas (add), subir cambios al repositorio (commit) y obtener copias locales de tablas del repositorio.
1. Que se se pueden crear leyendas asociadas a una capa y se cargan automaticamente al cargarla en una vista.
1. Que la integración con el marco de topologia funciona, pudiendose registrar planes
   de topologia en el repositorio, asociarlos a tablas de este, y ejecutarlos antes de subir cambios
   al repositorio.
   
El *plan de pruebas* se ha diseñado para la version 2.6.0-3221 de gvSIG desktop.

{% comment %}
1. Que se se detectan correctamente los conflictos al editar simultaneamente desde dos usuario una capa del repositorio.
1. Que se pueden definir modelos de datos y se puede cargar en los puestos.
{% endcomment %}

## Prerrequisitos

1. La version de gvSIG desktop a utilizar sera la 2.6.0-3221 o superior.

1. Para ejecutar este plan de prueba **se utilizaran dos portables de gvSIG desktop**. A lo largo
   del plan de pruebas nos referiremos a ellas como:
     * gvSIG desktop portable para el ```Servidor```.
     * gvSIG desktop portable para el ```Cliente```.
     
   Estas estaran descomprimidas en dos carpetas distintas en el sistema de ficheros.
   
   Durante la ejecución del plan de pruebas se ira indicando en cada caso que gvSIG desktop hay que 
   iniciar y con cual trabajar según las operaciones que se vayan a realizar. Siendo la pauta
   normal que a lo largo de la ejecución del plan esten iniciados los dos gvSIG desktop.

</div>

## Casos de prueba

<form  markdown="1">

1. ${InputUnknownOkError} [VC00CR00CP002 Iniciar servidor](../CR00/CP002/testVC00CR00CP002.md).
1. ${InputUnknownOkError} [VC00CW00CP002 Crear copia de trabajo](../CW00/CP002/testVC00CW00CP002.md).
1. ${InputUnknownOkError} [VC00AD00CP002 Añadir capa a la copia de trabajo (add)](../AD00/CP002/testVC00AD00CP002.md).
1. ${InputUnknownOkError} [VC00SY00CP002 Subir capa al repositorio (commit)](../SY00/CP002/testVC00SY00CP002.md).
1. ${InputUnknownOkError} [VC00CO00CP002 Obtener copia de trabajo de una capa (checkout)](../CO00/CP002/testVC00CO00CP002.md).
1. ${InputUnknownOkError} [VC00RE00CP0003 Asociar leyenda a una capa](../RE00/CP003/testVC00RE00CP003.md).
1. ${InputUnknownOkError} [VC00TP00CP000 Cargar un plan topologico en el repositorio](../TP00/CP000/testVC00TP00CP000.md).
1. ${InputUnknownOkError} [VC00TP00CP001 Asociar un plan topologico a una capa](../TP00/CP001/testVC00TP00CP001.md).
1. ${InputUnknownOkError} [VC00TP00CP002 Subir cambios en una capa con un plan topologico (que no pasen el plan)](../TP00/CP002/testVC00TP00CP002.md).
1. ${InputUnknownOkError} [VC00TP00CP003 Subir cambios en una capa con un plan topologico (que sí pasen el plan)](../TP00/CP003/testVC00TP00CP003.md).
1. ${InputUnknownOkError} [VC00CO00CP005 Obtener una revision concreta de una capa](../CO00/CP005/testVC00CO00CP005.md).
1. ${InputUnknownOkError} Exportar una capa a una fecha dada.
1. ${InputUnknownOkError} Exportar una capa a una revision dada.
1. ${InputUnknownOkError} Importar historial.
1. ${InputUnknownOkError} Definir y descargar un modelo de datos.

<table border="0">
<tr>
<td nowarp>Responsable de ejecutar el plan:</td><td width="90%"><input type="text" style="display:table-cell; width:100%"></td>
</tr>
<tr>
<td>Fecha de ejecucion del plan:</td><td><input type="date"></td>
</tr>
<tr>
<td nowrap>Version de gvSIG desktop utilizada:</td><td><input type="text" values="2.6.0-3221"></td>
</tr>
<tr>
<td colspan="2">Notas:<br><textarea rows="10" cols="80"></textarea></td>
</tr>
</table>
<input type="reset" value="Restablecer valores">
<input type="button" value="Imprimir" onclick="window.print();">
</form>

{% include es/footer.html %}
