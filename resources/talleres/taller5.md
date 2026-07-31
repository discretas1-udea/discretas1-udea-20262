---
layout: default
title: Taller 5 - Cuantificadores Múltiples
parent: Talleres de Repaso
nav_order: 5
math: mathjax
---

# Taller 5 – Matemáticas Discretas
{: .no_toc }

## Tabla de Contenidos
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Objetivo de aprendizaje

Al finalizar este taller, usted podrá traducir entre lenguaje natural y fórmulas con **cuantificadores múltiples** en ambas direcciones, evaluar el valor de verdad de proposiciones con más de un cuantificador, y reescribir la negación de proposiciones cuantificadas de modo que los símbolos de negación precedan inmediatamente a los predicados.

## Referencia rápida

### Prioridad de operadores lógicos
{: .no_toc }

| Prioridad | Operador | Símbolo | Significado |
|---|---|---|---|
| 1 (más alta) | Paréntesis | $( )$ | Agrupación |
| 2 | Cuantificadores | $\forall, \exists$ | Universal / Existencial |
| 3 | Negación | $\neg$ | No |
| 4 | Conjunción | $\land$ | Y |
| 5 | Disyunción | $\lor$ | O |
| 6 | Implicación | $\to$ | Si … entonces … |
| 7 (más baja) | Equivalencia | $\leftrightarrow$ | Si y solo si … |

### Equivalencias entre cuantificadores
{: .no_toc }

| Nombre | Equivalencia lógica |
|---|---|
| Negación de cuantificadores (De Morgan cuántico) | $\neg \forall x\ P(x) \equiv \exists x\ \neg P(x)$<br>$\neg \exists x\ P(x) \equiv \forall x\ \neg P(x)$ |
| Distributividad del cuantificador universal sobre conjunción | $\forall x(P(x) \land Q(x)) \equiv \forall x\ P(x) \land \forall x\ Q(x)$ |
| Distributividad del cuantificador existencial sobre disyunción | $\exists x(P(x) \lor Q(x)) \equiv \exists x\ P(x) \lor \exists x\ Q(x)$ |
| Distribución de cuantificadores (restricciones) | Si la fórmula $Q$ no contiene la variable cuantificada $x$:<br>$\forall x(P(x) \lor Q) \equiv (\forall x\ P(x)) \lor Q$<br>$\exists x(P(x) \land Q) \equiv (\exists x\ P(x)) \land Q$ |

### Reglas de inferencia para lógica cuantificacional
{: .no_toc }

| Regla | Nombre | Forma |
|---|---|---|
| $\forall I$ | Instanciación universal | $\forall x\ P(x) \Rightarrow P(c)$ |
| $\forall G$ | Generalización universal | $P(c) \Rightarrow \forall x\ P(x)$ |
| $\exists I$ | Instanciación existencial | $\exists x\ P(x) \Rightarrow P(c)$ |
| $\exists G$ | Generalización existencial | $P(c) \Rightarrow \exists x\ P(x)$ |

> El orden de los cuantificadores **sí importa**: $\forall x\ \exists y\ Q(x,y)$ no significa lo mismo que $\exists y\ \forall x\ Q(x,y)$. Preste especial atención a esto en los Bloques A y B.
{: .tip }

> Las **Formas Aristotélicas** y el **formulario de lógica proposicional** (equivalencias y reglas de inferencia de talleres anteriores) están disponibles en **Anexos completos**, al final de este documento.
{: .tip }

## Enunciados

### Bloque A — Traducción de fórmulas con cuantificadores múltiples a lenguaje natural (1, 2, 3)
{: .no_toc }

**1.** Traduzca estas afirmaciones al lenguaje natural, donde el dominio de cada variable consiste en todos los números reales:

- a. $\forall x\ \exists y\ (x < y)$
- b. $\forall x\ \forall y\ (((x \ge 0) \land (y \ge 0)) \to (xy \ge 0))$
- c. $\forall x\ \forall y\ \exists z\ (xy = z)$

**2.** Sea $Q(x,y)$ la afirmación "$x$ ha enviado un correo electrónico a $y$", donde el dominio tanto para $x$ como para $y$ consiste en todos los estudiantes de tu clase. Exprese cada una de estas cuantificaciones en lenguaje natural.

- a. $\exists x\ \exists y\ Q(x,y)$
- b. $\exists x\ \forall y\ Q(x,y)$
- c. $\forall x\ \exists y\ Q(x,y)$
- d. $\forall y\ \exists x\ Q(x,y)$
- e. $\forall y\ \forall x\ Q(x,y)$

**3.** Sea $W(x,y)$ "el estudiante $x$ ha visitado el sitio web $y$", donde el dominio de $x$ incluye a todos los estudiantes de tu escuela y el dominio de $y$ incluye a todos los sitios web. Exprese cada una de estas afirmaciones con una oración simple.

- a. $W(\text{Sarah Smith}, \text{www.att.com})$
- b. $\exists x\ W(x, \text{www.imdb.org})$
- c. $\exists y\ W(\text{Jose Perez}, y)$
- d. $\exists y\ (W(\text{Jose Perez}, y) \land W(\text{Cindy Yoon}, y))$
- e. $\exists y\ \forall z\ ((y \ne \text{David Belcher}) \land (W(\text{David Belcher}, z) \to W(y, z)))$
- f. $\exists x\ \exists y\ \forall z\ ((x \ne y) \land (W(x,z) \leftrightarrow W(y,z)))$

> En 3a, el PDF original trae "www. att. com" con espacios (artefacto de extracción del documento); se normalizó a "www.att.com".
{: .note }

### Bloque B — Traducción de lenguaje natural a fórmula cuantificada (4, 5, 6, 7)
{: .no_toc }

**4.** Sea $L(x,y)$ la afirmación "$x$ ama a $y$", donde el dominio tanto para $x$ como para $y$ consiste en todas las personas del mundo. Use cuantificadores para expresar cada una de estas afirmaciones.

- a. Todos aman a Jerry.
- b. Todos aman a alguien.
- c. Hay alguien a quien todos aman.
- d. Nadie ama a todos.
- e. Hay alguien a quien Lydia no ama.
- f. Hay alguien a quien nadie ama.
- g. Hay exactamente una persona a quien todos aman.
- h. Hay exactamente dos personas a quienes Lynn ama.
- i. Todos se aman a sí mismos.
- j. Hay alguien que no ama a nadie más que a sí mismo.

**5.** Sea $M(x,y)$ "$x$ ha enviado un correo electrónico a $y$" y $T(x,y)$ "$x$ ha llamado a $y$", donde el dominio consiste en todos los estudiantes de tu clase. Use cuantificadores para expresar cada una de estas afirmaciones. (Suponga que se reciben todos los correos electrónicos enviados, lo cual no suele ocurrir).

- a. Chou nunca le ha enviado un correo electrónico a Koko.
- b. Arlene nunca le ha enviado un correo electrónico a Sarah ni le ha llamado por teléfono.
- c. José nunca ha recibido un correo electrónico de Deborah.
- d. Todos los estudiantes de tu clase le han enviado un correo electrónico a Ken.
- e. Nadie en tu clase ha llamado por teléfono a Nina.
- f. Todos en tu clase han llamado a Avi o le han enviado un correo electrónico.
- g. Hay un estudiante en tu clase que ha enviado un correo electrónico a todos los demás.
- h. Hay alguien en tu clase que ha enviado un correo electrónico o ha llamado a todos los demás.
- i. Hay dos estudiantes en tu clase que se han enviado correos electrónicos.
- j. Hay un estudiante que se ha enviado un correo electrónico a sí mismo.
- k. Hay un estudiante en tu clase que no ha recibido ningún correo electrónico de ningún otro estudiante ni ha sido llamado por ningún otro estudiante.
- l. Todos los estudiantes de la clase han recibido un correo electrónico o una llamada telefónica de otro estudiante.
- m. Hay al menos dos estudiantes en tu clase: uno le ha enviado un correo electrónico al otro y el otro le ha llamado por teléfono.
- n. Hay dos estudiantes diferentes en tu clase que entre ambos han enviado un mensaje de correo electrónico o han llamado por teléfono a todos los demás en la clase.

**6.** Utilice cuantificadores y predicados con más de una variable para expresar las siguientes afirmaciones:

- a. Todo estudiante de informática necesita un curso de matemáticas discretas.
- b. Hay un estudiante en esta clase que tiene una computadora personal.
- c. Todos los estudiantes de esta clase han cursado al menos un curso de informática.
- d. Hay un estudiante en esta clase que ha cursado al menos un curso de informática.
- e. Todos los estudiantes de esta clase han estado en todos los edificios del campus.
- f. Hay un estudiante en esta clase que ha estado en todas las salas de al menos un edificio del campus.
- g. Todos los estudiantes de esta clase han estado en al menos una sala de todos los edificios del campus.

**7.** Exprese cada una de estas afirmaciones utilizando operadores matemáticos y lógicos, predicados y cuantificadores, donde el dominio consiste en todos los números enteros.

- a. La suma de dos números enteros negativos es negativa.
- b. La diferencia de dos números enteros positivos no es necesariamente positiva.
- c. La suma de los cuadrados de dos números enteros es mayor o igual que el cuadrado de su suma.
- d. El valor absoluto del producto de dos números enteros es el producto de sus valores absolutos.

### Bloque C — Evaluación de valores de verdad con cuantificadores múltiples (8)
{: .no_toc }

**8.** Sea $Q(x,y)$ la afirmación "$x + y = x - y$". Si el dominio de ambas variables está compuesto por todos los números enteros, ¿cuáles son los valores de verdad?

- a. $Q(1,1)$
- b. $Q(2,0)$
- c. $\forall y\ Q(1,y)$
- d. $\exists x\ Q(x,2)$
- e. $\exists x\ \exists y\ Q(x,y)$
- f. $\forall x\ \exists y\ Q(x,y)$
- g. $\exists y\ \forall x\ Q(x,y)$
- h. $\forall y\ \exists z\ Q(x,y)$
- i. $\forall x\ \forall y\ Q(x,y)$

> El literal h se transcribe tal como aparece en el PDF original: tiene una $x$ sin cuantificar y usa $z$ en el cuantificador en vez de $y$. Puede ser un error tipográfico de la fuente — no se corrigió.
{: .note }

### Bloque D — Negación de proposiciones cuantificadas (9, 10, 11)
{: .no_toc }

**9.** Reescriba cada una de estas afirmaciones de modo que las negaciones aparezcan solo dentro de los predicados (es decir, de modo que ninguna negación esté fuera de un cuantificador o una expresión que involucre conectores lógicos).

- a. $\neg \exists y\ \exists x\ P(x,y)$
- b. $\neg \forall x\ \exists y\ P(x,y)$
- c. $\neg \exists y\ (Q(y) \land \forall x\ \neg R(x,y))$
- d. $\neg \exists y\ (\exists y\ R(x,y) \lor \forall x\ S(x,y))$
- e. $\neg \exists y\ (\forall x\ \exists z\ T(x,y,z) \lor \exists x\ \forall z\ U(x,y,z))$

> En el literal d, el PDF original reutiliza la variable $y$ tanto en el cuantificador externo ($\neg \exists y$) como en uno interno ($\exists y\ R(x,y)$). Se transcribe verbatim; puede ser intencional (para que el estudiante note el conflicto de variables) o un error de la fuente.
{: .note }

**10.** Exprese las negaciones de cada una de estas proposiciones de modo que todos los símbolos de negación precedan inmediatamente a los predicados.

- a. $\forall x\ \exists y\ \forall z\ T(x,y,z)$
- b. $\forall x\ \exists y\ P(x,y) \lor \forall x\ \exists y\ Q(x,y)$
- c. $\forall x\ \exists y\ (P(x,y) \lor \exists z\ R(x,y,z))$
- d. $\forall x\ \exists y\ (P(x,y) \to Q(x,y))$

**11.** Exprese cada una de estas afirmaciones utilizando cuantificadores. Luego, forme la negación de la afirmación de modo que ninguna negación esté a la izquierda de un cuantificador. A continuación, exprese la negación en un lenguaje sencillo. (No utilice simplemente la frase "No es el caso que").

- a. Todos los estudiantes de esta clase han cursado exactamente dos clases de matemáticas en esta escuela.
- b. Alguien ha visitado todos los países del mundo excepto Libia.
- c. Nadie ha escalado todas las montañas del Himalaya.
- d. Todos los actores de cine han participado en una película con Kevin Bacon o han participado en una película con alguien que haya participado en una película con Kevin Bacon.

## ¿Cómo verificar sus propias respuestas?

> Antes de dar por terminado un ejercicio, revise:
> 1. Si intercambió el orden de dos cuantificadores distintos ($\forall$ y $\exists$), ¿verificó que el significado siga siendo el mismo? (En general, no lo es — ver el `[!TIP]` de la Referencia rápida).
> 2. Al empujar una negación hacia adentro, ¿alternó correctamente $\forall \leftrightarrow \exists$ en cada paso (De Morgan cuántico), o solo cambió el primer cuantificador?
> 3. En el resultado final, ¿quedó algún símbolo $\neg$ que no esté pegado directamente a un predicado?
{: .tip }

## Anexos completos (referencia extendida)

<details markdown="1">
<summary>Ver Anexo 1 — Formas Aristotélicas</summary>

| Forma | Nombre | Proposición | Forma lógica |
|---|---|---|---|
| $A(S,P)$ | Universal afirmativa | Todos los S son P | $\forall x\,(S(x) \to P(x))$ |
| $E(S,P)$ | Universal negativa | Ningún S es P / Todos los S no son P | $\forall x\,(S(x) \to \neg P(x))$ |
| $I(S,P)$ | Particular afirmativa | Algún S es P | $\exists x\,(S(x) \land P(x))$ |
| $O(S,P)$ | Particular negativa | Algún S no es P | $\exists x\,(S(x) \land \neg P(x))$ |

</details>

<details markdown="1">
<summary>Ver Anexo 2 — Fórmulas de lógica proposicional</summary>

**Equivalencias lógicas**

| Nombre | Forma $\land$ / $\to$ | Forma $\lor$ |
| :--- | :--- | :--- |
| **Conmutativa** | $p \land q \equiv q \land p$ | $p \lor q \equiv q \lor p$ |
| **Asociativa** | $(p \land q) \land r \equiv p \land (q \land r)$ | $(p \lor q) \lor r \equiv p \lor (q \lor r)$ |
| **Distributiva** | $p \land (q \lor r) \equiv (p \land q) \lor (p \land r)$ | $p \lor (q \land r) \equiv (p \land q) \land (p \land r)$ |
| **Idempotencia** | $p \land p \equiv p$ | $p \lor p \equiv p$ |
| **De Morgan** | $\neg(p \land q) \equiv \neg p \lor \neg q$ | $\neg(p \lor q) \equiv \neg p \land \neg q$ |
| **Identidad** | $p \land V \equiv p$ | $p \lor F \equiv p$ |
| **Dominación** | $p \land F \equiv F$ | $p \lor V \equiv V$ |
| **Absorción** | $p \land (p \lor q) \equiv p$ | $p \lor (p \land q) \equiv p$ |
| **Complemento** | $p \land \neg p \equiv F$ | $p \lor \neg p \equiv V$ |
| **Doble Negación** | $\neg(\neg p) \equiv p$ | — |
| **Implicación** | $p \to q \equiv \neg p \lor q$ | — |
| **Contrapositiva** | $p \to q \equiv \neg q \to \neg p$ | *(Muy útil)* |
| **Equivalencia** | $p \leftrightarrow q \equiv (p \to q) \land (q \to p)$ | — |

**Reglas de inferencia**

<table>
<thead>
<tr><th>Nombre</th><th>Regla (Esquema)</th><th>Descripción Intuitiva</th></tr>
</thead>
<tbody>
<tr>
<td><strong>Modus Ponens (MP)</strong></td>
<td>

$$
\begin{array}{l}
p \to q \\
p \\
\hline
\therefore\ q
\end{array}
$$

</td>
<td><strong>Causa-Efecto:</strong> Si se da la causa, ocurre el efecto.</td>
</tr>
<tr>
<td><strong>Modus Tollens (MT)</strong></td>
<td>

$$
\begin{array}{l}
p \to q \\
\neg q \\
\hline
\therefore\ \neg p
\end{array}
$$

</td>
<td><strong>Descarte:</strong> Si no veo el efecto, no pudo haber ocurrido la causa.</td>
</tr>
<tr>
<td><strong>Silogismo Hipotético (SH)</strong></td>
<td>

$$
\begin{array}{l}
p \to q \\
q \to r \\
\hline
\therefore\ p \to r
\end{array}
$$

</td>
<td><strong>Cadena:</strong> Si $p$ lleva a $q$ y $q$ lleva a $r$, entonces $p$ lleva a $r$.</td>
</tr>
<tr>
<td><strong>Silogismo Disyuntivo (SD)</strong></td>
<td>

$$
\begin{array}{l}
p \lor q \\
\neg p \\
\hline
\therefore\ q
\end{array}
$$

</td>
<td><strong>Eliminación:</strong> Si tengo dos opciones y descarto una, me toca la otra.</td>
</tr>
<tr>
<td><strong>Simplificación (Simp)</strong></td>
<td>

$$
\begin{array}{l}
p \land q \\
\hline
\therefore\ p
\end{array}
$$

</td>
<td><strong>Extracción:</strong> Si tengo todo, tengo una parte.</td>
</tr>
<tr>
<td><strong>Adición (Ad)</strong></td>
<td>

$$
\begin{array}{l}
p \\
\hline
\therefore\ p \lor q
\end{array}
$$

</td>
<td><strong>Generalización:</strong> Si algo es verdad, esa cosa "o cualquier otra" también lo es.</td>
</tr>
<tr>
<td><strong>Conjunción (Conj)</strong></td>
<td>

$$
\begin{array}{l}
p \\
q \\
\hline
\therefore\ p \land q
\end{array}
$$

</td>
<td><strong>Fusión:</strong> Puedo unir dos verdades independientes.</td>
</tr>
<tr>
<td><strong>Resolución (Res)</strong></td>
<td>

$$
\begin{array}{l}
p \lor q \\
\neg p \lor r \\
\hline
\therefore\ q \lor r
\end{array}
$$

</td>
<td><strong>Eliminación de una opción:</strong> una cláusula contiene $p$ y otra contiene $\neg p$; al combinarse, "se elimina" esa variable y quedan las alternativas restantes ($q \lor r$).</td>
</tr>
<tr>
<td><strong>División por Casos</strong></td>
<td>

$$
\begin{array}{l}
p \lor q \\
p \to r \\
q \to r \\
\hline
\therefore\ r
\end{array}
$$

</td>
<td><strong>Todos los caminos llevan a Roma:</strong> Si mis opciones son A o B, y ambas llevan al mismo resultado, el resultado es seguro.</td>
</tr>
</tbody>
</table>

</details>
