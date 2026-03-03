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
Determina si los siguientes limites existen.
- \\( \lim_{ (x,y)\to (0,0)} \frac{|y|}{\sqrt(x^{2} + y^{2})} \\)
Para determinar la existencia de este límite lo haremos mediante limites iterados:
$$ \lim_{x\to 0} lim_{y\to 0}\frac{|y|}{\sqrt(x^{2} + y^{2})} = \lim_{x\to 0} 0 = 0  $$
sin embargo podemos observar que:
$$ \lim_{y\to 0} lim_{x\to 0}\frac{|y|}{\sqrt(x^{2} + y^{2})}= \lim_{y\to 0}\frac{|y|}{\sqrt{y^{2}}}  = \lim_{y\to 0} \frac{|y|}{|y|} = \lim_{y\to 0}1 = 1$$
Como ambos límites son distintos podemos concluir que el límite original no existe.
- \\( \lim_{ (x,y)\to (0,0)} \frac{(x+y)^2}{x^{2} + y^{2}} \\)

Para este límite vamos a usar coordenadas polares, es decir vamos usar la sustitución \\(x = rcos(\theta)\\) e \\(y = rsin(\theta)\\). Veamos que obtenemos en el cociente del límite:
$$ \frac{(x+y)^2}{x^2+y^2} = \frac{x^2 + 2xy +y^2}{x^2+y^2} = \frac{r^2cos^2(\theta) + 2r^2cos(\theta)sin(\theta) + r^2sin^2(\theta)}{r^2(cos^2(\theta) + sin^2(\theta))} =1+ 2cos(\theta)sin(\theta) $$

Este límite depende de \\(\theta\\) por lo tanto este límte no existe.
# ÁLGEBRA
Prueba
# GEOMETRÍA

