# Clase 2 — Álgebra de Boole: Teoremas del Álgebra de Boole

## 🗺️ Mapa de la clase

- **Temas que cubre la clase y su orden en el material:**
  1. **Diferencia entre Axiomas y Teoremas en el Álgebra de Boole (Pág. 2):** repaso del concepto de propiedad axiomática e introducción del concepto de teorema como propiedad que requiere demostración lógica para ser válida.
  2. **Enunciado de los 6 Teoremas del Álgebra de Boole (Pág. 2):**
     - **Teorema 1:** Ley de Acotación (`A + 1 = 1` y `A • 0 = 0`).
     - **Teorema 2:** Ley de Idempotencia (`A + A = A` y `A • A = A`).
     - **Teorema 3:** Ley de Absorción (`A + (A • B) = A` y `A • (A + B) = A`).
     - **Teorema 4:** Ley de Asociatividad (para la suma lógica `+` y el producto lógico `.`).
     - **Teorema 5:** Ley de Involución (`A̿ = A`, doble negación).
     - **Teorema 6:** Ley de De Morgan (negación de una suma lógica y negación de un producto lógico).
  3. **Modos de demostración de teoremas e igualdades booleanas (Pág. 3 y Pág. 5):**
     - **Demostración algebraica (Pág. 3 y Pág. 5):** procedimiento paso a paso aplicando axiomas (y teoremas ya demostrados) para transformar un miembro de la igualdad en el otro (o ambos hasta una expresión idéntica), ilustrado en el material con la demostración de `A + 1 = 1`.
     - **Demostración por Tablas de Verdad (Pág. 3):** evaluación exhaustiva de la distribución de valores de verdad de ambos miembros de la igualdad, ilustrada en el material con la demostración de `A + A . B = A`.
  4. **Comprensión estructural e independencia simbólica (Pág. 4 y Pág. 5):** aplicación de axiomas y teoremas como esquemas o moldes lógicos más allá de las letras empleadas (`A, B, C` o `x, y, z` o expresiones compuestas).

- **Cómo se conectan entre sí:**
  - En la **Clase 1** se definieron las variables lógicas (`0` y `1`), las tres operaciones básicas (suma lógica `+`, producto lógico `•` y negación `Ā`) y los **4 Axiomas** (A1 Conmutativa, A2 Distributiva, A3 Elemento Neutro, A4 Complemento), que se aceptan sin demostración.
  - En esta **Clase 2**, a partir de esos 4 axiomas y de las tablas de definición de las operaciones, se deducen y demuestran los **6 Teoremas fundamentales**. Una vez demostrados, estos teoremas se suman al repertorio de herramientas válidas para simplificar expresiones y demostrar nuevas igualdades booleanas más complejas (que luego servirán en las Clases 3 y 4 para funciones booleanas, formas canónicas, circuitos combinacionales y mapas de Karnaugh).

- **Prerrequisitos (de Clase 1 y Matemática Discreta 1):**
  - Concepto de **variable lógica** (solo toma valores excluyentes `0` o `1`).
  - Tablas de verdad de las tres **operaciones lógicas**: suma lógica (`+`, análoga a la disyunción `∨`), producto lógico (`•` o `.`, análogo a la conjunción `∧`) y negación o complemento (`Ā`, análogo a `¬`).
  - Los **4 Axiomas del Álgebra de Boole (Clase 1)**:
    - **Ax 1 (Propiedad Conmutativa):** `A + B = B + A` y `A • B = B • A`.
    - **Ax 2 (Propiedad Distributiva):** `A • (B + C) = (A • B) + (A • C)` y `A + (B • C) = (A + B) • (A + C)`.
    - **Ax 3 (Elemento Neutro / Identidad):** `A + 0 = A` y `A • 1 = A`.
    - **Ax 4 (Complemento):** `A + Ā = 1` y `A • Ā = 0`.

---

## 2.1 Teoremas del Álgebra de Boole (Diferencia con los Axiomas)

> 📖 **Textual del material:** "En esta clase le propondremos profundizar un poco más sobre las propiedades, pero esta vez no solo axiomáticas sino también los teoremas y sus diferentes modos de demostración.
> Recordemos que los teoremas también son propiedades, pero a diferencia de los axiomas Sí necesitan de una demostración para que sean tomados como válidos."
>
> 📖 **Textual del material (pág. 2, pie):** "Como les dije hace un rato, las primeras propiedades, axiomas, no se demuestran, por el contrario, los teoremas sí."

**🗣️ En palabras simples:**
Tanto los axiomas (vistos en la Clase 1) como los teoremas (vistos en esta Clase 2) son propiedades o leyes que cumplen las operaciones del Álgebra de Boole. La única diferencia formal es su punto de partida: los **axiomas** son las reglas básicas que se aceptan como verdaderas sin demostración, mientras que los **teoremas** son propiedades derivadas que **obligatoriamente deben demostrarse** (ya sea algebraicamente a partir de los axiomas o mediante tablas de verdad) antes de poder darlas por válidas.

**🔍 Desglose de la jerga:**
- **"Propiedades":** igualdades lógicas universales que se cumplen para cualquier valor (`0` o `1`) que tomen las variables booleanas involucradas.
- **"Propiedades axiomáticas / Axiomas":** verdades iniciales o puntos de partida del sistema formal (Conmutativa, Distributiva, Elemento Neutro y Complemento en este material) que no se demuestran.
- **"Teoremas":** proposiciones o leyes lógicas que afirman una igualdad entre dos expresiones booleanas y cuya validez exige una **demostración**.
- **"Modos de demostración":** los procedimientos válidos en la materia para justificar que un teorema es cierto: la **demostración algebraica** y la **demostración por tablas de verdad**.

**💡 Ejemplo:**
- Que `A + 0 = A` es un **axioma** (Axioma 3: Elemento Neutro); no se demuestra, forma parte de las reglas de juego iniciales.
- En cambio, que `A + 1 = 1` (Ley de Acotación) o que `A + A = A` (Ley de Idempotencia) son **teoremas**: aunque parezcan intuitivos, en el Álgebra de Boole hay que demostrarlos usando los axiomas o construyendo su tabla de verdad.

**🔗 Conexiones:**
- Conecta directamente con la clasificación introducida en la **Clase 1 (pág. 5)** (*"Dentro de las propiedades del Álgebra de Boole haremos la distinción en dos grandes grupos, aquellas a las que llamamos Axiomas... y el otro grupo serán aquellas a las que llamamos Teoremas"*).
- Una vez demostrado un teorema, pasa a formar parte del conjunto de leyes utilizables para demostrar otros teoremas o simplificar funciones en las **Clases 3 y 4**.

**⚠️ Precisiones / errores comunes:**
- **Error típico en el oral:** llamar "axioma" a la Idempotencia, a De Morgan o a la Asociatividad, o llamar "teorema" al Elemento Neutro o a la Distributiva. En la bibliografía de esta cátedra (ISSD), la división es estricta:
  - **4 Axiomas (Clase 1):** Conmutativa (Ax 1), Distributiva (Ax 2), Elemento Neutro (Ax 3), Complemento (Ax 4).
  - **6 Teoremas (Clase 2):** Acotación (T1), Idempotencia (T2), Absorción (T3), Asociatividad (T4), Involución (T5), De Morgan (T6).
- *(Contexto adicional)* En otros libros de texto (como el sistema axiomático de Huntington), la asociatividad suele incluirse como axioma, pero **en esta materia la Ley de Asociatividad es el Teorema 4**. En el examen oral debés respetar estrictamente la clasificación de la cátedra.

**🎤 Cómo decirlo en el oral:**
> "Los teoremas del Álgebra de Boole también son propiedades que cumplen las operaciones lógicas, pero a diferencia de los axiomas —que se toman como válidos sin demostración—, los teoremas sí necesitan de una demostración lógica para ser tomados como válidos, la cual puede realizarse en forma algebraica o por tablas de verdad."

---

## 2.2 Teorema 1: Ley de Acotación

> 📖 **Textual del material:** "Teorema 1: Ley de Acotación
> Esta ley establece que:
> A + 1 = 1
> A • 0 = 0"
>
> 📖 **Textual del material (demostración algebraica en pág. 3):** "Tomemos el Teorema de Acotación, que dice A + 1 = 1. Hacer una demostración algebraica significa, como lo explicamos la clase anterior, que, partiendo de una de las expresiones, sea el primer miembro o el segundo de la igualdad, se debe ir escribiendo de otra manera hasta llegar al otro miembro, en este caso podríamos partir del A + 1 y llegar a qué es lo mismo que 1, ó partir del 1 y llegar a escribirlo como A + 1.
> Partamos del 1:
> Por el Ax 4 podemos escribir: 1 = A + Ā
> Por el Ax 3 podemos escribir: 1 = A + ( Ā . 1)
> Por el Ax 2 podemos escribir: 1 = A + Ā . A + 1
> Por el Ax 4 quedaría: 1 = 1 . A + 1
> Y Por axioma 3 quedará: 1 = A + 1
> De este modo quedaría demostrado en forma algebraica que el teorema es válido."

**🗣️ En palabras simples:**
La Ley de Acotación (también conocida en lógica como ley de dominación o de elementos absorbentes) dice dos cosas:
1. Si a cualquier variable lógica `A` le sumás lógicamente `1`, el resultado queda "clavado" o acotado en `1`, sin importar cuánto valga `A`.
2. Si a cualquier variable lógica `A` la multiplicás lógicamente por `0`, el resultado queda "clavado" o acotado en `0`, sin importar cuánto valga `A`.

**🔍 Desglose de la jerga:**
- **"Ley de Acotación":** se llama así porque el `1` es la cota superior del Álgebra de Boole (nada supera al `1`, y sumar `1` satura el resultado en `1`) y el `0` es la cota inferior (nada está por debajo del `0`, y multiplicar por `0` anula el resultado en `0`).
- **`A + 1 = 1`:** en la suma lógica (`+`), el `1` domina o absorbe a cualquier elemento `A`.
- **`A • 0 = 0`:** en el producto lógico (`•`), el `0` domina o anula a cualquier elemento `A`.

**💡 Ejemplo:**
- **En un circuito eléctrico (interruptores):**
  - `A + 1 = 1` representa un interruptor `A` conectado **en paralelo** con un cable directo siempre cerrado (`1`). Aunque abras o cierres `A`, la corriente siempre pasa por el cable directo y la lámpara permanece encendida (`1`).
  - `A • 0 = 0` representa un interruptor `A` conectado **en serie** con un cable cortado o llave siempre abierta (`0`). Aunque cierres `A`, la corriente nunca puede pasar y la lámpara permanece apagada (`0`).

**🧩 Idea de la demostración:**
- **Parte 1 (`A + 1 = 1`), según el desarrollo exacto del material (pág. 3):**
  El material elige partir del segundo miembro (`1`) para llegar al primero (`A + 1`):
  1. Se parte de `1`. Por **Ax 4 (Complemento: `A + Ā = 1`)**, se reemplaza `1` por `A + Ā`:
     `1 = A + Ā`
  2. Por **Ax 3 (Elemento Neutro del producto: `X • 1 = X`)**, se multiplica `Ā` por `1` sin alterar su valor:
     `1 = A + (Ā . 1)`
  3. Por **Ax 2 (Propiedad Distributiva de la suma respecto del producto: `A + (B . C) = (A + B) . (A + C)`)**, se distribuye `A +` sobre `(Ā . 1)`:
     `1 = (A + Ā) . (A + 1)` *(Nota: en el PDF impreso se omitieron tipográficamente los paréntesis y figura escrito `1 = A + Ā . A + 1`, pero algebraicamente corresponde al producto de `(A + Ā)` por `(A + 1)`).*
  4. Por **Ax 4 (Complemento: `A + Ā = 1`)**, el primer factor `(A + Ā)` vale `1`:
     `1 = 1 . (A + 1)` *(en el PDF impreso: `1 = 1 . A + 1`).*
  5. Por **Ax 3 (Elemento Neutro del producto, junto con Conmutativa Ax 1: `1 . X = X`)**, multiplicar por `1` deja la expresión `A + 1`:
     `1 = A + 1`. Queda demostrado.

- **Parte 2 (`A • 0 = 0`), demostración algebraica dual (propuesta como ejercicio en el Desempeño 3, pág. 3 — contexto adicional para el oral):**
  Siguiendo exactamente los pasos duales al ejemplo del material, partiendo del `0`:
  1. **Por Ax 4 (Complemento):** `0 = A • Ā`
  2. **Por Ax 3 (Elemento Neutro de la suma):** `0 = A • (Ā + 0)`
  3. **Por Ax 2 (Distributiva del producto respecto de la suma):** `0 = (A • Ā) + (A • 0)`
  4. **Por Ax 4 (Complemento):** `0 = 0 + (A • 0)`
  5. **Por Ax 3 (Elemento Neutro de la suma):** `0 = A • 0`.
  *(Alternativa partiendo de `A • 0`: por Ax 3 es `(A • 0) + 0`; por Ax 4 es `(A • 0) + (A • Ā)`; por Ax 2 es `A • (0 + Ā)`; por Ax 3 es `A • Ā`; por Ax 4 es `0`).*

**🤔 Intuición:**
En la suma lógica (`+`, que equivale al "O" lógico), basta con que **uno solo** de los términos sea verdadero (`1`) para que toda la suma sea verdadera (`1`). Como uno de los términos ya es fijo igual a `1`, no importa qué valga `A`: el resultado siempre será `1`. Dualmente, en el producto lógico (`•`, que equivale al "Y" lógico), basta con que **uno solo** sea falso (`0`) para que todo el producto sea falso (`0`).

**🔗 Conexiones:**
- No debe confundirse con el **Axioma 3 (Elemento Neutro)** de la Clase 1:
  - En el **Axioma 3 (Neutro)** se suma `0` (`A + 0 = A`) y se multiplica por `1` (`A • 1 = A`), por lo que el resultado es la variable **`A`**.
  - En el **Teorema 1 (Acotación)** se suma `1` (`A + 1 = 1`) y se multiplica por `0` (`A • 0 = 0`), por lo que la variable `A` desaparece y el resultado es la constante (**`1`** o **`0`**).
- Es la herramienta clave para demostrar el **Teorema 3 (Ley de Absorción)** algebraicamente.

**⚠️ Precisiones / errores comunes:**
- **Cuidado con el álgebra común:** en el álgebra numérica ordinaria `A • 0 = 0` se cumple, pero `A + 1 = 1` **no** existe en los números reales. En Álgebra de Boole `A + 1 = 1` es fundamental porque no hay ningún valor mayor que `1`.
- **Detalle del PDF en la demostración:** si en el oral el profesor te pide escribir la demostración de `A + 1 = 1`, escribí los paréntesis `(A + Ā) . (A + 1)` y `1 . (A + 1)` al aplicar el Ax 2 y el Ax 4, porque en el apunte faltan por una omisión tipográfica, pero son indispensables para que el producto afecte a toda la suma `A + 1`.

**🎤 Cómo decirlo en el oral:**
> "El Teorema 1 es la Ley de Acotación, y establece que `A + 1 = 1` y `A • 0 = 0`. Para demostrar `A + 1 = 1` algebraicamente partiendo del `1`: por el Axioma 4 de complemento, `1 = A + Ā`; por el Axioma 3 de elemento neutro, `1 = A + (Ā • 1)`; por el Axioma 2 de propiedad distributiva, `1 = (A + Ā) • (A + 1)`; nuevamente por el Axioma 4, `1 = 1 • (A + 1)`; y finalmente por el Axioma 3 de elemento neutro, `1 = A + 1`."

---

## 2.3 Teorema 2: Ley de Idempotencia

> 📖 **Textual del material:** "Teorema 2: Ley de Idempotencia
> Este teorema establece que:
> A + A = A
> A • A = A"

**🗣️ En palabras simples:**
Operar una variable lógica consigo misma —ya sea sumándola lógicamente (`A + A`) o multiplicándola lógicamente (`A • A`)— no cambia nada: da como resultado la misma variable `A`. En lógica, repetir la misma información no agrega ni quita verdad.

**🔍 Desglose de la jerga:**
- **"Idempotencia":** palabra que proviene del latín *idem* ("lo mismo") y *potentia* ("poder/potencia"), es decir, la propiedad de un elemento que al operarse consigo mismo reiteradas veces conserva exactamente el mismo valor.
- **`A + A = A`:** idempotencia de la suma lógica (en el álgebra clásica sería `2A`, pero en Boole no existen coeficientes distintos de `0` y `1`).
- **`A • A = A`:** idempotencia del producto lógico (en el álgebra clásica sería `A^2`, pero en Boole no existen exponentes mayores que 1).

**💡 Ejemplo:**
- Si `A = 0`: `0 + 0 = 0` (que es `A`) y `0 • 0 = 0` (que es `A`).
- Si `A = 1`: `1 + 1 = 1` (que es `A`) y `1 • 1 = 1` (que es `A`).
- En lenguaje cotidiano (MD1): decir *"Llueve o llueve"* (`A + A`) equivale exactamente a decir *"Llueve"* (`A`).

**🧩 Idea de la demostración:**
*(El material solicita demostrar este teorema en el Desempeño 3, punto 2, pág. 3: "Realice la demostración algebraica de los teoremas 2 y 3". A continuación se desarrolla usando únicamente los axiomas de la Clase 1):*
- **Demostración de `A + A = A` (partiendo de `A`):**
  1. Partimos de `A`. **Por Ax 3 (Elemento Neutro de la suma):** `A = A + 0`
  2. **Por Ax 4 (Complemento: `A • Ā = 0`):** `A = A + (A • Ā)`
  3. **Por Ax 2 (Distributiva de la suma respecto del producto):** `A = (A + A) • (A + Ā)`
  4. **Por Ax 4 (Complemento: `A + Ā = 1`):** `A = (A + A) • 1`
  5. **Por Ax 3 (Elemento Neutro del producto):** `A = A + A`. Queda demostrado.
- **Demostración de `A • A = A` (partiendo de `A`):**
  1. Partimos de `A`. **Por Ax 3 (Elemento Neutro del producto):** `A = A • 1`
  2. **Por Ax 4 (Complemento: `A + Ā = 1`):** `A = A • (A + Ā)`
  3. **Por Ax 2 (Distributiva del producto respecto de la suma):** `A = (A • A) + (A • Ā)`
  4. **Por Ax 4 (Complemento: `A • Ā = 0`):** `A = (A • A) + 0`
  5. **Por Ax 3 (Elemento Neutro de la suma):** `A = A • A`. Queda demostrado.

**🤔 Intuición:**
Una variable booleana representa el estado de una condición (verdadera o falsa). Preguntar dos veces por la misma condición —"¿está cerrada la llave A y está cerrada la llave A?" o "¿está cerrada la llave A o está cerrada la llave A?"— depende única y exclusivamente de si la llave A está cerrada.

**🔗 Conexiones:**
- Como consecuencia de la idempotencia (y la asociatividad), en el Álgebra de Boole `A + A + A + ... + A = A` y `A • A • A • ... • A = A`.
- En las demostraciones algebraicas (por ejemplo, en el Desempeño 4, ejercicio b, pág. 4, donde aparecen dos términos `y . z` repetidos y en el paso siguiente queda uno solo), la Ley de Idempotencia permite **eliminar términos duplicados** al simplificar o, inversamente, **duplicar un término existente** cuando se necesita factorizar con dos grupos distintos.

**⚠️ Precisiones / errores comunes:**
- **No confundir `A + A = A` con `A + Ā = 1`:**
  - Si ambos términos son **iguales** (`A + A` o `A • A`), se aplica **Idempotencia (Teorema 2)** y el resultado es **`A`**.
  - Si un término es el **complemento** del otro (`A + Ā` o `A • Ā`), se aplica **Complemento (Axioma 4)** y el resultado es **`1`** (en la suma) o **`0`** (en el producto).
- Tampoco escribir jamás `2A` ni `A^2`: en el Álgebra de Boole no existen ni el número `2` ni las potencias algebraicas.

**🎤 Cómo decirlo en el oral:**
> "El Teorema 2 es la Ley de Idempotencia, la cual establece que `A + A = A` y `A • A = A`. Para demostrar `A + A = A` a partir de los axiomas, partimos de `A`: por el Axioma 3 de elemento neutro es `A + 0`; por el Axioma 4 de complemento reemplazamos `0` por `A • Ā`, quedando `A + (A • Ā)`; por el Axioma 2 de propiedad distributiva esto es `(A + A) • (A + Ā)`; por el Axioma 4, `A + Ā` es `1`, quedando `(A + A) • 1`; y por el Axioma 3 de elemento neutro resulta `A + A`."

---

## 2.4 Teorema 3: Ley de Absorción

> 📖 **Textual del material:** "Teorema 3: Ley de Absorción
> Este teorema establece que:
> A + (A • B) = A
> A • (A + B) = A"
>
> 📖 **Textual del material (demostración por Tabla de Verdad en pág. 3):** "Tomemos el Teorema de Absorción.
> Teorema de Absorción
> A + A . B = A
>
> | A | B | A . B | A + A . B |
> |---|---|---|---|
> | 0 | 0 | 0 | 0 |
> | 0 | 1 | 0 | 0 |
> | 1 | 0 | 0 | 1 |
> | 1 | 1 | 1 | 1 |
>
> Aquí podemos ver entonces, que la distribución de valores de verdad de A, y de A + A.B (0 0 1 1) es exactamente la misma, lo que nos asegura que son expresiones iguales."

**🗣️ En palabras simples:**
Cuando tenés una variable `A` combinada (mediante suma o producto) con un paréntesis que usa la **operación opuesta** y que **vuelve a contener a la misma variable `A`** acompañada de otra variable `B`, la variable `B` resulta totalmente redundante: `A` "absorbe" todo el término `(A • B)` o `(A + B)` y el resultado final es simplemente `A`.

**🔍 Desglose de la jerga:**
- **"Ley de Absorción":** recibe este nombre porque la variable `A` que está fuera del paréntesis "absorbe" o hace desaparecer al término compuesto que contiene a `A` y a `B`, eliminando por completo la dependencia respecto de `B`.
- **`A + (A • B) = A`:** absorción de un producto dentro de una suma.
- **`A • (A + B) = A`:** absorción de una suma dentro de un producto.
- **"Distribución de valores de verdad (0 0 1 1)":** la columna completa de resultados en la tabla de verdad para todas las combinaciones posibles de entrada.

**💡 Ejemplo:**
- **El ejemplo del material (Tabla de verdad de `A + A . B = A` en pág. 3):**
  - Si `A = 0` y `B = 0` → `A . B = 0` → `A + A . B = 0 + 0 = 0` (coincide con `A = 0`).
  - Si `A = 0` y `B = 1` → `A . B = 0` → `A + A . B = 0 + 0 = 0` (coincide con `A = 0`).
  - Si `A = 1` y `B = 0` → `A . B = 0` → `A + A . B = 1 + 0 = 1` (coincide con `A = 1`).
  - Si `A = 1` y `B = 1` → `A . B = 1` → `A + A . B = 1 + 1 = 1` (coincide con `A = 1`).
  - En los 4 casos la columna de `A + A . B` es `0, 0, 1, 1`, idéntica a la columna de `A`.

**🧩 Idea de la demostración:**
1. **Por Tabla de Verdad (explícita en pág. 3 del material):**
   Se construye la tabla con las 4 combinaciones de `A` y `B`, se calcula la columna intermedia `A . B` y luego `A + A . B`. Como las columnas de `A` y de `A + A . B` tienen exactamente la misma distribución de valores de verdad (`0, 0, 1, 1`), ambas expresiones son iguales.
2. **Demostración algebraica (solicitada en Desempeño 3, punto 2, pág. 3 — contexto adicional para el oral):**
   - **Para `A + (A • B) = A` (partiendo del primer miembro):**
     1. Partimos de `A + (A • B)`.
     2. **Por Ax 3 (Elemento Neutro del producto: `A = A • 1`):** reemplazamos la primera `A` por `A • 1`:
        `(A • 1) + (A • B)`
     3. **Por Ax 2 (Propiedad Distributiva, sacando factor común `A`):**
        `A • (1 + B)`
     4. **Por Ax 1 (Conmutativa) y Teorema 1 (Ley de Acotación: `B + 1 = 1`):**
        `A • 1`
     5. **Por Ax 3 (Elemento Neutro del producto):**
        `A`. Queda demostrado.
   - **Para `A • (A + B) = A` (partiendo del primer miembro):**
     1. Partimos de `A • (A + B)`.
     2. **Por Ax 3 (Elemento Neutro de la suma: `A = A + 0`):**
        `(A + 0) • (A + B)`
     3. **Por Ax 2 (Propiedad Distributiva de la suma respecto del producto):**
        `A + (0 • B)`
     4. **Por Ax 1 (Conmutativa) y Teorema 1 (Ley de Acotación: `B • 0 = 0`):**
        `A + 0`
     5. **Por Ax 3 (Elemento Neutro de la suma):**
        `A`. Queda demostrado.
     *(Alternativa usando Idempotencia: `A • (A + B) = (A • A) + (A • B)` por Ax 2; `= A + (A • B)` por T2 Idempotencia; `= A` por la primera parte de Absorción).*

**🤔 Intuición:**
Pensalo en términos de condiciones: para que se cumpla `"A o (A y B)"`, si `A` es falsa, entonces `(A y B)` también es falsa y todo da falso (`0`); si `A` es verdadera, ya alcanza para que toda la expresión sea verdadera (`1`) sin importar qué pase con `B`. Por lo tanto, el valor de verdad depende exclusivamente de `A`.

**🔗 Conexiones:**
- Su demostración algebraica utiliza en cadena el **Axioma 3 (Neutro)**, el **Axioma 2 (Distributiva)** y el **Teorema 1 (Acotación)**.
- Es uno de los teoremas más usados en la práctica para **simplificar circuitos y expresiones booleanas**, ya que permite eliminar variables enteras (`B`) de un solo paso.

**⚠️ Precisiones / errores comunes:**
- **Condición clave para que haya Absorción:**
  1. Las dos operaciones deben ser **distintas** (una suma con un producto adentro `A + (A • B)`, o un producto con una suma adentro `A • (A + B)`). Si fueran iguales (`A + (A + B)`), no se absorbe `B`, sino que por asociatividad e idempotencia queda `A + B`.
  2. La variable de afuera y una de las de adentro deben ser **exactamente la misma y con el mismo signo de negación** (ambas `A`, o ambas `Ā`).
- **Diferencia con una variante muy común de examen (Desempeño 6a, pág. 5):**
  Si la variable de adentro está **negada** respecto de la de afuera, por ejemplo `A + (Ā • B)`, **NO es el Teorema de Absorción**, ni da `A`: aplicando el **Axioma 2 (Distributiva)** y el **Axioma 4 (Complemento)** da `(A + Ā) • (A + B) = 1 • (A + B) = A + B` (se absorbe solo el complemento `Ā`, pero sobrevive `B`). En el Desempeño 6a aparece como `A + Ā • B • C = A + B • C`. ¡No confundir `A + A • B = A` con `A + Ā • B = A + B`!

**🎤 Cómo decirlo en el oral:**
> "El Teorema 3 es la Ley de Absorción y establece que `A + (A • B) = A` y `A • (A + B) = A`. Algebraicamente se demuestra escribiendo la primera `A` como `A • 1` por el Axioma 3 de elemento neutro, luego aplicando el Axioma 2 de propiedad distributiva para obtener `A • (1 + B)`, que por el Teorema 1 de acotación es `A • 1`, y nuevamente por el Axioma 3 es igual a `A`. También se demuestra por tabla de verdad verificando que la distribución de valores de verdad de `A` y de `A + A • B` es exactamente la misma: `0, 0, 1, 1`."

---

## 2.5 Teorema 4: Ley de Asociatividad

> 📖 **Textual del material:** "Teorema 4: Ley de Asociatividad
> Tanto la suma como el producto lógico gozan de esta propiedad.
> A + (B + C) = (A + B) + C = A + B + C
> A . (B . C) = (A . B) . C = A . B . C"

**🗣️ En palabras simples:**
Cuando tenés tres (o más) variables conectadas **todas por la misma operación** (todas sumándose con `+`, o todas multiplicándose con `.`), no importa en qué orden las agrupes con paréntesis: el resultado final es exactamente el mismo. Gracias a esto, se pueden quitar los paréntesis y escribir directamente `A + B + C` o `A . B . C`.

**🔍 Desglose de la jerga:**
- **"Asociatividad":** propiedad de una operación binaria que permite reagrupar los operandos mediante paréntesis sin alterar el resultado.
- **"Tanto la suma como el producto lógico gozan de esta propiedad":** la asociatividad se cumple cuando todas las operaciones son sumas lógicas (`+`) o cuando todas son productos lógicos (`.`), pero **no** si se mezclan suma y producto en la misma expresión.
- **`= A + B + C` y `= A . B . C`:** indica que, al ser el resultado independiente del agrupamiento, la notación sin paréntesis carece de ambigüedad.

**💡 Ejemplo:**
- Si `A = 1`, `B = 0`, `C = 1`:
  - `A + (B + C) = 1 + (0 + 1) = 1 + 1 = 1`.
  - `(A + B) + C = (1 + 0) + 1 = 1 + 1 = 1`.
  - Ambos dan `1`.
- Para el producto:
  - `A . (B . C) = 1 . (0 . 1) = 1 . 0 = 0`.
  - `(A . B) . C = (1 . 0) . 1 = 0 . 1 = 0`.
  - Ambos dan `0`.

**🧩 Idea de la demostración:**
- **Por Tabla de Verdad (método estándar para 3 variables `A, B, C`):**
  Se construye una tabla de verdad de `2^3 = 8` filas (desde `000` hasta `111`).
  - Para la suma: tanto `A + (B + C)` como `(A + B) + C` dan `0` únicamente en la primera fila (`0, 0, 0`) y dan `1` en las 7 filas restantes (`0, 1, 1, 1, 1, 1, 1, 1`). Al coincidir la distribución de valores de verdad, son iguales.
  - Para el producto: tanto `A . (B . C)` como `(A . B) . C` dan `1` únicamente en la última fila (`1, 1, 1`) y dan `0` en las 7 filas anteriores (`0, 0, 0, 0, 0, 0, 0, 1`). Al coincidir la distribución de valores de verdad, son iguales.

**🤔 Intuición:**
En un circuito eléctrico, conectar tres llaves `A`, `B` y `C` **en serie** (`A . B . C`) deja pasar la corriente solo si las tres están cerradas, sin importar si pensás primero en el par `(A y B)` en serie con `C`, o en `A` en serie con el par `(B y C)`. Análogamente, tres llaves **en paralelo** (`A + B + C`) dejan pasar la corriente si al menos una está cerrada, sin importar cómo las agrupes mentalmente.

**🔗 Conexiones:**
- Junto con el **Axioma 1 (Propiedad Conmutativa)** de la Clase 1, la Ley de Asociatividad permite reordenar y reagrupar libremente los términos de cualquier suma lógica o los factores de cualquier producto lógico (como se hace en el Desempeño 4a, pág. 4, al reordenar factores `(x + y) . (x + z) . (x + y)` como `(x + z) . (x + y) . (x + y)`).
- En la **Clase 3 (Compuertas lógicas)**, esta ley justifica que podamos usar compuertas OR o AND de 3 o más entradas equivalentes a conectar dos compuertas de 2 entradas en cascada.

**⚠️ Precisiones / errores comunes:**
- **¡No asociar cuando las operaciones son distintas!**
  `A + (B . C)` **NO** es igual a `(A + B) . C`. Si hay mezcla de suma y producto, no se puede aplicar Asociatividad; ahí la propiedad que rige es el **Axioma 2 (Propiedad Distributiva)**: `A + (B . C) = (A + B) . (A + C)`.
- Recordar que en este curso la Asociatividad está catalogada como **Teorema 4**, no como axioma.

**🎤 Cómo decirlo en el oral:**
> "El Teorema 4 es la Ley de Asociatividad y establece que tanto la suma como el producto lógico gozan de esta propiedad: `A + (B + C) = (A + B) + C = A + B + C` para la suma lógica, y `A . (B . C) = (A . B) . C = A . B . C` para el producto lógico."

---

## 2.6 Teorema 5: Ley de Involución

> 📖 **Textual del material:** "Teorema 5: Ley de Involución
> Establece que negar dos veces un elemento es igual al mismo elemento:
> A̿ = A"

*(Nota tipográfica: `A̿` representa la variable `A` con doble barra superior de negación, es decir, el complemento del complemento de `A`: `(Ā)̅ = A`).*

**🗣️ En palabras simples:**
Si a una variable lógica `A` la negás una vez (`Ā`, invirtiendo su valor) y al resultado lo volvés a negar (`A̿`, invirtiendo nuevamente su valor), volvés exactamente al valor original de `A`. Dos negaciones seguidas sobre el mismo elemento se cancelan entre sí.

**🔍 Desglose de la jerga:**
- **"Involución":** en matemática, una función o transformación es una *involución* cuando al aplicarla dos veces seguidas se obtiene la identidad (el elemento original).
- **"Negar dos veces un elemento":** aplicar la operación de complementación o negación de manera sucesiva sobre la misma expresión.
- **`A̿ = A`:** la primera barra sobre `A` indica el complemento de `A` (`Ā`), y la segunda barra encima de la primera indica el complemento de `Ā`.

**💡 Ejemplo:**
- Si `A = 0`:
  - Primera negación: `Ā = 1`.
  - Segunda negación: `A̿ = 1̅ = 0 = A`.
- Si `A = 1`:
  - Primera negación: `Ā = 0`.
  - Segunda negación: `A̿ = 0̅ = 1 = A`.

**🧩 Idea de la demostración:**
- **Por Tabla de Verdad:**
  | A | Ā | A̿ |
  |---|---|---|
  | 0 | 1 | 0 |
  | 1 | 0 | 1 |
  Como la columna de `A` (`0, 1`) y la columna de `A̿` (`0, 1`) tienen exactamente la misma distribución de valores de verdad, queda demostrado que `A̿ = A`.
- *(Contexto adicional — Idea algebraica por unicidad del complemento, Ax 4):* Según el Axioma 4, el complemento de `Ā` (que es `A̿`) cumple `Ā + A̿ = 1` y `Ā • A̿ = 0`. Pero por Conmutativa (Ax 1) y el mismo Axioma 4, `A` también cumple `Ā + A = 1` y `Ā • A = 0`. Por lo tanto, el complemento de `Ā` es `A`, es decir, `A̿ = A`.

**🤔 Intuición:**
Si la negación lógica invierte el estado (de encendido a apagado, o de apagado a encendido), accionar un inversor dos veces seguidas te devuelve al estado inicial. Es idéntico a la ley de doble negación de la lógica proposicional (`¬(¬p) ⇔ p`) vista en Matemática Discreta 1.

**🔗 Conexiones:**
- Se relaciona directamente con la operación **Negación** definida en la **Clase 1 (pág. 4-5)** y con el **Axioma 4 (Complemento)**.
- Se utiliza constantemente en combinación con el **Teorema 6 (Ley de De Morgan)**: cuando aplicás De Morgan sobre una expresión que ya tenía alguna variable negada (por ejemplo, al negar `Ā + B` en el Desempeño 4c, pág. 4), queda `A̿ . B̄`, e inmediatamente por la **Ley de Involución (Teorema 5)** se simplifica `A̿` como `A`, obteniendo `A . B̄`.

**⚠️ Precisiones / errores comunes:**
- La doble barra debe cubrir **exactamente la misma expresión** para poder cancelarse.
  - Por ejemplo, en `(A + B)̿`, las dos barras cubren toda la suma `A + B`, por lo tanto por Involución da `A + B`.
  - En cambio, si tenés una barra larga sobre una suma de variables que tienen barras individuales, como `(Ā + B̄)̅`, **NO se cancelan las barras directamente** dejando `A + B`: primero hay que aplicar **De Morgan** para partir la barra larga (cambiando `+` por `•`), quedando `A̿ • B̿`, y recién ahí por **Involución** queda `A • B`.

**🎤 Cómo decirlo en el oral:**
> "El Teorema 5 es la Ley de Involución, y establece que negar dos veces un elemento es igual al mismo elemento: `A` doblemente negado es igual a `A` (`A̿ = A`)."

---

## 2.7 Teorema 6: Ley de De Morgan

> 📖 **Textual del material:** "Teorema 6: Ley de De Morgan
> Establece que:
> A̅+̅B̅ = Ā • B̄
> A̅•̅B̅ = Ā + B̄"

*(Nota sobre la notación del PDF en pág. 2: en la primera igualdad del material, el primer miembro tiene una única barra horizontal continua que abarca toda la suma `A + B`, es decir `(A + B)̅ = Ā • B̄`; en la segunda igualdad, el primer miembro tiene una única barra horizontal continua que abarca todo el producto `A • B`, es decir `(A • B)̅ = Ā + B̄`. En cambio, en los segundos miembros, las barras están separadas sobre cada variable individual: `Ā` y `B̄`).*

**🗣️ En palabras simples:**
Las Leyes de De Morgan nos dicen cómo "repartir" o "romper" una barra de negación larga que cubre toda una suma o todo un producto:
1. **La negación de una suma lógica** es igual al **producto lógico** de las negaciones individuales: al cortar la barra larga sobre `A + B`, quedan `Ā` y `B̄` separados, pero el `+` se transforma en `•`.
2. **La negación de un producto lógico** es igual a la **suma lógica** de las negaciones individuales: al cortar la barra larga sobre `A • B`, quedan `Ā` y `B̄` separados, pero el `•` se transforma en `+`.

Regla mnemotécnica clásica: *"Rompé la barra y cambiá el signo de la operación (de `+` a `•`, o de `•` a `+`)"*.

**🔍 Desglose de la jerga:**
- **`A̅+̅B̅` o `(A + B)̅`:** el complemento o negación del resultado total de la suma lógica `A + B`.
- **`Ā • B̄`:** el producto lógico entre el complemento de `A` y el complemento de `B`.
- **`A̅•̅B̅` o `(A • B)̅`:** el complemento o negación del resultado total del producto lógico `A • B`.
- **`Ā + B̄`:** la suma lógica entre el complemento de `A` y el complemento de `B`.

**💡 Ejemplo:**
- Verifiquemos para `A = 1` y `B = 0`:
  - **Primera ley `(A + B)̅ = Ā • B̄`:**
    - Primer miembro: `A + B = 1 + 0 = 1`; al negarlo: `1̅ = 0`.
    - Segundo miembro: `Ā • B̄ = 1̅ • 0̅ = 0 • 1 = 0`. Coinciden (`0 = 0`).
  - **Segunda ley `(A • B)̅ = Ā + B̄`:**
    - Primer miembro: `A • B = 1 • 0 = 0`; al negarlo: `0̅ = 1`.
    - Segundo miembro: `Ā + B̄ = 1̅ + 0̅ = 0 + 1 = 1`. Coinciden (`1 = 1`).
- **Ejemplo del material (Desempeño 4a y 4c, pág. 4):**
  - En el Desempeño 4a aparece `(x̅ . y)̅` (el producto de `x̅` por `y`, todo negado con una barra larga): aplicando De Morgan se parte la barra y el `.` pasa a `+`, quedando `(x̿ + y̅)`, y por Involución (`x̿ = x`) resulta `(x + y̅)`.
  - En el Desempeño 4c se tiene `((Ā + B) . (A + B̄))̅`: una barra grande cubre el producto de dos paréntesis. Al aplicar De Morgan al producto central, pasa a ser la suma de los paréntesis negados: `(Ā + B)̅ + (A + B̄)̅`. En el paso siguiente se vuelve a aplicar De Morgan a cada paréntesis: `(A̿ . B̄) + (Ā . B̿)`, que por Involución es `(A . B̄) + (Ā . B)`.

**🧩 Idea de la demostración:**
- **Por Tabla de Verdad (para ambas leyes simultáneamente):**

  | A | B | Ā | B̄ | A + B | (A + B)̅ | Ā • B̄ | A • B | (A • B)̅ | Ā + B̄ |
  |---|---|---|---|---|---|---|---|---|---|
  | 0 | 0 | 1 | 1 | 0 | **1** | **1** | 0 | **1** | **1** |
  | 0 | 1 | 1 | 0 | 1 | **0** | **0** | 0 | **1** | **1** |
  | 1 | 0 | 0 | 1 | 1 | **0** | **0** | 0 | **1** | **1** |
  | 1 | 1 | 0 | 0 | 1 | **0** | **0** | 1 | **0** | **0** |

  - La columna de `(A + B)̅` tiene la distribución `(1, 0, 0, 0)`, idéntica a la columna de `Ā • B̄` `(1, 0, 0, 0)`.
  - La columna de `(A • B)̅` tiene la distribución `(1, 1, 1, 0)`, idéntica a la columna de `Ā + B̄` `(1, 1, 1, 0)`.

**🤔 Intuición:**
- ¿Cuándo es falso que *"A o B están encendidas"* (`(A + B)̅`)? Únicamente cuando **A está apagada Y B está apagada** (`Ā • B̄`).
- ¿Cuándo es falso que *"A y B están ambas encendidas"* (`(A • B)̅`)? Cuando **A está apagada O B está apagada** (`Ā + B̄`).

**🔗 Conexiones:**
- Es la versión en Álgebra de Boole de las **Leyes de De Morgan de la lógica proposicional** vistas en Matemática Discreta 1: `¬(p ∨ q) ⇔ ¬p ∧ ¬q` y `¬(p ∧ q) ⇔ ¬p ∨ ¬q`, y de las leyes de complemento de unión e intersección de conjuntos: `(A ∪ B)^c = A^c ∩ B^c` y `(A ∩ B)^c = A^c ∪ B^c`.
- Se generaliza a 3 o más variables (por asociatividad): `(A + B + C)̅ = Ā • B̄ • C̄` y `(A • B • C)̅ = Ā + B̄ + C̄`.
- Se usa tanto de izquierda a derecha (para romper una barra larga en barras individuales) como de derecha a izquierda (para unificar `Ā • B̄` bajo una sola barra `(A + B)̅`).

**⚠️ Precisiones / errores comunes:**
- **El error más grave y frecuente:** distribuir la barra de negación sin cambiar la operación:
  - `(A + B)̅ ≠ Ā + B̄` (¡FALSO!).
  - `(A • B)̅ ≠ Ā • B̄` (¡FALSO!).
  La negación **NO es distributiva** respecto de la suma ni del producto; al partir la barra de negación **siempre** cambia `+` por `•` y `•` por `+`.
- **Respetar la jerarquía al romper barras múltiples:** si una barra larga abarca una expresión compuesta como `((Ā + B) . (A + B̄))̅` (Desempeño 4c), primero se rompe la barra más externa afectando a la operación principal que une los bloques (el `.` central pasa a `+`), sin tocar todavía los signos internos de cada paréntesis hasta el paso siguiente.

**🎤 Cómo decirlo en el oral:**
> "El Teorema 6 es la Ley de De Morgan, y establece dos igualdades: primero, que la negación de la suma lógica de dos elementos es igual al producto lógico de los complementos de cada elemento, es decir, `(A + B)` todo negado es igual a `Ā • B̄`; y segundo, que la negación del producto lógico de dos elementos es igual a la suma lógica de los complementos de cada elemento, es decir, `(A • B)` todo negado es igual a `Ā + B̄`."

---

## 2.8 Método 1: Demostración Algebraica de Teoremas e Igualdades

> 📖 **Textual del material (pág. 3):** "Hacer una demostración algebraica significa, como lo explicamos la clase anterior, que, partiendo de una de las expresiones, sea el primer miembro o el segundo de la igualdad, se debe ir escribiendo de otra manera hasta llegar al otro miembro, en este caso podríamos partir del A + 1 y llegar a qué es lo mismo que 1, ó partir del 1 y llegar a escribirlo como A + 1."
>
> 📖 **Textual del material (pág. 5, Desempeño 5):** "Recuerde que puede partir del primer miembro de la igualdad y llegar a la segunda o partir de la segunda y llegar a la primera o desarrollar las dos hasta llegar a expresiones idénticas."

**🗣️ En palabras simples:**
Demostrar algebraicamente una igualdad booleana `Expresión 1 = Expresión 2` consiste en transformar una expresión paso a paso, justificando cada renglón con el nombre o número del axioma o teorema aplicado, hasta comprobar que ambos lados son equivalentes. El material habilita **tres caminos válidos**:
1. Partir del **primer miembro** y llegar al segundo.
2. Partir del **segundo miembro** y llegar al primero (como hace el apunte al demostrar `A + 1 = 1` partiendo del `1`).
3. Desarrollar **ambos miembros** por separado hasta que los dos lleguen a una misma expresión idéntica.

**🔍 Desglose de la jerga:**
- **"Primer miembro / segundo miembro de la igualdad":** la expresión que está a la izquierda del signo `=` (primer miembro) y la que está a la derecha del signo `=` (segundo miembro).
- **"Ir escribiendo de otra manera":** sustituir una subexpresión por otra equivalente respaldada por alguno de los 4 axiomas o de los 6 teoremas.
- **"Indicar paso a paso la propiedad empleada" (Desempeño 4 y 6):** requisito metodológico por el cual cada transformación entre un renglón y el siguiente debe estar justificada explícitamente (p. ej. "Por Ax 2", "Por Teorema 6 de De Morgan", etc.).

**💡 Ejemplo:**
- **El ejemplo de la cátedra en el Desempeño 6a (pág. 5): `A + Ā • B • C = A + B • C`** *(demostración breve ilustrando el método)*:
  - Partimos del primer miembro: `A + (Ā • B • C)`
  - **Por Ax 2 (Propiedad Distributiva de la suma `+` respecto del producto entre `Ā` y `(B • C)`):**
    `= (A + Ā) • (A + B • C)`
  - **Por Ax 4 (Complemento: `A + Ā = 1`):**
    `= 1 • (A + B • C)`
  - **Por Ax 3 (Elemento Neutro del producto):**
    `= A + B • C` (llegamos al segundo miembro).

**🔗 Conexiones:**
- Es el método deductivo formal que conecta los **Axiomas (Clase 1)** con los **Teoremas (Clase 2)** y con la **simplificación algebraica de funciones booleanas (Clases 3 y 4)**.

**⚠️ Precisiones / errores comunes:**
- **No se pueden "pasar términos restando" ni "pasar dividiendo":** en el Álgebra de Boole **no existen la resta ni la división**. Nunca pases un término de un miembro al otro cambiando de signo; trabajá siempre transformando un miembro (o cada miembro por su lado) mediante axiomas y teoremas.
- **No saltear el Axioma 4 ni el Axioma 3:** cuando aparece `A + Ā`, primero se reemplaza por `1` (justificando con **Ax 4: Complemento**) y en el paso siguiente se elimina el factor `1` en el producto (justificando con **Ax 3: Elemento Neutro**).

**🎤 Cómo decirlo en el oral:**
> "Hacer una demostración algebraica en el Álgebra de Boole significa partir de una de las expresiones —sea el primer miembro de la igualdad para llegar al segundo, o el segundo miembro para llegar al primero, o bien desarrollar ambos miembros hasta llegar a expresiones idénticas—, reescribiendo la expresión paso a paso mediante la aplicación justificada de los axiomas y teoremas."

---

## 2.9 Método 2: Demostración por Tablas de Verdad

> 📖 **Textual del material (pág. 3):** "Además de la demostración algebraica de un teorema o de cualquier igualdad, también se puede llevar a cabo utilizando las tablas de verdad. ¿Y cómo es ésto? Simplemente se realiza la tabla de verdad, teniendo en cuenta la definición de las operaciones, como lo hacíamos en MD 1 y recordamos en la clase anterior, para cada miembro de la igualdad y si la distribución de valores de verdad coincide es porque las expresiones son iguales. Veamos un ejemplo para alguno de los teoremas enunciados.
> Tomemos el Teorema de Absorción.
> Teorema de Absorción
> A + A . B = A
>
> | A | B | A . B | A + A . B |
> |---|---|---|---|
> | 0 | 0 | 0 | 0 |
> | 0 | 1 | 0 | 0 |
> | 1 | 0 | 0 | 1 |
> | 1 | 1 | 1 | 1 |
>
> Aquí podemos ver entonces, que la distribución de valores de verdad de A, y de A + A.B (0 0 1 1) es exactamente la misma, lo que nos asegura que son expresiones iguales."

**🗣️ En palabras simples:**
Como en el Álgebra de Boole cada variable solo puede valer `0` o `1`, la cantidad de combinaciones posibles de valores para las variables de una expresión es **finita** (`2^n` filas para `n` variables). Por eso, para demostrar que dos expresiones son iguales, alcanza con armar la tabla de verdad evaluando ambos miembros en todas las filas posibles: si las columnas finales de ambos miembros dan exactamente los mismos `0` y `1` fila por fila (tienen la misma "distribución de valores de verdad"), queda demostrado que las dos expresiones son iguales.

**🔍 Desglose de la jerga:**
- **"Tabla de verdad":** tabla exhaustiva que lista todas las combinaciones de valores binarios (`0` y `1`) de las variables de entrada y el resultado de evaluar cada subexpresión y cada miembro de la igualdad.
- **"Teniendo en cuenta la definición de las operaciones":** aplicar las tablas básicas de la Clase 1:
  - Suma lógica (`+`): da `1` si al menos uno es `1` (solo da `0` para `0 + 0`).
  - Producto lógico (`.`): da `1` solo si ambos son `1` (da `0` en cualquier otro caso).
  - Negación (`Ā`): invierte `0` en `1` y `1` en `0`.
- **"Distribución de valores de verdad":** la secuencia ordenada de ceros y unos que resulta en la columna de cada miembro de la igualdad (por ejemplo, `(0 0 1 1)` en el ejemplo del material).

**💡 Ejemplo:**
- En el ejemplo del material (`A + A . B = A`), hay 2 variables (`A` y `B`), por lo que la tabla tiene `2^2 = 4` filas. La columna del segundo miembro (`A`) tiene la distribución `0, 0, 1, 1` y la columna del primer miembro (`A + A . B`) también tiene la distribución `0, 0, 1, 1`. Al coincidir fila por fila, queda demostrada la igualdad.

**🔗 Conexiones:**
- Conecta con las **tablas de verdad de lógica proposicional de Matemática Discreta 1** (allí con `V` y `F`, aquí con `1` y `0`).
- En el **Desempeño 5 (pág. 5)**, el material propone usar este método como **paso previo de verificación**: *"En estas igualdades, primero Verifica por tabla su validez, y en caso de ser verdaderas demuéstralas algebraicamente"*. Si en una sola fila de la tabla los dos miembros dan distinto, la igualdad es **falsa** y no tiene sentido intentar demostrarla algebraicamente.

**⚠️ Precisiones / errores comunes:**
- Para que la comparación por tabla de verdad sea válida, el orden de las combinaciones de las variables de entrada (`A, B, ...`) debe ser el mismo para ambos miembros, y deben coincidir **todas las filas sin excepción**. Basta con que difieran en una sola fila para que las expresiones **no** sean iguales.

**🎤 Cómo decirlo en el oral:**
> "La demostración por tablas de verdad consiste en construir la tabla de verdad para cada miembro de la igualdad, aplicando la definición de las operaciones lógicas (suma lógica, producto lógico y negación). Si la distribución de valores de verdad de ambos miembros coincide exactamente en todas las filas, queda demostrado que las expresiones son iguales."

---

## 2.10 Comprensión Estructural de las Propiedades y Cuadro Comparativo General

> 📖 **Textual del material (pág. 4 y pág. 5):** "Como le pedimos en la clase 1, que trate de comprender los axiomas más allá de las letras o símbolos que se utilicen, se lo recomendamos para que también lo haga con los teoremas. Aprenda y fije todas las propiedades y luego póngalas a prueba en el siguiente desempeño."

**🗣️ En palabras simples:**
Las letras `A`, `B` y `C` con las que se enuncian los axiomas y teoremas son simples "moldes" o contenedores: en su lugar puede ir cualquier variable (`x, y, z`), cualquier variable negada (`Ā, x̅`) o incluso todo un paréntesis completo (como `(x + y)`). Lo que importa es reconocer la **estructura de la operación**, no la letra.

**🔍 Desglose de la jerga:**
- **"Comprender los axiomas y teoremas más allá de las letras o símbolos que se utilicen":** principio de sustitución estructural; si una ley vale para `A`, vale reemplazando `A` en todos los lugares por cualquier expresión booleana compleja `E`.

**💡 Ejemplo (extraído de los Desempeños 4, 5 y 6 del material, págs. 4 y 5):**
- En el **Desempeño 4a (pág. 4)**, se pasa de `(x + y̅) . (x + y̅)` a un solo `(x + y̅)`: aquí se aplicó el **Teorema 2 (Ley de Idempotencia: `A • A = A`)** tomando a todo el paréntesis `(x + y̅)` en el rol de `A`.
- En el **Desempeño 4b (pág. 4)**, se pasa de `y . z . (x + x̅)` a `y . z . 1 = y . z` usando **Ax 4 (`x + x̅ = 1`)** y **Ax 3**, y luego se suma `+ 0` y se reemplaza `0` por `x . x̅` (**Ax 4 leído al revés: `0 = x . x̅`**) para poder factorizar `(z + x̅)`.
- En el **Desempeño 6c (pág. 5)**, aparece la igualdad `A • B + Ā • C + B • C = A • B + Ā • C` *(conocida en la literatura como Teorema del Consenso — contexto adicional)*: se demuestra multiplicando `B • C` por `1 = (A + Ā)` (Ax 3 y Ax 4), distribuyendo `A • B • C + Ā • B • C` (Ax 2) y absorbiendo cada término con `A • B` y `Ā • C` respectivamente mediante el **Teorema 3 (Ley de Absorción)**.

**📊 Tabla comparativa completa: Los 4 Axiomas (Clase 1) vs. Los 6 Teoremas (Clase 2)**

| Categoría | Código y Nombre exacto en el material | Forma para la Suma Lógica (`+`) | Forma para el Producto Lógico (`•` o `.`) | ¿Se demuestra? |
|---|---|---|---|---|
| **Axioma (Clase 1)** | **A1: Propiedad Conmutativa** | `A + B = B + A` | `A • B = B • A` | No (es axioma) |
| **Axioma (Clase 1)** | **A2: Propiedad Distributiva** | `A + (B • C) = (A + B) • (A + C)` | `A • (B + C) = (A • B) + (A • C)` | No (es axioma) |
| **Axioma (Clase 1)** | **A3: Elemento Neutro** | `A + 0 = A` | `A • 1 = A` | No (es axioma) |
| **Axioma (Clase 1)** | **A4: Complemento** | `A + Ā = 1` | `A • Ā = 0` | No (es axioma) |
| **Teorema (Clase 2)** | **Teorema 1: Ley de Acotación** | `A + 1 = 1` | `A • 0 = 0` | **Sí** (Algebraica / Tabla) |
| **Teorema (Clase 2)** | **Teorema 2: Ley de Idempotencia** | `A + A = A` | `A • A = A` | **Sí** (Algebraica / Tabla) |
| **Teorema (Clase 2)** | **Teorema 3: Ley de Absorción** | `A + (A • B) = A` | `A • (A + B) = A` | **Sí** (Algebraica / Tabla) |
| **Teorema (Clase 2)** | **Teorema 4: Ley de Asociatividad** | `A + (B + C) = (A + B) + C = A + B + C` | `A . (B . C) = (A . B) . C = A . B . C` | **Sí** (Tabla de verdad) |
| **Teorema (Clase 2)** | **Teorema 5: Ley de Involución** | `A̿ = A` *(aplica a la negación)* | `A̿ = A` *(aplica a la negación)* | **Sí** (Tabla / Unicidad) |
| **Teorema (Clase 2)** | **Teorema 6: Ley de De Morgan** | `A̅+̅B̅ = Ā • B̄` | `A̅•̅B̅ = Ā + B̄` | **Sí** (Tabla de verdad) |

*(Observación sobre Dualidad — contexto adicional útil para recordar todas las leyes):* Notá que en los axiomas A1 a A4 y en los teoremas T1 a T6 cada propiedad viene en **dos versiones duales**: si en cualquiera de las fórmulas intercambiás todas las sumas (`+`) por productos (`•`) e intercambiás los `0` por `1` (y `1` por `0`), obtenés automáticamente la otra fórmula del mismo axioma o teorema.

---

## 🧠 Resumen esquemático de la clase

- **Diferencia Axioma vs. Teorema:** Ambos son propiedades del Álgebra de Boole, pero los **axiomas** no se demuestran y los **teoremas sí necesitan demostración** para ser tomados como válidos.
- **Teorema 1 — Ley de Acotación:** `A + 1 = 1` y `A • 0 = 0` (el `1` acota o domina a la suma; el `0` acota o anula al producto).
- **Teorema 2 — Ley de Idempotencia:** `A + A = A` y `A • A = A` (operar un elemento consigo mismo reproduce el mismo elemento).
- **Teorema 3 — Ley de Absorción:** `A + (A • B) = A` y `A • (A + B) = A` (`A` absorbe al paréntesis con operación opuesta que contiene a `A`).
- **Teorema 4 — Ley de Asociatividad:** `A + (B + C) = (A + B) + C = A + B + C` y `A . (B . C) = (A . B) . C = A . B . C`.
- **Teorema 5 — Ley de Involución:** `A̿ = A` (negar dos veces un elemento es igual al mismo elemento).
- **Teorema 6 — Ley de De Morgan:** `A̅+̅B̅ = Ā • B̄` (la negación de una suma es el producto de los complementos) y `A̅•̅B̅ = Ā + B̄` (la negación de un producto es la suma de los complementos).
- **Demostración Algebraica:** partir de un miembro de la igualdad y reescribirlo aplicando axiomas/teoremas hasta llegar al otro miembro (o desarrollar ambos hasta una expresión idéntica).
- **Demostración por Tablas de Verdad:** construir la tabla de verdad para cada miembro según la definición de las operaciones; si la distribución de valores de verdad coincide fila a fila, las expresiones son iguales.

---

## ❓ Preguntas probables del oral

1. **¿Qué diferencia hay entre los axiomas y los teoremas del Álgebra de Boole?**
   - **Respuesta:** Tanto los axiomas como los teoremas son propiedades del Álgebra de Boole, pero mientras que los axiomas se toman como válidos o ciertos sin necesidad de demostrar nada (son la base de las demás propiedades), los teoremas **sí necesitan de una demostración** (algebraica o por tabla de verdad) para que sean tomados como válidos.

2. **¿Cuáles son los 6 teoremas del Álgebra de Boole vistos en clase? Nómbrelos con su denominación exacta.**
   - **Respuesta:**
     - Teorema 1: Ley de Acotación.
     - Teorema 2: Ley de Idempotencia.
     - Teorema 3: Ley de Absorción.
     - Teorema 4: Ley de Asociatividad.
     - Teorema 5: Ley de Involución.
     - Teorema 6: Ley de De Morgan.

3. **Enuncie el Teorema 1 (Ley de Acotación) y explique en qué se diferencia del Axioma 3 (Elemento Neutro).**
   - **Respuesta:** La Ley de Acotación establece que `A + 1 = 1` y `A • 0 = 0`. Se diferencia del Axioma 3 (Elemento Neutro: `A + 0 = A` y `A • 1 = A`) en que el elemento neutro (`0` para la suma, `1` para el producto) deja intacta a la variable `A`, mientras que en la Ley de Acotación se opera con el elemento opuesto (`1` en la suma, `0` en el producto), lo que absorbe a la variable `A` y da como resultado la constante `1` o `0`.

4. **Demuestre algebraicamente la Ley de Acotación `A + 1 = 1` tal como está en el material.**
   - **Respuesta:** Partiendo del segundo miembro (`1`):
     - Por el Axioma 4 (Complemento) podemos escribir: `1 = A + Ā`.
     - Por el Axioma 3 (Elemento Neutro) podemos escribir: `1 = A + (Ā . 1)`.
     - Por el Axioma 2 (Propiedad Distributiva) podemos escribir: `1 = (A + Ā) . (A + 1)`.
     - Por el Axioma 4 (Complemento) quedaría: `1 = 1 . (A + 1)`.
     - Y por el Axioma 3 (Elemento Neutro) quedará: `1 = A + 1`.

5. **Enuncie y demuestre algebraicamente el Teorema 2 (Ley de Idempotencia).**
   - **Respuesta:** La Ley de Idempotencia establece que `A + A = A` y `A • A = A`. Para demostrar `A + A = A` partiendo de `A`: por el Axioma 3 (Elemento Neutro) `A = A + 0`; por el Axioma 4 (Complemento) `A = A + (A • Ā)`; por el Axioma 2 (Distributiva) `A = (A + A) • (A + Ā)`; por el Axioma 4 `A = (A + A) • 1`; y por el Axioma 3 `A = A + A`. (Para `A • A = A` se parte de `A = A • 1 = A • (A + Ā) = (A • A) + (A • Ā) = (A • A) + 0 = A • A`).

6. **Enuncie el Teorema 3 (Ley de Absorción) y explique cómo se demuestra por Tabla de Verdad en el material.**
   - **Respuesta:** La Ley de Absorción establece que `A + (A • B) = A` y `A • (A + B) = A`. Por tabla de verdad, para `A + A . B = A` se evalúan las 4 combinaciones de `A` y `B` (`00, 01, 10, 11`), se calcula `A . B` (`0, 0, 0, 1`) y luego `A + A . B` (`0, 0, 1, 1`). Como la distribución de valores de verdad de `A` y de `A + A . B` es exactamente la misma (`0 0 1 1`), queda demostrado que las expresiones son iguales.

7. **¿Cómo se demuestra algebraicamente la Ley de Absorción `A + (A • B) = A`?**
   - **Respuesta:** Partiendo del primer miembro `A + (A • B)`, por el Axioma 3 (Elemento Neutro) escribimos la primera `A` como `A • 1`, obteniendo `(A • 1) + (A • B)`. Aplicando el Axioma 2 (Propiedad Distributiva) sacamos factor común `A`, quedando `A • (1 + B)`. Por el Teorema 1 (Ley de Acotación, `B + 1 = 1`), esto es `A • 1`, y nuevamente por el Axioma 3 (Elemento Neutro) es igual a `A`.

8. **¿Es lo mismo `A + (A • B)` que `A + (Ā • B)`? Justifique.**
   - **Respuesta:** No. `A + (A • B)` es el Teorema 3 (Ley de Absorción) y es igual a `A`. En cambio, en `A + (Ā • B)` la variable dentro del producto está complementada; si aplicamos el Axioma 2 (Distributiva de la suma respecto del producto) queda `(A + Ā) • (A + B)`, que por el Axioma 4 (Complemento) es `1 • (A + B)` y por el Axioma 3 (Elemento Neutro) da `A + B`.

9. **Enuncie el Teorema 4 (Ley de Asociatividad). ¿Es un axioma o un teorema en nuestro curso?**
   - **Respuesta:** En nuestro curso es el **Teorema 4**. Establece que tanto la suma como el producto lógico gozan de esta propiedad: `A + (B + C) = (A + B) + C = A + B + C` y `A . (B . C) = (A . B) . C = A . B . C`.

10. **Enuncie el Teorema 5 (Ley de Involución).**
    - **Respuesta:** La Ley de Involución establece que negar dos veces un elemento es igual al mismo elemento: `A̿ = A`.

11. **Enuncie el Teorema 6 (Ley de De Morgan) con precisión.**
    - **Respuesta:** La Ley de De Morgan establece que:
      1. `A̅+̅B̅ = Ā • B̄` (el complemento de una suma lógica es igual al producto lógico de los complementos).
      2. `A̅•̅B̅ = Ā + B̄` (el complemento de un producto lógico es igual a la suma lógica de los complementos).

12. **¿En qué consisten los dos modos de demostración de teoremas o igualdades que presenta la Clase 2?**
    - **Respuesta:**
      1. **Demostración algebraica:** consiste en partir de uno de los miembros de la igualdad (el primero o el segundo) e ir escribiéndolo de otra manera mediante axiomas y teoremas hasta llegar al otro miembro (o desarrollar ambos miembros hasta llegar a expresiones idénticas).
      2. **Demostración por tablas de verdad:** consiste en construir la tabla de verdad para cada miembro de la igualdad teniendo en cuenta la definición de las operaciones; si la distribución de valores de verdad coincide exactamente, las expresiones son iguales.

---

## 📚 Glosario de la clase

| Término | Definición breve fiel al material |
|---|---|
| **Teorema (en Álgebra de Boole)** | Propiedad del Álgebra de Boole que, a diferencia de los axiomas, sí necesita de una demostración para ser tomada como válida. |
| **Teorema 1: Ley de Acotación** | Teorema que establece que `A + 1 = 1` y `A • 0 = 0`. |
| **Teorema 2: Ley de Idempotencia** | Teorema que establece que `A + A = A` y `A • A = A`. |
| **Teorema 3: Ley de Absorción** | Teorema que establece que `A + (A • B) = A` y `A • (A + B) = A`. |
| **Teorema 4: Ley de Asociatividad** | Teorema según el cual tanto la suma como el producto lógico cumplen: `A + (B + C) = (A + B) + C = A + B + C` y `A . (B . C) = (A . B) . C = A . B . C`. |
| **Teorema 5: Ley de Involución** | Teorema que establece que negar dos veces un elemento es igual al mismo elemento: `A̿ = A`. |
| **Teorema 6: Ley de De Morgan** | Teorema que establece que `A̅+̅B̅ = Ā • B̄` y `A̅•̅B̅ = Ā + B̄`. |
| **Demostración algebraica** | Procedimiento que consiste en partir de una de las expresiones (primer o segundo miembro de la igualdad) e ir reescribiéndola mediante axiomas y teoremas hasta llegar al otro miembro (o desarrollar ambas hasta llegar a expresiones idénticas). |
| **Demostración por Tabla de Verdad** | Procedimiento que consiste en realizar la tabla de verdad para cada miembro de la igualdad según la definición de las operaciones; si la distribución de valores de verdad coincide, las expresiones son iguales. |
| **Distribución de valores de verdad** | Secuencia de valores `0` y `1` que toma una expresión booleana en su columna de la tabla de verdad para todas las combinaciones posibles de sus variables. |
