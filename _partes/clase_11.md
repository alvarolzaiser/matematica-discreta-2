# Clase 11 — Sistemas de Ecuaciones: Sistemas Incompatibles y Sistemas Compatibles Indeterminados

## 🗺️ Mapa de la clase

- **1. Propósito y ubicación en la Unidad 3 (Sistemas de Ecuaciones):**
  - Continuación de la aplicación del **método general de resolución** (reducción gaussiana a la matriz canónica equivalente) iniciado en la Clase 10.
  - Paso de los sistemas con solución única (Compatibles Determinados, vistos en Clase 10) a los dos casos restantes de la clasificación: **Sistemas Incompatibles** y **Sistemas Compatibles Indeterminados**.
- **2. Sistemas Incompatibles (sin solución):**
  - **11.1** Objetivos y propósito de la Clase 11.
  - **11.2** Definición de **Sistema Incompatible** y condición matricial mediante la comparación del **rango de la matriz de los coeficientes** y el **rango de la matriz ampliada** en la forma canónica (con uso de la columna de control).
  - **11.3** Observación teórica sobre la **detección temprana por contradicción** (`0 = k` con `k ≠ 0`) sin necesidad de completar todos los pasos hasta la matriz canónica.
- **3. Estructura matricial y equivalencia de sistemas lineales:**
  - **11.4** Reacomodamiento (ordenamiento) del sistema y definición de las **tres matrices fundamentales**: **Matriz de los coeficientes (`A`)**, **Matriz o vector de los términos independientes (`B`)** y **Matriz o vector de las incógnitas (`X`)**, junto con el concepto de **coeficientes**.
  - **11.5** **Forma matricial del sistema de ecuaciones** (`A • X = B`) y compatibilidad de órdenes para el producto matricial.
  - **11.6** **Matriz ampliada del sistema (`A°`)** y justificación teórica de por qué las **operaciones elementales** (`H_(i,j)(k)`) producen un **sistema equivalente** con las mismas soluciones.
- **4. Sistemas Compatibles Indeterminados (infinitas soluciones):**
  - **11.7** Condición matricial de **Sistema Compatible** y de **Sistema Compatible Indeterminado** (igualdad de rangos menor al número de incógnitas) y cuadro clasificatorio completo.
  - **11.8** Concepto de **variables libres o independientes**, variables dependientes y regla exacta para calcular la cantidad de variables libres (`número de incógnitas − rango de la matriz ampliada`).
  - **11.9** Construcción del vector **Solución General del Sistema de Ecuaciones (`X*`)** mediante el despeje de las incógnitas principales en función de la(s) variable(s) libre(s).
  - **11.10** Obtención de **Soluciones Particulares** a partir de la solución general asignando valores numéricos a la variable libre (existencia de infinitas soluciones particulares).
  - **11.11** Síntesis del **Método General de Resolución** aplicado a sistemas incompatibles e indeterminados.
- **5. Casos especiales y validación de soluciones en problemas reales:**
  - **11.12** **Sistemas con solución asegurada (Sistemas Homogéneos)** y la **solución trivial** (evaluados en el Desempeño de Síntesis de la clase).
  - **11.13** **Validación de la respuesta en problemas aplicados**: diferencia entre la **solución matemática** y las soluciones válidas según el contexto (restricción a números naturales `ℕ`, condición de divisibilidad/múltiplos enteros y restricción a reales no negativos `ℝ≥0` mediante inecuaciones).

### Prerrequisitos (conceptos de clases previas que hay que dominar)
- **Clases 6, 7 y 8 (Matrices, Operaciones Elementales, Matriz Canónica y Rango):**
  - Multiplicación de matrices (`A_(n×m) • X_(m×1) = B_(n×1)`).
  - Operaciones elementales por fila (`H_i(k)`, `H_(i,j)(k)`, permutación) y columna de control.
  - **Matriz canónica** (escalonada reducida por filas: elementos conductores iguales a `1`, ceros en el resto de la columna del elemento conductor, filas nulas abajo).
  - **Rango de una matriz (`ρ(A)`)**: número de filas no nulas de su matriz canónica equivalente.
- **Clase 9 (Introducción a Ecuaciones y Sistemas de Ecuaciones Lineales):**
  - Definición de ecuación lineal, raíz o solución, sistema de ecuaciones lineales, sistema homogéneo (términos independientes nulos) y no homogéneo, sistemas equivalentes y clasificación general según sus soluciones.
- **Clase 10 (Método General de Resolución y Sistemas Compatibles Determinados):**
  - Pasos del método general, observación del rango de `A` (sin la última columna) y del rango de `A°` (con la última columna), y resolución de Sistemas Compatibles Determinados (`ρ(A) = ρ(A°) = m`).

---

## 11.1 Objetivos y Propósito de la Clase 11

> 📖 **Textual del material:**
> "SISTEMAS DE ECUACIONES
> • Sistemas Incompatibles y Sistemas Compatibles Indeterminados
> Al finalizar la clase los alumnos:
> • Aplicar el método general de resolución de sistemas de ecuaciones.
> • Buscar soluciones a problemas y validar su respuesta.
> • Clasificar los sistemas de ecuaciones de acuerdo a las soluciones obtenidas."
>
> "INTRODUCCIÓN: Hoy continuamos trabajando son sistemas de ecuaciones, pero vamos a encontrar ahora, soluciones diferentes a las trabajadas anteriormente, que van a corresponder a sistemas Incompatibles y a sistemas indeterminados." *(Nota: "son" es una errata tipográfica del original por "con").*

**🗣️ En palabras simples:**
En la Clase 10 aprendiste a usar el método general (llevar la matriz ampliada a la forma canónica) cuando el sistema tenía una única solución (Compatible Determinado). En esta Clase 11 aplicamos exactamente la misma herramienta matricial pero para descubrir qué pasa en los otros dos escenarios posibles: cuando el sistema **no tiene ninguna solución** (Sistema Incompatible) y cuando tiene **infinitas soluciones** que dependen de una o más variables libres (Sistema Compatible Indeterminado), aprendiendo además a filtrar cuáles de esas soluciones matemáticas sirven realmente en un problema concreto.

**🔍 Desglose de la jerga:**
- **Método general de resolución:** Procedimiento matricial (eliminación de Gauss-Jordan) que transforma la matriz ampliada del sistema en su matriz canónica equivalente mediante operaciones elementales de fila.
- **Validar su respuesta:** Dos niveles de verificación: (1) algebraica, comprobando que los valores hallados satisfacen las ecuaciones originales al reemplazarlos; y (2) contextual, verificando que los valores tengan sentido en el problema real (por ejemplo, que cantidades de objetos sean números naturales y no negativos).
- **Clasificar los sistemas de acuerdo a las soluciones obtenidas:** Determinar si el sistema es Compatible Determinado (solución única), Compatible Indeterminado (infinitas soluciones) o Incompatible (ninguna solución).

**💡 Ejemplo:**
En la Clase 10 un sistema de 3 ecuaciones con 3 incógnitas terminaba en `x = 25, y = 35, z = 35`. En la Clase 11 veremos sistemas que terminan en un absurdo como `0 = 1` o `0 = 8` (incompatibles) o donde una incógnita queda libre y las demás dependen de ella, como `A = 36 − 7C, B = −24 + 6C` (compatibles indeterminados).

**🔗 Conexiones:**
Conecta directamente la **Clasificación de los sistemas de ecuaciones** presentada en la Clase 9 (pág. 6) y el **criterio de rangos** de la Clase 10 (págs. 7 y 8) con la resolución práctica y el análisis de soluciones generales y particulares.

**⚠️ Precisiones / errores comunes:**
- No cambiar de método: el alumno suele pensar que para sistemas rectangulares (más ecuaciones que incógnitas o menos ecuaciones que incógnitas) hace falta otro método. El **método general** se aplica a cualquier sistema lineal de `n` ecuaciones con `m` incógnitas.

**🎤 Cómo decirlo en el oral:**
"En la Clase 11 completamos el estudio del método general de resolución de sistemas de ecuaciones lineales analizando los dos casos en los que no hay solución única: los sistemas incompatibles, que carecen de solución, y los sistemas compatibles indeterminados, que poseen infinitas soluciones expresadas mediante una solución general y soluciones particulares."

---

## 11.2 Sistema Incompatible: Definición y Condición Matricial por Rangos

> 📖 **Textual del material:**
> "Una vez que se llega a la matriz canónica, la analizamos: El Rango de la matriz de los coeficientes es 3. El rango de la matriz Ampliada es 4 Por lo tanto, como el rango de la matriz ampliada y el rango de la matriz de los coeficientes son números distintos, eso nos indica que el sistema no tiene solución, es decir, que es un SISTEMA INCOMPATIBLE. Por lo tanto, no hay ningún conjunto de números que satisfagan las ecuaciones."

**🗣️ En palabras simples:**
Cuando llevás la matriz ampliada a la forma canónica y contás cuántas filas no nulas quedaron: si al tapar la columna de los términos independientes tenés menos filas no nulas que al destaparla (es decir, apareció una fila llena de ceros del lado de las incógnitas pero con un número distinto de cero del lado del término independiente, como `0  0  0 : 1`), los rangos son distintos (`ρ(A) ≠ ρ(A°)`). Eso significa que el sistema pide algo imposible y no existe ninguna combinación de números para las incógnitas que cumpla todas las ecuaciones a la vez.

**🔍 Desglose de la jerga:**
- **Matriz canónica:** Matriz escalonada reducida por filas equivalente a la matriz ampliada original.
- **Rango de la matriz de los coeficientes (`ρ(A)`):** Cantidad de filas no nulas de la matriz canónica mirando únicamente el bloque izquierdo (los coeficientes de las incógnitas, sin la última columna).
- **Rango de la matriz Ampliada (`ρ(A°)`):** Cantidad de filas no nulas de la matriz canónica considerando toda la fila completa (incluyendo la columna de los términos independientes).
- **Números distintos (`ρ(A) ≠ ρ(A°)`):** Condición necesaria y suficiente (Teorema de Rouché-Frobenius) para que el sistema carezca de solución.
- **SISTEMA INCOMPATIBLE:** Sistema de ecuaciones para el cual no existe ningún conjunto de valores de las incógnitas que satisfaga simultáneamente todas las ecuaciones (conjunto solución vacío, `S = ∅`).

**💡 Ejemplo (Ejemplo n° 6 del material, pág. 2):**
Sea el sistema completo y ordenado de 4 ecuaciones y 3 incógnitas:
- `2x + 3y + 4z = 5`
- `x − 2y + 2z = 0`
- `3x + 2y + z = 1`
- `4x − 2y + z = 2`

Se arma la matriz ampliada con su columna de control (donde cada elemento de control es la suma de los elementos de la fila: `2+3+4+5 = 14`, `1−2+2+0 = 1`, `3+2+1+1 = 7`, `4−2+1+2 = 5`) y se lleva a la forma canónica, llegando a:
- Fila 1: `1   0   0  :  0  |  1`
- Fila 2: `0   1   0  :  0  |  1`
- Fila 3: `0   0   1  :  0  |  1`
- Fila 4: `0   0   0  :  1  |  1`

Al analizarla:
- Sin la columna de términos independientes, la fila 4 es `[0  0  0]` (nula), por lo que el **Rango de la matriz de los coeficientes es 3** (`ρ(A) = 3`).
- Con la columna de términos independientes, la fila 4 es `[0  0  0 : 1]` (no nula), por lo que el **rango de la matriz Ampliada es 4** (`ρ(A°) = 4`).
- Como `3 ≠ 4`, el sistema es un **SISTEMA INCOMPATIBLE**.

**🧩 Idea de la demostración / Justificación:**
1. Las operaciones elementales aplicadas a la matriz ampliada conservan el conjunto de soluciones del sistema (producen sistemas equivalentes).
2. Si `ρ(A) ≠ ρ(A°)`, dado que `A°` tiene una columna más que `A`, necesariamente `ρ(A°) > ρ(A)`.
3. Esto implica que en la matriz canónica existe al menos una fila cuyos coeficientes en `A` son todos iguales a `0`, pero cuyo término independiente en `A°` es distinto de `0` (en la forma canónica, igual a `1`).
4. Al rearmar la ecuación correspondiente a esa fila, queda `0·x_1 + 0·x_2 + ... + 0·x_m = 1`, es decir, `0 = 1`.
5. Como `0 = 1` es falso para cualquier valor de las incógnitas, ningún vector `X` puede satisfacer el sistema equivalente ni, por equivalencia, el sistema original.

**🤔 Intuición:**
Cada ecuación es una condición o restricción que deben cumplir las incógnitas. Que el rango de la ampliada supere al de los coeficientes significa que una de las ecuaciones contradice a las demás (por ejemplo, dos ecuaciones suman algo igual a `5`, pero otra ecuación exige que esa misma combinación valga `8`). Al escalonar la matriz, esa incompatibilidad oculta queda al descubierto en una fila de la forma `0 = 1`.

**🔗 Conexiones:**
- Con la **Clase 8 (Rango de una matriz)** y la **Clase 10 (pág. 7 y 8)**: allí se enunció la regla general `ρ(A) ≠ ρ(A°) ⇒ Incompatible`, que en esta Clase 11 se aplica y ejemplifica en detalle.
- Con la **columna de control** (vista en matrices), que el Ejemplo n° 6 utiliza al lado derecho de la matriz ampliada para verificar que no haya errores de cálculo aritmético en cada paso de reducción.

**⚠️ Precisiones / errores comunes:**
- **No confundir cantidad de ecuaciones con rango:** En el Ejemplo n° 6 hay 4 ecuaciones y 3 incógnitas, pero no es incompatible "porque tenga más ecuaciones que incógnitas", sino porque `ρ(A) = 3` y `ρ(A°) = 4`. Si la cuarta ecuación hubiera sido combinación lineal coherente de las otras tres, la cuarta fila se habría anulado por completo (`0  0  0 : 0`) y el sistema habría sido compatible.
- **No olvidar mencionar ambos rangos en el oral:** Si el profesor pregunta por qué es incompatible desde el punto de vista matricial, no basta con decir "porque no tiene solución"; hay que decir que **el rango de la matriz de los coeficientes y el rango de la matriz ampliada son números distintos**.

**🎤 Cómo decirlo en el oral:**
"Desde el punto de vista matricial, una vez llevada la matriz ampliada a su forma canónica, un sistema es un Sistema Incompatible cuando el rango de la matriz de los coeficientes y el rango de la matriz ampliada son números distintos. Eso indica que el sistema no tiene solución, es decir, no hay ningún conjunto de números que satisfagan las ecuaciones."

---

## 11.3 Observación Teórica: Detección de Incompatibilidad por Contradicción (sin llegar a la Matriz Canónica)

> 📖 **Textual del material:**
> "Si bien en este caso no se llegó a la matriz canónica (a veces no es necesario) se puede advertir que el sistema es Incompatible, ya que la última ecuación 0 = 8 no se verifica para ningún conjunto de valores de las incógnitas, pues es una contradicción.
> Concluimos entonces que el sistema es un sistema INCOMPATIBLE."

**🗣️ En palabras simples:**
No hace falta terminar de hacer todos los ceros y unos de la matriz canónica si, en el medio del proceso de aplicar operaciones elementales, te aparece una fila donde todos los coeficientes de las incógnitas se hicieron `0` y del otro lado quedó un número distinto de cero (como `0  0  0 : 8`). Si reescribís esa fila como ecuación te queda `0 = 8`, que es una contradicción evidente, y ya podés frenar ahí y asegurar que el sistema es incompatible.

**🔍 Desglose de la jerga:**
- **No se llegó a la matriz canónica (a veces no es necesario):** Observación práctica y teórica que indica que la condición de incompatibilidad puede detectarse en cualquier matriz intermedia equivalente, sin necesidad de normalizar todos los elementos conductores a `1` ni anular los elementos por encima de ellos.
- **Última ecuación `0 = 8`:** Traducción algebraica de la fila `[0  0  0 : 8]`, que representa `0x + 0y + 0z = 8`.
- **No se verifica para ningún conjunto de valores de las incógnitas:** Porque cualquiera sea la terna `(x, y, z)`, multiplicar por cero y sumar siempre da `0` en el primer miembro, nunca `8`.
- **Contradicción:** Igualdad numérica falsa (del tipo `0 = k` con `k ≠ 0`).

**💡 Ejemplo (Ejemplo n° 7 del material, págs. 2 y 3):**
Dado el sistema:
- `x + y + z = 2`
- `x − y + z = −9`
- `2x + 2z = 1`

Su matriz ampliada es:
- Fila 1: `1   1   1  :   2`
- Fila 2: `1  −1   1  :  −9`
- Fila 3: `2   0   2  :   1`

Al aplicar operaciones elementales (por ejemplo, sumando o combinando las filas para eliminar `x` en la tercera fila) se llega a la matriz intermedia:
- Fila 1: `1   1   1  :   2`
- Fila 2: `0  −2   0  :  −1`
- Fila 3: `0   0   0  :   8`

Esta matriz aún **no** es canónica (en la fila 2 hay un `−2` en vez de un `1`, y en la fila 1 aún hay un `1` encima de ese `−2`), pero su tercera fila ya traduce la ecuación `0x + 0y + 0z = 8`, o sea `0 = 8`. Como es una contradicción, se concluye de inmediato que es un **sistema INCOMPATIBLE**.

**🧩 Idea de la demostración / Justificación:**
Si en un paso intermedio aparece una fila `[0  0  ...  0 : k]` con `k ≠ 0`, ninguna operación elemental posterior entre las filas de `A` puede devolver coeficientes no nulos a esa fila sin usar otra fila, y si se continúa hasta la forma canónica, esa fila simplemente se multiplicará por `1/k` para convertirse en `[0  0  ...  0 : 1]`, provocando inevitablemente que `ρ(A) ≠ ρ(A°)`.

**🤔 Intuición:**
Mirando el sistema original del Ejemplo n° 7: si sumás las dos primeras ecuaciones `(x + y + z) + (x − y + z) = 2 + (−9)`, las `y` se cancelan y queda `2x + 2z = −7`. ¡Pero la tercera ecuación del sistema dice que `2x + 2z = 1`! Como `2x + 2z` no puede valer `−7` y `1` al mismo tiempo, el sistema se contradice a sí mismo.

**🔗 Conexiones:**
- Con el **Ejemplo n° 6 (Sección 11.2)**: en el Ejemplo n° 6 la fila `[0  0  0 : 151/35]` se dividió por `151/35` para llegar a `[0  0  0 : 1]`; el Ejemplo n° 7 muestra que ya en el instante en que aparece `[0  0  0 : k]` con `k ≠ 0` la incompatibilidad está probada.

**⚠️ Precisiones / errores comunes:**
- **¡Cuidado con confundir `0 = 8` con `0 = 0`!**
  - Una fila `0  0  0 : 8` significa `0 = 8` → **Contradicción** → **Sistema Incompatible**.
  - Una fila `0  0  0 : 0` significa `0 = 0` → **Identidad (ecuación redundante)** → **No** es contradicción; esa fila es nula tanto en `A` como en `A°` y no rompe la compatibilidad (suele aparecer en sistemas compatibles indeterminados, como en los Desempeños 5 y 6 de la pág. 10).

**🎤 Cómo decirlo en el oral:**
"Aunque el criterio general compara los rangos en la matriz canónica, a veces no es necesario completar todos los pasos hasta llegar a la matriz canónica: si al aplicar operaciones elementales aparece una fila cuyos coeficientes de las incógnitas son todos cero pero el término independiente es distinto de cero —por ejemplo, dando lugar a la ecuación `0 = 8`—, se advierte de inmediato que el sistema es Incompatible, ya que esa igualdad no se verifica para ningún conjunto de valores de las incógnitas por ser una contradicción."

---

## 11.4 Preparación del Sistema y Las Tres Matrices Fundamentales (`A`, `B` y `X`)

> 📖 **Textual del material:**
> "• Recordemos: reacomodamos el sistema de tal manera que en el primer miembro queden los términos con las incógnitas, y en el segundo miembro queden los términos independientes. (ya lo habíamos hecho antes, pero es un paso necesario para la resolución)."
>
> "• Armamos las tres matrices: La matriz de los coeficientes, el vector de los términos independientes y el vector de las incógnitas. Las matrices quedarían así:
> A = [1  1  1 ; 2  3  −4] ,   B = [12 ; 0] ,   X = [A ; B ; C]
> A la matriz A la llamaremos Matriz de los coeficientes, a la matriz B la llamaremos Matriz (o vector) de los términos independientes y a la matriz X la llamaremos matriz (o vector) de las incógnitas. (Por si no quedó claro, los coeficientes son los números que multiplican a cada una de las incógnitas)"

**🗣️ En palabras simples:**
Antes de armar cualquier matriz, tenés que "ordenar y completar" las ecuaciones: todas las letras (incógnitas) tienen que pasar sumando o restando al lado izquierdo del signo `=` (primer miembro), en el mismo orden de columnas para todas las ecuaciones, y todos los números sueltos sin letra (términos independientes) tienen que quedar del lado derecho del `=` (segundo miembro). Si una ecuación no tenía término independiente del otro lado al despejar, queda un `0`. Una vez hecho eso, el sistema se desarma en tres piezas matriciales: la tabla de números que multiplican a las letras (`A`), la columna de letras (`X`) y la columna de resultados del lado derecho (`B`).

**🔍 Desglose de la jerga:**
- **Primer miembro:** Expresión algebraica ubicada a la izquierda del signo `=`. Allí deben ubicarse todos los términos con incógnitas.
- **Segundo miembro:** Expresión ubicada a la derecha del signo `=`. Allí deben ubicarse los términos independientes (números que no están multiplicados por ninguna incógnita).
- **Coeficientes:** Los números (con su respectivo signo `+` o `−`) que multiplican a cada una de las incógnitas. Si una incógnita aparece sola (ej. `+ C`), su coeficiente es `1`; si no aparece en una ecuación, su coeficiente es `0`.
- **Matriz de los coeficientes (`A`):** Matriz de orden `n × m` (donde `n` es el número de ecuaciones y `m` el número de incógnitas) formada por los coeficientes ordenados por ecuación (filas) y por incógnita (columnas).
- **Matriz (o vector) de los términos independientes (`B`):** Matriz columna (vector columna) de orden `n × 1` formada por los números del segundo miembro de cada ecuación.
- **Matriz (o vector) de las incógnitas (`X`):** Matriz columna (vector columna) de orden `m × 1` formada por los símbolos de las incógnitas del sistema en el mismo orden en que se armaron las columnas de `A`.

**💡 Ejemplo (Ejemplo n° 9 del material, pág. 3 — problema de los empresarios de la Clase 9):**
Sistema original desordenado:
- `A + B + C = 12`
- `2.A + 3B = 4.C`

1. **Reacomodamiento:** Pasamos `4.C` restando al primer miembro en la segunda ecuación, dejando `0` en el segundo miembro:
   - `A + B + C = 12`
   - `2.A + 3B − 4.C = 0`
2. **Armado de las tres matrices:**
   - **Matriz de los coeficientes (`A` de orden `2 × 3`):**
     - Fila 1: `1   1    1`
     - Fila 2: `2   3   −4`
   - **Matriz (o vector) de los términos independientes (`B` de orden `2 × 1`):**
     - Columna: `[12 ; 0]`
   - **Matriz (o vector) de las incógnitas (`X` de orden `3 × 1`):**
     - Columna: `[A ; B ; C]`

**🔗 Conexiones:**
- Retoma el **Ejemplo 3 de la Clase 9** (donde se habían probado valores a mano sin método matricial) y el **primer paso del Método General** de la Clase 10 ("1ero| Completar y ordenar el sistema dado").

**⚠️ Precisiones / errores comunes:**
- **Olvidar cambiar el signo al reacomodar:** En `2.A + 3B = 4.C`, al pasar `4.C` al primer miembro el coeficiente de `C` es `−4`, no `4`.
- **Confundir la letra `A` de la matriz de coeficientes con la incógnita `A` del problema:** En este ejemplo del material se usa `A` tanto para el nombre de la matriz de coeficientes como para la primera incógnita (`A, B, C` empresarios). En el oral conviene aclararlo: "`A` mayúscula fuera del vector es la matriz de los coeficientes, y `A, B, C` dentro del vector `X` son las tres incógnitas del problema".

**🎤 Cómo decirlo en el oral:**
"Para aplicar el método general, primero reacomodamos el sistema de tal manera que en el primer miembro queden los términos con las incógnitas ordenadas y en el segundo miembro queden los términos independientes. Luego definimos las tres matrices del sistema: la matriz `A`, llamada Matriz de los coeficientes (que contiene los números que multiplican a cada una de las incógnitas); la matriz `B`, llamada Matriz o vector de los términos independientes; y la matriz `X`, llamada Matriz o vector de las incógnitas."

---

## 11.5 Forma Matricial del Sistema de Ecuaciones (`A • X = B`)

> 📖 **Textual del material:**
> "Vamos a ver qué sucede si resolvemos el siguiente producto. (para esto tendremos que recordar cómo se resuelve la multiplicación de matrices).
> A_(nxm) • X_(mx1) • X_(3x1) = B_(nx1)
> En nuestro caso sería: A_(2x3) • X_(3x1) = B_(2x1)
> Esto es la forma matricial * del sistema de ecuaciones y será la que nos permita resolverlo con el método general.
> En este caso la forma matricial es:
> [1  1  1 ; 2  3  −4] • [A ; B ; C] = [12 ; 0]"

**🗣️ En palabras simples:**
Todo un sistema de `n` ecuaciones con `m` incógnitas se puede escribir como una sola ecuación de multiplicación de matrices: `A • X = B`. ¿Por qué funciona? Porque cuando multiplicás cada fila de `A` por la columna de incógnitas `X` (usando la regla de multiplicación de matrices: fila por columna) e igualás cada resultado a la fila correspondiente de `B`, reconstruís exactamente las ecuaciones originales del sistema.

**🔍 Desglose de la jerga:**
- **`A_(n×m)`:** Matriz de los coeficientes con `n` filas (cantidad de ecuaciones) y `m` columnas (cantidad de incógnitas).
- **`X_(m×1)`:** Vector columna de las incógnitas con `m` filas y `1` columna. *(Nota sobre errata tipográfica del PDF: en el renglón general de la pág. 4 se imprimió accidentalmente `A_(nxm) • X_(mx1) • X_(3x1) = B_(nx1)` repitiendo `X_(3x1)` del ejemplo; la expresión general correcta, como muestra la línea inmediata siguiente del material, es `A_(n×m) • X_(m×1) = B_(n×1)`).*
- **`B_(n×1)`:** Vector columna de los términos independientes con `n` filas y `1` columna.
- **Forma matricial del sistema de ecuaciones:** La igualdad matricial `A • X = B` que representa de manera compacta al sistema de ecuaciones lineales.

**💡 Ejemplo (Ejemplo n° 9 del material, pág. 4):**
Para el sistema de 2 ecuaciones (`n = 2`) y 3 incógnitas (`m = 3`):
- Producto matricial: `A_(2×3) • X_(3×1) = B_(2×1)`
- Expresión explícita:
  `[1   1   1 ; 2   3  −4] • [A ; B ; C] = [12 ; 0]`
- Si hacemos el producto fila por columna:
  - Fila 1 de `A` por columna `X`: `1·A + 1·B + 1·C = 12` (primera ecuación).
  - Fila 2 de `A` por columna `X`: `2·A + 3·B + (−4)·C = 0` (segunda ecuación).

**🔗 Conexiones:**
- Con la **Clase 6 (Multiplicación de matrices)**: recordemos que para poder multiplicar dos matrices `A_(n×m)` y `X_(m×1)`, el número de columnas de la primera (`m`, cantidad de incógnitas en cada ecuación) debe coincidir con el número de filas de la segunda (`m`, cantidad total de incógnitas), y el resultado tiene el número de filas de la primera y columnas de la segunda (`n × 1`, que es el orden de `B`).
- Con la **Clase 10 (pág. 8)**: allí se usa exactamente la notación `A_(n×m) • X_(m×1) = B_(n×1)` como raíz del árbol de clasificación de sistemas.

**⚠️ Precisiones / errores comunes:**
- **El orden del producto NO es conmutativo:** Es `A • X = B`, jamás `X • A = B` (de hecho, `X_(m×1) • A_(n×m)` ni siquiera es conformable salvo que `n = 1`).
- **No confundir la forma matricial (`A • X = B`) con la matriz ampliada (`A° = [A : B]`):** La forma matricial es una igualdad con el vector de incógnitas `X` explícito multiplicando a `A`; la matriz ampliada es una sola matriz donde se yuxtaponen `A` y `B` sin escribir las incógnitas.

**🎤 Cómo decirlo en el oral:**
"La forma matricial de un sistema de `n` ecuaciones lineales con `m` incógnitas es el producto `A_(n×m) • X_(m×1) = B_(n×1)`, donde `A` es la matriz de los coeficientes, `X` es el vector columna de las incógnitas y `B` es el vector columna de los términos independientes."

---

## 11.6 Matriz Ampliada del Sistema (`A°`) y Equivalencia por Operaciones Elementales

> 📖 **Textual del material:**
> "• A continuación armamos la matriz ampliada del sistema de ecuaciones dado, (recordemos que se forma a partir de la matriz de los coeficientes y del vector de los términos independientes), quedando de la siguiente manera:
> A° = [1  1  1 : 12 ; 2  3  −4 : 0]
> A partir de esta matriz ampliada, encontraremos, si tiene, la o las soluciones del sistema. Esto lo haremos llevándola a canónica y obteniendo así un sistema equivalente más sencillo de resolver, del cual sacaremos la o las soluciones.
> Como ya dijimos antes, podemos asegurar que el sistema que se obtiene es equivalente ya que si aplicamos operaciones elementales a la matriz ampliada, a cada una de las ecuaciones no le cambiarán las soluciones."

**🗣️ En palabras simples:**
Para no arrastrar las letras `A, B, C` (o `x, y, z`) en cada paso, juntamos la matriz de los coeficientes `A` y la columna de términos independientes `B` separadas por dos puntos (`:`), formando la **matriz ampliada `A°`**. Después le aplicamos operaciones elementales por fila hasta llevarla a la matriz canónica. ¿Por qué vale hacer esto? Porque hacer operaciones elementales en las filas de `A°` equivale a hacer cuentas válidas entre las ecuaciones del sistema, lo cual transforma el sistema original en otro **sistema equivalente** (mucho más fácil de leer, pero con exactamente las mismas soluciones).

**🔍 Desglose de la jerga:**
- **Matriz ampliada del sistema (`A°`):** Matriz de orden `n × (m + 1)` que se forma agregando a la derecha de la matriz de los coeficientes `A` la columna del vector de los términos independientes `B`, separada por `:` (`A° = [A : B]`).
- **Llevándola a canónica:** Aplicar una sucesión finita de operaciones elementales por fila (`~`) hasta obtener la matriz canónica equivalente por filas.
- **Sistema equivalente:** Dos sistemas de ecuaciones son equivalentes cuando tienen exactamente el mismo conjunto de soluciones (toda solución del primero es solución del segundo, y viceversa).
- **Operaciones elementales a la matriz ampliada:** Permutar dos filas, multiplicar una fila por una constante no nula `H_i(k)` con `k ≠ 0`, o sumar a una fila otra fila multiplicada por una constante `H_(i,j)(k)`.

**💡 Ejemplo (Ejemplo n° 9 del material, pág. 4):**
Partiendo de `A°`:
- Matriz ampliada inicial:
  - Fila 1: `1    1    1  :   12`
  - Fila 2: `2    3   −4  :    0`
- Paso 1 — Aplicamos la operación elemental `H_(2,1)(−2)` (a la fila 2 le sumamos la fila 1 multiplicada por `−2`):
  - Fila 1: `1    1    1  :   12`
  - Fila 2: `0    1   −6  :  −24`
- Paso 2 — Aplicamos la operación elemental `H_(1,2)(−1)` (a la fila 1 le sumamos la fila 2 multiplicada por `−1`):
  - Fila 1: `1    0    7  :   36`
  - Fila 2: `0    1   −6  :  −24`
Esta última matriz ya está en **forma canónica** (los elementos conductores de cada fila son `1` y en sus columnas el resto de los elementos son `0`).

**🧩 Idea de la demostración / Justificación:**
Cada fila de la matriz ampliada `A°` representa una ecuación lineal del sistema. Aplicar operaciones elementales de fila sobre `A°` equivale a:
1. Cambiar el orden en que se listan las ecuaciones (permutar filas),
2. Multiplicar ambos miembros de una igualdad por un mismo número distinto de cero (`H_i(k)` con `k ≠ 0`), o
3. Sumar miembro a miembro a una ecuación un múltiplo de otra ecuación del mismo sistema (`H_(i,j)(k)`).
Por las propiedades uniformes de la igualdad en ℝ, cualquier vector `X` que verifique las igualdades antes de la operación también verifica las nuevas igualdades, y como toda operación elemental es invertible, el proceso es reversible. Por lo tanto, a cada una de las ecuaciones del sistema no le cambiarán las soluciones, obteniéndose un **sistema equivalente**.

**🤔 Intuición:**
Es exactamente el método de "reducción por sumas y restas" que se usa en la escuela secundaria para eliminar una incógnita entre dos ecuaciones, pero organizado en una tabla sin escribir las letras una y otra vez.

**🔗 Conexiones:**
- Con la **Clase 7 y 8 (Operaciones elementales y Matriz canónica)** y con la **Clase 9 (Sistemas equivalentes)**.

**⚠️ Precisiones / errores comunes:**
- **Aplicar la operación elemental solo a `A` y olvidarse de la columna `B`:** Toda operación de fila se hace sobre la **matriz ampliada completa `A°`**. En el Ejemplo n° 9, al hacer `H_(2,1)(−2)`, el `0` del término independiente pasa a ser `0 + 12·(−2) = −24`, y en `H_(1,2)(−1)` el `12` pasa a ser `12 + (−24)·(−1) = 36`.
- **Usar operaciones por columnas:** En la resolución de sistemas mediante `A°`, solo se aplican operaciones elementales **por filas** (cada fila es una ecuación; mezclar columnas cambiaría las incógnitas).

**🎤 Cómo decirlo en el oral:**
"La matriz ampliada `A°` se forma a partir de la matriz de los coeficientes `A` y del vector de los términos independientes `B`. Al llevarla a su forma canónica mediante operaciones elementales por fila, obtenemos un sistema equivalente más sencillo de resolver; podemos asegurar que es equivalente porque al aplicar operaciones elementales a la matriz ampliada, no cambian las soluciones del sistema."

---

## 11.7 Sistema Compatible y Sistema Compatible Indeterminado: Condición Matricial y Clasificación

> 📖 **Textual del material:**
> "Analicemos ahora la matriz canónica obtenida: El rango de la matriz de los coeficientes es 2, y el rango de la matriz ampliada es también 2, eso nos indica que el sistema es un sistema COMPATIBLE, es decir, que tiene solución.
> Por otro lado, el número de incógnitas es 3, que es distinto al rango de la matriz ampliada (o de los coeficientes, ya que es el mismo número). Por lo tanto esto nos indica que el sistema es INDETERMINADO. Pero veamos cómo se llega a la solución:
> Si rearmamos las ecuaciones del sistema quedaría:
> 1A + 0B + 7C = 36 ; 0A + 1B − 6C = −24   O sea:   1A + 7C = 36 ; 1B − 6C = −24"

**🗣️ En palabras simples:**
Una vez que llegaste a la matriz canónica, hacés dos preguntas seguidas:
1. **¿El rango de `A` es igual al rango de `A°`?** Si son iguales (`ρ(A) = ρ(A°)`), el sistema es **COMPATIBLE** (tiene solución).
2. **¿Ese rango común es igual o menor a la cantidad de incógnitas (`m`)?**
   - Si es igual al número de incógnitas (`ρ(A) = ρ(A°) = m`), cada incógnita queda despejada con un único valor → **Compatible Determinado** (Clase 10).
   - Si es distinto (menor) al número de incógnitas (`ρ(A) = ρ(A°) < m`), "sobran" incógnitas respecto de las filas útiles: al rearmar las ecuaciones, no queda cada letra igualada a un número fijo, sino unas letras atadas a otras → **Compatible Indeterminado** (infinitas soluciones).

**🔍 Desglose de la jerga:**
- **Sistema COMPATIBLE:** Sistema de ecuaciones que **tiene solución** (al menos una). Matricialmente ocurre si y solo si `ρ(A) = ρ(A°)`.
- **Número de incógnitas (`m`):** Cantidad total de variables distintas que intervienen en el sistema (igual al número de columnas de la matriz de coeficientes `A`).
- **Distinto al rango de la matriz ampliada (o de los coeficientes):** Como el rango nunca puede superar al número de columnas de `A`, que el rango `ρ(A) = ρ(A°)` sea distinto del número de incógnitas `m` equivale exactamente a decir que es **menor** que `m` (`ρ(A) = ρ(A°) < m`).
- **Sistema INDETERMINADO (Compatible Indeterminado):** Sistema compatible que tiene **infinitas soluciones**, porque el rango común de `A` y `A°` es menor que el número de incógnitas.

**💡 Ejemplo (Continuación del Ejemplo n° 9, pág. 4):**
En la matriz canónica:
- Fila 1: `1    0    7  :   36`
- Fila 2: `0    1   −6  :  −24`
1. **Rango de `A`:** 2 filas no nulas (`ρ(A) = 2`).
2. **Rango de `A°`:** 2 filas no nulas (`ρ(A°) = 2`).
   → Como `ρ(A) = ρ(A°) = 2`, el sistema es **COMPATIBLE**.
3. **Número de incógnitas:** 3 (`A, B, C`), que es distinto (mayor) al rango `2`.
   → Por lo tanto, el sistema es **COMPATIBLE INDETERMINADO**.
4. **Rearmado del sistema equivalente:**
   - `1A + 7C = 36`
   - `1B − 6C = −24`

**🧩 Idea de la demostración / Justificación:**
1. Como `ρ(A) = ρ(A°) = r`, no hay ninguna fila de contradicción del tipo `[0  0  ...  0 : 1]` en la matriz canónica, por lo cual el sistema es consistente (compatible).
2. Cada una de las `r` filas no nulas de la matriz canónica tiene un `1` principal (elemento conductor) en una columna distinta. Esas `r` columnas corresponden a `r` incógnitas principales que pueden despejarse de manera única en términos de las demás.
3. Como el número total de incógnitas es `m > r`, quedan `m − r > 0` columnas sin elemento conductor. Las incógnitas asociadas a esas `m − r` columnas no están fijadas por ninguna fila y pueden tomar cualquier valor real libremente, generando infinitas soluciones.

**🤔 Intuición:**
Si tenés 3 incógnitas (`A, B, C`) pero solo 2 ecuaciones independientes (`r = 2`), tenés 2 condiciones para fijar 3 números. Con 2 condiciones solo podés atar dos de las incógnitas (`A` y `B`) al valor que elijas para la tercera (`C`). Como `C` puede elegirse de infinitas maneras, el sistema tiene infinitas soluciones.

### 📊 Tabla Comparativa: Clasificación Completa de Sistemas de Ecuaciones Lineales (`A_(n×m) • X_(m×1) = B_(n×1)`)

| Clasificación del Sistema | ¿Tiene solución? | Cantidad de soluciones | Condición Matricial (Rangos y `m` incógnitas) | Aspecto de la Matriz Canónica / Ecuaciones equivalentes |
| :--- | :--- | :--- | :--- | :--- |
| **Compatible Determinado** *(Clase 10)* | **Sí** (Compatible) | **Única solución** | `ρ(A) = ρ(A°) = m` | Queda la matriz identidad `I_m` del lado de `A` (y eventuales filas `0 = 0` abajo). Cada incógnita es igual a un número determinado (`x = k_1, y = k_2...`). |
| **Compatible Indeterminado** *(Clase 11)* | **Sí** (Compatible) | **Infinitas soluciones** (Solución General `X*` + infinitas Soluciones Particulares) | `ρ(A) = ρ(A°) < m` *(rango igual en `A` y `A°`, pero distinto/menor al n° de incógnitas `m`)* | Hay `r = ρ(A°)` elementos conductores y quedan `m − r` columnas extra sin conductor. Las incógnitas principales dependen de `m − r` **variables libres**. |
| **Incompatible** *(Clase 11)* | **No** (Incompatible) | **Ninguna solución** (`S = ∅`) | `ρ(A) ≠ ρ(A°)` *(es decir, `ρ(A) < ρ(A°)`)* | Aparece una fila con todos `0` en `A` y un número no nulo en `B` (`0  0  0 : 1`, o en paso intermedio `0  0  0 : k` con `k ≠ 0`), que equivale a la contradicción `0 = 1` (o `0 = k`). |

**🔗 Conexiones:**
- Responde de manera directa a las preguntas **a** y **b** del **Desempeño 1** (pág. 7) y completa el esquema del Teorema de Rouché-Frobenius visto en la Clase 10 (pág. 8).

**⚠️ Precisiones / errores comunes:**
- **Error típico de examen oral:** Decir que un sistema es compatible indeterminado "cuando tiene menos ecuaciones que incógnitas". ¡Falso! Un sistema puede tener 3 ecuaciones y 3 incógnitas (o 4 ecuaciones y 3 incógnitas) y ser Compatible Indeterminado si al llevarlo a canónica se anulan filas quedando `0 = 0` (como ocurre en los Desempeños 5, 6 y 7 de las págs. 10 y 11, donde sistemas de `3 × 3` tienen rango `2 < 3`). Lo que importa **no es el número de ecuaciones `n`**, sino el **rango `ρ(A) = ρ(A°)`** comparado con el **número de incógnitas `m`**.

**🎤 Cómo decirlo en el oral:**
"Para que un sistema sea compatible indeterminado se deben cumplir dos condiciones desde el punto de vista matricial al analizar la matriz canónica: primero, que el rango de la matriz de los coeficientes sea igual al rango de la matriz ampliada —lo que indica que el sistema es Compatible—; y segundo, que ese rango sea distinto (menor) al número de incógnitas del sistema —lo que indica que es Indeterminado—."

---

## 11.8 Variables Libres o Independientes y Regla para Determinar su Cantidad

> 📖 **Textual del material:**
> "Como se podrá observar, cada una de las incógnitas NO es igual a un número determinado.
> Como ya se dijo, como el rango de la matriz ampliada es 2 y el número de incógnitas es 3, esa diferencia entre ambos números, nos va a dar la cantidad de variables libres o independientes que va a tener este sistema. Para este caso, podemos pensar que es “C”, ya que es la variable que se repite en ambas ecuaciones."
>
> "Acá se ve que hay variables (o incógnitas) que dependen de otra. Es por esto que es un sistema indeterminado, ya que para cualquier valor que tome la variable libre “C”, van a cambiar los valores de “A” y de “B”."

**🗣️ En palabras simples:**
En un sistema compatible indeterminado, las incógnitas se dividen en dos equipos:
1. Las **variables libres o independientes**: son las incógnitas a las que vos les podés dar el valor que quieras. ¿Cuántas hay? Exactamente la **resta** entre el número total de incógnitas y el rango de la matriz ampliada (`m − ρ(A°)`). En la matriz canónica corresponden a las columnas que no quedaron con el `1` principal de la escalera (las que se repiten en las ecuaciones rearmadas).
2. Las **variables dependientes** (o principales): son las que tienen el `1` principal en la matriz canónica y cuyo valor queda atado (depende) del valor que tome la variable libre.

**🔍 Desglose de la jerga:**
- **Cada una de las incógnitas NO es igual a un número determinado:** A diferencia del sistema compatible determinado (donde queda `x = 50, y = 15, z = 10`), aquí las ecuaciones rearmadas conservan más de una incógnita por ecuación (`1A + 7C = 36`).
- **Diferencia entre ambos números (`m − ρ(A°)`):** Resta entre el número de incógnitas (`m`) y el rango de la matriz ampliada (`ρ(A°)`), que es igual al rango de la matriz de los coeficientes (`ρ(A)`). Ese resultado entero positivo indica exactamente cuántas variables libres tiene el sistema.
- **Variables libres o independientes:** Incógnitas que no quedan fijadas por las ecuaciones y a las cuales se les puede asignar cualquier valor arbitrario.
- **Variables que dependen de otra (dependientes):** Incógnitas que se despejan en función de las variables libres; al cambiar el valor de la variable libre, cambian automáticamente sus valores.

**💡 Ejemplo:**
1. **Con 1 variable libre (Ejemplo n° 9, pág. 5):**
   - Número de incógnitas: `3` (`A, B, C`).
   - Rango de la matriz ampliada: `2`.
   - Cantidad de variables libres: `3 − 2 = 1` variable libre.
   - En las ecuaciones `1A + 7C = 36` y `1B − 6C = −24`, la variable libre es `C` (la columna sin `1` conductor, que se repite en ambas ecuaciones), mientras que `A` y `B` dependen de `C`.
2. **Con 2 variables libres (Desempeño 4, inciso c, págs. 8 y 9):**
   - El sistema tiene `5` incógnitas (`x, y, z, w, u`) y `3` ecuaciones cuyo rango en la matriz canónica es `3`.
   - Cantidad de variables libres: `5 − 3 = 2` variables libres (`w` y `u`), quedando el vector solución expresado en función de ambas: `x = 1, y = 2w, z = −(1/3)u, w = w, u = u`.

**🧩 Idea de la demostración / Justificación:**
Si la matriz canónica tiene rango `r = ρ(A°) = ρ(A)`, existen exactamente `r` filas no nulas y, por definición de matriz canónica, exactamente `r` columnas con elementos conductores iguales a `1` (y ceros en los demás lugares de esas columnas). Esas `r` incógnitas aparecen una sola vez cada una y se despejan en función de las restantes. Como en total hay `m` incógnitas (columnas de `A`), la cantidad de incógnitas que no poseen elemento conductor es la diferencia `m − r = m − ρ(A°)`.

**🤔 Intuición:**
Cada fila no nula de la matriz canónica "ata" o "consume" un grado de libertad (fija a una incógnita en función de las demás). Si empezás con `m` incógnitas libres y tenés `ρ(A°)` ecuaciones verdaderamente independientes (el rango), te quedan `m − ρ(A°)` grados de libertad sin atar: esas son las variables libres.

**🔗 Conexiones:**
- Responde de forma literal a la pregunta **c** del **Desempeño 1** (pág. 7): *"¿Cómo se determina la cantidad de variables libres o independientes en un sistema indeterminado?"*.

**⚠️ Precisiones / errores comunes:**
- **Restar número de incógnitas menos número de ecuaciones (`m − n`):** ¡Error grave! No se resta el número de ecuaciones originales `n`, sino el **rango de la matriz ampliada (`ρ(A°)`)** (o de los coeficientes). Si un sistema tiene 3 ecuaciones y 3 incógnitas pero rango 2, la cantidad de variables libres es `3 − 2 = 1` (no `3 − 3 = 0`).

**🎤 Cómo decirlo en el oral:**
"La cantidad de variables libres o independientes de un sistema compatible indeterminado se determina haciendo la diferencia (resta) entre el número de incógnitas del sistema y el rango de la matriz ampliada (o de la matriz de los coeficientes). Las demás incógnitas se despejan en función de las variables libres, por lo que sus valores dependen del valor que tome la variable libre."

---

## 11.9 Solución General del Sistema de Ecuaciones (Vector Solución `X*`)

> 📖 **Textual del material:**
> "Te propongo que despejemos A y B en las ecuaciones:
> La primera ecuación…
> 1A + 7C = 36
> A = 36 – 7C
> La segunda ecuación quedaría:
> 1B – 6C = −24
> B = −24 + 6C
> Por lo tanto, podríamos pensar el vector solución de la siguiente manera:
> X* = [A ; B ; C]   reemplazando...   X* = [36 − 7C ; −24 + 6C ; C]"
>
> "El Vector solución hallado X* es la Solución General del Sistema de Ecuaciones:
> X* = [36 − 7C ; −24 + 6C ; C]"
>
> "Pasando en limpio lo trabajado… El sistema planteado es un Sistema de Ecuaciones Compatible Indeterminado… Se obtuvo un vector solución (solución General del Sistema).
> X* = [36 − 7C ; −24 + 6C ; C]"

**🗣️ En palabras simples:**
Como no podés dar un único número para cada incógnita, despejás las incógnitas principales dejando a la variable libre del otro lado del igual (`A = 36 − 7C` y `B = −24 + 6C`). Después armás el vector columna `X*` poniendo, en el lugar de cada letra, la fórmula que depende de la variable libre, y en el lugar de la variable libre ponés la misma letra (`C`). Ese vector con fórmulas adentro se llama **Solución General del Sistema (`X*`)** porque funciona como una "fábrica" o molde que contiene todas las infinitas soluciones del sistema al mismo tiempo.

**🔍 Desglose de la jerga:**
- **`X*` (Vector solución):** Notación del material (con asterisco suprayacente) para distinguir el vector columna de las incógnitas ya resuelto (`X*`) del vector de incógnitas genérico planteado al inicio (`X`).
- **Despejar en las ecuaciones:** Pasar los términos que contienen a la variable libre al segundo miembro de cada ecuación del sistema equivalente canónico.
- **Solución General del Sistema de Ecuaciones:** Expresión del vector solución `X*` en la cual las variables dependientes están escritas como expresiones algebraicas en función de la(s) variable(s) libre(s), y cada variable libre figura igual a sí misma (ej. `C = C` o `z = z`).

**💡 Ejemplo (Ejemplo n° 9, págs. 5 y 6, y Desempeño 3, pág. 9):**
- En el Ejemplo n° 9:
  - De `1A + 7C = 36` se despeja `A = 36 − 7C`.
  - De `1B − 6C = −24` se despeja `B = −24 + 6C`.
  - La variable libre queda `C = C`.
  - La **Solución General** es el vector columna:
    - Componente 1 (`A`): `36 − 7C`
    - Componente 2 (`B`): `−24 + 6C`
    - Componente 3 (`C`): `C`
- En el Desempeño n° 3 (pág. 9, problema de los tres cereales: trigo `x`, cebada `y`, mijo `z`), eligiendo `x` como variable libre, la solución general se escribe:
  - Componente 1 (`x`): `x`
  - Componente 2 (`y`): `(100 − 7x) / 3`
  - Componente 3 (`z`): `(200 + 4x) / 3`

**🔗 Conexiones:**
- En un **Sistema Compatible Determinado** (Clase 10), el vector solución `X*` tiene únicamente constantes numéricas (por ejemplo, `X* = [50 ; 15 ; 10]`). En un **Sistema Compatible Indeterminado** (Clase 11), `X*` es la **Solución General** y contiene parámetros (las variables libres).

**⚠️ Precisiones / errores comunes:**
- **Olvidar escribir la variable libre en el vector `X*`:** Si el sistema tiene 3 incógnitas (`A, B, C`), el vector `X*` tiene que tener **3 filas**, no 2. En la posición de la variable libre se debe escribir `C` (o en forma de llave `z = z`, como en el Desempeño 4.f de la pág. 9).
- **No respetar el orden de las incógnitas en `X*`:** Si el vector de incógnitas se definió como `X = [x ; y ; v ; z]` (como en el Desempeño 4.d), las filas de `X*` deben respetar exactamente ese orden.

**🎤 Cómo decirlo en el oral:**
"Para hallar la Solución General de un sistema compatible indeterminado, rearmamos el sistema equivalente a partir de la matriz canónica, despejamos las incógnitas dependientes en función de la variable libre y las reemplazamos en el vector solución `X*`, dejando en el lugar de la variable libre la propia letra. Ese vector `X*` expresado en función de la variable libre es la Solución General del Sistema de Ecuaciones."

---

## 11.10 Soluciones Particulares de un Sistema Compatible Indeterminado

> 📖 **Textual del material:**
> "Pero a partir de esta solución, se pueden hallar soluciones particulares según el valor que se le asigne a la variable libre, en este caso, C."
>
> "Siendo este vector otra SOLUCIÓN PARTICULAR del sistema de ecuaciones."
>
> "Aquí podemos ver cómo se puede asignar el valor a la variable libre para obtener el valor de las otras variables.
> Por ejemplo: si le asignamos a C el valor de 8 quedaría:
> A = 36 – 7. C → A = 36 – 7. 8 → A = −20
> B = −24 + 6. C → B = −24 + 6. 8 → B = 24
> Por lo tanto el vector solución sería: X* = [−20 ; 24 ; 8]
> Otro ejemplo: si le asignamos a C el valor de 3 quedaría:
> A = 36 – 7.C → A = 36 – 7.3 → A = 15
> B = −24 + 6.C → B = −24 + 6.3 → B = −6
> Por lo tanto el vector solución sería: X* = [15 ; −6 ; 3]"
>
> "Así se puede obtener infinitas soluciones particulares:
> X* = [−20 ; 24 ; 8] ,   X* = [15 ; −6 ; 3] ,   X* = [1 ; 6 ; 5]
> Y se pueden obtener muchas más (infinitas), dependiendo del valor que se le asigne a la variable libre C."

**🗣️ En palabras simples:**
Si la **Solución General** es el "molde" con la letra `C`, una **Solución Particular** es un resultado numérico concreto que sale de ese molde cuando elegís un número específico para `C` y hacés la cuenta. Por ejemplo, si decidís que `C = 5` y reemplazás `5` en la solución general, te da `A = 1, B = 6, C = 5`. Ese vector `[1 ; 6 ; 5]` ya no tiene letras: es **una solución particular**. Y como a `C` le podés dar infinitos números distintos, podés fabricar **infinitas soluciones particulares**.

**🔍 Desglose de la jerga:**
- **Solución Particular:** Cada uno de los vectores numéricos concretos `X*` que satisfacen el sistema de ecuaciones y que se obtienen al reemplazar la(s) variable(s) libre(s) de la Solución General por un valor numérico determinado.
- **Según el valor que se le asigne a la variable libre:** El procedimiento exacto para pasar de la solución general a una solución particular consiste en fijar arbitrariamente el valor de la variable libre y calcular las variables dependientes.
- **Infinitas soluciones particulares:** Como la variable libre puede tomar infinitos valores reales, el sistema compatible indeterminado posee infinitas soluciones particulares.

**💡 Ejemplo (Ejemplo n° 9 del material, págs. 5, 6 y 7):**
A partir de la Solución General `X* = [36 − 7C ; −24 + 6C ; C]`:
- **Si `C = 5`:**
  - `A = 36 − 7·5 = 36 − 35 = 1`
  - `B = −24 + 6·5 = −24 + 30 = 6`
  - `C = 5`
  - Solución particular: `X* = [1 ; 6 ; 5]` (que coincide con la solución tanteada en la Clase 9).
- **Si `C = 8`:**
  - `A = 36 − 7·8 = 36 − 56 = −20`
  - `B = −24 + 6·8 = −24 + 48 = 24`
  - `C = 8`
  - Solución particular: `X* = [−20 ; 24 ; 8]`.
- **Si `C = 3`:**
  - `A = 36 − 7·3 = 36 − 21 = 15`
  - `B = −24 + 6·3 = −24 + 18 = −6`
  - `C = 3`
  - Solución particular: `X* = [15 ; −6 ; 3]`.

*(Nota sobre errata de edición en la pág. 5 del PDF: al final de la pág. 5 el PDF dice "Si a C se le asigna el valor de 8 (C = 8)" y muestra debajo el vector `[15 ; −6 ; 3]`, que en realidad corresponde a `C = 3`. En la pág. 6 el propio material desarrolla las cuentas completas paso a paso para `C = 8` dando `[−20 ; 24 ; 8]` y para `C = 3` dando `[15 ; −6 ; 3]`).*

**🔗 Conexiones:**
- Responde directamente a la pregunta **d** del **Desempeño 1** (pág. 7): *"¿Cómo se obtiene una solución particular de un sistema indeterminado?"*.
- Permite verificar rápidamente si la Solución General fue bien calculada: basta con tomar una solución particular cualquiera y reemplazarla en las ecuaciones originales del sistema para comprobar que verifica todas las igualdades.

**⚠️ Precisiones / errores comunes:**
- **Confundir "Solución General" con "Solución Particular" en el oral:**
  - Si el profesor pide la **solución general**, el vector `X*` **debe llevar la letra de la variable libre** (`[36 − 7C ; −24 + 6C ; C]`).
  - Si pide una **solución particular**, el vector `X*` **debe contener únicamente números** obtenidos al darle un valor específico a la variable libre (`[1 ; 6 ; 5]`).
- **Cambiar el valor de la variable libre a mitad de camino:** Si hay una sola variable libre `C` que aparece en tres filas de `X*`, hay que reemplazar **el mismo valor numérico de `C` en todas las filas** simultáneamente. (Si hubiera dos variables libres distintas, como `w` y `u` en el Desempeño 4.c, a `w` y a `u` sí se les pueden dar valores independientes entre sí).

**🎤 Cómo decirlo en el oral:**
"Una solución particular de un sistema compatible indeterminado se obtiene a partir de la Solución General asignándole un valor numérico específico a la variable libre (o a cada una de las variables libres) y calculando los valores correspondientes de las variables dependientes. Como la variable libre puede tomar infinitos valores, se pueden obtener infinitas soluciones particulares."

---

## 11.11 Algoritmo: Método General de Resolución Aplicado a Sistemas Incompatibles e Indeterminados

**🎯 Qué problema resuelve:**
Permite resolver y clasificar cualquier sistema de `n` ecuaciones lineales con `m` incógnitas (`A_(n×m) • X_(m×1) = B_(n×1)`), determinando de manera exacta si no tiene solución (Incompatible), si tiene solución única (Compatible Determinado) o si tiene infinitas soluciones (Compatible Indeterminado), y hallando en este último caso su Solución General y Soluciones Particulares.

**📋 Pasos tal como el material los presenta y aplica:**
1. **Completar y ordenar (reacomodar) el sistema:** Ubicar en el primer miembro de cada ecuación todos los términos con las incógnitas (en el mismo orden de columnas, completando con coeficiente `0` las incógnitas ausentes) y en el segundo miembro los términos independientes.
2. **Identificar las matrices del sistema y armar la matriz ampliada (`A°`):**
   - Definir la matriz de los coeficientes `A`, el vector de los términos independientes `B` y el vector de las incógnitas `X` (forma matricial `A • X = B`).
   - Construir la matriz ampliada `A° = [A : B]` (opcionalmente agregando a la derecha la **columna de control**, donde cada fila suma los elementos de `A°`, como en el Ejemplo n° 6).
3. **Llevar la matriz ampliada `A°` a la forma canónica:**
   - Aplicar operaciones elementales por fila (`H_i(k)`, `H_(i,j)(k)`, permutación) para obtener un sistema equivalente más sencillo.
   - **Detección temprana (Ejemplo n° 7):** Si antes de terminar aparece una fila con todos `0` en los coeficientes y un número no nulo en el término independiente (una contradicción del tipo `0 = k` con `k ≠ 0`, como `0 = 8`), se puede detener el proceso y concluir que el sistema es **INCOMPATIBLE**.
4. **Analizar los rangos en la matriz canónica (`ρ(A)` y `ρ(A°)`):**
   - Contar las filas no nulas de la matriz de los coeficientes `A` (`ρ(A)`, sin mirar la última columna) y las filas no nulas de la matriz ampliada `A°` (`ρ(A°)`, mirando toda la fila).
   - **Caso 1 — `ρ(A) ≠ ρ(A°)`:** El sistema no tiene solución → es un **SISTEMA INCOMPATIBLE** (Ejemplo n° 6, donde `ρ(A) = 3` y `ρ(A°) = 4` por la fila `0  0  0 : 1`).
   - **Caso 2 — `ρ(A) = ρ(A°)`:** El sistema tiene solución → es un **SISTEMA COMPATIBLE**. Se compara entonces ese rango con el número de incógnitas `m`:
     - **Subcaso 2a — `ρ(A) = ρ(A°) = m`:** Es **Compatible Determinado** (solución única, visto en Clase 10).
     - **Subcaso 2b — `ρ(A) = ρ(A°) < m` (distinto al número de incógnitas):** Es **Compatible Indeterminado** (infinitas soluciones, Ejemplo n° 9).
5. **Hallar la Solución General (`X*`) y Soluciones Particulares (en el caso Compatible Indeterminado):**
   - Calcular la cantidad de variables libres o independientes: `m − ρ(A°)`.
   - Rearmar las ecuaciones del sistema equivalente a partir de la matriz canónica.
   - Despejar las incógnitas dependientes en función de la(s) variable(s) libre(s).
   - Escribir el vector **Solución General `X*`** en función de la(s) variable(s) libre(s).
   - Si se piden **Soluciones Particulares**, asignar valores numéricos a la(s) variable(s) libre(s) y evaluar `X*`. Si es un problema aplicado, **validar** las soluciones según las restricciones del contexto.

**⚙️ Por qué funciona:**
Porque las operaciones elementales sobre las filas de `A°` son transformaciones algebraicas reversibles sobre las ecuaciones que preservan el conjunto de soluciones (sistemas equivalentes), y la estructura escalonada reducida de la matriz canónica desacopla al máximo las incógnitas principales, haciendo visible el rango real del sistema y exponiendo cualquier contradicción (`0 = 1`) o grado de libertad remanente (`m − ρ(A°)`).

---

## 11.12 Sistemas con Solución Asegurada: Sistemas Homogéneos y Solución Trivial (Desempeños 1.e y 2)

> 📖 **Textual del material:**
> "Desempeño de Síntesis
> • Desempeño 1
> Luego de leer y analizar la clase n° 11, responde a las siguientes preguntas:
> a- ¿Qué condiciones desde el punto de vista matricial se debe dar para que un sistema sea incompatible?
> b- ¿Qué condiciones desde el punto de vista matricial se debe dar para que un sistema sea compatible indeterminado?
> c- ¿Cómo se determina la cantidad de variables libres o independientes en un sistema indeterminado?
> d- ¿Cómo se obtiene una solución particular de un sistema indeterminado?
> e- ¿Qué tipo de sistema, tiene seguro solución? ¿Cómo se llama dicha solución?
>
> • Desempeño 2
> Cuáles de los siguientes sistemas tienen:
> a- Solución única.
> b- Infinito número de soluciones.
> c- Sólo las soluciones triviales.
> d- Ninguna solución.
> e- Obtiene la solución de cada sistema.
> ...
> 4-  28x + 16y = 0 ; 21x + 12y = 0
> ...
> a- Solución única: 1-; 2-; 5-
> b- Infinitas soluciones: 3-; 4-
> c- Soluciones triviales: 4-
> d- Ninguna solución: 6-
>
> Respuestas a los Desempeños de Síntesis (pág. 9):
> 4| x = −4/7 . y   y = y"

*(Citas complementarias del material de la misma Unidad 3 — Clase 10, págs. 8 y 9 — a las que remite esta pregunta de síntesis de la Clase 11):*
> 📖 **Textual del material (Clase 10, págs. 8-9, referenciado en Clase 11 pág. 7):**
> "¿Qué sucede con los sistemas homogéneos? Sistemas homogéneos, siempre compatibles.
> Sea A.X = 0 un sistema de ecuaciones lineales homogéneo la matriz A es de orden (nxm).
> Si un sistema de ecuaciones es homogéneo siempre tiene solución, o sea el sistema siempre es compatible.
> La explicación es sencilla, puesto que la matriz ampliada es de la forma: Aº = [ A : 0 ]
> Y el rango de la misma es igual al rango de A, puesto que el vector que se agrega es el vector nulo."
> "Debe notarse que en este caso existen infinitas soluciones para el sistema dado, una de las cuales es la solución trivial que es solución de todo el sistema de ecuaciones homogéneo, en tanto que las otras son soluciones no triviales."
> "En este caso, la única solución que existe, es la solución trivial."

**🗣️ En palabras simples:**
En el Desempeño de Síntesis de la Clase 11 aparece una pregunta fija de examen oral: *"¿Qué tipo de sistema tiene seguro solución y cómo se llama dicha solución?"*. La respuesta es: el **sistema de ecuaciones lineales homogéneo** (aquel donde todos los términos independientes valen `0`, o sea `A • X = 0`). ¿Por qué tiene **seguro** solución? Porque si reemplazás todas las incógnitas por `0` (`x = 0, y = 0, z = 0...`), todas las cuentas dan `0 = 0`, que siempre se cumple. Esa solución formada por todos ceros se llama **solución trivial** (`X* = 0`).
Además, un sistema homogéneo puede ser:
- **Compatible Determinado** (`ρ(A) = m`): su única solución es la **solución trivial** (`x = 0, y = 0...`).
- **Compatible Indeterminado** (`ρ(A) < m`): tiene **infinitas soluciones**, entre las cuales está la **solución trivial** (cuando a la variable libre se le asigna el valor `0`) y también infinitas **soluciones no triviales** (cuando a la variable libre se le asigna cualquier valor distinto de `0`).

**🔍 Desglose de la jerga:**
- **Sistema homogéneo (`A • X = 0`):** Sistema de ecuaciones lineales en el que todos los términos independientes son nulos (`B = 0`).
- **Tiene seguro solución (Siempre compatible):** Propiedad fundamental de los sistemas homogéneos; jamás pueden ser incompatibles porque la última columna de `A° = [A : 0]` es toda de ceros, por lo que ninguna operación elemental de fila puede cambiar esos ceros y siempre se cumple `ρ(A) = ρ(A°)`.
- **Solución trivial:** La solución en la que todas las incógnitas toman el valor cero (`X* = [0 ; 0 ; ... ; 0]`). Todo sistema homogéneo la posee siempre.
- **Soluciones no triviales:** Soluciones particulares de un sistema homogéneo compatible indeterminado en las que al menos una incógnita es distinta de cero.

**💡 Ejemplo (Sistema 4 del Desempeño 2, págs. 7 y 9):**
Sea el sistema homogéneo:
- `28x + 16y = 0`
- `21x + 12y = 0`

1. Todos sus términos independientes son `0` → es un **sistema homogéneo**, por lo que **tiene seguro solución** (admite la solución trivial `x = 0, y = 0`).
2. Al llevar su matriz ampliada `[28  16 : 0 ; 21  12 : 0]` a la forma canónica, la segunda fila es proporcional a la primera (`Fila 2 = (3/4)·Fila 1`) y se anula, quedando una sola fila no nula: `[1   4/7 : 0 ; 0   0 : 0]`.
3. Por lo tanto, `ρ(A) = ρ(A°) = 1 < 2` (2 incógnitas): es un **Sistema Compatible Indeterminado** con **infinitas soluciones** de la forma `x = −(4/7)y, y = y`.
   - Si `y = 0`, se obtiene la **solución trivial** `(0, 0)`.
   - Si `y = 7`, se obtiene la **solución no trivial** `(−4, 7)`.

**🧩 Idea de la demostración / Justificación:**
En `A° = [A : 0]`, cualquier combinación lineal de ceros sigue dando cero. Por ende, una fila que tenga todos ceros en la parte de `A` tendrá obligatoriamente un `0` también en la columna de `B`. Nunca puede aparecer una fila `[0  0  ...  0 : 1]`, de modo que `ρ(A) = ρ(A°)` siempre.

**🤔 Intuición:**
Si ninguna ecuación exige llegar a un número distinto de cero del lado derecho, "no comprar nada / poner todo en cero" siempre cumple todas las condiciones.

**🔗 Conexiones:**
- Conecta la definición de **sistema homogéneo** de la Clase 9 (pág. 6), la demostración de la Clase 10 (págs. 8 y 9) y los ejercicios integradores del Desempeño 1.e, Desempeño 2 (inciso 4) y Desempeño 4 (inciso e, que también es un sistema homogéneo de 4 ecuaciones y 4 incógnitas `x, y, z, u` con rango 3 y solución general en función de `z`) de esta Clase 11.

**⚠️ Precisiones / errores comunes:**
- **Creer que un sistema homogéneo siempre tiene solución única (`0, 0`):** ¡No! Que sea homogéneo garantiza que **es compatible** y que `(0, 0, ..., 0)` es solución, pero puede ser **Compatible Determinado** (si `ρ(A) = m`, teniendo *solo* la solución trivial) o **Compatible Indeterminado** (si `ρ(A) < m`, teniendo la solución trivial *más* infinitas soluciones no triviales, como en el ejercicio 4 del Desempeño 2 y el 4.e).
- **Observación sobre el Desempeño 2 (pág. 7):** En las respuestas rápidas del PDF (pág. 7) se listó al sistema `4-` tanto en `b- Infinitas soluciones` como en `c- Soluciones triviales` porque es el único sistema homogéneo de la lista (y por ende el único que posee la solución trivial `(0,0)`), aunque al tener `ρ(A) = 1 < 2` no tiene *sólo* la solución trivial sino también infinitas soluciones no triviales (`x = −4/7 y`), tal como el propio PDF escribe en la pág. 9. En el oral conviene hacer esta distinción con total claridad.

**🎤 Cómo decirlo en el oral:**
"El tipo de sistema que tiene seguro solución es el **sistema de ecuaciones lineales homogéneo** (`A • X = 0`, donde todos los términos independientes son nulos), porque en su matriz ampliada `A° = [A : 0]` la última columna es nula y el rango de `A` siempre coincide con el rango de `A°`. La solución que todo sistema homogéneo tiene asegurada se llama **solución trivial**, que es aquella en la que todas las incógnitas valen cero. Si además `ρ(A) = m`, la solución trivial es la única solución (compatible determinado); si `ρ(A) < m`, además de la solución trivial existen infinitas soluciones no triviales (compatible indeterminado)."

---

## 11.13 Validación e Interpretación de las Soluciones en Problemas Aplicados (Restricciones de Dominio sobre la Solución General)

> 📖 **Textual del material:**
> **Caso 1 — Restricción a números naturales (Desempeño n° 5, pág. 10):**
> "Es un sistema compatible Indeterminado: X* = [15 − C ; 2 − C ; C].
> Siendo C la variable libre, (puede tomar cualquier valor). Pero teniendo en cuenta que tanto A, B y C son cantidad de lotes, solo pueden tomar valores naturales.
> Analiza que sucede si C es mayor o igual que 3.
> Después de probar con diferentes valores, puedes llegar a la conclusión que las posibilidades son:
> Si C = 0: 15 lotes de A, 2 lotes de B, Ningún lote de C.
> Si C = 1: 14 lotes de A, 1 lote de B, 1 lote de C.
> Si C = 2: 13 lotes de A, Ningún lote de B, 2 lotes de C."
>
> **Caso 2 — Restricción a números naturales y múltiplos por divisibilidad (Desempeño n° 6, págs. 10 y 11):**
> "o sea la solución general del sistema: X* = [2/7 z ; 400 − 10/7 z ; z]
> Si bien esta es la solución matemática, no tenemos que perder de vista que las incógnitas en nuestro problema representan cantidades de bicicletas a fabricar, por lo que solo pueden tomar valores naturales. Entonces analicemos cada una de las incógnitas. Para obtener números enteros, los valores que puede tomar z son números múltiplos de 7 (para poder simplificarlo con el denominador). Por lo tanto z puede tomar valores (habrá que ver hasta qué número puede ser posible)."
> "De la misma manera se puede calcular la cantidad de bicicletas de cada modelo a fabricar, para cada uno de los restantes valores de z que satisfacen la condición encontrada. Ahora… El máximo de bicicletas de carrera que se pueden fabricar es 280. ¿Podrías explicar por qué?"
>
> **Caso 3 — Restricción a números reales no negativos mediante inecuaciones (Desempeño n° 7, pág. 11):**
> "Es decir el vector solución sería: X* = [4 + 4z ; 9 − 5z ; z]
> Analicemos si todas las soluciones satisfacen las condiciones del problema. Como las incógnitas representan cantidades de comida en gramos, pueden tomar cualquier valor real, siempre que no sea negativo. Si z es un número real mayor o igual a cero, claramente x = 4 + 4z, también lo es. No ocurre lo mismo con y = 9 − 5z. Para ésta debemos establecer la condición que 9 − 5z mayor o igual que 0. Si despejamos, tenemos que z debe ser mayo o igual que 9/5.
> Conclusión: Las combinaciones de las tres comidas que cumplen con el requerimiento mínimo de las teres vitaminas son las que verifican
> X* = [4 + 4z ; 9 − 5z ; z]   Con   0 ≤ z ≤ 9/5"
> *(Nota: donde el texto dice "z debe ser mayo o igual que 9/5" es una errata verbal por "menor o igual que 9/5", tal como expresa correctamente la desigualdad final `0 ≤ z ≤ 9/5` dos renglones más abajo).*

**🗣️ En palabras simples:**
Este es el concepto que cumple el segundo objetivo de la portada de la clase (*"Buscar soluciones a problemas y validar su respuesta"*).
Cuando resolvés un sistema compatible indeterminado en abstracto, obtenés la **solución matemática** (la Solución General `X*`), donde la variable libre puede valer cualquier número real (positivo, negativo, con coma o fracción).
Pero cuando el sistema modela un **problema real** (lotes de librería, bicicletas fabricadas, gramos de comida), tenés que **validar la respuesta** preguntándote: *¿qué valores tienen sentido físico para TODAS las incógnitas del vector `X*`?*
Eso impone condiciones sobre la variable libre que recortan las soluciones válidas en tres escenarios típicos que muestra el material:
1. **Cantidades discretas enteras sin fracciones en la fórmula (ej. lotes):** Las incógnitas deben ser naturales/enteros no negativos (`≥ 0`). Si `B = 2 − C ≥ 0`, entonces `C` no puede ser `3` ni mayor porque daría lotes negativos; solo sirven `C = 0, 1, 2` (de infinitas soluciones matemáticas quedan solo **3 soluciones válidas**).
2. **Cantidades discretas enteras con fracciones en la fórmula (ej. bicicletas):** Como `x = (2/7)z` e `y = 400 − (10/7)z` deben ser números naturales (enteros no negativos), la variable libre `z` tiene que ser **múltiplo de 7** para cancelar el denominador `7`, y además no puede superar `280` porque a partir de `z > 280` la cantidad de bicicletas `y = 400 − (10/7)z` daría negativa.
3. **Cantidades continuas medibles (ej. gramos de alimento):** Como los gramos pueden tener decimales pero no pueden ser negativos, las incógnitas pueden tomar cualquier **valor real no negativo (`≥ 0`)**. Planteando que cada fila de `X*` sea `≥ 0` (`z ≥ 0`, `4 + 4z ≥ 0` y `9 − 5z ≥ 0`), la variable libre queda encerrada en un **intervalo real continuo**: `0 ≤ z ≤ 9/5`.

**🔍 Desglose de la jerga:**
- **Solución matemática:** La Solución General `X*` del sistema lineal considerada en todo el conjunto ℝ, sin restricciones de contexto.
- **Valores naturales (en el contexto de estos problemas):** Cantidades enteras no negativas (`0, 1, 2, 3...`), aplicables a objetos indivisibles como lotes de mercadería o bicicletas. *(Observación: en el Desempeño 5 incluye el `0` como "Ningún lote", y en el Desempeño 6 empieza la tabla desde `z = 7` para que se fabriquen unidades de los tres modelos).*
- **Múltiplos del denominador (múltiplos de 7):** Condición de divisibilidad sobre la variable libre cuando en la solución general aparecen coeficientes fraccionarios irreducibles y las incógnitas representan objetos indivisibles.
- **Cualquier valor real, siempre que no sea negativo (`≥ 0`):** Dominio continuo (`ℝ≥0`) propio de magnitudes medibles (peso en gramos, volumen en litros, tiempo), que restringe la variable libre mediante inecuaciones lineales (`0 ≤ z ≤ 9/5`).

**💡 Respuesta a la pregunta conceptual de la página 11 del material:**
- **Pregunta del material (Desempeño n° 6, pág. 11):** *"Ahora… El máximo de bicicletas de carrera que se pueden fabricar es 280. ¿Podrías explicar por qué?"*
- **Explicación exacta:** Porque la cantidad de bicicletas de hombre está dada por la segunda componente de la solución general: `y = 400 − (10/7)z`. Como no se puede fabricar una cantidad negativa de bicicletas, debe cumplirse que `y ≥ 0`, es decir:
  `400 − (10/7)z ≥ 0  ⇒  400 ≥ (10/7)z  ⇒  (400 · 7) / 10 ≥ z  ⇒  280 ≥ z`.
  Para `z = 280` se fabrican `y = 400 − (10/7)·280 = 0` bicicletas de hombre y `x = (2/7)·280 = 80` bicicletas de mujer. Si `z` fuera mayor que `280`, `y` resultaría negativo, lo cual es imposible en el problema.

### 📊 Tabla Comparativa: Los 3 Casos de Validación de la Solución General en Problemas de la Clase 11

| Problema del Material | Qué representan las incógnitas | Solución General Matemática (`X*`) | Restricción del contexto sobre las incógnitas | Condición resultante sobre la variable libre | Cantidad de soluciones válidas para el problema |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Desempeño n° 5** *(Lotes A, B, C)* | Cantidad de lotes de librería (indivisibles) | `[15 − C ; 2 − C ; C]` | Valores enteros no negativos (`A, B, C ∈ ℕ₀`) | `15 − C ≥ 0`, `2 − C ≥ 0` y `C ≥ 0` ⇒ `C ∈ {0, 1, 2}` (si `C ≥ 3`, `B` da negativo) | **Finitas (3 posibilidades):** `C = 0`, `C = 1` o `C = 2` |
| **Desempeño n° 6** *(Bicicletas x, y, z)* | Cantidad de bicicletas a fabricar (indivisibles) | `[(2/7)z ; 400 − (10/7)z ; z]` | Valores enteros no negativos + simplificación del denominador `7` | `z` debe ser **múltiplo de 7** y cumplir `400 − (10/7)z ≥ 0` ⇒ `z ≤ 280` | **Finitas:** múltiplos de `7` hasta `z = 280` (`z = 7, 14, 21, ..., 280`) |
| **Desempeño n° 7** *(Alimentos x, y, z en gramos)* | Cantidad de comida en gramos (magnitud continua) | `[4 + 4z ; 9 − 5z ; z]` | Cualquier valor real no negativo (`x, y, z ∈ ℝ, ≥ 0`) | `z ≥ 0` y `9 − 5z ≥ 0` ⇒ **`0 ≤ z ≤ 9/5`** | **Infinitas (acotadas en un intervalo real):** todo `z ∈ [0, 9/5]` |

**🔗 Conexiones:**
- Conecta el álgebra matricial de Sistemas Compatibles Indeterminados con el modelado matemático y el análisis de dominios (conjuntos numéricos `ℕ` vs `ℝ`).

**⚠️ Precisiones / errores comunes:**
- **Mirar solo la variable libre y olvidarse de las dependientes:** Un error muy común es decir "como `C` es cantidad de lotes, basta con que `C ≥ 0`". ¡No! Porque si `C = 5`, aunque `C` es positivo, `B = 2 − 5 = −3` da negativo. **Todas** las componentes del vector `X*` (`A`, `B` y `C`) deben cumplir la condición de no negatividad simultáneamente.
- **Restringir a enteros cuando la magnitud es continua:** En el problema de los gramos de comida (Desempeño 7), el material destaca expresamente que como son gramos *"pueden tomar cualquier valor real, siempre que no sea negativo"*, por lo que la respuesta no es una lista de enteros sino la desigualdad continua `0 ≤ z ≤ 9/5`.

**🎤 Cómo decirlo en el oral:**
"En un problema aplicado cuyo planteo lleva a un sistema compatible indeterminado, el vector `X*` hallado es la solución matemática, donde la variable libre puede tomar cualquier valor real. Sin embargo, para validar la respuesta debemos analizar qué representan las incógnitas en el problema: si representan objetos indivisibles (como lotes o bicicletas), todas las componentes de `X*` deben tomar valores naturales no negativos (y si hay fracciones en `X*`, la variable libre debe ser múltiplo del denominador para simplificarlo); en cambio, si representan magnitudes continuas (como gramos de alimento), pueden tomar cualquier valor real no negativo, lo que lleva a plantear inecuaciones (`≥ 0`) sobre cada componente de `X*` para acotar el intervalo de valores válidos de la variable libre."

---

## 🧠 Resumen esquemático de la clase

- **Forma matricial de un sistema lineal (`n × m`):** `A_(n×m) • X_(m×1) = B_(n×1)`, donde `A` es la **Matriz de los coeficientes**, `X` la **Matriz (o vector) de las incógnitas** y `B` la **Matriz (o vector) de los términos independientes** (previo reacomodamiento con incógnitas en el primer miembro y términos independientes en el segundo).
- **Matriz ampliada (`A°`) y equivalencia:** `A° = [A : B]`; al aplicarle operaciones elementales por fila para llevarla a la **matriz canónica**, se obtiene un **sistema equivalente** porque a las ecuaciones no les cambian las soluciones.
- **Condición de Sistema Incompatible:** En la matriz canónica, **el rango de la matriz de los coeficientes y el rango de la matriz ampliada son números distintos (`ρ(A) ≠ ρ(A°)`)**; el sistema **no tiene solución** (ningún conjunto de números satisface las ecuaciones).
- **Detección temprana de incompatibilidad por contradicción:** Si antes de llegar a la matriz canónica aparece una fila que traduce una igualdad del tipo `0 = k` con `k ≠ 0` (ej. `0 = 8`), ya se advierte que el sistema es **Incompatible** por ser una **contradicción**.
- **Condición de Sistema Compatible Indeterminado:** En la matriz canónica, **el rango de la matriz de los coeficientes es igual al rango de la matriz ampliada (`ρ(A) = ρ(A°)`)** —por eso es **Compatible**—, pero ese rango es **distinto (menor) al número de incógnitas (`ρ(A°) < m`)** —por eso es **Indeterminado** (infinitas soluciones)—.
- **Cantidad de variables libres o independientes:** Se calcula como la **diferencia (resta) entre el número de incógnitas y el rango de la matriz ampliada** (`cantidad de variables libres = m − ρ(A°)`).
- **Solución General (`X*`):** Vector solución del sistema compatible indeterminado en el que las variables dependientes se expresan despejadas en función de la(s) variable(s) libre(s).
- **Solución Particular:** Vector numérico concreto que se obtiene a partir de la Solución General asignándole un valor específico a la variable libre; existen **infinitas soluciones particulares**.
- **Sistema con solución asegurada:** El **sistema homogéneo (`A • X = 0`)** siempre es compatible (`ρ(A) = ρ(A°)`) y tiene asegurada la **solución trivial** (`X* = 0`).
- **Validación contextual de la Solución General:** Exigir que todas las componentes de `X*` respeten la naturaleza del problema (números naturales `ℕ₀`, múltiplos del denominador cuando hay fracciones en cantidades discretas, o números reales no negativos `ℝ≥0` acotados por inecuaciones en magnitudes continuas).

---

## ❓ Preguntas probables del oral

1. **¿Qué condiciones desde el punto de vista matricial se deben dar para que un sistema de ecuaciones sea incompatible?** *(Desempeño 1.a)*
   - **Respuesta:** Una vez llevada la matriz ampliada a la matriz canónica, el **rango de la matriz de los coeficientes** y el **rango de la matriz ampliada** deben ser **números distintos** (`ρ(A) ≠ ρ(A°)`). Esto indica que el sistema no tiene solución, es decir, no hay ningún conjunto de números que satisfagan las ecuaciones.

2. **¿Es siempre obligatorio llegar hasta la matriz canónica para saber que un sistema es incompatible?**
   - **Respuesta:** No, a veces no es necesario llegar a la matriz canónica. Si al aplicar operaciones elementales aparece en cualquier paso una fila cuyos coeficientes de las incógnitas son todos `0` y su término independiente es distinto de `0` (por ejemplo, dando lugar a la ecuación `0 = 8`), ya se puede advertir que el sistema es **Incompatible**, porque esa ecuación no se verifica para ningún conjunto de valores de las incógnitas al ser una **contradicción**.

3. **¿Qué condiciones desde el punto de vista matricial se deben dar para que un sistema sea compatible indeterminado?** *(Desempeño 1.b)*
   - **Respuesta:** En la matriz canónica se deben cumplir dos cosas: primero, que el **rango de la matriz de los coeficientes sea igual al rango de la matriz ampliada** (`ρ(A) = ρ(A°)`), lo que indica que el sistema es **Compatible** (tiene solución); y segundo, que ese rango sea **distinto (menor) al número de incógnitas** (`ρ(A°) < m`), lo que indica que el sistema es **Indeterminado** (tiene infinitas soluciones).

4. **¿Cómo se determina la cantidad de variables libres o independientes en un sistema compatible indeterminado?** *(Desempeño 1.c)*
   - **Respuesta:** Se determina mediante la **diferencia (resta) entre el número de incógnitas del sistema y el rango de la matriz ampliada** (o de la matriz de los coeficientes, ya que son el mismo número): `cantidad de variables libres = m − ρ(A°)`.

5. **¿Qué diferencia hay entre la Solución General y una Solución Particular en un sistema compatible indeterminado, y cómo se obtiene una solución particular?** *(Desempeño 1.d)*
   - **Respuesta:** La **Solución General** es el vector solución `X*` en el cual las variables dependientes están expresadas en función de la(s) variable(s) libre(s). Una **Solución Particular** es un vector numérico concreto que se obtiene a partir de la Solución General asignándole un valor determinado a la variable libre y calculando el valor resultante de las demás variables. Como a la variable libre se le pueden asignar infinitos valores, se pueden obtener **infinitas soluciones particulares**.

6. **¿Qué tipo de sistema tiene seguro solución y cómo se llama dicha solución?** *(Desempeño 1.e)*
   - **Respuesta:** El **sistema de ecuaciones lineales homogéneo** (`A • X = 0`, aquel cuyos términos independientes son todos nulos) tiene seguro solución, es decir, siempre es compatible, porque al agregar la columna nula en `A° = [A : 0]` el rango de la matriz ampliada siempre es igual al rango de la matriz de los coeficientes. La solución que siempre tiene asegurada se llama **solución trivial** (donde todas las incógnitas son iguales a `0`).

7. **¿Un sistema homogéneo tiene siempre únicamente la solución trivial?**
   - **Respuesta:** No. Todo sistema homogéneo tiene la solución trivial, pero solo es su *única* solución cuando el sistema es **Compatible Determinado** (`ρ(A) = m`). Si el rango es menor que el número de incógnitas (`ρ(A) < m`), el sistema homogéneo es **Compatible Indeterminado** y posee infinitas soluciones: la solución trivial (cuando la variable libre vale `0`) más infinitas **soluciones no triviales** (como ocurre en el ejercicio 4 del Desempeño 2: `28x + 16y = 0 ; 21x + 12y = 0`).

8. **¿Cómo se debe preparar el sistema antes de armar las matrices y cuáles son las tres matrices que componen su forma matricial?**
   - **Respuesta:** Primero se debe **reacomodar (completar y ordenar)** el sistema de tal manera que en el primer miembro queden los términos con las incógnitas y en el segundo miembro queden los términos independientes. Luego se arman las tres matrices: la **Matriz de los coeficientes (`A`)** (formada por los números que multiplican a cada una de las incógnitas), la **Matriz o vector de los términos independientes (`B`)** y la **Matriz o vector de las incógnitas (`X`)**, que se relacionan mediante la **forma matricial** `A_(n×m) • X_(m×1) = B_(n×1)`.

9. **¿Por qué podemos asegurar que al llevar la matriz ampliada `A°` a la forma canónica el sistema que se obtiene tiene las mismas soluciones que el original?**
   - **Respuesta:** Podemos asegurar que el sistema que se obtiene es **equivalente** porque para llevar la matriz ampliada a la canónica aplicamos **operaciones elementales** por fila, y al aplicar operaciones elementales a la matriz ampliada, a cada una de las ecuaciones no le cambiarán las soluciones.

10. **¿Qué diferencia hay entre encontrar una fila `0  0  0 : 8` y encontrar una fila `0  0  0 : 0` al reducir la matriz ampliada?**
    - **Respuesta:** La fila `0  0  0 : 8` representa la ecuación `0 = 8`, que es una **contradicción**; hace que `ρ(A) ≠ ρ(A°)` y demuestra que el sistema es **Incompatible**. En cambio, la fila `0  0  0 : 0` representa la identidad `0 = 0`; es una fila nula tanto en `A` como en `A°`, por lo que no altera la igualdad de rangos y suele presentarse cuando una ecuación era combinación lineal de las otras (por ejemplo, en sistemas compatibles indeterminados de `3 × 3` con rango `2`).

11. **Si un sistema compatible indeterminado modela un problema donde las incógnitas son cantidades de objetos (como lotes o bicicletas), ¿sigue teniendo infinitas soluciones válidas?**
    - **Respuesta:** Matemáticamente el sistema tiene infinitas soluciones, pero al **validar la respuesta** en el problema las incógnitas solo pueden tomar **valores naturales (enteros no negativos)**. Si en la Solución General una variable dependiente tiene la variable libre restando (por ejemplo `B = 2 − C` o `y = 400 − (10/7)z`), la condición de que todas las incógnitas sean mayores o iguales a cero acota superiormente a la variable libre (y si hay denominadores como `7`, exige además que la variable libre sea múltiplo de `7`), reduciendo las infinitas soluciones matemáticas a un número finito de posibilidades válidas.

12. **¿Cómo cambia la validación de la Solución General cuando las incógnitas representan gramos de alimento en lugar de unidades enteras?**
    - **Respuesta:** Como las cantidades en gramos representan una magnitud continua, las incógnitas pueden tomar **cualquier valor real, siempre que no sea negativo** (`≥ 0`). En ese caso no se exige que la variable libre sea entera, sino que se plantea la condición de que cada componente de `X*` sea mayor o igual que `0` (por ejemplo, `z ≥ 0` y `9 − 5z ≥ 0`), obteniendo un **intervalo real continuo** de soluciones válidas (`0 ≤ z ≤ 9/5`).

---

## 📚 Glosario de la clase

| Término | Definición breve fiel al material |
| :--- | :--- |
| **Sistema Incompatible** | Sistema de ecuaciones que no tiene solución (no hay ningún conjunto de números que satisfagan las ecuaciones). Matricialmente se da cuando el rango de la matriz de los coeficientes y el rango de la matriz ampliada son números distintos (`ρ(A) ≠ ρ(A°)`). |
| **Contradicción (`0 = k` con `k ≠ 0`)** | Igualdad falsa (como `0 = 8` o `0 = 1`) que surge de una fila con todos los coeficientes nulos y término independiente no nulo, y que permite advertir que el sistema es Incompatible aún sin haber llegado a la matriz canónica. |
| **Sistema Compatible** | Sistema de ecuaciones que tiene solución. Matricialmente se da cuando el rango de la matriz de los coeficientes es igual al rango de la matriz ampliada (`ρ(A) = ρ(A°)`). |
| **Sistema Compatible Indeterminado** | Sistema compatible (con `ρ(A) = ρ(A°)`) en el cual el número de incógnitas es distinto (mayor) al rango de la matriz ampliada (`ρ(A°) < m`), por lo que tiene infinitas soluciones. |
| **Coeficientes** | Los números que multiplican a cada una de las incógnitas en las ecuaciones del sistema. |
| **Matriz de los coeficientes (`A`)** | Matriz de orden `n × m` formada por los coeficientes que multiplican a cada una de las incógnitas en el sistema ordenado. |
| **Matriz (o vector) de los términos independientes (`B`)** | Matriz o vector columna de orden `n × 1` formado por los términos independientes ubicados en el segundo miembro de cada ecuación. |
| **Matriz (o vector) de las incógnitas (`X`)** | Matriz o vector columna de orden `m × 1` formado por las incógnitas del sistema. |
| **Forma matricial del sistema** | Expresión del sistema de ecuaciones como el producto matricial `A_(n×m) • X_(m×1) = B_(n×1)`. |
| **Matriz ampliada (`A°`)** | Matriz formada a partir de la matriz de los coeficientes `A` y del vector de los términos independientes `B` (`A° = [A : B]`), a la cual se le aplican operaciones elementales para llevarla a la forma canónica. |
| **Sistema equivalente** | Sistema obtenido al aplicar operaciones elementales a la matriz ampliada del sistema dado, cuyas ecuaciones conservan exactamente las mismas soluciones que el sistema original. |
| **Variables libres o independientes** | Incógnitas de un sistema compatible indeterminado a las que se les puede asignar cualquier valor arbitrario y de las cuales dependen las demás incógnitas. Su cantidad es la diferencia entre el número de incógnitas y el rango de la matriz ampliada (`m − ρ(A°)`). |
| **Solución General del Sistema (`X*`)** | Vector solución `X*` de un sistema compatible indeterminado cuyas componentes expresan a las incógnitas dependientes en función de la(s) variable(s) libre(s). |
| **Solución Particular** | Cada vector numérico concreto `X*` que se obtiene a partir de la Solución General al asignarle un valor específico a la variable libre. |
| **Sistema homogéneo (`A • X = 0`)** | Sistema de ecuaciones lineales cuyos términos independientes son todos iguales a cero; siempre es compatible (tiene seguro solución). |
| **Solución trivial** | Solución en la que todas las incógnitas valen cero (`X* = 0`), la cual verifica siempre todo sistema de ecuaciones homogéneo. |
