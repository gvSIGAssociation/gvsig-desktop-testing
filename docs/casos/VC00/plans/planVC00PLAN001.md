---
title: Plan de prueba "minimo" (repositorio local en H2 con autorizacion)
testcode: VC00PLAN001
srcpath: "casos/VC00/plans/planVC00PLAN001.md"
---

{% include es/header.md %}

# {{ page.title }}

Este plan de prueba contiene test para verificar la funcionalidad basica de VCSGis sobre 
un repositorio local en H2 con la autenticacion y autorizacion de usuarios activada.


<div class="noprint"  markdown="1">
<style scoped>
@media print{
   .noprint{
       display:none;
   }
}
</style>
</div>

<form  markdown="1">

Comprueba:
1. Que se crea un repositorio.
1. Que se crea una copia de trabajo.
1. Que se pueden añdir a la copia de trabajo capas, commitarlas y hacer checkout de ellas.

Casos de prueba:

1. ${InputUnknownOkError} [Crear repositorio sobre H2](../CR00/CP001/testVC00CR00CP001.md).
1. ${InputUnknownOkError} [Crear copia de trabajo asoiada a un repositorio local en H2](../CW00/CP001/testVC00CW00CP001.md).
1. ${InputUnknownOkError} [Añadir capa a la copia de trabajo (add)](../AD00/CP001/testVC00AD00CP001.md).
1. ${InputUnknownOkError} [Subir capa al repositorio local (commit)](../SY00/CP001/testVC00SY00CP001.md).
1. ${InputUnknownOkError} [Descargar capa a la copia de trabajo (checkout)](../CO00/CP001/testVC00CO00CP001.md).

<table border="0">
<tr>
<td>Persona&nbsp;que&nbsp;ha&nbsp;pasado&nbsp;el&nbsp;plan:</td><td width="90%"><input type="text" style="display:table-cell important!; width:100% important!"</td>
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

