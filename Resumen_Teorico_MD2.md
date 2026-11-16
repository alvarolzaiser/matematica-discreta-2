# RESUMEN TEÓRICO UNIFICADO — MATEMÁTICA DISCRETA 2 (MD2)

> **Propósito:** Compendio teórico unificado y conciso de las **12 clases** de Matemática Discreta 2 (Unidades 1, 2 y 3), auditado página por página contra los **12 PDFs originales (`1.pdf` a `12.pdf`)**. Cada concepto conserva **las palabras, fórmulas y jerga exactas del material de estudio** (`📖 Definición textual / Enunciado`) seguidas de su explicación conceptual directa en palabras simples (`💡 En simple`).

---

## 🗺️ ÍNDICE Y MAPA ESTRUCTURAL DE LAS 3 UNIDADES

| Unidad | Clases | Contenidos Teóricos Nucleares |
| :--- | :--- | :--- |
| **UNIDAD 1: ÁLGEBRA DE BOOLE Y FUNCIONES BOOLEANAS** | **Clases 1 a 4** | **• Clase 1:** Conjuntos discretos, sistema binario, circuitos de tuberías (serie/paralelo) y circuitos lógicos como sistemas, variables lógicas (`0` y `1`), operaciones lógicas (`+`, `.`, `Ā`), los **4 Axiomas (`A1` a `A4`)**, independencia simbólica y demostración con axiomas.<br>**• Clase 2:** Diferencia entre axiomas y teoremas, los **6 Teoremas (`T1` a `T6`)** y todas sus demostraciones (algebraicas y por tabla de verdad).<br>**• Clase 3:** Funciones Booleanas, evaluación, tablas de verdad (`2ⁿ` combinaciones, reglas operativas y doble lectura), las **5 compuertas lógicas (`OR`, `AND`, `NOT`, `NOR`, `NAND`)** y los 3 modos de representación.<br>**• Clase 4:** Términos canónicos (**Maxitérmino** y **minitérmino**), reconocimiento de casos, **Forma Canónica** (`∏M` / `IIM` y `∑m`) por tabla y algebraica, síntesis y simplificación de funciones. |
| **UNIDAD 2: MATRICES Y DETERMINANTES** | **Clases 5 a 8** | **• Clase 5:** Esquema de la Unidad 2, concepto de matriz, orden `n × m` (`n.m` elementos), posición `aᵢⱼ`, vectores fila y columna, matriz como conjunto ordenado de vectores, **clasificación de matrices especiales** e igualdad de matrices.<br>**• Clase 6:** Operaciones matriciales: **adición**, **sustracción**, **producto por un número (`kA`)**, los **4 pasos para resolver problemas**, **producto escalar** y **multiplicación de matrices** (conformables, permutables, propiedades y no cancelativa).<br>**• Clase 7:** **Matriz canónica por filas** (las 4 condiciones, elemento conductor `1`, **rango `ρ(A)`** y casos particulares), las **3 operaciones elementales (`Hᵢ,ⱼ`, `Hᵢ(k)`, `Hᵢ,ⱼ(k)`)**, equivalencia (`A ~ B`), **columna de control** y preguntas teóricas.<br>**• Clase 8:** **Determinante `|A|`** (concepto, orden 2, **Regla de Sarrus**, las **6 propiedades**, **matriz regular** y **Regla de Chío**), **Matriz Inversa (`A⁻¹`)** por Gauss-Jordan y **Cuestionario / Verdadero-Falso Oficial Integrador (`DF 4`, `DF 5`, `DF 8`)**. |
| **UNIDAD 3: SISTEMAS DE ECUACIONES LINEALES** | **Clases 9 a 12** | **• Clase 9:** Esquema de la Unidad 3, cuadrados mágicos y constante mágica, **ecuación**, parte literal, raíces o soluciones, **ecuaciones lineales**, sistemas lineales, clasificación en **homogéneos / no homogéneos** y en **compatibles (determinados / indeterminados) / incompatibles**, y verificación.<br>**• Clases 10 y 11:** Sistema completo y ordenado, matrices `A, B, X`, **forma matricial (`A . X = B`)**, **matriz ampliada (`A° = [ A : B ]`)**, los **5 pasos del Método General**, clasificación por rangos (`ρ(A)`, `ρ(A°)` y `m`), **sistemas homogéneos** (solución trivial y no triviales, criterio `|A| = 0`), contradicción, **variables libres (`m - ρ(A°)`)**, solución general (`X*`), soluciones particulares y **los 3 casos de validación**.<br>**• Clase 12:** **Sistema cuadrado**, **Regla de Cramer** (`xⱼ = |Aⱼ| / |A|`), caso `|A| = 0`, **Matriz de Insumo-Producto** `(I - A) . X = D` y **Verdadero/Falso Oficial Integrador**. |

---

# UNIDAD 1: ÁLGEBRA DE BOOLE Y FUNCIONES BOOLEANAS (CLASES 1 A 4)

## CLASE 1 — Introducción, Variables, Operaciones Lógicas y Axiomas del Álgebra de Boole

### 1.1 Matemática Discreta, Conjuntos Discretos y Sistema Binario
* **📖 Definición textual / Enunciado:**
  > *"Matemática Discreta recibe ese nombre ya que trabaja con **conjuntos discretos**, es decir **conjuntos finitos o infinitos pero numerables**. Ampliamos los conceptos de la lógica simbólica proposicional de MD1, en la que nuestras variables eran las **proposiciones**, sentencias que son verdaderas o son falsas, hacia el **Álgebra de Boole** [en la unidad 1; luego en la unidad 2 estudiaremos álgebra de Matrices, y en la unidad 3 las aplicaremos a la resolución de sistemas de ecuaciones lineales]. En las situaciones planteadas `[1]` [el **circuito de tuberías 1** en serie, donde el agua llega al recipiente inferior solo con **llave A y llave B abiertas (`A4`)**, y el **circuito de tuberías 2** en paralelo, donde el agua llega con **llave A o llave B abierta (`A2, A3, A4`)**], el estado de esos elementos solo tiene dos posibilidades (abierta o cerrada), como así también el resultado. Estos elementos que pueden asociarse a dos estados podemos relacionarlos al **sistema de numeración binario**, en el que basó Boole su esquema, para formalizar su Álgebra."*
* **💡 En simple:** Un conjunto es **discreto** cuando sus elementos son aislados y se pueden contar uno por uno (sea finito o infinito numerable). El **Álgebra de Boole** traduce la lógica proposicional de MD1 (verdadero/falso) al **sistema binario (`0` y `1`)** para modelar cualquier sistema cuyos componentes y resultados solo admitan **dos estados posibles** (como dos llaves de agua en serie o en paralelo).

### 1.2 Codificación Binaria y Circuitos Lógicos como Sistemas
* **📖 Definición textual / Enunciado:**
  > *"Las computadoras usan **codificación binaria**, entonces una **unidad elemental de información** puede tomar solamente dos valores, `0` ó `1`, por lo que la base de las computadoras son los **circuitos lógicos**, los cuales son analizados mediante el Álgebra de Boole. Podemos considerar al circuito como un **sistema que transforma las señales de entrada**, que serían la posición de los interruptores A, B y C, en **señales de salida**, que sería el estado de la lámpara."*
* **💡 En simple:** Como cada bit (unidad elemental de información) solo vale `0` ó `1`, el hardware digital se construye con **circuitos lógicos** que funcionan como sistemas: reciben **señales de entrada** (`0` o `1` en los interruptores) y devuelven una **señal de salida** (`0` o `1` en la lámpara).

### 1.3 Elementos Básicos del Álgebra de Boole y Variables Lógicas
* **📖 Definición textual / Enunciado:**
  > *"Los elementos básicos con los que se define el Álgebra de Boole son las **variables** y las **operaciones**.*
  > *· **Variables lógicas:** solo pueden tomar un valor entre dos opciones excluyentes, `0` ó `1`. En una tubería una llave puede estar abierta (`1`) o cerrada (`0`), en un circuito eléctrico un interruptor puede estar abierto (`0`) o cerrado (`1`), y una lámpara en el mismo puede estar apagada (`0`) o encendida (`1`). Por lo tanto el estado de los distintos elementos de un circuito, se describe usando variables lógicas."*
* **💡 En simple:** Una **variable lógica** (`A, B, C...`) solo puede valer **`0` ó `1` de forma excluyente**. Atención a la convención física del material: en una **tubería**, llave abierta es `1` (pasa agua) y cerrada es `0`; en un **circuito eléctrico**, **interruptor cerrado es `1`** (cierra el contacto y pasa corriente) e **interruptor abierto es `0`** (corta el paso), mientras que **lámpara encendida es `1`** y **apagada es `0`**.

### 1.4 Operaciones Lógicas: Suma Lógica (`+`), Producto Lógico (`.`) y Negación (`Ā`)
* **📖 Definición textual / Enunciado:**
  > *"· **Operaciones lógicas:** permiten combinar variables para poder obtener otras variables. **Si bien reciben nombres similares o iguales a algunas operaciones del Álgebra clásica, debes tener en cuenta que no tienen nada que ver con ellas** (hay que desestructurar las estructuras del álgebra clásica). Las operaciones son: **suma lógica**, **producto lógico** y **negación**.*
  > *- **Suma Lógica (`+`):** se relaciona con el conector lógico “`∨`” (disyunción) de MD1. Tabla: `0 + 0 = 0` ; `0 + 1 = 1` ; `1 + 0 = 1` ; `1 + 1 = 1`. En un circuito eléctrico (`F = A + B`, en paralelo), el estado encendido (`1`) de la lámpara se dará cuando al menos uno de los interruptores esté cerrado (`1`). **La suma lógica tendrá un valor de `1` cuando al menos una de las variables tenga el valor `1`, es decir que será `0`, solo cuando todas las variables sumadas sean `0`.***
  > *- **Producto lógico (`.`):** se relaciona con el conector lógico “`∧`” (conjunción) de MD1. Tabla: `0 . 0 = 0` ; `0 . 1 = 0` ; `1 . 0 = 0` ; `1 . 1 = 1`. En un circuito eléctrico (`F = A . B`, en serie), el estado encendido (`1`) de la lámpara se dará cuando los dos interruptores estén cerrados (`1`). **El producto lógico tendrá un valor de `1` sólo cuando todas las variables tengan el valor `1`, es decir que siempre que en el producto haya un valor `0`, sin importar la cantidad de `1`, el resultado será `0`.***
  > *- **Negación o Complemento (`Ā`):** corresponde al conector “`¬`” de MD1; **se aplica sobre una sola variable, y lo que hace es invertir el valor de la misma**: si `A = 0`, `Ā = 1` ; si `A = 1`, `Ā = 0`. En el circuito `F = Ā`, el estado encendido (`1`) de la lámpara se da cuando el estado del interruptor es (`0`)."*
* **💡 En simple:** No deben confundirse con la aritmética común:
  * **Suma lógica (`+`):** Equivale al **"O" (`∨`)** e interruptores en **paralelo**; basta un solo `1` para que dé `1` (por eso `1 + 1 = 1`), y solo da `0` si **todas** las variables valen `0`.
  * **Producto lógico (`.` o `•`):** Equivale al **"Y" (`∧`)** e interruptores en **serie**; exige que **todas** las variables valgan `1` para dar `1`, y basta un solo `0` para anular el producto a `0`.
  * **Negación o complemento (`Ā`):** Es unaria (`¬`) e **invierte el valor** (`0 ↔ 1`).

### 1.5 Propiedades del Álgebra de Boole: Axiomas (`A1` a `A4`), Independencia Simbólica y Demostración con Axiomas
* **📖 Definición textual / Enunciado:**
  > *"Dentro de las propiedades del Álgebra de Boole haremos la distinción en dos grandes grupos, aquellas a las que llamamos **Axiomas**, que son la base de las demás, ya que ellas **se toman como válidas o ciertas sin la necesidad de demostrar nada**; y el otro grupo serán aquellas a las que llamamos **Teoremas**, que **no se toman como válidas hasta haberlas demostrado lógicamente**.*
  > *Axiomas que constituyen la base de este Álgebra (para elementos `A, B, C` pertenecientes a `M`):*
  > *• **A1: PROPIEDAD CONMUTATIVA:** Para cualesquiera dos elementos, A y B pertenecientes a M, se cumple: `a- A + B = B + A` ; `b- A • B = B • A`.*
  > *• **A2: PROPIEDAD DISTRIBUTIVA:** Para cualesquiera elementos, A, B y C pertenecientes a M, se cumple: `a- A • (B + C) = (A • B) + (A • C)` ; `b- A + (B • C) = (A + B) • (A + C)`.*
  > *• **A3: ELEMENTO NEUTRO:** Existen para cada una de las operaciones un elemento neutro que cumple con la propiedad de identidad, esto es: `a- A + 0 = A` ; `b- A • 1 = A`.*
  > *• **A4: COMPLEMENTO:** Para cada elemento A de M existe otro que oficia de negación o complemento del mismo (`Ā`), es decir, que cumpla lo siguiente: `a- A + Ā = 1` ; `b- A • Ā = 0`.*
  > *• **Recomendación de comprensión estructural (pág. 7):** “Debe recordarlos y tratar de **comprender sus enunciados más allá de las letras que se utilicen**. El axioma de la propiedad distributiva dice `A + B . C = (A + B) . (A + C)`, eso mismo lo podría decir así, `1 + 2 . 3 = (1 + 2) . (1 + 3)`, o también podría ser `$ + & . % = ($ + &) . ($ + %)`. Es decir, trate de entender el enunciado más allá de los símbolos empleados.”*
  > *• **Demostración de igualdades con axiomas (Desempeños 1 y 2, pág. 6):** En cada paso se indica qué axioma se aplicó al pasar del renglón superior al inferior (ejemplos resueltos del Desempeño 1: **`a-` `M + N.N̄ = M`** → `M + 0` `[Ax 4b]` → `M` `[Ax 3a]`; **`b-` `X . (Y + Ȳ) = X`** → `X . 1` `[Ax 4a]` → `X` `[Ax 3b]`; **`c-` `J.K + K̄.J = J`** → `J.K + J.K̄` `[Ax 1b]` → `J . (K + K̄)` `[Ax 2a]` → `J . 1` `[Ax 4a]` → `J` `[Ax 3b]`)."*
* **💡 En simple:** Los **4 Axiomas** se aceptan sin demostración y vienen en pares duales (`a-` para suma y `b-` para producto):
  1. **A1 (Conmutativa):** El orden de los sumandos o factores no altera el resultado.
  2. **A2 (Distributiva):** Funciona de izquierda a derecha para expandir paréntesis y **de derecha a izquierda para sacar factor común** (y debe entenderse como molde estructural sin importar qué letras o expresiones ocupen cada lugar). Destaca la parte `b-` (`A + B•C = (A + B)•(A + C)`), que no existe en el álgebra numérica común.
  3. **A3 (Elemento Neutro):** Operar con el neutro deja intacta a la variable (`0` es neutro de la suma y `1` es neutro del producto).
  4. **A4 (Complemento):** Operar una variable con su propio complemento `Ā` da siempre constante (`A + Ā = 1` y `A • Ā = 0`).

---

## CLASE 2 — Teoremas del Álgebra de Boole y Métodos de Demostración

### 2.1 Métodos de Demostración: Algebraica y por Tablas de Verdad
* **📖 Definición textual / Enunciado:**
  > *"Recordemos que los **teoremas** también son propiedades, pero a diferencia de los axiomas **Sí necesitan de una demostración para que sean tomados como válidos**. Como le pedimos en la clase 1, trate de comprender los axiomas y también los teoremas **más allá de las letras o símbolos que se utilicen**.*
  > *• **Demostración algebraica:** significa que, partiendo de una de las expresiones, sea el primer miembro o el segundo de la igualdad, se debe ir escribiendo de otra manera [aplicando axiomas y teoremas en cada paso] hasta llegar al otro miembro (puede partir del primer miembro y llegar a la segunda, o partir de la segunda y llegar a la primera, o desarrollar las dos hasta llegar a expresiones idénticas).*
  > *• **Demostración por tablas de verdad:** simplemente se realiza la tabla de verdad, teniendo en cuenta la definición de las operaciones, para cada miembro de la igualdad y **si la distribución de valores de verdad coincide es porque las expresiones son iguales**. (En el Desempeño 5 se indica: **primero verifica por tabla su validez, y en caso de ser verdaderas demuéstralas algebraicamente**; si las columnas finales difieren en alguna fila, la igualdad es falsa)."*
* **💡 En simple:** Toda igualdad booleana se puede demostrar por dos vías: **1) Algebraicamente**, transformando un miembro en el otro (o ambos hasta coincidir) y justificando cada renglón con el código del axioma o teorema aplicado; o **2) Por tabla de verdad**, comprobando que la columna final de ambos miembros tenga exactamente la misma secuencia de `0` y `1` (**distribución de valores de verdad**), método que además sirve para verificar primero si una igualdad propuesta es verdadera o falsa antes de intentar demostrarla algebraicamente.

### 2.2 Los 6 Teoremas del Álgebra de Boole (`T1` a `T6`) y todas sus Demostraciones Oficiales
* **📖 Definición textual / Enunciado:**
  > *• **Teorema 1: Ley de Acotación:** Esta ley establece que: `A + 1 = 1` ; `A • 0 = 0`.*
  >   *- Demostración algebraica oficial de `A + 1 = 1` (partiendo del `1`, pág. 3): Por Ax 4: `1 = A + Ā` → Por Ax 3: `1 = A + (Ā . 1)` → Por Ax 2: `1 = (A + Ā) . (A + 1)` → Por Ax 4: `1 = 1 . (A + 1)` → Por Ax 3: `1 = A + 1`.*
  > *• **Teorema 2: Ley de Idempotencia:** Este teorema establece que: `A + A = A` ; `A • A = A`.*
  > *• **Teorema 3: Ley de Absorción:** Este teorema establece que: `A + (A • B) = A` ; `A • (A + B) = A`.*
  >   *- Demostración por Tabla de Verdad de `A + A . B = A` (pág. 3): Para `(A,B) = (0,0), (0,1), (1,0), (1,1)`, la columna `A . B` es `(0, 0, 0, 1)` y la distribución de valores de verdad de `A` y de `A + A.B` es `(0, 0, 1, 1)`, exactamente la misma, lo que asegura que son expresiones iguales.*
  > *• **Teorema 4: Ley de Asociatividad:** Tanto la suma como el producto lógico gozan de esta propiedad: `A + (B + C) = (A + B) + C = A + B + C` ; `A . (B . C) = (A . B) . C = A . B . C`.*
  > *• **Teorema 5: Ley de Involución:** Establece que negar dos veces un elemento es igual al mismo elemento: `A̿ = A`.*
  > *• **Teorema 6: Ley de De Morgan:** Establece que: `A̅+̅B̅ = Ā • B̄` ; `A̅•̅B̅ = Ā + B̄`."*
* **💡 En simple (significado y las 6 demostraciones algebraicas completas del Desempeño 3, más identidades del Desempeño 6):**
  1. **T1 (Acotación):** El `1` absorbe la suma (`A + 1 = 1`) y el `0` anula el producto (`A • 0 = 0`).
     * *Demostración de `A • 0 = 0` (Desempeño 3.1):* Partiendo de `0`: `0 = A • Ā` *(Ax 4b)* `= A • (Ā + 0)` *(Ax 3a)* `= (A • Ā) + (A • 0)` *(Ax 2a)* `= 0 + (A • 0)` *(Ax 4b)* `= A • 0` *(Ax 3a)*.
  2. **T2 (Idempotencia):** Repetir la misma variable sumada o multiplicada no la altera (`A + A = A` y `A • A = A`).
     * *Demostración de `A + A = A` (Desempeño 3.2):* `A = A + 0` *(Ax 3a)* `= A + (A • Ā)` *(Ax 4b)* `= (A + A) • (A + Ā)` *(Ax 2b)* `= (A + A) • 1` *(Ax 4a)* `= A + A` *(Ax 3b)*.
     * *Demostración de `A • A = A` (Desempeño 3.2):* `A = A • 1` *(Ax 3b)* `= A • (A + Ā)` *(Ax 4a)* `= (A • A) + (A • Ā)` *(Ax 2a)* `= (A • A) + 0` *(Ax 4b)* `= A • A` *(Ax 3a)*.
  3. **T3 (Absorción):** Si `A` se opera con un paréntesis que ya contiene a `A` con la operación opuesta, la otra variable `B` se absorbe y desaparece.
     * *Demostración algebraica de `A + (A • B) = A` (Desempeño 3.2):* `A + (A • B) = (A • 1) + (A • B)` *(Ax 3b)* `= A • (1 + B)` *(Ax 2a)* `= A • (B + 1)` *(Ax 1a)* `= A • 1` *(T1a)* `= A` *(Ax 3b)*.
     * *Demostración algebraica de `A • (A + B) = A` (Desempeño 3.2):* `A • (A + B) = (A + 0) • (A + B)` *(Ax 3a)* `= A + (0 • B)` *(Ax 2b)* `= A + (B • 0)` *(Ax 1b)* `= A + 0` *(T1b)* `= A` *(Ax 3a)*.
     * *Identidades clásicas derivadas (Desempeño 6, pág. 5):* **`a-`** `A + Ā•B•C = (A + Ā)•(A + B•C) = 1•(A + B•C) = A + B•C` ; **`b-`** `A•B + Ā•B + A•B̄ = (A + B) • (Ā + B)` ; **`c-`** `A•B + Ā•C + B•C = A•B + Ā•C` *(teorema del consenso)*.
  4. **T4 (Asociatividad):** Permite agrupar o quitar paréntesis cuando se repite la misma operación.
  5. **T5 (Involución):** Dos barras de negación superpuestas sobre la misma expresión se cancelan (`A̿ = A`).
  6. **T6 (De Morgan):** Al partir una barra de negación larga sobre cada término, **cambia la operación central** (`+` pasa a `•`, y `•` pasa a `+`). Atención: `A̅+̅B̅ ≠ Ā + B̄` y `A̅•̅B̅ ≠ Ā • B̄`.

---

## CLASE 3 — Funciones Booleanas, Tablas de Verdad y Compuertas Lógicas

### 3.1 Función Booleana, Evaluación y Tabla de Verdad (`2ⁿ` Combinaciones)
* **📖 Definición textual / Enunciado:**
  > *"Una **función** es una relación entre dos variables, para la que se debe cumplir que una variable independiente se debe relacionar con una y solo una variable dependiente [ej. en funciones clásicas `f(x) = 2x + 3`, si `x = 1` vale `f(1) = 5` y si `x = 4` vale `f(4) = 11`]. En el Álgebra de Boole existen **funciones Booleanas**, que resultan de combinar un número de variables mediante las tres operaciones ya definidas. La gran diferencia con las funciones clásicas es que **las variables solo pueden tomar el valor `0` ó `1`, y la función podría ser solo `0` ó `1`**.*
  > *• **Ejemplos de evaluación (pág. 2):** Con una sola variable, `F(B) = B̄`: `F(0) = 1` y `F(1) = 0`. Con dos variables (4 combinaciones), `F(A,B) = A . B̄`: si `A = 0, B = 0` → `F(0,0) = 0 . 0̄ = 0 . 1 = 0`; si `A = 1, B = 0` → `F(1,0) = 1 . 0̄ = 1 . 1 = 1` (y pueden escribirse con tres, cuatro, cinco o más variables).*
  > *• **Tablas de verdad (pág. 3):** A los fines de conocer el resultado para todas las posibles combinaciones resulta mucho más práctico la confección de **Tablas de verdad**, que nos mostrarán todos los resultados. Se deberán colocar las variables que intervienen, una por columna y debajo de ellas todas las combinaciones de `0` y `1` posibles. **La cantidad de posibilidades será siempre `2ⁿ` donde `n` es la cantidad de variables** (`2² = 4` para 2 variables; `2³ = 8` para 3 variables). En columnas siguientes se irán completando los resultados parciales según las operaciones que vinculan a las variables, y la última columna indica el valor de la función para cada combinación de entrada.*
  > *• **Reglas recordatorias al pie de la tabla (pág. 3):** **1)** “Recuerde que en el producto si hay un `0` el resultado será `0`”; **2)** “Recuerde que el complemento es lo contrario”; **3)** “Y por último no olvide que en la suma si hay un `1` el resultado es `1`”.*
  > *• **Doble lectura de la tabla (pág. 3, ej. `F(A,B,C) = B . C + Ā`):** De izquierda a derecha vemos el resultado a partir de las entradas (ej. si `A=1, B=1, C=0`, la función toma el valor `0`); y **si lo miramos de derecha a izquierda**, vemos para qué entradas la función toma un valor dado (ej. la función es `1` si `A=0, B=0, C=0`, entre otras posibilidades)."*
* **💡 En simple:** Una **función Booleana** `F(A, B, C...)` toma entradas binarias (`0` ó `1`), las combina con suma (`+`), producto (`.`) y complemento (`Ā`), y devuelve un único valor binario (`0` ó `1`). Su **tabla de verdad** tiene exactamente **`2ⁿ` filas** para cubrir todas las entradas posibles, y puede leerse tanto de entradas a salida (evaluar) como de salida a entradas (base de la forma canónica).

### 3.2 Circuitos Lógicos, las 5 Compuertas Lógicas y los 3 Modos de Representación
* **📖 Definición textual / Enunciado:**
  > *"Existe otra manera de representar las funciones Booleanas, por medio de los **circuitos lógicos**, los que se realizan empleando las llamadas **“compuertas lógicas”**. Cada compuerta lógica es un símbolo que representa a una operación, hay tres que corresponden a las tres operaciones definidas y dos que corresponden al complemento de la suma y del producto. En casi todos los casos puede haber más de una entrada, pero **siempre habrá una sola salida**:*
  > *• **`F(A,B) = A + B` → Compuerta `OR`** (suma lógica; símbolo con entrada curva y salida en punta).*
  > *• **`F(A,B) = A • B` → Compuerta `AND`** (producto lógico; símbolo con entrada recta y salida semicircular en forma de D).*
  > *• **`F(A) = Ā` → Compuerta `NOT`** (complemento; triángulo con un círculo pequeño en la salida; tiene una sola entrada).*
  > *• **`F(A,B) = A̅+̅B̅` → Compuerta `NOR`** (complemento de la suma; símbolo `OR` con círculo pequeño en la salida).*
  > *• **`F(A,B) = A̅·̅B̅` → Compuerta `NAND`** (complemento del producto; símbolo `AND` con círculo pequeño en la salida).*
  > *• **Implementar una función (Desempeño 7, pág. 5):** “**Implementa con compuertas lógicas las siguientes funciones, que es lo mismo que decir realice el circuito lógico correspondiente**” (y a la inversa, en el Desempeño 8 se obtiene la expresión algebraica siguiendo las señales desde las entradas hasta la salida del circuito, como en `F(A,B,C) = Ā + B + B.C` de pág. 4).*
  > *• **Los tres modos de representación (pág. 4):** De esta manera hemos llegado a poder escribir o representar una función Booleana de **tres modos diferentes**: mediante su **expresión algebraica**, su **tabla de verdad** y su **circuito lógico**, pudiendo pasar de una a otra. Para poder escribir la expresión algebraica a partir de los resultados de la tabla de verdad, necesitamos ver un modo especial de escribir una función Booleana, que llamamos **forma canónica** de ella."*
* **💡 En simple:** **Implementar una función** significa dibujar su **circuito lógico** con compuertas. **OR**, **AND** y **NOT** ejecutan las 3 operaciones básicas, mientras que **NOR** y **NAND** equivalen a una OR o una AND seguida de una negación completa (barra continua sobre toda la operación). Como la **expresión algebraica**, la **tabla de verdad** y el **circuito lógico** representan la misma función, son totalmente interconvertibles; y al simplificar una función (Desempeño 9), la función original y la simplificada tienen **idéntica tabla de verdad**, pero el circuito simplificado usa **menos compuertas**.

---

## CLASE 4 — Forma Canónica y Simplificación de Funciones Booleanas

### 4.1 Forma Canónica, Término Canónico, Maxitérmino y Minitérmino (y Reconocimiento de Casos)
* **📖 Definición textual / Enunciado:**
  > *"Una función Booleana está escrita en **forma canónica**, cuando es una suma o un producto de términos canónicos."*
  > *"Un **término canónico** es una expresión que relaciona a todas las variables (ya sea directa o complementada) una sola vez mediante una sola operación. Es decir si hay tres variables en la función sería cualquier terna de ellas todas sumadas o todas multiplicadas."*
  > *"• Cuando todas las variables se relacionan con la operación suma, a ese término canónico se lo llama **Maxitérmino** (ej.: `X + Y + Z` ; `X̄ + Y + Z̄`).*
  > *• Si todas las variables se relacionan con la operación producto, a ese término canónico se lo llama **minitérmino** (ej.: `X̄ . Y . Z` ; `X . Ȳ . Z̄`).*
  > *Si volvemos a la definición de forma canónica, diremos que **una función está en forma canónica cuando es una suma de minitérminos o es un producto de Maxitérminos**.*
  > *• **Ejemplos oficiales de reconocimiento (págs. 2 y 3, y Desempeño 10):***
  >   *- **NO están en forma canónica:** `F(A,B) = Ā . B + A` (el segundo término no es minitérmino porque no están las dos variables multiplicadas); `F(A,B) = (A + B) . (A + Ā)` (el segundo factor no es maxitérmino porque una variable se repite y falta la otra); `F(X,Y,Z) = X.Z + Y.Z + X.Y` (falta una variable en cada término, debería haber 3 por cada minitérmino); `F(P,Q,R,S) = (P + Q) . (R + S)` (a cada factor le faltan dos de las cuatro variables).*
  >   *- **SÍ están en forma canónica:** `F(A,B) = A . B` (sí lo está, ya que es un minitérmino solo); `F(X,Y,Z) = (X + Y + Z) . (X̄ + Y + Z̄)` (producto de dos maxitérminos); `F(X,Y,Z) = X̄YZ + XȲZ + XYZ̄ + XYZ` (suma de 4 minitérminos); `F(X,Y) = X̄ + Ȳ` (un maxitérmino solo); `F(A,B,C) = ABC + A̅B̅C + B̅AC + CBĀ` (suma de 4 minitérminos, aunque las variables dentro de un término estén en distinto orden).*
  > *Toda función, aunque no esté escrita en la forma canónica, puede ser llevada mediante procedimientos algebraicos o por medio de tablas de verdad, a dicha forma. **Debe quedar claro que toda función tiene su forma canónica.**"*
* **💡 En simple:** Para que una función de `n` variables esté en **forma canónica**, cada uno de sus términos (o factores) debe contener **las `n` variables completas**, **sin repetir ninguna** y **con una sola operación interna** (un único minitérmino o un único maxitérmino también cuenta como forma canónica, y el orden en que aparezcan las letras dentro de cada término no altera que sea canónico por el Axioma 1 conmutativo).

### 4.2 Obtención de la Forma Canónica por Tabla de Verdad (`IIM` / `∏M` y `∑m`) y Algebraicamente
* **📖 Definición textual / Enunciado:**
  > *"Se construye una Tabla de Verdad de la función dada y se observa la última columna que es la de resultado de la función: **Las filas donde la función da ‘0’ conformarán la expresión productoria de sumas (`PS`) y las filas donde la función toma valor ‘1’ conformarán la expresión sumatoria de productos (`SP`)**. Para ubicarnos mejor en la tabla, utilizamos el número de **secuencia decimal (`Sec. Dec.`)** en el extremo izquierdo de la tabla, que coincide con las combinaciones binarias de las variables.*
  > *En síntesis:*
  > *• **1| Las sumas canónicas** son aquellas combinaciones para las cuales la **función vale `0`** y conforman la **productoria de maxitérminos (`IIM` o `∏M`)**. **NOTA: Las variables que valen ‘1’ se leen negadas y las que valen ‘0’, directas.***
  > *• **2| Los productos canónicos** son aquellas combinaciones para las cuales la **función vale `1`** y conforman la **sumatoria de minitérminos (`∑m`)**. **NOTA: Las variables que valen ‘1’ se leen directas y las que valen ‘0’, negadas.***
  > *Ejemplo para `F(A,B,C) = A + B • C`: `F(A,B,C) = IIM(0,1,2) = (A+B+C) • (A+B+C̄) • (A+B̄+C)` y `F(A,B,C) = ∑m(3,4,5,6,7) = ĀBC + AB̄C̄ + AB̄C + ABC̄ + ABC`. Estas tres expresiones tienen la misma tabla de verdad. **Observe que las formas canónicas por lo general, son mucho más extensas que la función original.**"*
* **💡 En simple:**
  1. **Desde la Tabla de Verdad:** Mirás la última columna (`F`). Para armar la **Suma de Productos (`∑m`, minitérminos)** tomás las filas donde **`F = 1`** (leyendo `1 → directa` y `0 → negada`). Para armar el **Producto de Sumas (`∏M` / `IIM`, Maxitérminos)** tomás las filas donde **`F = 0`** (leyendo al revés: `0 → directa` y `1 → negada`).
  2. **Por Procedimiento Algebraico (Desempeño 12a):**
     * **Para llevar a suma de minitérminos (`SP`):** Si a un término producto le falta la variable `A` (ej. `B • C`), se multiplica por el neutro `1` (**Ax 3b**), se reemplaza `1 = A + Ā` (**Ax 4a**), se distribuye `(A + Ā) • B • C = A•B•C + Ā•B•C` (**Ax 2a**) y se eliminan los minitérminos repetidos por **Idempotencia (T2a)**.
     * **Para llevar a producto de maxitérminos (`PS`):** Si a un factor suma le falta la variable `C` (ej. `A + B`), se le suma el neutro `0` (**Ax 3a**), se reemplaza `0 = C • C̄` (**Ax 4b**), se distribuye la suma sobre el producto `(A + B) + (C • C̄) = (A + B + C) • (A + B + C̄)` (**Ax 2b**) y se eliminan los maxitérminos repetidos por **Idempotencia (T2b)**.

### 4.3 Síntesis de Funciones y Simplificación de Funciones Booleanas
* **📖 Definición textual / Enunciado:**
  > *"• **¿Cómo encontrar una función que logre los resultados que queremos? (pág. 5):** Esta forma de escribir la función utilizando la tabla de verdad nos permitirá realizar una de las principales aplicaciones, que consiste en encontrar una función que logre llegar a los resultados que queremos (si sabemos qué resultados deseamos a la salida para cada combinación de entrada, escribimos la forma canónica tomando los `1` como suma de productos, o los `0` como producto de sumas). Ejemplo en pág. 5: para dos variables `(A,B)` con salidas deseadas `F(0,0)=1, F(0,1)=0, F(1,0)=1, F(1,1)=1`, tomando los tres `1` obtenemos `F(A,B) = Ā.B̄ + A.B̄ + A.B`.*
  > *• **Eficiencia del circuito y Simplificación (pág. 6):** Mientras menos elementos (compuertas lógicas) haya en el circuito, más económico será y más rápido llegaremos al resultado, es decir, **sería más eficiente el circuito**. Como las compuertas representan las operaciones entre las variables, si queremos que haya menos compuertas en el circuito, deberá haber menos operaciones en la función.*
  > ***Simplificar las funciones** significa buscar escribir las mismas de una manera más reducida, mediante la utilización de los axiomas y teoremas enunciados como propiedades. Siempre que cambie el formato de una expresión, ese cambio debe estar justificado por alguna de las propiedades enunciadas, ¡NO Vale Inventar Nuevas! (En el ejemplo de pág. 6: `F(A,B) = Ā.B̄ + A.B̄ + A.B = B̄.(Ā + A) + A.B` `[Ax 2]` `= B̄.1 + A.B` `[Ax 4]` `= B̄ + A.B` `[Ax 3]`, o aplicando nuevamente `Ax 2, Ax 4, Ax 3` se reduce a `B̄ + A`)."*
* **💡 En simple:** Las formas canónicas permiten **sintetizar (diseñar)** cualquier función a partir de una tabla de resultados deseados, pero suelen ser muy extensas; **simplificar esa función** mediante axiomas y teoremas reduce la cantidad de operaciones lógicas manteniendo **exactamente la misma tabla de verdad**, lo que permite construir un circuito lógico con **menos compuertas (más económico, rápido y eficiente)**.

---

# UNIDAD 2: MATRICES Y DETERMINANTES (CLASES 5 A 8)

## CLASE 5 — Concepto de Matriz, Notación, Vectores, Clasificación e Igualdad

### 5.1 Esquema de la Unidad 2, Definición Formal de Matriz, Orden (`n × m`), Notación General y Subíndices (`aᵢⱼ`)
* **📖 Definición textual / Enunciado:**
  > *"• **Esquema de la Unidad 2 (pág. 2):** En esta unidad vas a distinguir dos secciones: **1) LA MATRIZ:** definición, terminología, operaciones matemáticas básicas (**adición, sustracción, producto por un número y multiplicación**) y **operaciones elementales** (características de las matrices, para llegar a la **matriz canónica**). **2) DETERMINANTES:** de las matrices cuadradas, su concepto, métodos de cálculo y propiedades.*
  > *• **Organización de información y Definición de Matriz (págs. 3 a 8):** Hay infinidad de situaciones donde es conveniente arreglar la información numérica en filas y columnas (notas de alumnos, **los puntos del monitor de una computadora**, cotizaciones de la Bolsa, ubicación de personas en un espectáculo, gastos por rubro, casos clínicos por región, etc.). Al ordenar los elementos, la forma puede variar según lo que se elija como “fila” o como “columna” de la matriz, pero la información representada es la misma.*
  > *Esta disposición rectangular de números se denomina **MATRIZ**. Definiremos **MATRIZ `n x m`** a un conjunto de `n.m` números dispuestos en `n` filas y `m` columnas. Diremos que **`n x m` es el ORDEN de la matriz** (se lee “ene por eme”). (Desempeño 19: en una matriz `1x1` hay `1` elemento; en `3x5` hay `15`; en `m x n` hay `m.n`; y en una cuadrada `r x r` hay `r²` elementos).*
  > *A los elementos de las matrices los pondremos entre corchetes (pueden ser paréntesis o doble barra) y las designaremos con letras mayúsculas. En forma general a una matriz `n x m` la escribiremos `Aₙₓₘ = [aᵢⱼ]`, donde los subíndices nos indican la posición del elemento: en `Aₙₓₘ`, **`n` es la cantidad de filas** y **`m` es la cantidad de columnas**; y en el elemento genérico **`aᵢⱼ`**, **`i` es el N° de fila** y **`j` es el N° de columna**. (Si se pide un subíndice fuera del orden de la matriz, ej. `a₁₄` en una matriz `3x3`, **ese elemento no existe, no pertenece a la matriz**)."*
* **💡 En simple:** Una matriz ordena datos numéricos en una tabla rectangular de **`n` filas horizontales** por **`m` columnas verticales**. El par `n × m` (sin multiplicar) indica el **orden (tamaño)** de la matriz, mientras que el producto `n . m` indica **cuántos elementos tiene en total**. Dentro de la matriz `A`, cada elemento `aᵢⱼ` lleva dos coordenadas: primero su fila `i` (`1 ≤ i ≤ n`) y segundo su columna `j` (`1 ≤ j ≤ m`).

### 5.2 Vectores (Fila y Columna) y Matriz como Conjunto Ordenado de Vectores
* **📖 Definición textual / Enunciado:**
  > *"Cuando una matriz tiene 1 columna o 1 fila se la llama **VECTOR**. Es decir que un vector es una matriz de orden `n x 1` ó `1 x n`. En el caso de tener una columna (`n x 1`) se lo llama **vector columna**. En caso de tener una fila (`1 x n`) se llama **vector fila**.*
  > *Suele ser útil ver a las matrices como un conjunto de vectores. Esto da lugar a **otra definición de matriz**:*
  > *• **Una matriz es un conjunto ordenado de vectores filas**, ó*
  > *• **Una matriz es un conjunto ordenado de vectores columnas**.*
  > *La ventaja de visualizar de esta manera a las matrices es que en cada fila o columna hay reunida información del mismo tipo."*
* **💡 En simple:** Una matriz de una sola fila (`1 × n`) es un **vector fila** y una de una sola columna (`n × 1`) es un **vector columna**. Pensar una matriz `n × m` como una lista **ordenada** de `n` vectores fila (o de `m` vectores columna) permite agrupar datos del mismo rubro en cada línea y fundamenta las operaciones por filas y el producto matricial.

### 5.3 Clasificación de Matrices Especiales (Según su Forma y sus Elementos)
* **📖 Definición textual / Enunciado:**
  > *"Es posible realizar una clasificación de las matrices según su forma y según los elementos que tengan. Las matrices, en general son **RECTANGULARES**, pero según cuáles sean sus elementos o cantidad de filas y columnas reciben un nombre en particular:*
  > *• **MATRIZ NULA (`0`):** Una matriz cuyos elementos son todos ceros se llama matriz nula y se simboliza por `0`. **Una matriz nula no necesita ser cuadrada** (puede ser también una matriz fila o columna). En símbolos: `Aₙₓₘ es nula ⇔ aᵢⱼ = 0 para todo i,j`.*
  > *• **MATRIZ CUADRADA:** Aquella que **tiene el mismo número de filas que de columnas**. Basta decir que es una matriz cuadrada de **orden `n`**. Sólo para matrices cuadradas distinguimos: los elementos de la **“diagonal principal”** (desde el ángulo superior izquierdo al inferior derecho, `i = j`) y los de la **“diagonal secundaria”** (desde el ángulo inferior izquierdo al superior derecho).*
  > *• **MATRIZ DIAGONAL:** Es una **matriz cuadrada** en la que los elementos que **NO pertenecen a la diagonal principal son nulos** (iguales a `0`). (En la diagonal principal puede haber cualquier número, incluso algún `0`, como en `C = diag(3, -5, 0, 7)` del Desempeño 20).*
  > *• **MATRIZ ESCALAR:** Es una **matriz diagonal**, con **todos sus elementos de la diagonal, iguales**.*
  > *• **MATRIZ IDENTIDAD O MATRIZ UNIDAD (`Iₙ`):** Es una **matriz cuadrada** que tiene los **elementos de la diagonal principal iguales a uno (`1`) y los restantes son ceros (`0`)**. En símbolos: `Aₙₓₙ es identidad ⇔ aᵢⱼ = 1 cuando i = j ; aᵢⱼ = 0 cuando i ≠ j`. **En cada orden matricial existe una matriz unidad** (ej. `I₂`, `I₃`, `I₄`).*
  > *• **MATRIZ TRIANGULAR:** Es una **matriz cuadrada** que tiene nulos todos los elementos que están a un mismo lado de la diagonal principal:*
  >   *- **Triangular Superior:** Si los elementos que están **por debajo de la diagonal principal son todos nulos** (`aᵢⱼ = 0 para todo i > j`, impreso `aᵢⱼ > j`).*
  >   *- **Triangular Inferior:** Si los elementos que están **por encima de la diagonal principal son todos nulos** (`aᵢⱼ = 0 para todo i < j`).*
  > *• **MATRIZ CANÓNICA O ESCALONADA:** Matriz (no necesariamente cuadrada) cuyos ceros iniciales por fila forman escalones."*
* **💡 En simple:** Hay una jerarquía clave para preguntas teóricas y Verdadero/Falso:
  1. **No necesitan ser cuadradas:** Rectangular, Vector fila, Vector columna, **Matriz Nula (`0`)** y **Matriz Escalonada / Canónica**.
  2. **Deben ser obligatoriamente cuadradas (`n × n`):** Toda matriz que hable de **diagonales** (principal o secundaria): **Cuadrada** ⊃ **Triangular** (superior o inferior) ⊃ **Diagonal** (ceros fuera de la diagonal principal; en la diagonal puede haber cualquier número, incluso ceros) ⊃ **Escalar** (diagonal principal con el mismo número repetido) ⊃ **Identidad o Unidad `Iₙ`** (diagonal principal toda de `1`).

### 5.4 Igualdad de Matrices y Elementos Correspondientes
* **📖 Definición textual / Enunciado:**
  > *"Dada dos matrices A y B (no necesariamente cuadradas), estas serán **iguales (`A = B`)** si:*
  > *1| **Son del mismo orden**.*
  > *2| **Si los elementos correspondientes (los que ocupan el mismo lugar) son iguales**.*
  > ***Elementos correspondientes** en matrices son aquellos que tienen **igual par de subíndices `ij`** (`a₁₁` con `b₁₁`, `a₁₂` con `b₁₂`, etc.; **no son correspondientes** por ejemplo `a₂₁` y `b₁₂`, `a₃₂` y `b₂₃`, `aₘₙ` y `bₙₘ`). En símbolos: `A = B ⇔ aᵢⱼ = bᵢⱼ para todo i,j`."*
* **💡 En simple:** Dos matrices son iguales si y solo si tienen exactamente el **mismo tamaño (`n × m`)** y en cada coordenada `(i, j)` tienen el mismo número.

---

## CLASE 6 — Operaciones con Matrices y sus Propiedades

### 6.1 Adición, Sustracción y Multiplicación de una Matriz por un Número
* **📖 Definición textual / Enunciado:**
  > *• **Adición y Sustracción:** "Para sumar dos matrices (no necesariamente cuadradas), éstas **deben ser del mismo orden**, si esto es así se suman los elementos correspondientes: `(A + B)ₘₓₙ = [aᵢⱼ + bᵢⱼ]`. **La matriz resultante tiene el mismo orden que las matrices sumadas.** En la **sustracción** se procede de igual forma que en la adición, la única diferencia es que los elementos se restan (la resta no es conmutativa: si restamos en diferente orden da distinto resultado)."*
  > *• **Propiedades de la suma de matrices:** **1| Conmutativa:** `A + B = B + A` ; **2| Asociativa:** `(A + B) + C = A + (B + C)` ; **3| Existencia de elemento neutro aditivo:** `A + 0 = A` (donde `0` es la **matriz nula**; se llama **elemento neutro** para una operación a un elemento que al operar con él no cambia al otro) ; **4| Existencia de elemento inverso aditivo:** `A + (-A) = 0` (donde `-A` es la **matriz opuesta**, todos sus elementos son opuestos; se llama **elemento inverso** para una operación a un elemento que al operar con él nos da el neutro de la operación).*
  > *• **Producto de una matriz por un número (`kA`):** "Será igual a una nueva matriz del **mismo orden** que la anterior, cuyos elementos son los de la matriz original multiplicados por el número: `kA = [k . aᵢⱼ]`." Cumple **4 propiedades** (**convención notacional:** *"Recordemos que las letras griegas (`α, β, δ`) representan números y las de nuestro alfabeto representan matrices"*): **1| Distributiva respecto a la suma de números:** `(α + β) . A = α . A + β . A` ; **2| Distributiva respecto a la suma de matrices:** `β . (A + B) = β . A + β . B` ; **3| Asociativa respecto a los números:** `(α . β) . A = α . (β . A)` ; **4| Existencia del elemento neutro:** `1 . A = A`. Estas propiedades sirven para facilitar cálculos, predecir resultados y modelar variaciones porcentuales (ej. Situación 6: elevar un 20% la producción es `1,20 . A` y disminuirla un 10% es `0,90 . B`)."*
* **💡 En simple:** Sumar o restar exige que ambas matrices tengan el **mismo orden `m × n`** y conserva ese orden (siendo la **matriz nula `0`** el neutro aditivo y la **matriz opuesta `-A`** el inverso aditivo). En cambio, multiplicar una matriz por un escalar `k` **no pide ninguna condición** ni para la matriz ni para el escalar, y multiplica todos los casilleros por `k`.

### 6.2 Los 4 Pasos para Resolver un Problema, Producto Escalar, Multiplicación de Matrices y Matrices Conformables
* **📖 Definición textual / Enunciado:**
  > *• **Para resolver un problema, ten en cuenta lo siguiente (pág. 6):** **1| ENTENDER:** Leer varias veces el problema y tener en claro qué se quiere averiguar. **2| PLANIFICAR:** Analizar cómo se puede resolver el problema; qué operación es necesario aplicar. **3| RESOLVER:** Realizar las operaciones necesarias para encontrar los resultados. **4| REVISAR:** Comprobar el resultado, tratar de analizar si es correcto o no, si es acorde al problema planteado.*
  > *• **Producto escalar:** "Se realiza entre un **vector fila y un vector columna, con igual cantidad de elementos**, multiplicando los elementos correspondientes y sumando esos productos. **Observaciones:** **1|** El producto escalar entre dos vectores **siempre da por resultado un número, no una matriz**. **2|** Sólo puede realizarse entre vectores que tengan la **misma cantidad de elementos**. **3|** Siempre se realiza entre un **vector fila y otro columna, nunca al revés**."*
  > *• **Producto entre matrices y Matrices Conformables:** "Definimos el **producto entre matrices** como la matriz que se obtiene al realizar todos los productos escalares posibles entre las filas de la primera matriz y las columnas de la segunda.*
  > ***Para que dos matrices puedan multiplicarse es necesario que el número de columnas de la primera sea igual al número de filas de la segunda. A matrices con esta característica se las llama CONFORMABLES. El resultado es la nueva matriz de orden igual al número de filas de la primera por el número de columnas de la segunda y cuyo elemento “ij” ésimo es el producto escalar del vector fila `i` de la primera matriz por el vector columna `j` de la segunda matriz**: `Aₘₓₙ . Bₙₓₚ = Cₘₓₚ`." (Desempeño 40f: **¿Es posible multiplicar dos matrices filas?** No, para vectores fila `1 × n` con `n > 1`, porque las columnas de la primera `n` no coinciden con la única fila `1` de la segunda).*
* **💡 En simple:** Para poder multiplicar `Aₘₓₙ . Bₙₓₚ`, los dos números internos deben coincidir (**columnas de la 1.ª = filas de la 2.ª = `n`**; eso significa ser **conformables**), y los dos números externos dan el tamaño del resultado (**`m × p`**). Cada elemento `cᵢⱼ` del resultado es el producto escalar de la **fila `i` de `A`** por la **columna `j` de `B`**.

### 6.3 Propiedades de la Multiplicación de Matrices (Permutables, No Cancelativa, Neutro e Inversa)
* **📖 Definición textual / Enunciado:**
  > *"Propiedades del producto matricial (atípicas respecto a los números reales):*
  > *• **1| Propiedad asociativa:** `(Aₙₓₚ . Bₚₓₘ) . Cₘₓₖ = Aₙₓₚ . (Bₚₓₘ . Cₘₓₖ)`.*
  > *• **2| Propiedad conmutativa (NO se cumple en general):** Si el producto `A.B` existe, el producto `B.A` no necesariamente existe. Además, si existiera no necesariamente sería igual a `A.B`. **Si dos matrices A y B tienen la particularidad de que `A . B = B . A` se dice que son PERMUTABLES.***
  > *• **3| Propiedad distributiva del producto respecto a la suma (a derecha):** `Aₙₓₘ . (Bₘₓₚ + Cₘₓₚ) = Aₙₓₘ . Bₘₓₚ + Aₙₓₘ . Cₘₓₚ`.*
  > *• **4| Propiedad cancelativa (NO se cumple):** **Esta propiedad no se puede aplicar en el álgebra de matrices. Implica que si `A . B = A . C`, NO podemos cancelar A y asegurar que `B = C`.** ¿Por qué? Restando `A.C` y aplicando distributiva queda `A(B - C) = 0`; en el álgebra clásica algún factor sería cero, **pero con matrices podemos multiplicar dos matrices no nulas y obtener como resultado la matriz nula** (ej. pág. 11: `[[-1, 3], [0, 0]] ∙ [[0, 6], [0, 2]] = [[0, 0], [0, 0]]`; y Desempeño 37, pág. 13: `[[2, 4], [4, 8]] ∙ [[2, -4], [-1, 2]] = [[0, 0], [0, 0]] = [[0, 0], [0, 0]] ∙ [[2, -4], [-1, 2]]` a pesar de que `[[2, 4], [4, 8]] ≠ [[0, 0], [0, 0]]`).*
  > *• **5| Elemento neutro multiplicativo:** **`I . A = A . I = A`**. La **matriz identidad** es el elemento neutro en la multiplicación de matrices.*
  > *• **6| Elemento inverso multiplicativo (`A⁻¹`):** **`A . A⁻¹ = A⁻¹ . A = I`**. Sólo existe para matrices cuadradas, y no en todos los casos (ej. pág. 11: para `A = [[3, 2], [4, 3]]`, su inversa es `A⁻¹ = [[3, -2], [-4, 3]]` pues `A . A⁻¹ = [[1, 0], [0, 1]] = I₂`)."*
* **💡 En simple:** Tres puntos críticos para el oral: **1)** El producto de matrices **no es conmutativo** (solo cuando `A.B = B.A` se llaman **permutables**); **2)** **No vale la propiedad cancelativa** porque existen divisores de cero (dos matrices **no nulas** multiplicadas pueden dar la **matriz nula `0`**); y **3)** El neutro multiplicativo es la **Identidad `I`** y el inverso multiplicativo es la **Inversa `A⁻¹`**.

---

## CLASE 7 — Matriz Canónica por Filas, Rango y Operaciones Elementales

### 7.1 Matriz Canónica por Filas, Elemento Conductor, Rango `ρ(matriz)` y Casos Particulares
* **📖 Definición textual / Enunciado:**
  > *"La **matriz canónica** es una matriz rectangular que tiene las siguientes características:*
  > *1| El primer elemento no nulo de las filas, si lo hubiera, debe ser el `1`, denominado **elemento conductor**.*
  > *2| En la columna a la que pertenece dicho `1`, los elementos restantes son cero.*
  > *3| Los elementos conductores están dispuestos en **escalera**, o sea que cada fila tiene mayor número de ceros que la anterior adelante del elemento conductor; y las **filas nulas**, si las hubiera, están **últimas**.*
  > *4| El número de filas no nulas se denomina **rango de la matriz (`ρ(matriz)`)**.*
  > *• **Casos particulares y errores frecuentes (Desempeño 41, págs. 3 y 10):** La **matriz nula** (`C = [[0, 0], [0, 0]]`) **sí es canónica** (es un caso particular que no contradice ninguna condición, porque la condición 1 dice “si lo hubiera”). En cambio, NO son canónicas: `B = [[1, 2], [0, 1]]` (el `2` debería ser `0` porque en su columna hay un elemento conductor), `D` con una fila nula en la fila 2 antes de una fila no nula en la fila 3 (viola la condición 3), o `F` cuyo primer elemento no nulo de la segunda fila es `4` en vez de `1` (viola la condición 1)."*
* **💡 En simple:** Toda matriz puede llevarse a su **forma canónica por filas**, que exige: **1)** primer número no nulo de cada fila igual a **`1` (elemento conductor)**, **2)** el resto de la columna de cada conductor llena de **`0`**, y **3)** conductores **en escalera** hacia abajo a la derecha con las filas nulas al final. La cantidad de filas no nulas de esa canónica es el **rango `ρ(A)`**.

### 7.2 Operaciones Elementales por Filas, Equivalencia (`A ~ B`), Columna de Control y Preguntas Teóricas
* **📖 Definición textual / Enunciado:**
  > *"Las **operaciones elementales** son tres, y se aplican tanto en las filas como a columnas, pero debido al interés que presenta este tema para nosotros, **se aplicarán las operaciones elementales solamente a las filas de la matriz**:*
  > *• **1º Operación:** Permutar filas entre sí. Se simboliza con **`Hᵢⱼ` (o `Hᵢ,ⱼ`)**, lo que indica intercambiar la fila `i` con la fila `j`.*
  > *• **2º Operación:** Multiplicar una fila por una constante distinta de cero. Se simboliza con **`Hᵢ(k)`**, lo que indica multiplicar la fila `i` por la constante `k` (`k ≠ 0`).*
  > *• **3º Operación:** Sumar a una fila otra fila previamente multiplicada por una constante distinta de cero. Se simboliza con **`Hᵢⱼ(k)` (o `Hᵢ,ⱼ(k)`)**, lo que indica sumar a la fila `i`, la fila `j` multiplicada por `k` (`i + k . j`, con `k ≠ 0`).*
  > *La matriz que se obtiene luego de aplicar las operaciones se dice que es **equivalente** a la primera (se simboliza con **`~`**, `A ~ B`; si bien no son iguales, son equivalentes y nos servirá para trabajar con sistemas de ecuaciones).*
  > *• **Procedimiento paso a paso (págs. 2, 6, 7 y 9):** Primero busca el elemento conductor de la fila (`1`) —multiplicando la fila por el recíproco `1/a` (ej. para `-3` se multiplica por `-1/3`, no por `3` ni `-3`) o bien **intercambiando filas (`Hᵢ,ⱼ`) para evitar fracciones**— e inmediatamente después anula su columna sumando a cada fila `i` la fila `j` del elemento conductor multiplicada por el **opuesto** del número que se quiere convertir en `0`; segundo pasa al elemento conductor de otra fila y anula su columna, y así sucesivamente (se pueden trabajar dos operaciones simultáneas en el mismo paso siempre y cuando no afecten a la misma fila).*
  > *• **Columna de control (pág. 8):** Se agrega una columna más a la matriz dada cuyos elementos **se obtienen sumando los elementos de cada fila de la matriz original**. A esta columna también se le aplican las operaciones elementales como si fuese una columna más, y se debe controlar en cada paso que sus elementos sigan siendo la suma de los elementos de la fila ahora transformada (si no coincide, se revisa solo ese paso).*
  > *• **Preguntas teóricas del Desempeño 46 (pág. 10):***
  >   *- **`b-` ¿La matriz canónica de una matriz de orden `3x4` puede ser la matriz identidad?** **No**, porque la matriz identidad es cuadrada (`n × n`) y la canónica de una matriz `3 × 4` mantiene el orden `3 × 4`.*
  >   *- **`c-` ¿La matriz canónica de una matriz cuadrada es siempre una matriz identidad?** **No siempre** ("cuidado, no en todos los casos pasa esto", pág. 7): solo da la identidad cuando ninguna fila se anula (`ρ(A) = n`).*
  >   *- **`d-` ¿La matriz canónica obtenida depende de qué operación elemental se aplique en cada paso?** **No**, la matriz canónica equivalente a una matriz dada es única aunque existan distintos caminos de operaciones para llegar a ella."*
* **💡 En simple:** Para transformar `A` en su única canónica equivalente (`A ~ B`), en cada columna primero se logra el **`1` conductor** (con `Hᵢ(1/a)` o permutando con `Hᵢ,ⱼ` para ahorrar fracciones) y enseguida se hacen **`0`** los demás elementos de esa columna aplicando `Hᵢ,ⱼ(k)`. La **columna de control** permite detectar al instante cualquier error de cuentas en ese paso.

---

## CLASE 8 — Determinantes, Matriz Inversa e Integración de la Unidad 2

### 8.1 Concepto de Determinante (`|A|`), Orden 2 y Orden 3 (Regla de Sarrus)
* **📖 Definición textual / Enunciado:**
  > *"En la clase de hoy solo trabajaremos con **matrices cuadradas**, ya que los conceptos de **determinante e inversa de una matriz se definen para ellas solamente**. El determinante nos permitirá decir si una matriz tiene o no inversa, y en la unidad siguiente saber si los sistemas de ecuaciones cuadrados tienen solución única.*
  > *Se llama **DETERMINANTE** de una matriz cuadrada de orden `n` **al número** que se obtiene al sumar algebraicamente* (*suma algebraica indica adición y/o sustracción*) todos los productos posibles entre `n` elementos de la matriz que pertenezcan a distinta fila y columna.*
  > ***Observaciones:** **1)** El determinante **sólo se calcula a matrices cuadradas**. **2)** El determinante **es un número**, no debe confundirse con la matriz (que es un conjunto de números). **3)** Se simboliza con barras **`|A|`** y se llama determinante de enésimo orden.*
  > *• **Método Particular A — Orden 2:** Se calcula multiplicando entre sí los elementos de la diagonal principal, y restándole el producto de los elementos de la diagonal secundaria: **`|A| = a₁₁ . a₂₂ - a₁₂ . a₂₁`**.*
  > *• **Método Particular B — Orden 3 (Regla de Sarrus, sólo para orden 3):** `|A| = (a₁₁.a₂₂.a₃₃ + a₂₁.a₃₂.a₁₃ + a₃₁.a₁₂.a₂₃) - (a₁₃.a₂₂.a₃₁ + a₂₃.a₃₂.a₁₁ + a₃₃.a₁₂.a₂₁)`. Tiene dos formas: **1)** repitiendo las dos primeras filas debajo de la tercera y restando a los 3 productos de la diagonal principal y sus paralelas los 3 productos de la diagonal secundaria y sus paralelas; o **2)** sumando la diagonal principal y los productos de cada paralela por su vértice opuesto, y restando la diagonal secundaria y los productos de cada paralela por su vértice opuesto."*
* **💡 En simple:** El **determinante `|A|`** solo existe para **matrices cuadradas** (si una matriz es rectangular, como `5 × 6` o `4 × 5` en el Desempeño 51a y 51c, **su determinante no existe**) y su resultado es siempre **un único número** que no depende del método utilizado para calcularlo. Para orden `2` es producto cruzado (`diagonal principal − diagonal secundaria`), y para orden `3` se usa la **Regla de Sarrus**.

### 8.2 Las 6 Propiedades de los Determinantes, Seguimiento de Operaciones y Matriz Regular
* **📖 Definición textual / Enunciado:**
  > ***Bloque 1 — Referidas a las operaciones elementales:***
  > *• **1º PROPIEDAD:** “Si se intercambian entre sí, dos filas, el determinante cambia de signo pero no de valor absoluto”. En símbolos: **`Si A ~ B por Hᵢ,ⱼ → |A| = - |B|`**.*
  > *• **2º PROPIEDAD:** “Si se multiplican los elementos de una fila por un número distinto de cero, el determinante queda multiplicado por ese número”. En símbolos: **`Si A ~ B por Hᵢ(k) → |B| = k . |A|`**.*
  > *• **3º PROPIEDAD (la más importante, que permite abreviar considerablemente el cálculo):** “Si a una fila de una matriz se le suma otra previamente multiplicada por una constante distinta de cero, el determinante no varía”. En símbolos: **`Si A ~ B por Hᵢ,ⱼ(k) → |A| = |B|`**.*
  >
  > ***Bloque 2 — Cuando un determinante vale cero:***
  > *• **4º PROPIEDAD:** “Si todos los elementos de una línea (fila o columna) son nulos, el determinante de la matriz es nulo”.*
  > *• **5º PROPIEDAD:** “Si una matriz tiene dos líneas paralelas iguales, su determinante es nulo”.*
  > *• **6º PROPIEDAD:** “Si dos líneas paralelas son proporcionales*, el determinante es nulo” (*Dos líneas son proporcionales cuando una de ellas es la otra multiplicada por un cierto número).*
  >
  > *• **MATRIZ REGULAR O NO SINGULAR:** “Si una matriz tiene el determinante no nulo (`|A| ≠ 0`) se dice que la matriz es **REGULAR o NO SINGULAR**”.*
  > *• **Aplicación encadenada de las propiedades 1, 2 y 3 (Desempeños 52 y 53, págs. 13 y 15):** Si `A ~ B` a través de `H₂,₃ ⇒ H₁(3) ⇒ H₃(2) ⇒ H₃,₁ ⇒ H₃,₂(6) ⇒ H₂,₃(5)`, las dos permutaciones (`H₂,₃` y `H₃,₁`) cambian el signo dos veces `(-1).(-1) = +1`, las dos multiplicaciones de fila (`H₁(3)` y `H₃(2)`) multiplican el determinante por `3 . 2 = 6`, y las dos sumas de filas (`H₃,₂(6)` y `H₂,₃(5)`) no lo alteran, por lo que **`|B| = 6 . |A|`**: si `|B| = -18 ⇒ |A| = -18 / 6 = -3` (Desempeño 52), y si `|A| = 4 ⇒ |B| = 6 . 4 = 24` (Desempeño 53).*
  > *• **Determinante de la Matriz Identidad y de matrices diagonales/triangulares (Desempeño 51d y 56g):** El determinante de una matriz diagonal o triangular es el producto de los elementos de su diagonal principal (ej. para `D = diag(2, 2, 1)` es `|D| = 4`), y **el determinante de la matriz identidad es siempre `|I| = 1`**."*
* **💡 En simple:** Al aplicar operaciones elementales de `A` a `B`, permutar filas (`Hᵢ,ⱼ`) cambia el signo del determinante, multiplicar una fila por `k` (`Hᵢ(k)`) multiplica al determinante por `k` (luego `|A| = |B| / k`), y sumar a una fila otra multiplicada por `k` (`Hᵢ,ⱼ(k)`) **deja el determinante intacto**. Además, si hay una línea de ceros, dos líneas paralelas iguales o dos proporcionales, **`|A| = 0` sin hacer cuentas**. Si **`|A| ≠ 0`**, la matriz es **Regular**.

### 8.3 Método General (Regla de Chío) y Matriz Inversa (`A⁻¹`) por Gauss-Jordan
* **📖 Definición textual / Enunciado:**
  > *• **Regla de Chio (Método general para cualquier orden `n`, inclusive orden 2, 3 o superior como orden 6):** Consta de tres pasos:*
  >   ***1er|*** *Aplicamos operaciones elementales en la matriz hasta lograr que una columna (cualquiera) tenga nulos todos sus elementos excepto uno (`aᵢⱼ`).*
  >   ***2do|*** *Realizamos la multiplicación de tres factores: **1)** el elemento no nulo `aᵢⱼ` de la columna elegida, **2)** el factor de posición **`(-1)ⁱ⁺ʲ`** (donde `i,j` corresponden a la fila y columna de ese elemento), y **3)** el **determinante de orden `n - 1`** de la matriz que surge al sacar la fila `i` y la columna `j` del elemento elegido.*
  >   ***3er|*** *Aplicamos las propiedades correspondientes (1, 2 o 3) según las operaciones usadas para lograr los ceros, si es necesario.*
  > *• **Matriz Inversa (`A⁻¹`):** Las únicas matrices que pueden tener inversa son las matrices cuadradas, y **UNA MATRIZ TIENE INVERSA SI ES REGULAR (`|A| ≠ 0`)** (si `|A| = 0` la inversa no existe y no se continúa el ejercicio). **Cálculo por operaciones elementales (o método de Gauss-Jordan)** [nota pág. 2: también puede calcularse mediante la matriz adjunta]: Con la matriz cuadrada `A` y la matriz identidad `I` de orden adecuado formamos la matriz rectangular **`[ A : I ]`**, y le aplicamos operaciones elementales hasta obtener la matriz canónica **`[ I : A⁻¹ ]`**: a la izquierda queda la Identidad y a la derecha la inversa buscada `A⁻¹`. Se verifica comprobando que **`A . A⁻¹ = I`**."*
* **💡 En simple:** La **Regla de Chío** sirve para cualquier orden (y para órdenes mayores como orden 4, 5 o 6 se aplica sucesivamente bajando un grado por vez hasta llegar a orden 3 o 2): se hacen ceros todos los elementos de una columna salvo uno usando `Hᵢ,ⱼ(k)` (que por la 3.ª propiedad no altera el determinante) y se multiplica `aᵢⱼ . (-1)ⁱ⁺ʲ . |menor|`. Por su parte, la **matriz inversa `A⁻¹`** existe si y solo si `A` es cuadrada y **regular (`|A| ≠ 0`)**, y se calcula llevando `[ A : I ]` a la canónica `[ I : A⁻¹ ]`.

### 8.4 Cuestionario Teórico y Verdadero / Falso Integrador Oficial de la Unidad 2 (`DF 4` y `DF 8`, págs. 16 y 17)
* **📖 Preguntas Conceptuales Integradoras (`DF 4`, pág. 16):**
  1. ***"a- ¿Qué puedes decir sobre dos matrices, si sabes que sumadas dan la matriz nula (`A + B = 0`)?"*** → Que una es la **matriz opuesta (inversa aditiva)** de la otra (`B = -A`), por lo que tienen el mismo orden y sus elementos correspondientes son opuestos.
  2. ***"b- ¿Qué puedes decir sobre dos matrices, si sabes que multiplicadas dan la matriz identidad (`A . B = I`)?"*** → Que son **matrices cuadradas regulares e inversas multiplicativas entre sí** (`B = A⁻¹` y `A = B⁻¹`).
  3. ***"c- ¿Qué operación representa `#` si sabes que la igualdad `A # B = B # A` entre matrices es válida?"*** → Representa la **adición de matrices (`+`)**, que siempre es conmutativa (o el producto solo en el caso particular de matrices permutables).
  4. ***"d- Si `D` (`3×3`) tiene en filas los negocios A, B, C y en columnas los productos `a, b, c`, y `A = [1  1  1]` es un vector fila `1×3`, ¿qué representan los elementos de `A . D`?"*** → Representan un vector fila `1 × 3` con la **suma total vendida de cada producto (`a`, `b` y `c`)** entre los tres negocios.
* **📖 Verdadero / Falso Integrador Oficial de la Unidad 2 (`DF 8`, pág. 17):**
  1. ***"a- Si dos matrices pueden multiplicarse y sumarse, podemos asegurar que son cuadradas."*** → **VERDADERO (`V`)**: para poder sumarse deben tener el mismo orden (`m × n` y `m × n`), y para poder multiplicarse el número de columnas de la primera debe igualar al de filas de la segunda (`n = m`), por lo que ambas son cuadradas de orden `n × n`.
  2. ***"b- La inversa de una matriz `mxn` es una matriz `mxn`."*** → **FALSO (`F`)**: la matriz inversa **sólo existe para matrices cuadradas (`n × n`) que sean regulares (`|A| ≠ 0`)**; una matriz rectangular `m × n` con `m ≠ n` nunca tiene inversa.
  3. ***"c- Si dos matrices son conformables entonces se pueden sumar."*** → **FALSO (`F`)**: que sean conformables (`Aₘₓₙ` y `Bₙₓₚ`) sólo asegura que se pueden multiplicar, pero si `m ≠ n` o `n ≠ p` no tienen el mismo orden y no se pueden sumar.
  4. ***"d- Tanto en la Adición como en la Multiplicación de matrices se cumplen las propiedades asociativa y conmutativa."*** → **FALSO (`F`)**: la propiedad asociativa se cumple en ambas, pero **la propiedad conmutativa NO se cumple en general en la multiplicación de matrices** (`A . B ≠ B . A`).
  5. ***"e- A una matriz se le puede calcular el determinante o no, según la cantidad de elementos que tenga."*** → **FALSO (`F`)**: que se pueda calcular el determinante depende de que su **orden sea cuadrado (`n × n`)**, no solo de la cantidad de elementos (por ejemplo, una matriz de 4 elementos de orden `1 × 4` no es cuadrada y no tiene determinante, mientras que una de orden `2 × 2` sí).

---

# UNIDAD 3: SISTEMAS DE ECUACIONES LINEALES (CLASES 9 A 12)

## CLASE 9 — Ecuaciones, Sistemas de Ecuaciones Lineales y Clasificaciones

### 9.1 Esquema de la Unidad 3, Cuadrados Mágicos y Concepto de Ecuación Lineal
* **📖 Definición textual / Enunciado:**
  > *"En esta unidad veremos una aplicación de Matrices y Determinantes para la resolución de sistemas de ecuaciones mediante un **método de resolución general** (usando **matriz canónica y rango**) y un **método particular: Regla de Cramer** (usando el cálculo de **determinantes**).*
  > *• **Cuadrados mágicos (págs. 2 y 3):** Son distribuciones de números que se disponen en una matriz cuadrada de forma que la suma de cualquiera de las filas, de cualquiera de las columnas y de las dos diagonales da siempre el mismo resultado, denominado **“constante mágica”** (usualmente se utilizan números consecutivos comenzando en el `1`). Ejemplos históricos del apunte: el **Cuadrado Mágico del río Amarillo** (emperador de China, tercer milenio a.C., de orden `3` con números del `1` al `9` y constante mágica `15`), los estudios de Benjamin Franklin y el **Cuadrado Mágico de Durero** (de orden `4` y constante mágica `34`). (Nota al desafío de pág. 3: **no es posible construir un cuadrado mágico de orden 2** con números distintos).*
  > *• **ECUACIÓN (pág. 5):** Una ecuación es una **igualdad entre dos expresiones algebraicas que sólo se satisface para determinados valores de la parte literal** (la parte literal sería la o las incógnitas). Estos valores que satisfacen la igualdad se denominan **raíces o soluciones** de la ecuación. Dada una ecuación, el objetivo es **RESOLVERLA**, esto es encontrar, si tiene, sus raíces o soluciones.*
  > *• **Ecuaciones lineales (pág. 5):** Son aquellas en las que **la suma de los exponentes de la parte literal* es a lo sumo `1`, en cada término** (*La **parte literal de un término** es la letra junto a su exponente, ej. en `3.a⁵ - 3.b²` son `a⁵` y `b²`). Ejemplos no lineales: `x² + 4x = -2` ó `3x⁴ + 2x³ - 5x = 2x`."*
* **💡 En simple:** Una ecuación es **lineal** cuando en cada término sus incógnitas (**parte literal**) tienen exponente `1` y no se multiplican entre sí (la suma de exponentes por término es como máximo `1`). **Resolver** una ecuación es hallar sus **raíces o soluciones**.

### 9.2 Sistema de Ecuaciones Lineales, Verificación y Clasificaciones (Homogéneo / Soluciones)
* **📖 Definición textual / Enunciado:**
  > *"Cuando dos o más ecuaciones se deben cumplir simultáneamente, estamos frente a un **sistema de ecuaciones**. Se acomoda el sistema de tal manera que en el primer miembro queden los términos con las incógnitas, y en el segundo miembro los términos independientes. **Resolver un sistema significa encontrar un conjunto de valores para sus incógnitas que satisfagan todas las ecuaciones simultáneamente.** Para comprobar si un conjunto de valores es solución, reemplazamos cada incógnita por su valor en **todas** las ecuaciones para ver si se verifica la igualdad (si verifica todas las ecuaciones, podemos asegurar que el sistema es **Compatible**, aunque sin resolverlo aún no sabemos si tiene única o infinitas soluciones).*
  > ***1) Clasificación según los términos independientes:***
  > *• **Sistema HOMOGÉNEO:** Cuando en un sistema **todas** las ecuaciones tienen sus términos independientes nulos (`= 0`).*
  > *• **Sistema NO HOMOGÉNEO:** Cuando en un sistema **existe por lo menos un** término independiente distinto de cero (`≠ 0`).*
  > ***2) Clasificación de acuerdo a las soluciones obtenidas:***
  > *• **COMPATIBLE:** El sistema de ecuaciones **tiene solución**.*
  >   *- **DETERMINADO:** El sistema tiene **una única solución**.*
  >   *- **INDETERMINADO:** El sistema tiene **infinitas soluciones**.*
  > *• **INCOMPATIBLE:** El sistema de ecuaciones **no tiene solución** (no se puede encontrar valores que satisfagan las ecuaciones)."*
* **💡 En simple:** Un sistema lineal se clasifica por sus términos independientes (luego de ordenar las incógnitas a la izquierda y los números solos a la derecha) en **Homogéneo** (todos `0`) o **No Homogéneo** (al menos uno `≠ 0`), y por la cantidad de soluciones que satisfacen **todas las ecuaciones a la vez** en **Compatible Determinado** (`1` solución), **Compatible Indeterminado** (`∞` soluciones) o **Incompatible** (`0` soluciones).

---

## CLASES 10 Y 11 (UNIFICADAS) — Método General de Resolución, Clasificación Matricial, Sistemas Homogéneos y Variables Libres

### 10.1 Las Tres Matrices (`A`, `B`, `X`), Forma Matricial (`A . X = B`), Matriz Ampliada (`A°`) y los 5 Pasos
* **📖 Definición textual / Enunciado:**
  > *"Para armar la forma matricial es importante que el sistema esté **completo y ordenado** (en el primer miembro los términos con las incógnitas y en el segundo miembro los términos independientes). Armamos tres matrices: a la matriz `A` la llamamos **Matriz de los coeficientes** (los números que multiplican a cada incógnita), a la matriz `B` la llamamos **Matriz (o vector) de los términos independientes** y a la matriz `X` la llamamos **matriz (o vector) de las incógnitas**.*
  > *• **Forma matricial del sistema:** **`Aₙₓₘ . Xₘₓ₁ = Bₙₓ₁`**.*
  > *• **Matriz ampliada del sistema:** Se forma a partir de la matriz de los coeficientes y del vector de los términos independientes: **`A° = [ A : B ]`**.*
  > *• **Sistemas equivalentes:** Al llevar `A°` a canónica mediante operaciones elementales se obtiene un **sistema equivalente** (dos sistemas son equivalentes cuando tienen las mismas soluciones, ya que aplicar operaciones elementales a la matriz ampliada no cambia las soluciones de las ecuaciones).*
  > *• **Rearmado del sistema desde la matriz canónica (pág. 4):** Una vez en la matriz canónica, se rearma el sistema (ej. `1.x + 0.y + 0.z = 25`), y teniendo en cuenta que cualquier número multiplicado por `0` da `0` y multiplicado por `1` da el mismo número, queda directamente el valor de cada incógnita (`x = 25, y = 35, z = 35`).*
  > *• **Pasos del Método General de resolución:** **1ero|** Completar y ordenar el sistema dado. **2do|** Armar la matriz ampliada correspondiente (`A° = [ A : B ]`). **3ero|** Llevar dicha matriz a la forma canónica. **4to|** Clasificar el sistema. **5to|** Armar el vector solución."*
* **💡 En simple:** El **Método General** (eliminación de Gauss-Jordan sobre `A° = [ A : B ]`) sirve para resolver **cualquier** sistema lineal de `n` ecuaciones con `m` incógnitas. Dos sistemas son **equivalentes** si y solo si tienen **el mismo conjunto solución**.

### 10.2 Criterio Matricial de Clasificación por Rangos y Caso de Sistemas Homogéneos
* **📖 Definición textual / Enunciado:**
  > *"El **RANGO** de una matriz es el número de filas no nulas de la canónica equivalente. Una vez llevada la matriz ampliada a la canónica, el **rango de `A` (`ρ(A)`)** se observa **sin tener en cuenta la última columna**, y para obtener el **rango de la ampliada (`ρ(A°)`)** **sí se tiene en cuenta dicha columna**. (Desempeño 1j, pág. 9: **¿Puede ser el rango de la matriz de los coeficientes mayor que el rango de la matriz ampliada?** **No, nunca**, porque `A` está contenida dentro de `A° = [ A : B ]`, por lo que siempre se cumple `ρ(A) ≤ ρ(A°)`).*
  > *• **Criterio de Compatibilidad:** El sistema será **Compatible** (tendrá solución) si **`ρ(A) = ρ(A°)`**. Si esta igualdad no se verifica (**`ρ(A) ≠ ρ(A°)`**), el sistema es **Incompatible** (no tendrá solución). Esta condición se aplica a cualquier sistema lineal sin restricción sobre el número de ecuaciones, variables o términos independientes.*
  > *• **Criterio de Determinación (si es Compatible):** Es **Determinado** si el rango de la matriz ampliada es igual al número de incógnitas (**`ρ(A) = ρ(A°) = m`**), y es **Indeterminado** si dicho rango es menor que el número de incógnitas (**`ρ(A°) < m`**).*
  > *• **Sistemas homogéneos (`A . X = 0`, siempre compatibles):** Siempre tienen solución porque `A° = [ A : 0 ]` y el vector nulo agregado no puede aumentar el rango (`ρ(A) = ρ(A°)` siempre). El vector nulo siempre es solución (`A . 0 = 0`), denominada **solución trivial** (dar el valor cero a todas las variables). Las soluciones representadas por vectores distintos del nulo se llaman **soluciones no triviales**.*
  > *• **Sistemas homogéneos cuadrados (`Aₙₓₙ . X = 0`):** La condición para que tenga **soluciones no triviales** (sea **indeterminado**, `ρ(A) < n`) es que **`|A| = 0`**. Si **`|A| ≠ 0`**, entonces `ρ(A) = n`, el sistema es **determinado** y la única solución que existe es la **solución trivial**."*
* **💡 En simple:** En la matriz canónica de `A°`, siempre se cumple `ρ(A) ≤ ρ(A°) ≤ m`:
  * Si **`ρ(A) ≠ ρ(A°)`** → **Incompatible** (sin solución).
  * Si **`ρ(A) = ρ(A°) = m`** → **Compatible Determinado** (solución única).
  * Si **`ρ(A) = ρ(A°) < m`** → **Compatible Indeterminado** (infinitas soluciones).
  * En todo **sistema homogéneo (`B = 0`)** es imposible que sea incompatible: si `ρ(A) = m` (o `|A| ≠ 0` cuando es cuadrado) solo tiene la **solución trivial `X = 0`**; si `ρ(A) < m` (o `|A| = 0` cuando es cuadrado) tiene infinitas soluciones (**la trivial + las no triviales**).

### 11.1 Contradicción en Sistemas Incompatibles, Variables Libres (`m - ρ(A°)`), Solución General (`X*`), Soluciones Particulares y los 3 Casos de Validación
* **📖 Definición textual / Enunciado:**
  > *• **Sistema Incompatible en la canónica y por Contradicción temprana (Clase 11, págs. 2 y 3):** Al llevar a la forma canónica completa un sistema incompatible (Ejemplo N° 6, pág. 2), aparece una fila con todos ceros en `A` y un `1` conductor en la columna de términos independientes (`[0  0  0 : 1]`, de modo que `ρ(A) = 3 ≠ ρ(A°) = 4`). Además (Ejemplo N° 7, pág. 3): "A veces no es necesario llegar a la matriz canónica para advertir que el sistema es **Incompatible**, si aparece una ecuación como `0 = 8` [fila `[0  0  0 : 8]`], que no se verifica para ningún conjunto de valores de las incógnitas, pues es una **contradicción**."*
  > *• **Variables libres, Solución General (`X*`) y Soluciones Particulares (Clase 11, págs. 4 a 7):** En un sistema **Compatible Indeterminado** (`ρ(A) = ρ(A°) < m`), cada incógnita NO es igual a un número determinado: **la diferencia entre el número de incógnitas y el rango de la matriz ampliada (`m - ρ(A°)`) nos da la cantidad de variables libres o independientes** que tiene el sistema (pudiendo haber 1, 2 o más variables libres, como en el Desempeño 4c con `m = 5` y `ρ(A°) = 3 ⇒ 2` variables libres). Despejando las demás incógnitas (variables dependientes) en función de la(s) variable(s) libre(s), el vector solución hallado **`X*`** es la **Solución General del Sistema** (ej.: `X* = [36 - 7C ; -24 + 6C ; C]`). A partir de esta solución general se pueden hallar infinitas **soluciones particulares** según el valor numérico que se le asigne a la variable libre (ej. para `C = 8 → X* = [-20 ; 24 ; 8]`; para `C = 3 → X* = [15 ; -6 ; 3]`; para `C = 5 → X* = [1 ; 6 ; 5]`).*
  > *• **Validación de la respuesta y sus casos prácticos (Clase 10 pág. 10 y Clase 11 págs. 10 y 11):** "**Validar la respuesta** significa que la solución obtenida tiene que estar acorde a la situación problemática trabajada."*
  >   *- **En un Sistema Determinado (Clase 10, Desempeño 4d):** Si para una cantidad de personas da fracciones (`B = 31/3, R = 16/3, OC = 40/3`), **es solución al sistema planteado, pero no es solución al problema planteado**.*
  >   *- **En un Sistema Indeterminado (Clase 11, Desempeños 5, 6 y 7):** El contexto físico restringe los valores de la variable libre en tres casos típicos: **1) Naturales acotados (Desempeño 5, lotes de librería):** `X* = [15 - C ; 2 - C ; C]` exige valores naturales no negativos (`2 - C ≥ 0`), por lo que solo existen 3 posibilidades válidas (`C = 0, 1` ó `2`); **2) Divisibilidad por múltiplos enteros (Desempeño 6, fábrica de bicicletas):** `X* = [2/7 z ; 400 - 10/7 z ; z]` exige que `z` sea **múltiplo de `7`** para dar números enteros y que `400 - 10/7 z ≥ 0 ⇒ z ≤ 280` (máximo `280` bicicletas de carrera); **3) Reales no negativos mediante inecuaciones (Desempeño 7, gramos de alimento):** `X* = [4 + 4z ; 9 - 5z ; z]` admite números reales `≥ 0`, exigiendo `z ≥ 0` y `9 - 5z ≥ 0 ⇒ 0 ≤ z ≤ 9/5`."*
* **💡 En simple:** En un **Sistema Compatible Indeterminado**, restás **`m - ρ(A°)`** para saber cuántas **variables libres** hay, despejás las incógnitas principales en función de ellas para escribir el vector **Solución General `X*`**, y reemplazás la variable libre por números concretos para obtener **Soluciones Particulares**. Al final, **validar la respuesta** consiste en filtrar cuáles de esas soluciones matemáticas tienen sentido físico real en el problema (enteros no negativos, múltiplos del denominador o intervalos reales `≥ 0`).

---

## CLASE 12 — Método Particular (Regla de Cramer), Matriz de Insumo-Producto e Integración

### 12.1 Sistema Cuadrado, Regla de Cramer, Matriz `Aⱼ` y Caso `|A| = 0`
* **📖 Definición textual / Enunciado:**
  > *"Un **sistema cuadrado** es aquel que **tiene la misma cantidad de ecuaciones que de incógnitas**.*
  > ***Condiciones de la Regla de Cramer:** La Regla de Cramer es posible aplicarla cuando:*
  > *• **1)** Se tiene un sistema de ecuaciones que tiene la **misma cantidad de ecuaciones que de incógnitas** (sistema cuadrado), y*
  > *• **2)** **El determinante de la matriz de los coeficientes es distinto de cero (`|A| ≠ 0`**, es decir, la matriz `A` es **Regular**).*
  > ***Enunciado general y fórmula:** Sea el sistema completo y ordenado `A . X = B` (atención en los ejercicios a ordenar primero las columnas de las incógnitas en el mismo orden en todas las ecuaciones y los términos independientes a la derecha), donde `A` es la matriz de los coeficientes, cuadrada y regular; `X` es el vector de las incógnitas y `B` el vector de los términos independientes. Definimos a la **matriz cuadrada `Aⱼ`** como la matriz que resulta de **reemplazar en la matriz `A` a la columna `j` por el vector de los términos independientes `B`**. Entonces el sistema tiene por **única solución** (siendo siempre un **Sistema Compatible Determinado**, incluso en un sistema de 4 ecuaciones con 4 incógnitas —Desempeño 1d—) el vector `X = [x₁ ; x₂ ; ... ; xₙ]` donde:*
  > **`x₁ = |A₁| / |A| ,   x₂ = |A₂| / |A| ,   ... ,   xₙ = |Aₙ| / |A|`**
  > ***¿Qué ocurre si `|A| = 0` (la matriz de los coeficientes no es regular, Desempeño 1c y Ejemplo N° 12)?*** *Si `|A| = 0`, **el sistema no se puede resolver por la regla de Cramer** y **se puede asegurar que el sistema no es Compatible Determinado**. En este caso hay que aplicar el **método general de resolución**."*
* **💡 En simple:** La **Regla de Cramer** solo aplica a sistemas **cuadrados (`n × n`)** cuya matriz `A` sea **regular (`|A| ≠ 0`)**, y calcula cada incógnita dividiendo `|Aⱼ| / |A|`, dando siempre **solución única (SCD)**. Si da **`|A| = 0`**, Cramer queda descartado, ya sabemos con certeza que el sistema **no es SCD**, y debemos usar Gauss-Jordan sobre `A°` para ver si es Indeterminado o Incompatible.

### 12.2 Matriz de Insumo-Producto y Verdadero / Falso Integrador Oficial
* **📖 Definición textual / Enunciado (Matriz de Insumo-Producto, pág. 8):**
  > *"En el modelo económico de producción, la matriz `A` se llama **matriz de insumo-producto**, donde sus elementos son los **coeficientes de insumo** [insumos requeridos de cada sector por cada `1` peso producido]. **Se considera que esta matriz es productiva, si las sumas de los elementos de cada columna son menores que `1`.** Los niveles de producción se calculan siguiendo el modelo económico dado por **`(I - A) . X = D`**, donde `X` es la **matriz de producción**, `D` es la **matriz de demanda externa** e `I` es la **matriz Identidad**."*
* **📖 Verdadero / Falso Integrador Oficial de la Unidad 3 (Desempeño Integrador 2, págs. 6 y 8):**
  1. ***"a- Todo sistema de ecuaciones lineales tiene solución."*** → **FALSO (`a veces`)**: los sistemas Incompatibles no tienen solución.
  2. ***"b- Un sistema homogéneo siempre tiene solución."*** → **VERDADERO (`V`)**: siempre es Compatible (`ρ(A) = ρ(A°)`) y admite al menos la solución trivial `X = 0`.
  3. ***"c- Dos sistemas son equivalentes cuando son determinados."*** → **FALSO (`son equivalentes cuando tienen la misma solución`)**.
  4. ***"d- En un sistema determinado el número de variables independientes se calcula como el número de incógnitas menos el rango de la matriz ampliada."*** → **FALSO (`en un sistema indeterminado`)**: en uno determinado es `m - ρ(A°) = 0`.
  5. ***"e- Un sistema que tiene 2 variables libres, es un sistema Incompatible."*** → **FALSO (`es un sistema indeterminado`)**: tener variables libres implica que es Compatible Indeterminado.
  6. ***"f- Si existen menos ecuaciones que incógnitas en un sistema lineal, entonces el sistema o no tiene solución, o tiene infinitas soluciones."*** → **VERDADERO (`V`)**: como `ρ(A) ≤ n < m`, nunca puede ser Determinado (`ρ(A) = m`).
  7. ***"g- Un sistema homogéneo siempre es Compatible indeterminado."*** → **FALSO (`admite siempre la solución trivial. Hay que ver si es indeterminado`)**: si `ρ(A) = m` (o `|A| ≠ 0`) es Compatible Determinado.
  8. ***"h- Si el rango de la matriz de los coeficientes es igual al rango de la matriz ampliada, entonces estamos ante un sistema Incompatible."*** → **FALSO (`Compatible`)**: `ρ(A) = ρ(A°)` es la condición de sistema Compatible.
  9. ***"i- Si el determinante de la matriz de los coeficientes de un sistema es distinto de cero, podemos asegurar que el sistema tiene solución."*** → **VERDADERO (`V`)**: por Regla de Cramer es Compatible Determinado (tiene solución única).
  10. ***"j- Si el rango de la matriz de los coeficientes es distinto al rango de la matriz ampliada, eso indica que el sistema es Indeterminado."*** → **FALSO (`Incompatible`)**: `ρ(A) ≠ ρ(A°)` indica que es Incompatible.

---

# 📊 CUADROS-RESUMEN INTEGRADORES DE FÓRMULAS Y CRITERIOS CLAVE

## Cuadro 1 — Unidad 1: Axiomas, Teoremas y Formas Canónicas del Álgebra de Boole

| Categoría | Código y Nombre Oficial | Forma para la Suma (`+`) | Forma para el Producto (`•` o `.`) | Clave Teórica |
| :--- | :--- | :---: | :---: | :--- |
| **Axiomas (Clase 1)**<br>*(Sin demostración)* | **A1: Propiedad Conmutativa** | `A + B = B + A` | `A • B = B • A` | Válida para cualesquiera `A, B ∈ M`. |
| **Axiomas (Clase 1)** | **A2: Propiedad Distributiva** | `A + (B • C) = (A + B) • (A + C)` | `A • (B + C) = (A • B) + (A • C)` | La suma también distribuye sobre el producto (`b-`). |
| **Axiomas (Clase 1)** | **A3: Elemento Neutro** | `A + 0 = A` *(neutro `0`)* | `A • 1 = A` *(neutro `1`)* | Cumple la propiedad de identidad. |
| **Axiomas (Clase 1)** | **A4: Complemento** | `A + Ā = 1` | `A • Ā = 0` | Para cada `A ∈ M` existe su negación `Ā`. |
| **Teoremas (Clase 2)**<br>*(Con demostración)* | **Teorema 1: Ley de Acotación** | `A + 1 = 1` | `A • 0 = 0` | Demostrado partiendo de `1 = A + Ā` y `0 = A • Ā`. |
| **Teoremas (Clase 2)** | **Teorema 2: Ley de Idempotencia** | `A + A = A` | `A • A = A` | Reduce términos o factores idénticos. |
| **Teoremas (Clase 2)** | **Teorema 3: Ley de Absorción** | `A + (A • B) = A` | `A • (A + B) = A` | Elimina la variable `B` acompañante. |
| **Teoremas (Clase 2)** | **Teorema 4: Ley de Asociatividad** | `A + (B + C) = (A + B) + C` | `A . (B . C) = (A . B) . C` | Permite quitar paréntesis en igual operación. |
| **Teoremas (Clase 2)** | **Teorema 5: Ley de Involución** | `A̿ = A` | `A̿ = A` | Negar dos veces da el mismo elemento. |
| **Teoremas (Clase 2)** | **Teorema 6: Ley de De Morgan** | `A̅+̅B̅ = Ā • B̄` | `A̅•̅B̅ = Ā + B̄` | Rompe la barra continua cambiando `+ ↔ •`. |
| **Formas Canónicas (Clase 4)** | **Maxitérmino (`PS` / `∏M` / `IIM`)** vs. **Minitérmino (`SP` / `∑m`)** | **Maxitérmino (Suma canónica):** Filas donde **`F = 0`**. Variable en `0` → **directa** (`A`); en `1` → **negada** (`Ā`). Productoria **`IIM` (`∏M`)**. | **minitérmino (Producto canónico):** Filas donde **`F = 1`**. Variable en `1` → **directa** (`A`); en `0` → **negada** (`Ā`). Sumatoria **`∑m`**. | Cada término canónico relaciona **todas** las variables **una sola vez** con **una sola operación**. |

---

## Cuadro 2 — Unidad 2: Operaciones Matriciales, Operaciones Elementales y Determinantes (`DF 5`)

| Concepto / Operación | Condición de Aplicabilidad (`¿Cuándo puede realizarse?`) | Resultado / Efecto Exacto (`¿Cuál es el orden del resultado?`) |
| :--- | :--- | :--- |
| **Adición (`A + B`) y Sustracción (`A - B`)** | Matrices del **mismo orden** (`m × n`, no necesariamente cuadradas). | Matriz del **mismo orden (`m × n`)** operando elementos correspondientes (`aᵢⱼ ± bᵢⱼ`). Neutro aditivo: **Matriz nula `0`**. Inverso aditivo: **Matriz opuesta `-A`**. |
| **Producto por un número (`k . A`)** | **Ninguna** (cualquier matriz `m × n` y cualquier escalar `k`). | Matriz del **mismo orden (`m × n`)** multiplicando cada elemento por `k` (`[k . aᵢⱼ]`). Neutro: **`1`**. |
| **Producto escalar (`A . B` entre vectores)** | **Vector fila (`1 × n`)** por **vector columna (`n × 1`)** de igual cantidad de elementos (nunca al revés). | Da por resultado **un número** (no una matriz): suma de los productos de elementos correspondientes. |
| **Multiplicación de matrices (`Aₘₓₙ . Bₙₓₚ = Cₘₓₚ`)** | Matrices **conformables**: N.° de **columnas de la 1.ª (`n`)** = N.° de **filas de la 2.ª (`n`)**. | Matriz `C` de orden **`m × p`** con `cᵢⱼ = fila i de A ∙ columna j de B`. **No es conmutativa** (si `A.B = B.A` son **permutables**) y **no cumple propiedad cancelativa**. Neutro: **Identidad `I`**. |
| **1.ª Op. Elemental: `Hᵢ,ⱼ`** *(Permutar filas `i` y `j`)* | Cualquier matriz. | `A ~ B`. **1.ª Propiedad de Determinantes:** cambia de signo pero no de valor absoluto (**`|A| = -|B|`**). |
| **2.ª Op. Elemental: `Hᵢ(k)`** *(Multiplicar fila `i` por `k ≠ 0`)* | Constante **`k ≠ 0`**. | `A ~ B`. **2.ª Propiedad de Determinantes:** queda multiplicado por `k` (**`|B| = k . |A|`**, luego **`|A| = |B| / k`**). |
| **3.ª Op. Elemental: `Hᵢ,ⱼ(k)`** *(Sumar a fila `i` la fila `j` por `k ≠ 0`)* | Constante **`k ≠ 0`**. | `A ~ B`. **3.ª Propiedad de Determinantes (la más importante):** el determinante **NO varía** (**`|A| = |B|`**). |
| **Determinante Nulo (`|A| = 0`)**<br>*(Propiedades 4.ª, 5.ª y 6.ª)* | Solo matrices cuadradas (`n × n`). | Vale **`0`** si: **4.ª)** tiene una **línea nula**; **5.ª)** tiene **dos líneas paralelas iguales**; **6.ª)** tiene **dos líneas paralelas proporcionales** (una es múltiplo escalar de otra). |
| **Matriz Regular e Inversa (`A⁻¹`)** | Matriz **cuadrada** con **`|A| ≠ 0` (Regular o No Singular)**. | **Tiene inversa si es regular.** Se calcula llevando `[ A : I ]` a la canónica **`[ I : A⁻¹ ]`** (Gauss-Jordan) y verifica **`A . A⁻¹ = A⁻¹ . A = I`**. |

---

## Cuadro 3 — Unidad 3: Clasificación y Resolución de Sistemas Lineales (`Aₙₓₘ . Xₘₓ₁ = Bₙₓ₁`)

| Clasificación del Sistema | Soluciones | Condición en el Método General (Rangos en Canónica de `A° = [ A : B ]`, `m` incógnitas) | Condición en Sistema Cuadrado (`n = m`) por Determinante `|A|` y Regla de Cramer |
| :--- | :--- | :--- | :--- |
| **COMPATIBLE DETERMINADO (SCD)** | **Única solución** | **`ρ(A) = ρ(A°) = m`**<br>*(0 variables libres).* | **`|A| ≠ 0` (`A` Regular)**.<br>**Sí aplica Cramer:** **`xⱼ = |Aⱼ| / |A|`**. |
| **COMPATIBLE INDETERMINADO (SCI)** | **Infinitas soluciones** (`X*` general + particulares) | **`ρ(A) = ρ(A°) < m`**<br>*(Tiene **`m - ρ(A°)` variables libres**).* | **`|A| = 0` (`A` no Regular)**.<br>**No aplica Cramer** (usar Método General). |
| **INCOMPATIBLE (SI)** | **Sin solución** | **`ρ(A) ≠ ρ(A°)`** *(siempre `ρ(A) < ρ(A°)`)*<br>*(Aparece fila de **contradicción** `0 = k` con `k ≠ 0`).* | **`|A| = 0` (`A` no Regular)**.<br>**No aplica Cramer** (usar Método General). |
| **SISTEMA HOMOGÉNEO (`A . X = 0`)** | **Siempre Compatible** (`ρ(A) = ρ(A°)`). Siempre admite la **solución trivial (`X = 0`)**. | • Si **`ρ(A) = m`** → **Determinado** (solo solución trivial `X = 0`).<br>• Si **`ρ(A) < m`** → **Indeterminado** (solución trivial + **no triviales `X ≠ 0`**). | En **Homogéneo Cuadrado (`n × n`)**:<br>• **`|A| ≠ 0`** → **Determinado** (solo trivial).<br>• **`|A| = 0`** → **Indeterminado** (**tiene soluciones no triviales**). |
