---
title: "Estadística"
date: 2025-08-01T22:53:58+05:30
draft: false
author: "Moisés A."
tags:
  - Matemáticas
  - Estadística
  - Datos
image: /images/est_portada.png
description: "Ideas básicas de estadística"
toc: true
mathjax: True
---
# 10 Lecciones Básicas de Estadística
## Lección 1 Estadística Descriptiva

En la actualidad nos encontramos con una inmensa cantidad de datos, estos vienen en distintas "formas", "sabores" y "colores"; desde datos numéricos, una inmensa cantidad de texto, miles de imágenes, y millones de horas de video a la mano de todas las personas con acceso a internet, sin embargo es tanta la información que el poder entender y obtener información a partir de esta es una habilidad que se ha convertido de vital importancia. 

Es gracias a las matemáticas que tenemos una forma de comprender la información que tenemos a la mano, una de las tantas ramas que se usan es la estadística.

> Definición: La estadística como área de estudio es el arte y ciencia de diseñar estudios y analizar  los datos que estos producen. Su objetivo final es el traducir los datos en   conocimiento y comprensión del mundo que nos rodea. En resumen, la estadística es el arte y la ciencia de aprender de los datos,

Dentro de la misma estadística no encontramos con una subrama a la que se le suele llamar estadística descriptiva, esta es una serie de herramientas que nos permite resumir nuestros datos con la finalidad de enfatizar nuestra información y con esto poder lograr nuestro planteamiento de preguntas y modelos. 

A lo largo de esta secciones daremos algunas definiciones así como ejemplos con Python y R, esto con la finalidad de ejemplificar cada idea y obtener habilidades a lo largo de la lectura.

***Definición (Muestra)***:  Entenderemos como muestra a una parte  de una población de estudio. a la información y mediciones obtenidas de esta los llamaremos datos.

***Definición (Variable)***: Diremos que una variable es cualquier característica de un individuo perteneciente a una población.

A nuestras variables las podemos clasificar en cuantitativas y cualitativas.

**Definición (Variables Cuantitativas)**: Diremos que una variable es cuantitativa si esta puede tomar valores numéricos y representan una cantidad, además podemos dividir a estas variables en discretas y continuas.

**Definición (Variables Cualitativas)**: Aquí los valores que toma la variable representan una cualidad, atributo o categoría, en algunos textos pueden ser llamadas *variables categóricas*.

Para dar un breve ejemplo de este tipo de variables pensemos en un grupo de estudiantes en alguna universidad, sus estaturas, sus calificaciones son ejemplos de variables cuantitativas mientras que su sexo, o religión son ejemplos de variables cualitativas.

En la practica algunos modelos de Machine Learning aceptan variables categóricas de entrada o salida, por lo que es común usar números para etiquetar los valores de alguna variable categórica, sin embargo es importante no confundir el echo de que no representa un cantidad si no que señala una cualidad.

### Descripciones numéricas

Empezaremos por explicar las medidas de tendencia central las cuales tienen como finalidad buscar un valor central que representen a nuestros datos, estas son la *media, moda* y *mediana*.

> Definición (Media): Consideremos $$ x_1, x_2, ..., x_n$$ observaciones de alguna muestra, la media no es otra cosa más que el promedio de estos números y comúnmente lo representamos por \\(\bar{x}\\), teniendo de esta forma que: $$ \bar{x} := \frac{x_1 + x_2 +... + x_3}{n} $$

En Python tenemos muchas formas de obtener la mediana de un arreglo unidimensional, por ejemplo si empezamos con una lista a este le podemos calcular la suma de sus elementos y dividir esto entre su longitud, o con la ayuda de la librería Numpy podemos crear un array, y este objeto cuenta con el método mean.

Por ejemplo consideremos un arreglo con las estaturas de un grupo de personas, veamos como podemos calcular la media en Python.

```python
#### Primera forma 
estaturas = [187, 163, 145, 178, 177, 172, 169]
sum(estaturas) / len(estaturas)

#### Segunda forma
import numpy as np
array = np.array([187, 163, 145, 178, 177, 172, 169])
print(array.mean())
170.14285714285714
```
en el caso de R podemos proceder de la misma forma considerar un vector numérico, sumar cada entrada de este, y dividirlo entre su longitud, o directamente aplicar la función para calcular su media, tal y como vemos a continuación:
```r
estaturas <- c(187, 163, 145, 178, 177, 172, 169)
### Primera forma
sum(estaturas) / length(estaturas)

### Segunda forma
mean(estaturas)
170.142857142857
```
Hay una serie de propiedades y observaciones interesantes de la media, cuya demostración es directa de la definición, las cuales solo se enunciaran:
1. La media no necesariamente pertenece al conjunto de observaciones.
2. Si tenemos las observaciones \\(x_1, x_2, x_3,...,x_n\\) y consideramos una constante \\(c\\) y se define \\(y_i = x_i + c\\) entonces \\(\bar{y} = \bar{x} + c\\).
3. De nuevo si tenemos las observaciones \\(x_1, x_2, x_3,...,x_n\\) y consideramos una constante \\(c\\) y se define \\(y_i = c\bar{x_i}\\) entonces  \\(\bar{y} = c \bar{x}\\).

>Definición (Mediana): 


>Definición (Moda):

Existen otras cantidades que nos permiten medir la dispersión de los datos, a continuación se detallarán algunas de estas.

>Definición (Varianza):



### Descripciones gráficas
Nosotros trabajaremos con los siguientes datos:      los cuales correspondes a 

#### Gráfica de barras
#### Histograma
#### Polígono de frecuencia 
#### Gráfica de pastel
#### Boxplot
#### Distribución empírica









