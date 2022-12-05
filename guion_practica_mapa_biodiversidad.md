# Instrucciones para realizar la práctica denominada "Guión de la práctica: Aplicción de WebMapping para la gestión de datos espaciales abientales y forestales"


> + **_Versión_**: 2022-2023
> + **_Asignatura_** : SIG II (Máster GEOFOREST). 
> + **_Autor_**: Cristina (cristina.acosta@uco.es)
> + **_Duración_**: 3,5 horas.



## Objetivos

Esta práctica tiene los siguientes objetivos:
+ Disciplinares:
  + Aprender qué es un WebMapping
  + Conocer los fundamentos de los WebMapping
  
+ Instrumentales:

  + Aprender a utilizar una aplicación de cartografía Web que permita interpretar el análisis de información ambiental y forestal de una zona determinada.
  + Aprender y conocer el proceso de publicación de datos geoespaciales a través de servidores web.
  
## Instrucciones para la práctica

+ Lea atentamente toda la guía.
+ Verifique que cuenta con los elementos de hardware, software, red e inputs necesarios.
+ Identifique y complete la información que se le solicita.
+ Asegúrese de descargar la información necesaria para el desarrollo de esta prácitca.
+ Utilice el material como se lo indica el profesor
+ Al finalizar el ejercicio participe en la socialización de las diferentes respuestas expuestas.   

## Materiales facilitados para la realización de la práctica:

| DESCRIPCIÓN               | NOMBRE Y LOCALIZACION                       |
|---------------------------------|---------------------------------------|
| Guión de la práctica      | UDII_P_GUIA_WEBMAPPING.pdf / Moodle         |
| Datos suministrados       | Data_mapping.rar / Moodle                   |
| Presentación WebMapping   | Presentación_webmapping / Moodle            |

------------------------------------------------------------------------

## Entrega: 

Esta práctica NO tiene ningún entregable por parte del estudiante, solo se desarrollará durante el tiempo de clase para que el estudiante pueda aprender y afianzar conocimientos.  

------------------------------------------------------------------------

## Introducción: Publicar mapas en la web
<a name="inicio"></a>
Webmapping se refiere la publicación de mapas dinámicos en la web, a diferencia de los mapas estáticos (por ejemplo, un PDF). Los mapas web tienen la ventaja de poder llegar a un público más amplio con mayor 
rapidez. Solo tienes que facilitar una URL de tu mapa online, para que otro usuario pueda consultarla. Aunque el mapeo web está estrechamente relacionado con la programación y tiene una curva de aprendizaje, 
existen algunas herramientas que podemos usar para hacer mapas interactivos de una manera fácil.
![WEBMAPPING_diagram](https://github.com/aprendiendo-cosas/P_webmapping_SIGII_Geoforest/blob/main/images/WEBMAPPING_diagram.JPG)
¿Qué es qgis2web?
qgis2web es una herramienta que exporta proyectos QGIS a mapas web OpenLayers o Leaflet (crea automáticamente los archivos HTML, Javascript y CSS).El origen de este complemento está en los complementos qgis2leaf 
existentes, desarrollados por Tom Chadwin, Riccardo Klinger, Victor Olaya, Nyall Dawson (https://github.com/tomchadwin/qgis2web/wiki).
¿Cómo funciona qgis2web?
qgis2web crea un mapa web basado en OpenLayers o Leaflet de todas las capas existentes en un proyecto QGIS. La herramienta convierte capas vectoriales a GeoJSON y crea una estructura de carpetas con un archivo 
index.html que contiene el mapa web. El complemento también puede exportar la simbología definida por QGIS de puntos, líneas y polígonos e incluye un control de visibilidad de capa y varios otros controles.
<p align="center">
<img src="https://github.com/aprendiendo-cosas/P_webmapping_SIGII_Geoforest/blob/main/images/qgis2web.JPG" alt="Figura 2" style="zoom:0%;"/><a name="figura2"></a><br><br>**Figura WebMapping QGIS2WEB**
</p>
En esta práctica desarrollaremos un mapa web, es decir, como proceso de diseñar, aplicar, generar y visualizar datos geoespaciales, así como poder interactuar con ellos. Para ello codificaremos una estructura, apariencia
y funcionalidades del mapa para mostrar capas de diferentes formatos (pueden ser: KMZ, geojson, shp, CAD, WMS). 
Para realizar este tipo de mapas interactivos existen diferentes aplicaciones online donde podemos ir codificando y visualizando al mismo tiempo, sin necesidad de tener el mapa guardado localmente. Las Aplication Programming interface 

## Datos de entrada en esta práctica:
- Capas utilizadas y generadas en las prácticas anteriores de esta misma asignatura. 

## Software para el desarrollo de esta práctica:
- QGIS.

### Desarrollo de la práctica:

## Instalación del complemento QGIS2WEB 

1. Abra un nuevo proyecto de QGIS.

2. Vaya a la barra de menú  superior y haga click en: COMPLEMENTOS --> ADMINISTRAR E INSTALAR COMPLEMENTOS...
<p align="center">
<img src="https://github.com/aprendiendo-cosas/P_webmapping_SIGII_Geoforest/blob/main/images/Install_qgis2web00A.JPG" alt="Figura 3" style="zoom:60%;"/><a name="figura2"></a><br><br> **Figura 3**
</p>

3. En la ventana de diálogo busque: "QGIS2WEB".  Seleciónelo y haga click en "INSTALAR COMPLEMENTO".
<p align="center">
<img src="https://github.com/aprendiendo-cosas/P_webmapping_SIGII_Geoforest/blob/main/images/Install_qgis2web00B.JPG" alt="Figura 4" style="zoom:60%;"/><a name="figura2"></a><br><br> **Figura 4**
</p>

## Crear una aplicación de WebMapping
4. Prepara en tu visior todas las capas que utilizarás, estableciendo la simbología y diseño de apariencia para las mismas. 
- Puede mejorar su proyecto, estableciendo un título, colores de fondo o resaltado en PROYECTO --> PROPIEDADES.
- De nombres amigables en el panel de CAPAS
- Asigne a las columnas de las tablas de atributos nombres amigables desde CAPA --> PROPIEDADES --> pestaña FORMULARIO DE ATRIBUTOS en el apartado de ALIAS
- Si hay columnas de la tabla de atributos que no quieres que se muestren en la ventana emergente, puede establecer en TIPO DE CONTROL como "OCULTO".
- Si alguno de los campos contiene nombres de archivos de imágenes, cambia en la ventana de edicion a "FOTO" para que las imágenes aparezcan en ventanas emergentes. 
- También se puede configurar la visibilidad de las capas dependiendo de la escala desde la pestaña de las propiedades de capa llamada REPRESENTACIÓN activando "VISIBILIDAD DEPENDIENTE DE LA ESCALA" y estableciendo 
los valores mínimo y máximo. 

5. Cuando el mapa y las capas estén listas, entonces es hora de abrir la aplicación de mapas web utilizando el complemento QGIS2WEB. Para ello, inicie la herramienta QGIS2WEB, en una de las siguientes opciones que 
se muestran:

<p align="center">
<img src="https://github.com/aprendiendo-cosas/P_webmapping_SIGII_Geoforest/blob/main/images/Install_qgis2web03.JPG" alt="Figura 5" style="zoom:60%;"/><a name="figura2"></a><br><br> **Figura 5**
</p>
- Si quiere, puede elegir un mapa base de la lista que hay debajo  del panel de vista previa y haga click en "UPDATE PREVIEW".
- Todos los cambios en la configuración, quedarán guardados en su proyecto de QGIS, por tanto guarde los cambios en el proyecto si quiere mantenerlos.

6. En la parte izquierda de la ventana de diálogo es posible establecer algunos parámetros para para la muestra web de cada capa de información cargada en QGIS.  
<p align="center">
<img src="https://github.com/aprendiendo-cosas/P_webmapping_SIGII_Geoforest/blob/main/images/Install_qgis2web04.JPG.JPG" alt="Figura 6" style="zoom:60%;"/><a name="figura2"></a><br><br> **Figura 6**
</p>

- En la parte inferior izquierda encuentra las palabras: QGIS, OpenLayers y Leaflet, éstas son todas diferentes tecnologías de mapeo. Esto significa que su funcionalidad respectiva difiera en muchos aspectos. 
QGIS2WEB hace todo lo posible para interpretar un proyecto de QGIS y exportar HTML, Javastript y CSS para crear un mapa web lo más parecido posible al proyecto de QGIS. Sin embargo, muchos elementos de un proyecto 
de QGIS no se pueden reproduciry muchos solo son posibles en OpenLayers o Leaflet. QGIS2WEB hace todo lo posible para producir un mapa listo para publicar, pero siempre puede se puede editarmanualmente en el código 
de la salida para lograr lo que WGIS2WEB no puede. 


7. Para ver el diseño y modificaciones de las distintas opciones, presione el botón "UPDATE PREVIEW". Recuerde que cada vez que modifique o configure un parámetro, debe hacer click en este botón para ver el resultado. 
- Opciones de capa: 

8. Entre las pestañas encontramos:
 a) LAYERS AND GROUPS: Controla cómo se mostrará una capa en el mapa, incluida la opción de campos emergentes, o emergente con un click:
  - Visible - Selecciona si la capa será visible al cargar el mapa (aparecerá la capa desactiva en la visualización). Esto solo determina la visibilidad: la capa se cargará independientemente de esta configuración, 
  aunque aparecerá desactivdad. 
 Popups - Especifique si una capa muestra o no una ventana emergente haciendo click, o si no despliega nada al hacer click sobre el contenido. 
 Cluster - Caracteriza los puntos de una agrupación
 Popup fields - Especifica como quiere que se vea cada archivo etiquetado en los popups

 b) APPEARANCE: Donde podemos agregar algunas herramientas al mapa web como: búsqueda de direcciones, lista de capas, herramientas de medición, ventana emergente, geologcalización de usuarios. En este apartado también 
 podemos definir la extensión del mapa. 
 c) EXPORT: Esta parte brinda algunas opciones para exportar el mapa a un mapa web como: ubicación de los archivos de mapa web exportados, ubicación de la biblioteca de mapas, extracción del archivo GeoJSON, etc.
 d) SETTINGS:
 e) HELP:  















## Contextualización ecológica y estructura de la sesión

Para cuantificar la diversidad biológica se pueden utilizar muchos índices. En nuestro caso usaremos el denominado índice de Shannon-Wiever,

+ Delimitación espacial de la comunidad para la que queremos calcular el índice de diversidad.

También puedes verla [aquí](https://prezi.com/view/07Hx3W5wMEZBtpdeeouO/) y descargarla


<p><iframe src="https://prezi.com/view/07Hx3W5wMEZBtpdeeouO/embed" width="1200" height="900"> </iframe></p>


![puntos](https://github.com/aprendiendo-cosas/P_shannon_ecologia_ccaa/raw/2020-2021/imagenes/puntos.png)


<iframe frameborder="0" style="width:100%;height:2815px;" src="www.METER AQUÍ EL ENLACE.com"></iframe>

La ejecución del anterior flujo de trabajo se realiza usando R. Para ello iremos ejecutando secuencialmente las líneas del siguiente bloque de código:

```R
#Este script calcula el Indice Shannon de Sierra Nevada
# usando la información existente en GBIF y un mapa de vegetación a escala 1:10.000

## Establece directorio de trabajo. Recuerda cambiarlo por el tuyo.
setwd("/Users/fjbonet_trabajo/Google_Drive/4_docencia/eco_ccaa_uco/actos_docentes/P_shannon_ecologia_ccaa/preparacion")

## Carga paquetes que necesitamos
install.packages("rgdal")
library(rgdal)

install.packages("sqldf")
library(sqldf)

## Importa la capa con las ocurrencias de GBIF
ocurrencias<-readOGR(dsn=".", layer="ocurrencias_sierra_nevada_23030", verbose = FALSE)

## Importa la capa con la delimitación de las comunidades ecológicas.
comunidades<-readOGR(dsn=".",layer="vegetacion_snevada_23030", verbose = FALSE)

## Unión espacial: asigna a cada punto el código de la comunidad en la que se encuentra.
ocurrencias$id_com <- over(ocurrencias, comunidades)$OBJECTID

## Extraer la "tabla de atributos" para hacer los cálculos del índice de Shannon
bio<-ocurrencias@data

## Calcular el índice de Shannon

### Calcular el número de individuos por especie y por comunidad (num_ind_sp_com)
T_num_ind_sp_com<-sqldf("SELECT id_com, scientific,  count(scientific) num_ind_sp_com  FROM bio GROUP BY id_com, scientific")

### Calcular el número total de individuos por comrícula.
T_num_ind_com<-sqldf("SELECT id_com, sum(num_ind_sp_com) num_ind_com FROM T_num_ind_sp_com GROUP BY id_com")

### Fusionar las tablas anteriores para calcular Pi
T_num_ind_sp_com_mas_num_ind_com<-sqldf("SELECT id_com, scientific, num_ind_sp_com, num_ind_com FROM T_num_ind_sp_com LEFT JOIN T_num_ind_com USING(id_com)")

### Calcular pi por especie y por comunidad
T_num_ind_sp_com_mas_num_ind_com<-sqldf("SELECT id_com, scientific, num_ind_sp_com, num_ind_com, (num_ind_sp_com*1.0/num_ind_com) pi FROM T_num_ind_sp_com_mas_num_ind_com")

### Calcular el log2 pi por especie y por comunidad (log = ln). Log2(pi)=log(pi)/log(2)
T_num_ind_sp_com_mas_num_ind_com<-sqldf("SELECT id_com, scientific, num_ind_sp_com, num_ind_com, pi, (log(pi)/log(2))*pi lnpi_pi FROM T_num_ind_sp_com_mas_num_ind_com")

### Calcular H por comunidad
T_Shannon<-sqldf("SELECT id_com, sum(lnpi_pi)*-1 H FROM T_num_ind_sp_com_mas_num_ind_com GROUP BY id_com")

## Fusionar la tabla que tiene el índice de Shannon con la distribución de comunidades.
comunidades<-merge(x = comunidades, y = T_Shannon, by.x = "OBJECTID", by.y = "id_com")

## Exportar la capa resultante a un shapefile.
writeOGR(comunidades, dsn=".", layer="Shannon_com_sierra_nevada", driver="ESRI Shapefile", overwrite=TRUE )

```

## Vídeos de las sesiones

Lamentablemente en esta ocasión no grabé las sesiones. Así que tenemos que conformarnos con versiones similares de esta práctica en otros años y en otras titulaciones. Ahí va la misma práctica pero impartida para alumnos de tercer curso de biología:

<iframe width="560" height="315" src="https://www.youtube.com/embed/6OOusJU4ljs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>



