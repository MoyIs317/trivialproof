---
title: "Estadística"
date: 2025-08-01T22:53:58+05:30
draft: false
author: "Moisés A."
tags:
  - Matemáticas
  - Estadística
  - Datos
image: /images/estadis_cover.png
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

> Definición (Mediana):
> Dado un conjunto de observaciones \\( x_1, x_2,..., x_n  \\), la **mediana** se define de la siguiente manera:  
> 
> - Si \\( n \\) es **impar**, la mediana es el valor en la posición  \\( \frac{n+1}{2} \\) una vez que ordenamos las observaciones.  
> - Si \\( n \\) es **par**, entonces la mediana se calcula como  
>   $$\text{Mediana} = \frac{x_{n/2} + x_{n/2 + 1}}{2}$$  
>   una vez que tengamos ordenados nuestros datos.




Tanto en Python como en R tenemos muchas formas de obtener este resultado, expondré una de las más sencillas.
```python
import numpy as np
estaturas = [187, 163, 145, 178, 177, 172, 169]
#Igual que en ejejmplo anterior puedes hacer el procedimiento paso a paso o simplemente usar la función ya integrada en alguna librería, en nuestro caso aplicaremos la segunda forma
mediana = np.median(estaturas)
print(mediana)
172.0
```
para el caso de R es igual de simple
```r
estaturas <- c(187, 163, 145, 178, 177, 172, 169)
median(estaturas)
172.0
```
>Definición (Moda): Definimos a la moda como el valor más repetido en el conjunto de nuestras observaciones.

Es importante señalar que para el caso de la moda existen ocasiones en la que no es única. Para calcular este valor en Python utilizaremos otra librería interesante que os permitirá obtener esta medida.

```python
from scipy import stats
#Hemos modificado nuestra lista para observar mejor el resultado
estaturas = [187, 163, 145, 178, 177, 172, 169, 145, 178, 145]
print(stats.mode(estaturas))
ModeResult(mode=np.int64(145), count=np.int64(3))
#Nota: Es importante hacer notar que si la moda no es única entonces devuelve le dato menor
```
Existen otras cantidades que nos permiten medir la dispersión de los datos es decir que tan separados están nuestros, a continuación se detallarán algunas de estas.

>Definición (Varianza Muestral): Para un conjunto de observaciones

### Descripciones gráficas
Nosotros trabajaremos con los siguientes datos [Student Depresion Dataset](https://www.kaggle.com/datasets/adilshamim8/student-depression-dataset) los cuales correspondes a un dataset de Kaggle en el que se mide el nivel de estrés de una muestra de estudiantes, para más información respecto a las variables revisar el link. Con este dataset exploraremos algunas gráficas más  comunes en estadística.

#### Gráfica de barras
Para datos categóricos la forma más común para poder visualizarlos es por medio del gráfico de barras. En este gráfico cada barra representa la frecuencia(o frecuencias relativas) de las diferentes categorías. 

Para nuestro ejemplo tenemos que nuestro dataset tenemos una columna llamada **Gender** que corresponde al genero de cada individuo en el dataset, podríamos construir una gráfica que nos permita ver la cantidad de integrantes de cada sexo. Usaremos la librería de Seaborn, en particular usaremos el objeto catplot el cual es usado para variables categóricas y el parámetro kind = 'bar' , se recomienda leer la documentación al respecto

```python
import kagglehub
import pandas as pd 
import matplotlib.pyplot as plt
import os
import seaborn as sns
path = kagglehub.dataset_download("adilshamim8/student-depression-dataset")
files = os.listdir(path)
csv_files = [f for f in files if f.endswith(".csv")]
if csv_files:
    file_path = os.path.join(path, csv_files[0])
    estres = pd.read_csv(file_path)
    print(f"\nLeyendo archivo: {csv_files[0]}")
    display(df.head())
else:
    print("Error")
genero = estres["Gender"].value_counts()
sns.catplot(data = genero, kind="bar", color = 'palette')
plt.xlabel("Genero")
plt.ylabel("Cantidad")
```
El anterior código nos devuelve la siguiente imagen:

![Gráfica de barras](/images/estadis/genero.png)
#### Histograma
Ahora veremos un gráfico que perecería darnos un resultado parecido al gráfico de barras sin embargo le damos el nombre de histograma cuando existe un orden entre nuestras variables, aquí se intenta el tener una idea de como se comportan nuestros datos pensando en una función de densidad empírica, aquí cada barra representa la frecuancia de un intervalo sobre el rango de observaciones. 

Vamos a construir un histograma para la columna de **CGPA** el cual corresponde al promedio acumulado de calificaciones por sus siglas en inglés, usando Seaborn con la función displot y el parámetro kind = 'hist', podemos ver la dstribución de CGPA por genero. 

```python
sns.displot(data=estres, x= 'CGPA', kind = 'hist', col = 'Gender', hue = 'Gender');
```
obteniendo
![Histograma del CGPA](/images/estadis/CGPA_gender.png)
#### Gráfica de pastel
Una gráfica de pastel
#### Boxplot
#### Distribución empírica









