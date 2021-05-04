---
title: Plan de prueba "basico" (repositorio remoto en H2 con autorizacion)
plancode: VC00PLAN002
srcpath: "casos/VC00/plans/planVC00PLAN002.md"
---

{% include es/header.md %}

# {{ page.title }}

Este plan de prueba contiene test para verificar la funcionalidad basica de VCSGis sobre 
un repositorio remoto en H2 con la autenticacion y autorizacion de usuarios activada.


<div class="noprint"  markdown="1">
<style scoped>
@media print{
   .noprint{
       display:none;
   }
}
</style>
## Descripción
   
Comprueba:

1. Que se crea un repositorio.
1. Que se crea una copia de trabajo.
1. Que se pueden añdir a la copia de trabajo capas, commitarlas y hacer checkout de ellas.
1. Que se se pueden crear leyendas asociadas a una capa y se cargan automaticamente al cargarla en una vista.
1. Que la integración con el marco de topologia funciona, pudiendose registrar planes
   de topologia en el repositorio, asociarlos a tablas de este, y pasarlos antes de subir cambios
   al repositorio.
{% comment %}
1. Que se se detectan correctamente los conflictos al editar simultaneamente desde dos usuario una capa del repositorio.
1. Que se pueden definir modelos de datos y se puede cargar en los puestos.
{% endcomment %}

## Prerrequisitos

Para pasar este plan de prueba se utilizaran dos versiones portables de gvSIG desktop. A lo largo
del plan de pruebas nos referiremos a ellas como "Servidor" y "Cliente".

</div>

## Casos de prueba

<form  markdown="1">

1. ${InputUnknownOkError} [Iniciar servidor](../CR00/CP002/testVC00CR00CP002.md).
3. ${InputUnknownOkError} [Crear copia de trabajo](../CW00/CP002/testVC00CW00CP002.md).
4. ${InputUnknownOkError} [Añadir capa a la copia de trabajo (add)](../AD00/CP002/testVC00AD00CP002.md).
5. ${InputUnknownOkError} [Subir capa al repositorio local (commit)](../SY00/CP002/testVC00SY00CP002.md).
6. ${InputUnknownOkError} [Descargar capa a la copia de trabajo (checkout)](../CO00/CP002/testVC00CO00CP002.md).
7. ${InputUnknownOkError} [Asociar leyenda a una capa](CP003/testVC00RE00CP003.md).
8. ${InputUnknownOkError} [Cargar un plan topologico en el repositorio](../TP00/CP000/testVC00TP00CP000.md).
9. ${InputUnknownOkError} [Asociar un plan topologico a una capa](../TP00/CP001/testVC00TP00CP001.md).
10. ${InputUnknownOkError} [Subir cambios en una capa con un plan topologico (que sí pasen el plan)](../TP00/CP002/testVC00TP00CP002.md).
11. ${InputUnknownOkError} [Subir cambios en una capa con un plan topologico (que no pasen el plan)](../TP00/CP003/testVC00TP00CP003.md).
{% comment %}
1. ${InputUnknownOkError} [Definir y descargar un modelo de datos](CP003/testVC00RE00CP003.md).
{% endcomment %}

<table border="0">
<tr>
<td>Persona&nbsp;que&nbsp;ha&nbsp;pasado&nbsp;el&nbsp;plan:</td><td width="90%"><input type="text" style="display:table-cell; width:100%"></td>
</tr>
<tr>
<td>Fecha:</td><td><input type="date"></td>
</tr>
<tr>
<td colspan="2">Notas:<br><textarea rows="10" cols="80"></textarea></td>
</tr>
</table>
<input type="reset" value="Restablecer valores">
</form>

{% include es/footer.html %}
