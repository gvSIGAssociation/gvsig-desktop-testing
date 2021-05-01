# Conceptos basicos.

Aqui se explican brebemene los conceptos basicos utilizados en los planes y casos de prueba.


* **Plan de pruebas**. Representa un conjunto de pruebas realizar sonbre una funcionalidad o grupos de funcionalidades.
  Pueden existir varios *planes de prueba* que comprueben una funcionalidad o grupo de estas,
  cada uno de estos haciendolo con un nivel de detalle distinto, disponiendo asi de *planes de prueba*
  mas ligeros y rapidos de pasar que garantizan minimamante el correcto de una funcionalidad o grupo de estas,
  y otros mas pesados que comprueban en detalle las mismas funcionalidades. Es normal disponer de dos
  o tres planes de prueba sobre una misma funcionalidad o grupo.

* **Grupo de casos de prueba**. Agrupa un conjunto de casos de prueba normalmente de una funcionalidad concreta.
  Es un mero artefacto para mejorar la orgaizacion de los casos de prueba. Normalmente los casos de prueba 
  que agrupa son usados en varios *planes de prueba*.
  
* **Caso de prueba**. Representa a una prueba a realizar sobre una funcionalidad. 
  Normalmente la prueba es *atomica*, se pasa o no. Se identifica por un codico unico de trece caracteres. 
  Suele constar de:
  * Su codigo.
  * Un titulo.
  * Una descripcion informal de en que consiste la prueba que se va a realizar.
  * Una serie de datos de entrad que podemos necesitar para pasar la prueba (nombres de fichero, capas...).
  * Una serie de requisitos que debemos cumplir antes de tratar de realizar la prueba (software instalado, plugins...).
  * Una Serie de pasos a realizar especificando como hay que realizarlo y que esperar tras su ejecucion.
  * Una descripcion de cuales son los resultados esperados.
  * Indicaciones sobre como consultar si ya hay errores reportados sobre el *caso de prueba* o 

* **Procedimiento**. Representa un fragmento de un test que normalmente se va a reutilizar
  en varios *casos de prueba*. Suele constar de los mismos elementos que un *caso de prueba*, cobrando
  especial importancia la descripcion de los datos de entrada, los cuales deberan especificarse en 
  el *caso de prueba* donde se usen.
