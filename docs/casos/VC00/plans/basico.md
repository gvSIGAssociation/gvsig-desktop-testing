# Plan de prueba "basico" sobre VCSGis.

Este plan de prueba contiene test para verificar la funcionalidad basica de VCSGis.

Comprueba:
* Que se crean correctamente repositorio sobre una BBDD de H2.
* Que se crean copia de trabajo asociadas a un repositorio en H2 local y remoto.
* Que se pueden añdir a la copia de trabajo capas, commitarlas y hacer checkout de ellas.
* Que se se detectan correctamente los conflictos al editar simultaneamente desde dos usuario una capa del repositorio.
* Que se se pueden crear leyendas asociadas a una capa y se cargan automaticamente al cargarla en una vista.
* Que se pueden definir modelos de datos y se puede cargar en los puestos.
* Que esto funciona con y sin activar la autenticacion y autorizacion en el repositorio.

Casos de prueba:
* [Crear repositorio sobre H2](../CR00/CP000/testVC00CR00CP000.md).
* [Crear copia de trabajo asoiada a un repositorio local en H2](../CW00/CP000/testVC00CW00CP000.md).
* [Añadir capa a la copia de trabajo (add)](../AD00/CP000/testVC00AD00CP000.md).
* [Subir capa al repositorio local (commit)](../CI00/CP000/testVC00CI00CP000.md).
* [Descargar capa a la copia de trabajo (checkout)](../CO00/CP000/testVC00CO00CP000.md).





