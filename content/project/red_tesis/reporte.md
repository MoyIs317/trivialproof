---
title: "Análisis de Red de Tesis UNAM"
date: 2025-10-24
draft: false
author: "Moisés A."
toc: true
mathjax: true
tags: ["matemáticas", "redes", "tesis"]
---
## Introducción

Una red social (en el área de las matemáticas) es un grupo de personar unidas por cierto tipo de relación, hay una gran variedad de relaciones que tenemos los humanos entre sí, por ejemplo las relaciones de amistad, de romance, laborales, etc.

En las redes sociales cada nodo representa una persona y una arista entre dos nodos representa la relación que existe entre ellos. Las redes nos permiten estudiar distintos fenómenos que involucran la interacción entre las personas.

Antes de explicar la estructura de la red expuesta a continuación me gustaría hablar de un concepto que inspiró este proyecto.

Paul Erdos fue un matemático húngaro que además de su excentricidad es conocido por la impresionante cantidad de trabajos colaborativos que realizo durante su vida, a esto le debemos añadir la diversa variedad de áreas de las matemáticas que estos trabajos abarcan, en sus investigaciones podemos encontrar trabajos relacionados con la teoría de números, teoría de gráficas, teoría de la aproximación, combinatoria, teoría de conjuntos y la probabilidad. 

Es gracias a lo anterior que se inventó el número de Erdos esto como homenaje, este numero se construye de la siguiente forma: A Erdos le corresponde el 0, todo aquel colaborador en algún articulo con él le corresponde el número 1, aquellos que hayan colaborado con alguno de estos colaboradores pero no directamente con Erdos se les da el número 2 y así sucesivamente. Lo sorprendente es es que algunas estimaciones dan que el 90% de los matemáticos activos tiene un número de Erdos menor a 8.

<div style="text-align: center;">
  <img src="/projects/red_tesis/erdos_ai.png" alt="Paul Erdos" width="300">
  <p style="font-size: 0.9em; color: gray;">
    <em>Paul Erdos (Imagen generada con AI)</em>
  </p>
</div>

Lo que se intenta hacer aquí es encontrar si existe un análogo a Erdos es decir buscamos si es que existe un autor o director de tesis quién tenga suficientes publicaciones y colaboraciones como para dotar a los demás nodos con un número menor a 8.

La red esta constituida solamente por las tesis realizadas para obtener el titulo de matemático a nivel licenciatura ([Red de Tesis de Matemáticas](/red_tesis_final_version_search3.html)), cada nodo corresponde a una persona cada nodo cuenta con dos metadatos el primero corresponde al titulo de la tesis y el segundo señala el año de publicación, en la red existen tres tipos de nodos, los cuales son señalados de colores distintos de la siguiente forma:

- Nodos Azules: Corresponden a aquellos registros que sólo parecen como autores.
- Nodos Rojos: Estos señalan aquellos que sólo han sido directores.
- Nodos Morados: Estos nodos son aquellos registros que aparecen como autores y directores.

<div style="text-align: center;">
  <img src="/projects/red_tesis/red_ejemplo.png" alt="Imagen ejemplo de la red">
</div>

Las aristas corresponden a la relación de trabajo colaborativo es decir no se trata de una red dirigida pues consideramos a esta realción como la de colaboración.

> **Nota** Existen registros los cuales no tienen director de tesis o algunos se desconoce el año de publicación.

## Dos pequeñas observaciones

Los datos extraídos del portal de la UNAM no son muchos, pero si podemos hacer dos observaciones interesantes respecto a los directores y el año de publicación.

### ¿Quién es el director que más trabajos dirigidos?
 Para responder esta pregunta se realizaron una serie de pasos para poder limpiar los datos pues existen varias inconsistencias, lo primero que se realizo fue una estandarización de los nombres la cal consistía en quitar puntos, convertir a minúsculas, eliminar acentos. Esto no basto pues existían además errores tipográficos lo que imposibilitaba el conteo de forma correcta, pues podíamos encontrar registros como: Pablo R Juárez y Pablo Ruiz Juares estos registros se refieren a la misma persona sin embargo a la hora de realizar el conteo lo consideraba como dos personas distintas, en este caso usamos la librería de Python llamada rapidfuzz con esta pude detectar cadenas de texto similares pero que no son iguales, para después poder realizar una corrección en los registros que hicieran falta. Después de esta limpieza pudimos encontrar lo que se presenta en el siguiente gráfico.

<div id="plotly-graph-f9fc2c73fcc6425cb21422690b8ee6c9" style="width:100%;height:600px;"></div>
<script src="https://cdn.plot.ly/plotly-latest.min.js"></script>
<script type="text/javascript">
    var fig_data = {"data":[{"marker":{"color":[21,21,22,22,22,23,23,23,25,25,25,26,29,29,44],"colorbar":{"title":{"text":"Conteo"}},"colorscale":[[0.0,"rgb(211, 242, 163)"],[0.16666666666666666,"rgb(151, 225, 150)"],[0.3333333333333333,"rgb(108, 192, 139)"],[0.5,"rgb(76, 155, 130)"],[0.6666666666666666,"rgb(33, 122, 121)"],[0.8333333333333334,"rgb(16, 89, 101)"],[1.0,"rgb(7, 64, 80)"]],"showscale":true},"orientation":"h","x":[21,21,22,22,22,23,23,23,25,25,25,26,29,29,44],"y":["Jose Antonio Gomez Ortega","Oscar Alfredo Palmas Velasco","Jose Rafael Martinez Enriquez","Julio Cesar Guevara Bravo","Emilio Esteban Lluis Puebla","Alejandro Ricardo Garciadiego Dantan","Maria Isabel Puga Espinoza","Monica Alicia Clapp Jimenez Labora","Jose Rios Montes","Alejandro Bravo Mojica","Guillermo Gomez Alcaraz","Alejandro Illanes Mejia","Antonio Lascurain Orive","Hugo Alberto Rincon Mejia","Hortensia Galeana Sanchez"],"type":"bar"}],"layout":{"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermap":[{"type":"scattermap","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"title":{"text":"Top 15 de los directores con m\u00e1s trabajos dirigidos","y":0.95,"x":0.5,"xanchor":"center","yanchor":"top"},"xaxis":{"title":{"text":"N\u00famero de Publicaciones"}},"yaxis":{"title":{"text":"Nombre del Director"}}}};
    Plotly.newPlot('plotly-graph-f9fc2c73fcc6425cb21422690b8ee6c9', fig_data.data, fig_data.layout);
</script>


### ¿Cuántas publicaciones se han hecho por año?
En esta parte durante la exploración nos encontramos con registros los cuales contenían en año el valor de "0000" esto claramente es un error así que revisando el portal de tesis UNAM podemos encontrar que no fue un error a la hora de la extracción, por lo que para esta pregunta solo consideramos lo registros donde el año sea mayor a 0.

<div id="plotly-graph-90ad28db9393489bb10832af248b185c" style="width:100%;height:600px;"></div>
<script src="https://cdn.plot.ly/plotly-latest.min.js"></script>
<script type="text/javascript">
    var fig_data = {"data":[{"line":{"color":"#2ecc71","width":2},"marker":{"color":"#2ecc71","size":6},"mode":"lines+markers","x":[1937,1938,1950,1951,1953,1954,1955,1956,1957,1958,1961,1962,1963,1964,1965,1966,1967,1968,1969,1970,1971,1972,1973,1974,1975,1976,1977,1978,1979,1980,1981,1982,1983,1984,1985,1986,1987,1988,1989,1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019,2020,2021,2022,2023,2024,2025],"y":[1,1,3,1,2,2,1,2,2,1,3,3,5,4,7,12,11,4,15,14,20,23,22,26,43,31,21,29,32,40,35,31,30,40,36,46,29,44,46,37,42,35,35,40,34,34,47,40,20,38,45,54,44,57,34,49,50,43,71,66,65,66,56,68,66,67,64,95,82,48,82,79,68,70,52],"type":"scatter"}],"layout":{"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermap":[{"type":"scattermap","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"title":{"text":"N\u00famero de publicaciones por a\u00f1o","y":0.95,"x":0.5,"xanchor":"center","yanchor":"top"},"xaxis":{"title":{"text":"A\u00f1o"}},"yaxis":{"title":{"text":"N\u00famero de Publicaciones"}}}};
    Plotly.newPlot('plotly-graph-90ad28db9393489bb10832af248b185c', fig_data.data, fig_data.layout);
</script>

De este gráfico podemos observar que durante el 2018 fue el año con más tesis de matematicas.

## Propiedades de la Red

El análisis realizado de la red se hizo usando la librería de Python llamada [Networkx](https://networkx.org/documentation/stable/index.html) la cual se recomienda leer la documentación, mientras que para las viualizaciones se utilizó [Pyvis](https://pyvis.readthedocs.io/en/latest/index.html).

```pyhton
num_nodos = red.number_of_nodes()
num_aristas = red.number_of_edges()

La red cuenta con: 

    # Nodos : 3024 

    # Aristas: 2385 
```
>**Densidad:** Si consoderamos un grafo no dirigido podemos definir a la densidad como la proporción que existe entre la cantidad de aristas exitentes con la máxima posible. Esto lo podemos calcular como: $$ d = \frac{2|E|}{|V|(|V| - 1)}$$ Podemos notar que para un grafo completo este número es uno, para otro caso es menor.
```python
print(f"La densidad de la red es: {nx.density(red)}")
La densidad de la red es: 0.0005217932359844367
```

>**Grado Promedio:**  Para un grafo no dirigido podemos definir el gredo proemdio como la siguiente expresión: $$ \<k\> = \frac{2|E|}{|V|}$$ Este numero nos índica el número de conexionesde cada nodo en promedio.

Para nuestra red tenemos lo siguiente:
```python
average_degree_1 = 2* num_aristas / num_nodos
print(f"El grado promedio es: {average_degree_1}")
1.5773809523809523
```

En resumen tenemos:

| Red   | #Nodos | #Aristas | Densidad       | Grado Promedio |
|:------|-------:|---------:|:--------------|---------------:|
| Tesis | 3024   | 2385     | 0.00052       | 1.58           |

De estas metricas podemos concluir que tenemos una red muy dispersa y que la red cuenta con un gran cantidad de componentes conexas esto concuerda con lo que podemso ver en la imagen de la red.

<div style="text-align: center;">
  <img src="/projects/red_tesis/red_imagen_general.png" alt="Imagen ejemplo de la red">
</div>



## Conexidad

## Busqueda de comunidades

## Conclusión


