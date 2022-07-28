# Memoria - TFM - MPVD - 2021-2022

Autor:  Darío Ojeda

Tutor: Adrián Blanco

## Agradecimientos

- A Adrián Blanco por sus consejos y su paciencia durante las últimas semanas de trabajo con el TFM.

- A Adolfo Antón por la coordinación del máster y por su ayuda en la matriculación al comienzo del curso.

- Al claustro por su trabajo durante todo el curso, en unas condiciones (clases 'online') que no son las mejores, pero en las que han sabido transmitirnos los conocimientos necesarios para seguir mejorando a partir de ahora.

- A todos los invitados a dar las charlas y talleres por dedicarnos su tiempo y responder a nuestras preguntas.

- Y a mis compañeros por su apoyo, su entusiasmo y su esfuerzo a lo largo del último año.

## Título

**"La huella de las armas españolas en el mundo"**

## Fecha

03/07/2022

## Objetivos

El tema elegido fue la venta de armas españolas y su huella en el mundo. Lo objetivos que me propuse se pueden dividir en dos bloques: los propios del asunto tratado y aquellos producto de la aplicación de las herramientas aprendidas durante el curso. Detallo brevemente los primeros antes de profundizar en los segundos:

- Cuánto armamento vende España
- A quién se lo vende
- Para qué se lo vende
- Dónde y cómo se utiliza
- Las consecuencias de esa utilización

Solo tenía una cosa clara cuando empecé a pensar en cómo iba a ser mi TFM: quería utilizar cuantas más herramientas posibles de aquellas que habíamos conocido durante el máster. El contenido era secundario. Fuera cual fuera, después debería esforzarme por visualizarlo utilizando esa variedad de herramientas.

Como el formato de presentación debía ser preferentemente una web, la utilización de HTML, CSS y JavaScript, vistos en el módulo 8, estaba asegurada. A partir de ahí, decidí utilizar los dos principales lenguajes de programación utilizados durante el curso para el análisis de datos: Python y R (vistos en los módulos 3, 5, 6 y 7). Quería también utilizar programas de edición de imagen, como Inkscape (módulo 4); la terminal (módulos 1 y 4); y elaborar algún mapa (módulo 9). Y por supuesto, teniendo en cuenta también la parte más teórica de lo aprendido, como el módulo 2. El objetivo era poner en práctica la mayor cantidad posible de conocimientos adquiridos durante el máster. 

## Metodología

### Localización de los datos

La búsqueda de los datos la realicé durante el proceso de elección del tema para el TFM. Para mi objetivo de mostrar la huella de las armas españolas en el mundo, necesitaba saber tres cosas: cuántas armas vende España y a qué países; cuántas armas vende en comparación con otros países; y los conflictos armados que se han desarrollado en el mundo. Localicé esos datos en tres fuentes: 

- Los [informes](https://comercio.gob.es/ImportacionExportacion/Informes_Estadisticas/Paginas/Hitorico_Material_Defensa.aspx) de las exportaciones de material de defensa y doble uso que publica el Ministerio de Industria, Comercio y Turismo en virtud de la Ley 53/2007, de 28 de diciembre, sobre el control del comercio exterior de material de defensa y de doble uso. La Secretaría de Estado de Comercio elabora cada año el informe "Estadísticas españolas de exportación de material de defensa, de otro material y de productos y tecnología de doble uso". De ahí obtuve el dato de exportaciones totales a cada país  (en euros) entre 2005 y 2021.

- La [base de datos](https://www.sipri.org/databases/armstransfers) de transferencia de armas del Stockholm International Peace and Research Institute (SIPRI), que contiene información detallada desde 1950 hasta la actualidad. De ahí obtuve tanto el ránking de países exportadores desde el año 2000 como la evolución de las ventas españolas por tipo de arma desde 1960.

- La [base de datos](https://www.prio.org/data/31) de conflictos del Peace Research Institute Oslo (PRIO).


### Manipulación de los datos

La extracción y el trabajo con los datos no fue igual en los tres casos. Para extraer las tablas de los informes del Ministerio de Industria, Comercio y Turismo utilicé tres herramientas: pdftk desde la consola para separar las páginas en las que estaban esas tablas; Tabula para leerlas y convertirlas a csv; y OpenRefine para limpiarlas y quedarme con un archivo csv en formato largo.

Los datos del SIPRI y del PRIO estaban en formato csv, por lo que su limpieza y tratamiento fue más sencillo: lo hice con la librería Pandas de Python y los terminé de manipular con el paquete Tidyverse de R.

### Visualizaciones

El proyecto incluye cinco visualizaciones. Tres de ellas (gráfico de columnas con las ventas de armas a Arabia Saudí; gráfico de barras con el ránking de países exportadores desde el año 2000); y  gráfico de áreas con las ventas españolas por tipo de arma desde 1960) están elaboradas con la librería ggplot2 de R y después rematadas con Inkscape. En los tres casos, consulté la web 'The R Graph Gallery' en busca de ejemplos y también la referencia de ggplot2 para modificar el tema de los gráficos. Luego los exporté como SVG.

Otra de las visualizaciones es un mapa de símbolos proporcionales que muestra a qué países ha vendido más armas España desde el año 2005 y si esos países han estado inmersos en conflictos armados en alguno de los años en los que ha recibido armas españolas. Para empezar, localicé la cartografía en [Natural Earth](https://www.naturalearthdata.com/).

. Por otra parte, extraje con Pandas la tabla exportaciones totales de armas españolas por país desde 2005. Y uní a esos datos los datos de conflictos, de modo que para cada país tenía la información de cuántas armas había recibido (si es que había comprado armas a España) y si había tenido o participado o no conflicto (interno o externo).

Con la cartografía y los datos cargados en QGIS, empecé a construir el mapa, que además de los símbolos proporcionales (según la cantidad de armas) es también un mapa coroplético cualitativo en base a los datos de conflictos. Tras elaborarlo, lo edité en el mismo programa (título, subtítulo, fuente, leyenda, etc.) y lo exporté como SVG.

Terminé de tratarlo en Inkscape, donde modifiqué incluí la leyenda de las coropletas en el subtítulo dándolo color a la fuente. Utilicé ese mismo programa para rematar los tres gráficos elaborados con R: además de darles a todos el mismo tamaño y ajustar los títulos, cambié el color de la barra de España en el gráfico de barras para destacarlo.

También utilicé Inkscape para elaborar el pictograma del 'scrolly' de la web. Los informes del ministerio desde 2007 incluyen detalles de las exportaciones de armas de más de 10 millones de euros. Entre los tipos de armas en ese rango de precio están distintos tipos de aeronaves, buques y vehículos blindados. Los conté e hice un pictograma en el que cada icono representa diez unidades. Los iconos son de [SVG Repo](https://www.svgrepo.com/).

Los colores utilizados en todo el proyecto son los siguientes: 

- Color principal: #0c2d41
- Color secundario: #f03351
- Otros colores: #4e8bb9 / #bfbdb2
- Fondo del mapa: #e8e6dc

Es la paleta de colores que utiliza El Confidencial en sus gráficos.

### Web

Para la web, utilicé una plantilla de Bootstrap similar a la utilizada en las clases del módulo 8 del máster. La elaboración de la web fue la puesta en práctica de lo visto en ese módulo. En el proyecto también tenía claro que quería utilizar la librería Scrollama, de ahí el pictograma, que son cuatro imágenes. Con la plantilla elegida y esa idea clara, monté la web modificando la fuente (elegí Roboto), el ancho de la columna de texto, el color de fondo, añadiendo una caja al final para diferenciar el texto de la metodología del resto o modificando las 'cards' del 'scrolly'.

Una vez completado el trabajo, modifiqué más aspectos para que la web se viera sin problemas en móvil, como el espacio entre la cabecera y el cuerpo del artículo o el 'padding' de los svg de los gráficos, que en la primera versión estaban demasiado ajustados a los bordes. La programación de la web la hice con Visual Studio Code.

### Repositorio

El último paso fue subir la web a un repositorio de Github, cosa que hice desde la terminal.

## Bibliografía

Además de la bibliografía proporcionada por los profesores a lo largo del máster, he consultado los siguientes recursos web y libros durante la elaboración del TFM:

- [The R Graph Gallery](https://r-graph-gallery.com/)

- [Bootstrap](https://getbootstrap.com/)

- [Ggplot2](https://ggplot2.tidyverse.org/reference/theme.html)

- "Data Visualization. A practical Introduction". Kieran Haley

- "Curso de desarrollo web. HTML, CSS y Javascript". Mario Rubiales Gómez

## Enlaces al proyecto

[Repositorio](https://github.com/ojedadario/tfm-mpvd-armas-espana)

[Web](https://ojedadario.github.io/tfm-mpvd-armas-espana/)

## Conclusiones

Extraigo varias lecciones del TFM. La primera es que un trabajo así necesita planificación y no se puede/debe improvisar. Esa planificación exige establecer ventanas de tiempo para las distintas fases del trabajo, desde el estudio del tema elegido a los últimos pasos, como la visualización y la elaboración de la web. Pero sobre todo, para la limpieza y el análisis de los datos.

Como nos habían advertido muchos profesores, en proyectos de este tipo, la tarea de limpiar los datos es la más costosa. Y aunque la elección de mi tema estuvo motivada, en parte, por la facilidad de acceso a los datos, una parte de ellos (los que estaban en los informes en PDF del Ministerio de Industria, Comercio y Turismo) me exigió un gran esfuerzo y bastante tiempo.

Una vez superado ese obstáculo, la parte de visualización fue otra prueba. Realicé la mayoría de los gráficos con la librería ggplot2 porque quería demostrarme que podía conseguirlo. La parte de análisis con R la tenía más clara, no así la visualización. Fue una tarea lenta en la que, ante cada paso que quería dar (modificar cualquier aspecto del gráfico) tuve que buscar cómo hacerlo.

Algo similar me sucedió con Inkscape y con la programación de la web, para lo que utilicé las referencias que nos habían proporcionado los profesores durante el máster. Me costó, pero por el camino aprendí bastante.

El TFM, y el máster, han supuesto un reto para mí. Compaginarlos con el trabajo no ha sido fácil, pero el resultado (y no me refiero solo al trabajo entregado) ha valido la pena.
