---
title: "Ejercicios de Matemáticas"
date: 2025-10-15
draft: false
author: "Moisés A."
tags:
  - Matemáticas
  - Ejecicios
image: 
description: "Ejecicios de Matemáticas"
toc: true
mathjax: True
---
# CÁLCULO
## Cálculo Multivariable
Determina si los siguientes limites existen.
- \\( \lim_{ (x,y)\to (0,0)} \frac{|y|}{\sqrt(x^{2} + y^{2})} \\)
Para determinar la existencia de este límite lo haremos mediante limites iterados:
$$ \lim_{x\to 0} lim_{y\to 0}\frac{|y|}{\sqrt(x^{2} + y^{2})} = \lim_{x\to 0} 0 = 0  $$
sin embargo podemos observar que:
$$ \lim_{y\to 0} lim_{x\to 0}\frac{|y|}{\sqrt(x^{2} + y^{2})}= \lim_{y\to 0}\frac{|y|}{\sqrt{y^{2}}}  = \lim_{y\to 0} \frac{|y|}{|y|} = \lim_{y\to 0}1 = 1$$
Como ambos límites son distintos podemos concluir que el límite original no existe.

- \\( \lim_{ (x,y)\to (0,0)} \frac{(x+y)^2}{x^{2} + y^{2}} \\)
Para este límite vamos a usar coordenadas polares, es decir vamos usar la sustitución \\(x = rcos(\theta)\\) e \\(y = rsin(\theta)\\). Veamos que obtenemos en el cociente del límite, cosiderando \\(\theta\\) arbitrario:
$$ \frac{(x+y)^2}{x^2+y^2} = \frac{x^2 + 2xy +y^2}{x^2+y^2} = \frac{r^2cos^2(\theta) + 2r^2cos(\theta)sin(\theta) + r^2sin^2(\theta)}{r^2(cos^2(\theta) + sin^2(\theta))} =1+ 2cos(\theta)sin(\theta) $$
De esta forma obtenemos un límite equivalente:
$$ \lim_{r \to 0}1+ 2cos(\theta)sin(\theta) = 1+ 2cos(\theta)sin(\theta)$$
Este límite depende de \\(\theta\\) por lo tanto este límte no existe. También podemos usar la sustitución \\(y = mx\\) donde \\(m\\) es un real arbitrario, esto corresponde a las rectas que pasan por el origen, si usamos esta sustitución podemos ver que:
$$ \frac{(x+y)^2}{x^2+y^2} = \frac{(x + mx)^2}{x^2 + m^2x^2} = \frac{x^2(1+m)^2}{x^2(1+m^2)} = \frac{(1+m)^2}{(1+m^2)} $$
Entonces obtenemos ahora el siguiente límite
$$\lim_{x \to 0} \frac{(1+m)^2}{(1+m^2)}  = \frac{(1+m)^2}{(1+m^2)}$$
El cual de nuevo es un límite que depende de un parámetro, con esto concluimos que el límite no existe.
- \\( \lim_{ (x,y)\to (0,0)} \frac{2x^2 + y^2}{x^{2} + y^{2}}\\)
Usando límites iterados podemosobservar que:
$$ \lim\limits_{x \to 0} \lim\limits_{y \to 0}\frac{2x^2 + y^2}{x^{2} + y^{2}} = \lim_{x\to 0}\frac{2x^2}{x^2} = \lim_{x\to 0}2 = 2 $$
mientras que por otro lado:
$$  \lim\limits_{y \to 0} \lim\limits_{x \to 0}\frac{2x^2 + y^2}{x^{2} + y^{2}} = \lim_{y\to 0}\frac{y^2}{y^2} = \lim_{y\to 0} 1 = 1$$ 
Como ambos límites son distintos concluimos que el límite original no existe.

# ÁLGEBRA
## Teoría de Grupos
-
# GEOMETRÍA

# VARIABLE COMPLEJA
## Números Complejos
- Demostrar que \\( 1  + cos(\theta) + cos(2\theta) + ... + cos(n\theta) = \frac{1}{2} + \frac{sin((n + \frac{1}{2})\theta)}{2sin(\frac{\theta}{2})}\\)

Demostración: Sea \\(z = e^{i\theta}\\), además sabemos que:
$$ \sum_{k = 0}^{n}z^k = \frac{1-z^{n+1}}{1-z}$$
De esta forma tenemos que:
$$ \sum_{k = 0}^{n}z^k = \frac{1-(e^{i\theta})^{n+1}}{1-e^{i\theta}} = \frac{1-e^{i(n+1)\theta}}{1-e^{i\theta}} = \frac{1-e^{i(n+\frac{1}{2})\theta + \frac{1}{2}i\theta}}{1-e^{\frac{2}{2}i\theta}}  = \frac{e^{\frac{1}{2}i\theta}(e^{-\frac{1}{2}i\theta} -e^{i(n+\frac{1}{2})\theta})}{e^{\frac{1}{2}i\theta}(e^{-\frac{1}{2}i\theta}-e^{\frac{1}{2}i\theta})} = \frac{e^{-\frac{1}{2}i\theta} -e^{i(n+\frac{1}{2})\theta}}{e^{-\frac{1}{2}i\theta}-e^{\frac{1}{2}i\theta}} $$
Ahora en el denominador tenemos la resta de un número complejo con su conjugado, entonces esto sabemos que es igual a \\(-2iIm(e^{\frac{1}{2}i\theta} = -2isin(\frac{\theta}{2}))\\), ahora desarrollando el numerador tenemos que:
$$\frac{cos(\frac{\theta}{2}) - isin(\frac{\theta}{2}) - cos((n + \frac{1}{2})\theta) - isin((n + \frac{1}{2})\theta)}{-2isin(\frac{\theta}{2})}$$

Nos quedaremos sólo con la parte real, de esta forma:
$$ \frac{-sin(\frac{\theta}{2}) - sin((n + \frac{1}{2})\theta)}{2sin(\frac{\theta}{2})} = \frac{1}{2} + \frac{sin((n + \frac{1}{2})\theta)}{2sin(\frac{\theta}{2})}$$
Obteniendo de esta forma que:
$$\sum_{k =0}^{n}cos(k\theta) =\frac{1}{2} + \frac{sin((n + \frac{1}{2})\theta)}{2sin(\frac{\theta}{2})} $$