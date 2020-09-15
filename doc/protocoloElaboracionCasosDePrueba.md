# Protocolo para la elaboracion de casos de prueba
## gvSIG Association.

### 1. ¿Que es un caso de prueba?
Un caso de prueba no es mas que un breve documento que describe de manera detallada el comportamiento de una parte o herramienta del software al realizar una determinada accion concreta. Para que esta simulacion sea de utilidad las condiciones con las que se realiza deben de ser fijas al igual que los datos utilizados, testandose unicamente el “motor” o algoritmo que trata dichos datos bajo dichas condiciones.
Por tanto, la funcion principal de un caso de prueba es poder detectar errores de manera facil y sin apenas consumir tiempo y esfuerzo cada vez que se realizan cambios en el codigo del software.

### 2. Partes de un caso de prueba
Un caso de prueba es un documento en formato Markdown (.md) compuesto por las partes que se detalla en la siguiente ilustracion.

![Partes de un caso de prueba](https://github.com/jolicar/gvsig-desktop-testing/blob/master/doc/images/partesCasoDePrueba.PNG)

  1) **Titulo**. Esta compuesto por un identificador unico mas una breve frase de describe que se va a probar.
  2) **Enlace de peticion existente con ese caso**. Enlace a la web de control de errores de gvSIG con el identificador unico de forma que se puede comprobar si ya hay algun reporte de error asociado al caso en cuestion.
  3) **Descripcion**. Breve texto que resume la accion a realizar asi como el tipo de resultados obtenidos. La descripcion debe identificar sin ninguna tipo de duda el comportamiento a testear. 
  4) **Prerrequisitos**. Lista con los datos y configuracion necesarios para la correcta ejecucion del caso practico.
  5) **Pasos**. Secuencia de acciones a realizar que proporcionan una serie de resultados tanto intermedios como finales. Esta es la parte mas importante del documento ya que en ella se detallan todos los aspectos a probar y la forma de hacerlo.
  6) **Resultados esperados**. Texto en el que se indican tanto los resultados intermedios si son necesarios, como los resultados finales del caso. Puede presentarse como un parrafo o en forma de lista si los resultados son varios o asi se mejora la comprension.
  7) **Reportar fallo**. Parte del documento en el que se facilita la comunicacion de errores detectados tras realizar el caso practico. Se compone de dos enlaces, un primer enlace que te dirige a la pagina web de control de errores de gvSIG y un segundo enlace, que previo a identificacion te permite reportar en la pagina anterior una peticion de correccion de error de dicho caso mediante su identificador unico y titulo de manera automatica.

#### 2.1 Markdown
Como se cita en el anterior apartado los casos de prueba son documentos en formato Markdown (.md). El formato Markdown es una herramienta que permite convertir un texto plano a formato HTML.
En este [enlace](https://www.youtube.com/watch?time_continue=148&v=y6XdzBNC0_0&feature=emb_logo ) puedes ver de manera rapida las diferentes formas de editar un texto en Markdown.

A parte de lo anterior, el **Editor de Scripts** de gvSIG al tratar con archivos en este formato, permite realizar mediante iconos alguna de esas formas para facilitar aun mas el trabajo.

![Iconos de Markdown en gvSIG](https://github.com/jolicar/gvsig-desktop-testing/blob/master/doc/images/iconosMD.png)

### 3. Almacenamiento 
El almacenamiento de los casos de prueba se realiza en una estructura de carpetas de modo que estos queden diferenciados segun la herramienta que testeen. Dicha estructura de carpetas se basa en una carpeta madre llamada testing, la contiene tres carpetas hijas llamadas casos, datos y planes.
  - **Casos**. Dicha carpeta es la mas importante y en ella se almacenan los casos como tal. Esta carpeta almacena todos los casos de prueba del software divididos en varias “capas” de subcarpetas o carpetas hijas. Un ejemplo de esto se detalla a continuacion; Si se busca realizar el caso de prueba detallado en el apartado 2, este se almacenara en la siguiente sucesion de carpetas.
    
    ***testing/casos/HE00_herramientas/FB00_ficha_de_busqueda_simple/CP002_1c_igual_str***
    
    La carpeta  ***HE00_herramientas*** almacena los casos de prueba referentes a herramientas del software, la carpeta  ***FB00_ficha_de_busqueda_simple*** guarda los casos de la herramienta ficha de busqueda simple y por ultimo la carpeta ***CP002_1c_igual_str*** es la que almacena todo lo referente a ese caso en cuestion, en este caso un archivo readme.md.

*NOTA: Los caracteres iniciales de cada carpeta conforman el identificador unico con el que se identifica de manera inequivoca al caso de prueba.*

  - **Datos**. Esta carpeta al igual que la anterior se subdivide en otras subcarpetas que almacena si es necesario los datos para ejecutar los casos de prueba. Esta carpeta se suele utilizar si todos los casos de prueba de una herramienta presentan el mismo dataset, si cada caso presenta un conjunto de datos diferente este se almacena en la carpeta que contiene el archivo markdown.
  - **Planes**. Al igual que las dos anteriores, la carpeta se subdivide en otras subcarpetas en funcion de las diferentes herramientas. En esta carpeta se guardan los planes de prueba que son un documento que engloba todos los casos de prueba para una herramienta. A continuacion se muestra la estructura de un plan de prueba.

![Estructura plan de prueba](https://github.com/jolicar/gvsig-desktop-testing/blob/master/doc/images/planDePrueba.png)

#### 3.1 GitHub
En este subapartado del apartado **3. Almacenamiento** se esboza la herramienta que utiliza el software gvSIG para el control de versiones, lo que mas coloquialmente podria decirse como creacion de copias de seguridad en linea.
La herramienta utilizada en cuestion es GitHub y no solo permite la gestion de copias de seguridad en linea sino que tambien permite trabajar a varios usuarios sobre un mismo proyecto de manera simultanea. Dicha herramienta para mayor comodidad de los usuarios y desarrolladores ha sido implantada en el **Editor de Scripts** de gvSIG Desktop.
El acceso a la herramienta pude realizarse de dos modos, accediendo a **git** dentro de la pestana **Herramientas**, ver siguiente ilustracion.

![Acceso 1 a herramientas GitHub](https://github.com/jolicar/gvsig-desktop-testing/blob/master/doc/images/accesoGit.png)

La segunda forma de acceder a los diferentes utiles de la herramienta es mediante iconos presentes en el propio interfaz del *Editor de Scripts* de gvSIG Desktop.
La secuencia logica para trabajar gestionando un proyecto con GitHub es la siguiente:
1. Creacion de carpeta local con el mismo nombre que el proyecto donde se va atrabajar.
2. Clone del repositorio en GitHub al equipo. Para ello es necesario la URL del repositorio que contiene el proyecto en GitHub.
3. Comprobar si la carpeta contiene la informacion disponible en internet. Lo anterior se puede comprobar mediante el comando **Refrescar** dentro de la pestana **Proyectos**.
4. Anadir, modificar o borrar archivos o carpetas. Para anadir archivos o carpetas se dispone de un icono o se puede realizar con comandos desde la pestana **Archivo**.
5. Para asegurar los cambios en el repositorio de GitHub se tiene que hacer “commit” y posteriormente “Push”.
    
*NOTA: Ademas de lo anterior se puede realizar mas acciones con GitHub y su implementacion en gvSIG pero no se considera necesario explicarlo ya que para la creacion y gestion de casos de prueba lo anterior es mas que suficiente.*

### 4. Buena praxis
A continuacion se detallan una serie de recomendaciones a tener en cuenta para la correcta elaboracion de un caso de prueba.
- Cuidar la ortografia en todo el documento.
- Garantizar la comprension de todo el texto. Prestar especial atencion a la **Descripcion** ya que esta debe describir inequivocamente lo que se va a realizar.
- El **Titulo** debe estar compuesto por el identificador unico y un breve resumen de la descripcion.
- El apartado **Pasos** debe de detallar sin ningun tipo de dudas la accion a realizar por simple que sea.
- En el apartado **Pasos** no se debe obviar ningun paso intermedio por simple que sea.
- En el apartado de **Resultados esperados** se puede detallar el resultado en un parrafo o en forma de lista si hay resultados intermedios. La eleccion del formato dependera de que caso hace mas comprensible el resultado final. 
- Se permite el uso de imagenes en los apartados **Pasos** y  **Resultados esperados**, pero si se puede describir en texto mejor.
