---
layout: default
title: Taller 8 - Órdenes Parciales
parent: Talleres de Repaso
nav_order: 8
math: mathjax
---

# Taller 8 – Matemáticas Discretas
{: .no_toc }

## Tabla de Contenidos
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Objetivo de aprendizaje

Al finalizar este taller, usted podrá determinar si una relación es un orden parcial (a partir de conjuntos, matrices, grafos dirigidos o lenguaje natural), construir e interpretar diagramas de Hasse, y encontrar los elementos distinguidos de un conjunto parcialmente ordenado (maximales, minimales, cotas superiores e inferiores).

## Referencia rápida

> Este taller no trae anexo de fórmulas en el PDF original. La siguiente Referencia rápida fue redactada para este documento (apoyada en la notación estándar de Rosen), no transcrita de una fuente.
{: .note }

### Orden parcial (POSET)
{: .no_toc }

| Concepto | Definición |
|---|---|
| Orden parcial | Una relación $R$ sobre un conjunto $S$ es un orden parcial si es **reflexiva**, **antisimétrica** y **transitiva** |
| POSET | Un conjunto $S$ junto con un orden parcial $R$ se denota $(S, R)$ y se llama conjunto parcialmente ordenado |
| Comparables | $a$ y $b$ son comparables si $aRb$ o $bRa$ |
| Incomparables | $a$ y $b$ son incomparables si ni $aRb$ ni $bRa$ se cumplen |
| Orden total | Un POSET donde **todo** par de elementos es comparable |

> Para descartar rápidamente que una relación sea orden parcial, basta con encontrar **una sola** falla en reflexividad, antisimetría o transitividad — no hace falta revisar las tres propiedades si ya encontró una que falla.
{: .tip }

### Diagrama de Hasse — reglas de construcción
{: .no_toc }

Un diagrama de Hasse simplifica el grafo dirigido de un orden parcial eliminando información redundante:

1. Elimine los lazos (self-loops) — la reflexividad se da por sentada.
2. Elimine las aristas que se deducen por transitividad (si $a \to b$ y $b \to c$, no dibuje $a \to c$ directamente).
3. Elimine las flechas — se asume que toda arista apunta hacia arriba.
4. Organice los elementos por niveles, de menor (abajo) a mayor (arriba).

### Elementos distinguidos de un POSET
{: .no_toc }

| Concepto | Definición |
|---|---|
| Elemento maximal | $a$ es maximal si no existe ningún $b \ne a$ tal que $aRb$ (nada está "por encima" de $a$) |
| Elemento minimal | $a$ es minimal si no existe ningún $b \ne a$ tal que $bRa$ (nada está "por debajo" de $a$) |
| Elemento mayor (máximo) | $a$ es el mayor si $bRa$ para todo $b \in S$ — es único si existe |
| Elemento menor (mínimo) | $a$ es el menor si $aRb$ para todo $b \in S$ — es único si existe |
| Cota superior de $A \subseteq S$ | $u \in S$ tal que $aRu$ para todo $a \in A$ |
| Cota inferior de $A \subseteq S$ | $l \in S$ tal que $lRa$ para todo $a \in A$ |
| Mínima cota superior (supremo) | La menor de todas las cotas superiores de $A$ |
| Máxima cota inferior (ínfimo) | La mayor de todas las cotas inferiores de $A$ |

> Un POSET puede tener **varios** elementos maximales y minimales a la vez (a diferencia del elemento mayor/menor, que si existe es único). No confunda "maximal" con "mayor" — todo elemento mayor es maximal, pero no todo maximal es el mayor.
{: .tip }

## Enunciados

### Bloque A — Identificación de órdenes parciales (1-7)
{: .no_toc }

**1.** ¿Cuáles de estas relaciones en $\lbrace 0,1,2,3\rbrace $ son relaciones de orden parcial? Determine las propiedades de una relación de orden parcial que las otras no tienen.

- a. $\lbrace (0,0), (1,1), (2,2), (3,3)\rbrace $
- b. $\lbrace (0,0), (1,1), (2,0), (2,2), (2,3), (3,2), (3,3)\rbrace $
- c. $\lbrace (0,0), (1,1), (1,2), (2,2), (3,3)\rbrace $
- d. $\lbrace (0,0), (1,1), (1,2), (1,3), (2,2), (2,3), (3,3)\rbrace $
- e. $\lbrace (0,0), (0,1), (0,2), (1,0), (1,1), (1,2), (2,0), (2,2), (3,3)\rbrace $

**2.** ¿Cuáles de estas relaciones en $\lbrace 0,1,2,3\rbrace $ son relaciones de orden parcial? Determine las propiedades de una relación de orden parcial que las otras no tienen.

- a. $\lbrace (0,0), (2,2), (3,3)\rbrace $
- b. $\lbrace (0,0), (1,1), (2,0), (2,2), (2,3), (3,3)\rbrace $
- c. $\lbrace (0,0), (1,1), (1,2), (2,2), (3,1), (3,3)\rbrace $
- d. $\lbrace (0,0), (1,1), (1,2), (1,3), (2,0), (2,2), (2,3), (3,0), (3,3)\rbrace $
- e. $\lbrace (0,0), (0,1), (0,2), (0,3), (1,0), (1,1), (1,2), (1,3), (2,0), (2,2), (3,3)\rbrace $

**3.** ¿Cuáles de las siguientes relaciones $(S, R)$ son relaciones de orden parcial (POSET) si $S$ es el conjunto de todas las personas en el mundo y $(a,b) \in R$, donde $a$ y $b$ son personas?

- a. $a$ es más alto que $b$.
- b. $a$ no es más alto que $b$.
- c. $a = b$ o $a$ es un ancestro de $b$.
- d. $a$ y $b$ tienen un amigo en común.

**4.** Determine si las relaciones representadas por estas matrices binarias son órdenes parciales.

a.
$$\begin{bmatrix} 1 & 1 & 1 \\ 1 & 1 & 0 \\ 1 & 0 & 1 \end{bmatrix}$$

b.
$$\begin{bmatrix} 1 & 1 & 1 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}$$

c.
$$\begin{bmatrix} 1 & 1 & 1 & 0 \\ 0 & 1 & 1 & 0 \\ 0 & 0 & 1 & 1 \\ 1 & 1 & 0 & 1 \end{bmatrix}$$

> La matriz 4c aparece en el PDF original partida visualmente por el ancho de página (como si fuera de 8 filas × 2 columnas). Se reconstruyó como matriz 4×4 verificando la posición exacta de cada número en el documento fuente, igual que en el Taller 7.
{: .note }

**5.** Determine si las relaciones representadas por estas matrices binarias son órdenes parciales.

a.
$$\begin{bmatrix} 1 & 0 & 1 \\ 1 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}$$

b.
$$\begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 1 & 0 & 1 \end{bmatrix}$$

c.
$$\begin{bmatrix} 1 & 0 & 1 & 0 \\ 0 & 1 & 1 & 0 \\ 0 & 0 & 1 & 1 \\ 1 & 1 & 0 & 1 \end{bmatrix}$$

**6.** Para los siguientes ejercicios, determine si la relación con el grafo dirigido que se muestra es un orden parcial.

a. ![Grafo dirigido ejercicio 6a]({{ '/assets/images/talleres/taller8/taller8-ejercicio6-a.png' | relative_url }})

b. ![Grafo dirigido ejercicio 6b]({{ '/assets/images/talleres/taller8/taller8-ejercicio6-b.png' | relative_url }})

c. ![Grafo dirigido ejercicio 6c]({{ '/assets/images/talleres/taller8/taller8-ejercicio6-c.png' | relative_url }})

d. ![Grafo dirigido ejercicio 6d]({{ '/assets/images/talleres/taller8/taller8-ejercicio6-d.png' | relative_url }})

**7.** ¿Cuáles de estos pares de elementos son comparables en la relación de orden parcial (POSET) $(\mathbb{Z}^+, \mid)$?

- a. $5, 15$
- b. $6, 9$
- c. $8, 16$
- d. $7, 7$

### Bloque B — Construcción de diagramas de Hasse (8-9)
{: .no_toc }

**8.** Dibuje el diagrama de Hasse para la divisibilidad en el conjunto.

- a. $\lbrace 1, 2, 3, 4, 5, 6\rbrace $
- b. $\lbrace 3, 5, 7, 11, 13, 16, 17\rbrace $
- c. $\lbrace 2, 3, 5, 10, 11, 15, 25\rbrace $
- d. $\lbrace 1, 3, 9, 27, 81, 243\rbrace $

**9.** Dibuje el diagrama de Hasse para la divisibilidad en el conjunto.

- a. $\lbrace 1, 2, 3, 4, 5, 6, 7, 8\rbrace $
- b. $\lbrace 1, 2, 3, 5, 7, 11, 13\rbrace $
- c. $\lbrace 1, 2, 3, 6, 12, 24, 36, 48\rbrace $
- d. $\lbrace 1, 2, 4, 8, 16, 32, 64\rbrace $

### Bloque C — Lectura de diagramas de Hasse (10)
{: .no_toc }

**10.** En los siguientes ejercicios, liste todos los pares ordenados asociados al diagrama de Hasse adjunto.

a. ![Diagrama de Hasse 10a]({{ '/assets/images/talleres/taller8/taller8-ejercicio10-a.png' | relative_url }})

b. ![Diagrama de Hasse 10b]({{ '/assets/images/talleres/taller8/taller8-ejercicio10-b.png' | relative_url }})

c. ![Diagrama de Hasse 10c]({{ '/assets/images/talleres/taller8/taller8-ejercicio10-c.png' | relative_url }})

### Bloque D — Elementos distinguidos de un POSET (11-13)
{: .no_toc }

**11.** De acuerdo al diagrama de Hasse mostrado a continuación:

![Diagrama de Hasse ejercicio 11]({{ '/assets/images/talleres/taller8/taller8-ejercicio11.png' | relative_url }})

Responda las siguientes preguntas:

- a. Hallar los maximales.
- b. Hallar los minimales.
- c. ¿Existe un elemento mayor?
- d. ¿Existe un elemento menor?
- e. Hallar todas las cotas superiores de $\lbrace a, b, c\rbrace $.
- f. Hallar la menor de las cotas superiores de $\lbrace a, b, c\rbrace $, si existe.
- g. Hallar todas las cotas inferiores de $\lbrace f, g, h\rbrace $.
- h. Hallar la mayor de las cotas inferiores de $\lbrace f, g, h\rbrace $, si existe.

**12.** Responda estas preguntas para la relación de orden parcial $(\lbrace 3, 5, 9, 15, 24, 45\rbrace , \mid)$.

- a. Encuentre los elementos maximales.
- b. Encuentre los elementos minimales.
- c. ¿Hay un elemento máximo?
- d. ¿Hay un elemento mínimo?
- e. Encuentre todas las cotas superiores de $\lbrace 3, 5\rbrace $.
- f. Encuentre la mínima cota superior de $\lbrace 3, 5\rbrace $, si existe.
- g. Encuentre todas las cotas inferiores de $\lbrace 15, 45\rbrace $.
- h. Encuentre la máxima cota inferior de $\lbrace 15, 45\rbrace $, si existe.

**13.** Responda estas preguntas para la relación de orden parcial $(\lbrace \lbrace 1\rbrace , \lbrace 2\rbrace , \lbrace 4\rbrace , \lbrace 1,2\rbrace , \lbrace 1,4\rbrace , \lbrace 2,4\rbrace , \lbrace 3,4\rbrace , \lbrace 1,3,4\rbrace , \lbrace 2,3,4\rbrace \rbrace , \subseteq)$.

- a. Encuentre los elementos maximales.
- b. Encuentre los elementos minimales.
- c. ¿Existe un elemento mayor?
- d. ¿Existe un elemento menor?
- e. Encuentre todas las cotas superiores de $\lbrace \lbrace 2\rbrace , \lbrace 4\rbrace \rbrace $.
- f. Encuentre la mínima cota superior de $\lbrace \lbrace 2\rbrace , \lbrace 4\rbrace \rbrace $, si existe.
- g. Encuentre todas las cotas inferiores de $\lbrace \lbrace 1,3,4\rbrace , \lbrace 2,3,4\rbrace \rbrace $.
- h. Encuentre la máxima cota inferior de $\lbrace \lbrace 1,3,4\rbrace , \lbrace 2,3,4\rbrace \rbrace $, si existe.

## ¿Cómo verificar sus propias respuestas?

> Antes de dar por terminado un ejercicio, revise:
> 1. ¿Verificó las tres propiedades (reflexiva, antisimétrica, transitiva) por separado, en vez de asumir que si una se cumple las demás también?
> 2. Al construir un diagrama de Hasse, ¿eliminó correctamente los lazos y las aristas transitivas antes de dibujar? Un diagrama de Hasse con una arista transitiva de más ya no es un diagrama de Hasse válido.
> 3. Al buscar cotas superiores/inferiores, ¿revisó **todo** el conjunto, no solo los elementos "cercanos" en el diagrama?
> 4. ¿Confundió "maximal" (puede haber varios) con "mayor" (único, si existe)? Revise la tabla de Referencia rápida si tiene dudas.
{: .tip }
