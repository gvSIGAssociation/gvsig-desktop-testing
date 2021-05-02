---
title: Plan de prueba "minimo" (repositorio local en H2 con autorizacion)
testcode: VC00PLAN001
srcpath: "casos/VC00/plans/planVC00PLAN001.md"
---

{% include es/header.md %}

# {{ page.title }}

Este plan de prueba contiene test para verificar la funcionalidad basica de VCSGis sobre 
un repositorio local en H2 con la autenticacion y autorizacion de usuarios activada.

Comprueba:
* Que se crea un repositorio.
* Que se crea una copia de trabajo.
* Que se pueden añdir a la copia de trabajo capas, commitarlas y hacer checkout de ellas.

Casos de prueba:
* ${check} [Crear repositorio sobre H2](../CR00/CP001/testVC00CR00CP001.md).
* ${check} [Crear copia de trabajo asoiada a un repositorio local en H2](../CW00/CP001/testVC00CW00CP001.md).
* ${check} [Añadir capa a la copia de trabajo (add)](../AD00/CP001/testVC00AD00CP001.md).
* ${check} [Subir capa al repositorio local (commit)](../SY00/CP001/testVC00SY00CP001.md).
* ${check} [Descargar capa a la copia de trabajo (checkout)](../CO00/CP001/testVC00CO00CP001.md).


{% include es/footer.html %}


