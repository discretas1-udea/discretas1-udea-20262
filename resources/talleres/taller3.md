---
layout: default
title: Taller 3 - Lógica Proposicional
parent: Talleres de Repaso
nav_order: 3
math: mathjax
---

# Taller 3 – Matemáticas Discretas
{: .no_toc }

## Tabla de Contenidos
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Objetivo de aprendizaje

Al finalizar este taller, usted podrá determinar la validez de formas de argumento mediante tablas de verdad y mediante reglas de inferencia, y traducir argumentos formulados en lenguaje natural a notación proposicional.

## Referencia rápida

### Reglas de inferencia
{: .no_toc }

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

> Esta tabla es la que necesitará para los Bloques C y D. Si necesita repasar operadores lógicos, precedencia o equivalencias lógicas, están disponibles en el **Anexo completo**, al final de este documento.
{: .tip }

## Enunciados

### Bloque A — Validez mediante tabla de verdad (1-6)
{: .no_toc }

> Utilice tablas de verdad para determinar si las formas de argumento de los ejercicios, mostrados a continuación, son válidas. Indique qué columnas representan las premisas y cuáles representan la conclusión e incluya una frase de explicación de cómo la tabla de verdad apoya su respuesta. Su explicación debe demostrar que entiende lo que significa que una forma de argumento sea válida o no válida.

**1.** Argumento 1:

$$\begin{aligned}
&p \to q \\
&q \to p \\
&\therefore p \lor q
\end{aligned}$$

**2.** Argumento 2:

$$\begin{aligned}
&p \\
&p \to q \\
&\neg p \lor r \\
&\therefore r
\end{aligned}$$

**3.** Argumento 3:

$$\begin{aligned}
&p \lor q \\
&p \to \neg q \\
&p \to r \\
&\therefore r
\end{aligned}$$

**4.** Argumento 4:

$$\begin{aligned}
&p \land q \to \neg r \\
&p \lor \neg q \\
&\neg q \to p \\
&\therefore \neg r
\end{aligned}$$

**5.** Argumento 5: Error converso

$$\begin{aligned}
&p \to q \\
&q \\
&\therefore p
\end{aligned}$$

**6.** Argumento 5: Error contrario

$$\begin{aligned}
&p \to q \\
&\neg p \\
&\therefore \neg q
\end{aligned}$$

> El enunciado original repite "Argumento 5" tanto en el ejercicio 5 como en el 6. Se transcribe tal como aparece en el documento fuente.
{: .note }

### Bloque B — Argumentos en lenguaje natural, validez mediante tabla de verdad (7-11)
{: .no_toc }

> Dadas las siguientes argumentaciones en lenguaje hablado:
> - Defina las proposiciones simples involucradas en cada enunciado del argumento.
> - Exprese en las tres formas (Notación de consecuentes, tautología y notación proposicional) cada caso.
> - Mediante el uso de la tabla de verdad (identificando claramente las columnas asociadas a las premisas y a la conclusión) identifique la validez de cada argumento.

**7.** Argumento 1: Si Tom no está en el equipo A, entonces, Hua está en el equipo B. Si Hua no está en el equipo B, entonces, Tom está en el equipo A. Por lo tanto, Tom no está en el equipo A o Hua no está en el equipo B.

**8.** Argumento 2: Oleg estudia la licenciatura en matemáticas o Oleg estudia la licenciatura en economía. Si Oleg estudia la licenciatura en matemáticas, entonces a Oleg se le requiere que curse Matemáticas 362. Por lo tanto, Oleg estudia la licenciatura en economía o a Oleg no se le requiere que curse Matemáticas 362.

**9.** Argumento 3: Sandra sabe Java y Sandra sabe C++. Por lo tanto, Sandra sabe C++.

**10.** Argumento 4: Si este número es mayor que 2, entonces su cuadrado es mayor que 4. Este número no es mayor que 2. Por lo tanto, el cuadrado de este número no es mayor que 4.

**11.** Argumento 5: Si este programa es correcto, entonces produce la salida correcta cuando se ejecuta con los datos de prueba que me dio el profesor. Este programa genera la salida correcta cuando se ejecuta con los datos de prueba que me dio el profesor. Por lo tanto, el programa es correcto.

### Bloque C — Validez mediante reglas de inferencia (12-15)
{: .no_toc }

> Mediante el empleo de las reglas de inferencia (dadas en la tabla) demuestre la validez para los siguientes argumentos lógicos:

**12.** Argumento 1:

$$\begin{aligned}
&\neg p \lor q \to r \\
&s \lor \neg q \\
&\neg t \\
&p \to t \\
&\neg p \land r \to \neg s \\
&\therefore \neg q
\end{aligned}$$

**13.** Argumento 2:

$$\begin{aligned}
&p \lor q \\
&q \to r \\
&p \land s \to t \\
&\neg r \\
&\neg q \to u \land s \\
&\therefore t
\end{aligned}$$

**14.** Argumento 3:

$$\begin{aligned}
&\neg p \to r \land \neg s \\
&t \to s \\
&u \to \neg p \\
&\neg w \\
&u \lor w \\
&\therefore \neg t
\end{aligned}$$

**15.** Argumento 4:

$$\begin{aligned}
&p \to q \\
&r \lor s \\
&\neg s \to \neg t \\
&\neg q \lor s \\
&\neg s \\
&\neg p \land r \to u \\
&w \lor t \\
&\therefore u \land w
\end{aligned}$$

### Bloque D — Argumentos en lenguaje natural, validez mediante reglas de inferencia (16-17)
{: .no_toc }

> Dadas las siguientes argumentaciones en lenguaje hablado:
> - Defina las proposiciones simples involucradas en cada enunciado del argumento.
> - Exprese en las tres formas (Notación de consecuentes, tautología y notación proposicional) cada caso.
> - Mediante el empleo de las reglas de inferencia (dadas en la tabla) demuestre la validez para las expresiones lógicas a las que llegó.

**16.** Dada la siguiente información sobre un programa de computadora, encuentre el error en el programa.

a. Hay una variable no declarada o hay un error de sintaxis en las primeras cinco líneas.
b. Si hay un error de sintaxis en las primeras cinco líneas, entonces, falta un punto y coma o el nombre de una variable está mal escrito.
c. No falta un punto y coma.
d. No está mal escrito el nombre de una variable.

**17.** En la parte trasera de un viejo armario descubre una nota firmada por un pirata famoso por su extraño sentido del humor y amor a los rompecabezas lógicos. En la nota escribió que él había escondido el tesoro en algún lugar de la propiedad. Hizo una lista de cinco enunciados verdaderos (del a al e que se muestran a continuación) y desafió a quien encuentre la nota a usarlos para averiguar la ubicación del tesoro:

a. Si esta casa está al lado de un lago, entonces el tesoro no está en la cocina.
b. Si el árbol en el patio delantero es un olmo, entonces el tesoro está en la cocina.
c. Esta casa está al lado de un lago.
d. El árbol del patio delantero es un olmo o el tesoro está enterrado bajo el asta de la bandera.
e. Si el árbol del patio trasero es un roble, el tesoro está en el garaje.

¿Dónde está escondido el tesoro?

## ¿Cómo verificar sus propias respuestas?

> Antes de dar por terminado un ejercicio, revise:
> 1. En su tabla de verdad, ¿marcó con claridad cuáles columnas son premisas y cuál es la conclusión?
> 2. Para declarar un argumento válido, ¿revisó **todas** las filas donde todas las premisas son verdaderas (no solo una)? Un argumento es válido si en cada una de esas filas la conclusión también es verdadera.
> 3. Si usó reglas de inferencia, ¿cada paso de su demostración cita explícitamente el nombre de la regla aplicada (Modus Ponens, Silogismo Hipotético, etc.)?
{: .tip }

## Anexo completo (referencia extendida)

<details markdown="1">
<summary>Ver Anexo completo — formulario completo de operadores lógicos</summary>

**Clasificación de las proposiciones según su estructura**

| Tipo | Descripción | Ejemplo |
|---|---|---|
| Simples (atómicas) | No se pueden dividir en partes más pequeñas con valor de verdad. | Hoy es lunes. |
| Compuestas (moleculares) | Formadas al unir dos o más proposiciones simples mediante conectores lógicos. | Hoy es lunes y hace sol. |

**Clasificación de las proposiciones de acuerdo al valor de verdad de todas sus interpretaciones**

| Tipo | Descripción | Ejemplo |
|---|---|---|
| Tautología | Siempre verdadera para todas sus interpretaciones. | $p \lor \neg p$ |
| Contradicción | Siempre falsa en todas las interpretaciones. | $p \land \neg p$ |
| Contingencia | A veces verdadera, a veces falsa, depende de los valores de verdad. | $p \to q$ |

**Operadores lógicos**

| Operador | Símbolo | Nombre | Descripción |
|---|---|---|---|
| Negación | $\neg p$ | No (NOT) | Niega el valor de verdad de una proposición. Si $p$ es verdadera, $\neg p$ es falsa. |
| Conjunción | $p \land q$ | Y (AND) | Es verdadera solo si ambas proposiciones lo son. |
| Disyunción | $p \lor q$ | O (OR) | Es verdadera si al menos una de las proposiciones lo es. |
| Disyunción exclusiva | $p \oplus q$ | O exclusiva (XOR) | Es verdadera si una, y solo una, de las proposiciones es verdadera. |
| Condicional | $p \to q$ | Si … entonces … (Implica) | Solo es falsa cuando $p$ es verdadera y $q$ es falsa. |
| Bicondicional | $p \leftrightarrow q$ | … si y solo si … (Equivale) | Es verdadera cuando ambas proposiciones tienen el mismo valor de verdad. |

**Tablas de verdad de los operadores lógicos**

Negación

| $p$ | $\neg p$ |
|---|---|
| F | V |
| V | F |

Conjunción

| $p$ | $q$ | $p \land q$ |
|---|---|---|
| F | F | F |
| F | V | F |
| V | F | F |
| V | V | V |

Disyunción inclusiva

| $p$ | $q$ | $p \lor q$ |
|---|---|---|
| F | F | F |
| F | V | V |
| V | F | V |
| V | V | V |

Disyunción exclusiva

| $p$ | $q$ | $p \oplus q$ |
|---|---|---|
| F | F | F |
| F | V | V |
| V | F | V |
| V | V | F |

Condicional

| $p$ | $q$ | $p \to q$ |
|---|---|---|
| F | F | V |
| F | V | V |
| V | F | F |
| V | V | V |

Bicondicional

| $p$ | $q$ | $p \leftrightarrow q$ |
|---|---|---|
| F | F | V |
| F | V | F |
| V | F | F |
| V | V | V |

**Precedencia y asociatividad**

| Prioridad | Símbolo | Asociatividad | Ejemplo con paréntesis |
|---|---|---|---|
| 1 (más alta) | $\neg$ | No aplica (unitario) | $\neg p \land q \Longrightarrow ((\neg p) \land q)$ |
| 2 | $\land$ | Izquierda | $p \land q \land r \Longrightarrow ((p \land q) \land r)$ |
| 3 | $\lor$ | Izquierda | $p \lor q \lor r \Longrightarrow ((p \lor q) \lor r)$ |
| 4 | $\oplus$ | Izquierda | $p \oplus q \oplus r \Longrightarrow ((p \oplus q) \oplus r)$ |
| 5 | $\to$ | Derecha | $p \to q \to r \Longrightarrow (p \to (q \to r))$ |
| 6 (más baja) | $\leftrightarrow$ | Derecha | $p \leftrightarrow q \leftrightarrow r \Longrightarrow (p \leftrightarrow (q \leftrightarrow r))$ |

**Clasificación de expresiones condicionales**

| Nombre | Símbolo | Lectura | Significado lógico |
|---|---|---|---|
| Condicional | $p \to q$ | Si $p$ entonces $q$ | Es falsa solo si $p$ es verdadera y $q$ es falsa. |
| Recíproco | $q \to p$ | Si $q$ entonces $p$ | Invierte antecedente y consecuente. |
| Contrarrecíproco | $\neg q \to \neg p$ | Si no $q$ entonces no $p$ | Lógicamente equivalente a la condicional original. |
| Contrario | $\neg p \to \neg q$ | Si no $p$ entonces no $q$ | Negación de ambas partes de la condicional. |

**Equivalencias lógicas**

| Nombre | Forma $\land$ / $\to$ | Forma $\lor$ |
| :--- | :--- | :--- |
| **Conmutativa** | $p \land q \equiv q \land p$ | $p \lor q \equiv q \lor p$ |
| **Asociativa** | $(p \land q) \land r \equiv p \land (q \land r)$ | $(p \lor q) \lor r \equiv p \lor (q \lor r)$ |
| **Distributiva** | $p \land (q \lor r) \equiv (p \land q) \lor (p \land r)$ | $p \lor (q \land r) \equiv (p \land q) \land (p \land r)$ |
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