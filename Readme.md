# La huella de las armas españolas en el mundo

## Máster en Periodismo y Visualización de Datos

### Trabajo de fin de máster

- Autor: Darío Ojeda

- Tutor: Adrián Blanco

Este es el trabajo fin de máster del **Máster en Periodismo y Visualización de Datos** (MPVD) de la **Universidad de Alcalá**. Como tarea final del curso se nos pidió elaborar un proyecto de periodismo y visualización de datos aplicando lo aprendido durante el curso. 

El tema que elegí es la venta de armas españolas. Lo objetivos que me propuse, como detallé en la propuesta, eran los siguientes:

- Cuánto armamento vende España
- A quién se lo vende
- Para qué se lo vende
- Dónde y cómo se utiliza
- Las consecuencias de esa utilización

No he conseguido cumplirlos todos, pero al menos creo que el proyecto permite conocer el creciente peso de la industria de defensa española, que en las últimas dos décadas se ha situado entre las más importantes del mundo. Y también que una parte de esas armas acaban en países con conflictos armados abiertos.

#### Qué contiene este repositorio

Los siguientes archivos en la carpeta `data`:

`TIV-Export-SPA-1950-2021.csv`: archivo original del **Stockholm International Peace Research Institute** (SIPRI) con los datos anuales de exportaciones de los principales tipos de armas de España desde 1950 hasta 2021.

`TIV-Export-Top-20-2000-2021.csv`: archivo original del SIPRI con los datos de los 20 países que más armas exportaron entre el 2000 y el 2021.

`exportaciones_espana_paises_2005_2021.csv`: archivo en formato largo con todas las exportaciones de material de defensa de España a cada país entre 2005 y 2021.

`armas_arabia_saudi_05_21.csv`: archivo con los datos anuales de exportaciones de armas a Arabia Saudí entre 2005 y 2021 con los que se elaboró el gráfico de columnas.

`exportaciones_tipo_arma.ipynb`: notebook de Jupyter para limpiar los datos de las exportaciones de España por tipo de arma desde 1950.

`exportaciones_armas_tipo_espana_1950_2021.csv`: archivo con los datos de las exportaciones de España por tipo de arma desde 1950 con los que se elaboró el gráfico de áreas.

`top_20_exportadores_2000_2021.ipynb`: notebook de Jupyter para extraer los datos de los 20 países que más armas exportaron entre el 2000 y el 2021.

`ranking_armas_int_00_21.csv`:  archivo con los datos del ránking de países más exportadores desde el año 2000 para elaborar el gráfico de barras.

`codigo_graficos.rmd`: código para la elaboración del gráfico de columnas, el gráfico de barras y el gráfico de áreas en R.

Además, los archivos necesarios para montar la web:

`index.html`: archivo html con el código de la web.

`assets`: carpeta con los archivos css y javascript.

`img`: carpeta con los svg de las visualizaciones.

#### Fuente de los datos

Para este proyecto he utilizado datos de cuatro fuentes:

- El gráfico de Arabia Saudí y el mapa están elaborados con la información de [los informes](https://comercio.gob.es/ImportacionExportacion/Informes_Estadisticas/Paginas/Hitorico_Material_Defensa.aspx) de las exportaciones de material de defensa y doble uso que publica el **Ministerio de Industria, Comercio y Turismo**. La Secretaría de Estado de Comercio elabora cada año el informe **"Estadísticas españolas de exportación de material de defensa, de otro material y de productos y tecnología de doble uso"**. Se han tenido en cuenta solo el volumen total (en euros) de exportaciones realizadas (los informes también detallan las exportaciones autorizadas) de las 22 tipos de artículos que detallan los informes.

- El ránking de países y la evolución de las exportaciones de los principales tipos de armas (aeronaves, barcos, vehículos blindados, etc. ) están elaborados con con información de [la base de datos de transferencia de armas del SIPRI](https://www.sipri.org/databases/armstransfers), que contiene información detallada desde 1950 hasta la actualidad. 

- Los datos de conflictos utilizados para pintar el mapa están extraídos de [la base de datos](https://www.prio.org/data/31) del **Peace Research Institute Oslo (PRIO)**. La cartografía del mapa es de Natural Earth.

#### Herramientas utilizadas

La información de los PDF del Ministerio de Industria, Comercio y Turismo la extraje con varias herramientas: **pdftk** desde la consola para separar las páginas en las que estaban las tablas, **Tabula** para leerlas y convertirlas a csv y **OpenRefine** para manipularlas y quedarme con un archivo csv en formato largo con todos los datos de exportaciones de España por países desde 2005 a 2021. De ahí obtuve el dato de exportaciones totales a cada país en ese período de tiempo para pintarlo en el mapa de símbolos proporcionales y las cifras de exportaciones a Arabia Saudí para el gráfico de barras.

Los datos del SIPRI, tanto los del ránking de países como la evolución de las ventas españolas por tipo de arma, los trabajé con la librería **Pandas** de **Python** y los terminé de manipular con el paquete **Tidyverse** de **R**.

El proyecto incluye cinco visualizaciones. Tres de ellas (el gráfico de columnas, el gráfico de barras y el gráfico de áreas) están elaboradas con la librería **ggplot2** de R y después rematadas con Inkscape. Ese programa también lo he utilizado para rematar el mapa hecho con **QGIS** y para hacer las cuatro imágenes del pictograma que he incluido en el 'scrolly' de la página. Por último, para la web he utilizado **Bootstrap**, la librería **Scrollama** de Javascript y el editor **Visual Studio Code**.

#### Conclusiones

Antes de empezar a trabajar en este proyecto desconocía el peso de la industria de defensa española a nivel mundial. Ahora sé que España es uno de los principales exportadores de armas del mundo. **Este siglo, en apenas una década, las exportaciones se multiplicaron por diez y pasaron de 400 millones de euros a 4.000**. Aunque han bajado en los últimos años, siguen estando por encima de los 3.000 millones anuales.

También sé que parte de esas armas se venden a países inmersos en conflictos armados dentro y fuera de sus fronteras, lo que deja una huella española en guerras que se producen por todo el mundo. El caso más claro es el de Arabia Saudí (uno de los grandes socios de la industria armamentística española), como escenificó el bombero  Ignacio Robles en 2017, pero hay más casos, como Turquía o Marruecos.
