---
layout: default
title: Taller 2 - Lógica Proposicional
parent: Talleres de Repaso
nav_order: 2
math: mathjax
---

# Taller 2 – Matemáticas Discretas
{: .no_toc }

## Tabla de Contenidos
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Objetivo de aprendizaje

Al finalizar este taller, usted podrá traducir proposiciones compuestas hacia y desde lenguaje natural, reescribir enunciados condicionales y bicondicionales, evaluar valores de verdad, construir proposiciones compuestas a partir de condiciones dadas, elaborar tablas de verdad y determinar la equivalencia lógica entre formas proposicionales.

## Referencia rápida

### Operadores lógicos
{: .no_toc }

| Operador | Símbolo | Nombre | Descripción |
|---|---|---|---|
| Negación | $\neg p$ | No (NOT) | Niega el valor de verdad de una proposición. Si $p$ es verdadera, $\neg p$ es falsa. |
| Conjunción | $p \land q$ | Y (AND) | Es verdadera solo si ambas proposiciones lo son. |
| Disyunción | $p \lor q$ | O (OR) | Es verdadera si al menos una de las proposiciones lo es. |
| Disyunción exclusiva | $p \oplus q$ | O exclusiva (XOR) | Es verdadera si una, y solo una, de las proposiciones es verdadera. |
| Condicional | $p \to q$ | Si … entonces … (Implica) | Solo es falsa cuando $p$ es verdadera y $q$ es falsa. |
| Bicondicional | $p \leftrightarrow q$ | … si y solo si … (Equivale) | Es verdadera cuando ambas proposiciones tienen el mismo valor de verdad. |

### Precedencia y asociatividad
{: .no_toc }

| Prioridad | Símbolo | Asociatividad | Ejemplo con paréntesis |
|---|---|---|---|
| 1 (más alta) | $\neg$ | No aplica (unitario) | $\neg p \land q \Longrightarrow ((\neg p) \land q)$ |
| 2 | $\land$ | Izquierda | $p \land q \land r \Longrightarrow ((p \land q) \land r)$ |
| 3 | $\lor$ | Izquierda | $p \lor q \lor r \Longrightarrow ((p \lor q) \lor r)$ |
| 4 | $\oplus$ | Izquierda | $p \oplus q \oplus r \Longrightarrow ((p \oplus q) \oplus r)$ |
| 5 | $\to$ | Derecha | $p \to q \to r \Longrightarrow (p \to (q \to r))$ |
| 6 (más baja) | $\leftrightarrow$ | Derecha | $p \leftrightarrow q \leftrightarrow r \Longrightarrow (p \leftrightarrow (q \leftrightarrow r))$ |

> Este taller también requiere las **equivalencias lógicas** y las **tablas de verdad completas** de cada operador (necesarias para los bloques de Tablas de verdad y Equivalencias lógicas más abajo). Para no repetir contenido, esas tablas están disponibles completas en el **Anexo completo**, al final de este documento.
{: .tip }

## Enunciados

### Bloque 1 — Traducción e interpretación de conectores (1-2)
{: .no_toc }

**1.** Sean $p$ y $q$ las proposiciones "Se permite nadar en la costa de Coveñas" y "Se han avistado tiburones cerca de la costa", respectivamente. Exprese cada proposición compuesta como una oración en lenguaje natural.

- $\neg p$
- $p \land q$
- $\neg p \lor q$
- $p \to \neg q$
- $\neg q \to p$
- $\neg p \to \neg q$
- $p \leftrightarrow \neg q$
- $\neg p \land (p \lor \neg q)$

**2.** Para cada una de estas oraciones, determine si el *o* que empleado es inclusivo o exclusivo. Explique su respuesta:

- El café o el té viene con la cena.
- Una contraseña debe tener al menos tres dígitos o al menos ocho caracteres de longitud.
- El requisito previo para el curso es teoría de números o criptografía.
- Puedes pagar con dólares o euros.
- Experiencia con C++ o Java es requerida.
- Para entrar al país necesitas un pasaporte o una tarjeta de registro electoral.

### Bloque 2 — Reescritura condicional (3, 5, 6)
{: .no_toc }

**3.** Escriba cada una de estas afirmaciones en la forma *Si p, entonces q*:

- Es necesario lavar el carro del jefe para ascender.
- Los vientos del sur implican un deshielo primaveral.
- Una condición suficiente para que la garantía sea válida es que hayas comprado el ordenador hace menos de un año.
- A Willy lo pillan cada vez que hace trampa.
- Solo podrás acceder al sitio web si pagas una tarifa de suscripción.
- Ser elegido es una cuestión de conocer a las personas adecuadas.
- Carol se marea cada vez que está en un barco.

**5.** Reescriba cada uno de los enunciados de los siguientes ejercicios como una conjunción de dos enunciados si-entonces (Nota: recuerde que $p \leftrightarrow q \equiv (p \to q) \land (q \to p)$).

- Esta ecuación de segundo grado tiene dos raíces reales distintas si y sólo si, su discriminante es mayor que cero.
- Este entero es par si y sólo si, es igual a dos veces un número entero.

**6.** Reescriba los enunciados que se muestran a continuación en la forma si-entonces de dos maneras, una de las cuales es el contrarrecíproco de la otra.

- Los Cachorros van a ganar el campeonato sólo si ganan el partido de mañana.
- A Sam se le permitirá participar en la carrera de botes Signe sólo si él es un experto navegante.

### Bloque 3 — Evaluación de valores de verdad (4, 7, 8)
{: .no_toc }

**4.** Determine si cada una de las siguientes afirmaciones es verdadera o falsa:

- Si 1 + 1 = 3, entonces los unicornios existen.
- Si 1 + 1 = 3, entonces los perros pueden volar.
- Si 1 + 1 = 2, entonces los perros pueden volar.
- Si 2 + 2 = 4, entonces 1 + 2 = 3.

**7.** Sean $P$, $Q$ y $R$ expresiones lógicas. Si $R \land P \to Q \land P$ es formalmente cierta, ¿cuáles valores de verdad no pueden tomar $P$, $Q$ y $R$? Explique sin el uso de una tabla de verdad. Luego, mediante el uso de esta, compruebe la explicación a la que llegó al principio.

**8.** Sean $P$, $Q$, $R$ y $S$ fórmulas. Si se sabe únicamente que $P$ es verdadero, ¿qué puede afirmarse del valor de verdad de cada una de las formas proposicionales siguientes?

- $P \land Q$
- $R \to P$
- $S \to \neg P$
- $R \lor P$
- $P \to Q$
- $R \to (S \to P)$
- $R \land P$
- $P \to P \lor S$
- $P \lor S \to (Q \lor \neg P)$
- $S \lor \neg P$
- $\neg P \to Q \land R$
- $Q \land \neg P \to R \land Q$

### Bloque 4 — Construcción de proposiciones compuestas (9-10)
{: .no_toc }

**9.** Encuentre una proposición compuesta que involucre las variables proposicionales $P$, $Q$ y $R$, que sea verdadera cuando $P$ y $Q$ son verdaderas y $R$ es falsa, pero falsa en caso contrario. (Pista: use una conjunción de cada variable proposicional o su negación).

**10.** Encuentre una proposición compuesta que incluya las variables proposicionales $P$, $Q$ y $R$ que sea verdadera cuando exactamente dos de $P$, $Q$ y $R$ sean verdaderas, y falsa en caso contrario. (Pista: forme una disyunción de conjunciones. Incluya una conjunción para cada combinación de valores para la cual la proposición compuesta sea verdadera. Cada conjunción debe incluir cada una de las tres variables proposicionales o sus negaciones).

### Bloque 5 — Tablas de verdad (11)
{: .no_toc }

**11.** Construya la tabla de verdad para cada una de las siguientes proposiciones compuestas:

- $(P \leftrightarrow Q) \oplus (P \leftrightarrow \neg Q)$
- $(P \oplus Q) \to (P \oplus \neg Q)$
- $((P \to Q) \to R) \to S$
- $R \land (S \to \neg T)$
- $(R \land S) \to \neg T$

> Antes de empezar, revise en el **Anexo** las tablas de verdad de los operadores base ($\neg, \land, \lor, \oplus, \to, \leftrightarrow$) — las necesitará como bloques de construcción para armar las tablas de estas proposiciones compuestas.
{: .tip }

### Bloque 6 — Equivalencias lógicas (12-15)
{: .no_toc }

**12.** Muestre que las siguientes formas de enunciados son lógicamente equivalentes: $p \to q \lor r$, $p \land \neg p \to r$, $p \land \neg r \to p$.

**13.** Demuestre que $(p \to q) \to (r \to s)$ y $(p \to r) \to (q \to s)$ no son lógicamente equivalentes.

**14.** Escriba cada uno de los dos enunciados en forma simbólica y determine si son lógicamente equivalentes.

- Si pagó el precio completo y no compró en la librería Corona. No compró en la librería Corona o pagó el precio completo.
- Si 2 es un factor de n y 3 es un factor de n, entonces 6 es un factor de n. 2 no es un factor de n o 3 no es un factor de n o 6 es un factor de n.

**15.** Escriba cada uno de los siguientes tres enunciados en forma simbólica y determine qué pares son lógicamente equivalentes.

- Si camina como un pato y habla como un pato, entonces es un pato.
- O bien no camina como un pato o no habla como un pato, o es un pato.
- Si no camina como un pato y no habla como un pato, entonces no es un pato.

> Para demostrar o refutar una equivalencia lógica puede usar tabla de verdad (comparando columnas finales) o una cadena de equivalencias ya conocidas (ver **Anexo → Equivalencias lógicas**).
{: .tip }

### Bloque 7 — Casos aplicados y especiales (16-17)
{: .no_toc }

**16.** ¿Verdadero o falso? La negación de "Si Susana es la madre de Luis, entonces, Ali es su primo" es "Si Susana es la madre de Luis, entonces, Ali no es su primo".

**17.** Teniendo una gran visión de su educación, va a la corporación Prestigio y pregunta qué debe estudiar en la universidad para que se le contrate cuando se gradúe. El director de personal responde que se le contratará sólo si hace una carrera de matemáticas o en ciencias de la computación, obtiene un promedio de B o mejor y toma el curso de contabilidad. De hecho, lo hace: estudia matemáticas, obtiene un promedio de B+ y estudia contabilidad. Regresa a la compañía Prestigio, hace una solicitud formal y es rechazada. ¿El director de personal le mintió?

### Bloque 8 — Operador lógico personalizado (18)
{: .no_toc }

**18.** En la siguiente tabla de verdad se define una nueva operación llamada $imp2$:

| $p$ | $q$ | $p \text{ imp2 } q$ |
|---|---|---|
| V | V | V |
| V | F | F |
| F | V | V |
| F | F | F |

- Demuestre que $(p \text{ imp2 } q) \land (p \text{ imp2 } p) \not\equiv p \leftrightarrow q$.
- Si se modifica el tercer renglón de la tabla de verdad asociada a $imp2$, de tal manera que el resultado (que actualmente es V) cambie a F, ¿qué se puede decir de la equivalencia demostrada en el punto anterior?

## ¿Cómo verificar sus propias respuestas?

> Antes de dar por terminado un ejercicio, revise:
> 1. En una tabla de verdad, ¿el número de filas corresponde a $2^n$, donde $n$ es el número de variables proposicionales distintas?
> 2. Al descomponer un bicondicional, ¿verificó ambas direcciones ($p \to q$ **y** $q \to p$), no solo una?
> 3. Al afirmar una equivalencia lógica, ¿la respaldó con una tabla de verdad completa o con una cadena de leyes lógicas nombradas (Anexo), y no solo con intuición?
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

> La negación siempre aplica a la proposición o expresión inmediatamente después de ella. Los operadores con igual precedencia se agrupan según su asociatividad. Cuando la expresión tiene paréntesis anidados, evalúela de adentro hacia afuera.
{: .tip }

**Clasificación de expresiones condicionales**

| Nombre | Símbolo | Lectura | Significado lógico |
|---|---|---|---|
| Condicional | $p \to q$ | Si $p$ entonces $q$ | Es falsa solo si $p$ es verdadera y $q$ es falsa. |
| Recíproco | $q \to p$ | Si $q$ entonces $p$ | Invierte antecedente y consecuente. |
| Contrarrecíproco | $\neg q \to \neg p$ | Si no $q$ entonces no $p$ | Lógicamente equivalente a la condicional original. |
| Contrario | $\neg p \to \neg q$ | Si no $p$ entonces no $q$ | Negación de ambas partes de la condicional. |

**Equivalencias lógicas — leyes duales (forma con $\land$ y forma con $\lor$)**

| Nombre | Forma con $\land$ | Forma con $\lor$ |
|---|---|---|
| Conmutatividad | $P \land Q \equiv Q \land P$ | $P \lor Q \equiv Q \lor P$ |
| Asociatividad | $(P \land Q) \land R \equiv P \land (Q \land R)$ | $(P \lor Q) \lor R \equiv P \lor (Q \lor R)$ |
| Distributividad | $P \land (Q \lor R) \equiv (P \land Q) \lor (P \land R)$ | $P \lor (Q \land R) \equiv (P \lor Q) \land (P \lor R)$ |
| Idempotencia | $P \land P \equiv P$ | $P \lor P \equiv P$ |
| Leyes de De Morgan | $\neg(P \land Q) \equiv \neg P \lor \neg Q$ | $\neg(P \lor Q) \equiv \neg P \land \neg Q$ |
| Identidad | $P \land V \equiv P$ | $P \lor F \equiv P$ |
| Dominación | $P \land F \equiv F$ | $P \lor V \equiv V$ |
| Absorción | $P \land (P \lor Q) \equiv P$ | $P \lor (P \land Q) \equiv P$ |
| Complemento | $P \land \neg P \equiv F$ | $P \lor \neg P \equiv V$ |

**Equivalencias lógicas — sin forma dual $\land$/$\lor$**

| Nombre | Equivalencia lógica |
|---|---|
| Doble negación | $\neg(\neg P) \equiv P$ |
| Implicación | $P \to Q \equiv \neg P \lor Q$ |
| Contrarrecíproco | $P \to Q \equiv \neg Q \to \neg P$ |
| Equivalencia | $P \leftrightarrow Q \equiv (P \to Q) \land (Q \to P)$ |

</details>
