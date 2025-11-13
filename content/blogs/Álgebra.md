---
title: "Álgebra"
date: 2025-10-15
draft: false
author: "Moisés A."
tags:
  - Matemáticas
  - Álgebra abstracta
image: /images/algebra_cover.png
description: "Conceptos e ideas básicas del álgebra"
toc: true
mathjax: True
---
# Lecciones básicas del álgebra 
## Enteros y el algoritmo de la división
Los números enteros son un conjunto de números con los que estamos familiarizados desde una temprana edad estos los escribimos de la siguiente forma: $$ \mathbb{Z} = \{ 0, 1, -1, 2, -2, \ldots \} $$ 
Este conjunto tiene una gran cantidad de propiedades y características, de las cuales exploraremos solo algunas las cuales nos permitirán deducir más.

Euclides en su séptimo libro escribe que que dado  cualquier entero \\(b\\) al dividirlo por cualquier entero \\(a\\) nos da como resultado un numero \\(q\\) que llama cociente y otro numero el cual es único \\(r\\) conocido como residuo el cual además cumple con \\(0 \leq r < a\\), esto lo traducimos a que $$b = aq + r$$ al proceso para obtener dichos números es conocido como el algoritmo de la división. Para entender lo que estamos diciendo daremos un pequeño ejemplo consideremos  \\(b = 13, a = 4\\) entonces observe que $$13 = 4(3) + 1$$ de donde en este caso en particular \\(q = 3, r = 1\\)

Tenemos un caso particular que ocurre cunado \\(r = 0\\), entonces \\(b = aq\\) en dicho caso diremos que \\(a\\) divide a \\(b\\) o que \\(b\\) es un múltiplo de \\(a\\) esto se tiende denotar de la forma \\(a|b\\).

Con esto podemos demostrar algunos hechos simples los cuales solo se usa la definición anterior:
- Si \\(a|b\\) y \\(b|c\\) entonces \\(a|c\\)
- Si \\(a|b\\) y \\(a|c\\) y \\(x,y\\) son cualesquiera enteros entonces  \\(a|bx + cy\\)
- Si \\(b \neq 0 \\) y \\(a|b\\) entonces \\(|a| \leq |b|\\)
- Si \\(a|b\\) y \\(b|a\\) entonces \\(a = b\\) o \\(a = -b\\) 




## Grupos
Una de las estructuras algebraicas más sencillas que se presentan en la universidad son los grupos, pues lo único que necesitamos es un conjunto, una operación binaria y asociativa, y ciertas restricciones sobre sus elementos, podríamos empezar directamente con las definiciones de estos objetos sin embargo, es mejor dar un ejemplo y explorar esta idea.

    - Simetrías sobre un triángulo: Para empezar definamos lo que es una simetría, imaginemos primero en 























