---
title: Plan de prueba "basico" (repositorio remoto en H2 con autorizacion)
testcode: VC00PLAN002
srcpath: "casos/VC00/plans/planVC00PLAN002.md"
---

{% include es/header.md %}

# {{ page.title }}

Este plan de prueba contiene test para verificar la funcionalidad basica de VCSGis sobre 
un repositorio con la autenticacion y autorizacion de usuarios activada.

Comprueba:
* Que se crea un repositorio sobre una BBDD de H2.
* Que se crea una copia de trabajo.
* Que se pueden añdir a la copia de trabajo capas, commitarlas y hacer checkout de ellas.

{% comment %}

* Que se se detectan correctamente los conflictos al editar simultaneamente desde dos usuario una capa del repositorio.

{% endcomment %}

* Que se se pueden crear leyendas asociadas a una capa y se cargan automaticamente al cargarla en una vista.
* Que se pueden definir modelos de datos y se puede cargar en los puestos.

Casos de prueba:
* ${check} [Crear repositorio sobre H2](../CR00/CP001/testVC00CR00CP001.md).
* ${check} [Crear copia de trabajo](../CW00/CP002/testVC00CW00CP002.md).

* ${check} [Añadir capa a la copia de trabajo (add)](../AD00/CP002/testVC00AD00CP002.md).
* ${check} [Subir capa al repositorio local (commit)](../CI00/CP002/testVC00CI00CP002.md).
* ${check} [Descargar capa a la copia de trabajo (checkout)](../CO00/CP002/testVC00CO00CP002.md).

* ${check} [Asociar leyenda a una capa](CP003/testVC00RE00CP003.md).
* ${check} [Definir y descargar un modelo de datos](CP003/testVC00RE00CP003.md).

* ${check} [Cargar un plan topologico en el repositorio](../TP00/CP000/testVC00TP00CP000.md).
* ${check} [Asociar un plan topologico a una capa](../TP00/CP001/testVC00TP00CP001.md).
* ${check} [Subir cambios en una capa con un plan topologico (sin pasar el plan)](../TP00/CP002/testVC00TP00CP002.md).

{% include es/footer.html %}


