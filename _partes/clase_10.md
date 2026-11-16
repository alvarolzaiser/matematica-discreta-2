# Clase 10 — Sistemas de Ecuaciones (Método General de Resolución y Sistemas Compatibles Determinados)

## 🗺️ Mapa de la clase

### Estructura y orden de los temas en el material
- **1. Introducción y motivación (Pág. 2):** Aplicación de las matrices a la resolución práctica de sistemas de ecuaciones lineales, especialmente cuando hay varias ecuaciones y varias incógnitas.
- **2. Descomposición y representación matricial de un sistema (Págs. 2, 3 y 5):**
  - Preparación del sistema: **reacomodar, completar y ordenar** (incógnitas en el primer miembro, términos independientes en el segundo miembro) (**10.1**).
  - Las tres matrices del sistema: **Matriz de los coeficientes (A)**, **Matriz o vector de los términos independientes (B)** y **Matriz o vector de las incógnitas (X)** (**10.2**).
  - **Forma matricial** del sistema de ecuaciones: `A_(n×m) · X_(m×1) = B_(n×1)` (**10.3**).
  - **Matriz ampliada** del sistema: `A° = [ A : B ]` y la propiedad de **equivalencia de sistemas** bajo operaciones elementales de fila (**10.4**).
- **3. Algoritmo del Método General de Resolución y sistemas compatibles determinados (Págs. 3 a 6 y 11):**
  - Los **5 pasos oficiales** del método general de resolución (**10.5**).
  - Reducción de `A°` a su forma canónica, rearme del sistema equivalente y construcción del vector solución `X*`.
  - Concepto de **Sistema Compatible** y **Sistema Determinado** (**10.6**).
- **4. Clasificación de sistemas mediante el Rango de la Matriz Ampliada (Págs. 6 a 8):**
  - Definición de **rango de una matriz** `ρ(A)` y lectura simultánea de `ρ(A)` y `ρ(A°)` sobre la matriz ampliada llevada a la canónica (**10.7**).
  - Criterio de compatibilidad (Teorema de Rouché-Frobenius): **Compatible** (`ρ(A) = ρ(A°)`) vs. **Incompatible** (`ρ(A) ≠ ρ(A°)`) (**10.8**).
  - Criterio de determinación dentro de los compatibles: **Determinado** (`ρ(A°) = m`) vs. **Indeterminado** (`ρ(A°) < m`), donde `m` es la cantidad de incógnitas (**10.9**).
  - Cuadro sinóptico general de clasificación (**10.10**).
- **5. Sistemas de ecuaciones lineales homogéneos (Págs. 8 y 9):**
  - Definición (`A · X = 0`), demostración de por qué **siempre son compatibles** (`ρ(A) = ρ(A°)`), **solución trivial** (`X = 0`) y **soluciones no triviales** (**10.11**).
  - **Sistemas homogéneos cuadrados** (`A` de orden `n×n`): criterio del **determinante** (`|A| = 0` para soluciones no triviales / sistema indeterminado vs. `|A| ≠ 0` para única solución trivial / sistema determinado) (**10.12**).
- **6. Validación de la respuesta en problemas aplicados (Págs. 1 y 10):**
  - Diferencia conceptual entre **solución del sistema matemático** y **solución del problema real** (**10.13**).

### Prerrequisitos (conexiones con clases previas)
- **Clase 7 y Clase 8 (Matrices, operaciones elementales y matriz canónica):** Orden de una matriz (`n×m`), vector columna (`m×1`), vector nulo (`0`), multiplicación de matrices y su condición de conformabilidad, operaciones elementales de fila (`H_i(k)`, `H_(i,j)(k)`, `H_(i,j)`), matrices equivalentes (`~`) y condiciones para que una matriz sea **canónica** (escalonada reducida por filas).
- **Clase 8 y Clase 9 (Determinantes y planteo de sistemas de ecuaciones):** Cálculo del determinante de una matriz cuadrada, relación entre determinante nulo y rango, traducción del lenguaje coloquial al lenguaje algebraico, y la noción general de sistema compatible (determinado/indeterminado) e incompatible vista en la Clase 9.

---

## 10.1 Preparación del sistema: sistema completo y ordenado

> 📖 **Textual del material:** "Para comenzar con este método general, reacomodamos el sistema de tal manera que en el primer miembro queden los términos con las incógnitas, y en el segundo miembro queden los términos independientes. (si es necesario, se completa)."
>
> 📖 **Textual del material (recuadro destacado, Pág. 3):** "Para tener en cuenta: Para armar la forma matricial es importante que el sistema este completo y ordenado."
>
> 📖 **Textual del material (Pág. 5):** "Para comenzar con este método general, reacomodamos el sistema. Recordemos que en el primer miembro deben quedar los términos con las incógnitas, y en el segundo miembro los términos independientes. (si es necesario, se completa)."

**🗣️ En palabras simples:** Antes de volcar un sistema de ecuaciones en una matriz, hay que "prolijarlo": pasar todas las incógnitas a la izquierda del signo `=`, todos los números sueltos (sin incógnita) a la derecha del `=`, encolumnar las incógnitas siempre en el mismo orden (por ejemplo, primero `x`, después `y`, después `z`) y, si en alguna ecuación falta una incógnita, agregarla multiplicada por `0` (o recordar que su coeficiente vale `0`).

**🔍 Desglose de la jerga:**
- **Primer miembro:** Todo lo que está a la izquierda del signo igual (`=`) en cada ecuación. Allí deben ubicarse únicamente los términos que contienen incógnitas.
- **Segundo miembro:** Todo lo que está a la derecha del signo igual (`=`). Allí deben ubicarse únicamente los **términos independientes** (los números que no están multiplicados por ninguna incógnita).
- **Sistema ordenado:** Todas las ecuaciones tienen las incógnitas escritas exactamente en la misma secuencia de izquierda a derecha (por ejemplo, `x`, luego `y`, luego `z`), de modo que cada columna de la futura matriz corresponda a una única incógnita.
- **Sistema completo:** Si una ecuación no menciona alguna de las incógnitas del sistema, esa posición no se saltea ni se corre: se completa con coeficiente `0` (por ejemplo, `+ 0·y`).

**💡 Ejemplo (basado en el Ejemplo N° 4 y Ejemplo N° 5 del material, Págs. 2 y 5):**
En el Ejemplo N° 4 (Pág. 2), la tercera ecuación surge del planteo como:
`x + z + 10 = 2y`
No está ordenada ni tiene separados los miembros. Al reacomodar, pasamos `2y` restando al primer miembro y `10` restando al segundo miembro, ubicando `-2y` entre `x` y `z`:
`x - 2y + z = -10`
En el Ejemplo N° 5 (Pág. 5), el sistema original es:
- `x - 2y = 2z`
- `x = 8z - 2y`
- `4y + 4z = 150 - x`

Reacomodado, completo y ordenado queda:
- `x - 2y - 2z = 0`
- `x + 2y - 8z = 0`
- `x + 4y + 4z = 150`
(Observá cómo en las dos primeras ecuaciones, al pasar todos los términos al primer miembro, el segundo miembro se completa con término independiente `0`).

**🔗 Conexiones:** Es el **Paso 1** (`1ero| Completar y ordenar el sistema dado`) del Método General de Resolución (sección **10.5**). Sin este paso, los elementos de la matriz de coeficientes `A` quedarían mal ubicados en las columnas o con signos incorrectos.

**⚠️ Precisiones / errores comunes:**
- **Error de signo al trasponer miembros:** Al pasar un término de un miembro al otro (como `2y` en `x + z + 10 = 2y`), cambia su signo (`-2y`). Olvidar cambiar el signo altera toda la matriz `A` y el vector `B`.
- **Error de encolumnado (desorden):** En el Desempeño 5b (Pág. 10), la tercera ecuación está escrita como `3x_3 + 4x_1 = 5`. Si uno copia `[3, 0, 4]` sin ordenar primero como `4x_1 + 0x_2 + 3x_3 = 5`, asigna el coeficiente de `x_3` a la columna de `x_1`.
- **Falta de término independiente explícito:** Cuando todas las incógnitas pasan a la izquierda y no había número suelto, en el segundo miembro queda `0` (como en el Ejemplo N° 5).

**🎤 Cómo decirlo en el oral:**
> "Antes de armar las matrices de un sistema para aplicar el método general, es fundamental que el sistema esté **completo y ordenado**: debemos reacomodarlo de tal manera que en el primer miembro queden todos los términos con las incógnitas (respetando el mismo orden en todas las ecuaciones y completando con coeficiente cero las incógnitas ausentes) y en el segundo miembro queden los términos independientes."

---

## 10.2 Las tres matrices del sistema: Matriz de los coeficientes (A), Vector de los términos independientes (B) y Vector de las incógnitas (X)

> 📖 **Textual del material (Pág. 2):** "Lo que hay que hacer a continuación es armar tres matrices: La matriz de los coeficientes, el vector de los términos independientes y el vector de las incógnitas. Al hacer esto vamos a estar en cierta forma “desarmando” el sistema, para armar matrices."
>
> 📖 **Textual del material (Pág. 3):** "A la matriz A la llamaremos Matriz de los coeficientes, a la matriz B la llamaremos Matriz (o vector) de los términos independientes y a la matriz X la llamaremos matriz (o vector) de las incógnitas. (Por si no quedó claro, los coeficientes son los números que multiplican a cada una de las incógnitas)."
>
> 📖 **Textual del material (recuadro destacado, Pág. 5):** "Recordemos: A la matriz A la llamamos Matriz de los coeficientes, a la matriz B la llamamos Matriz (o vector) de los términos independientes y a la matriz X la llamamos matriz (o vector) de las incógnitas. (Por si no quedó claro, los coeficientes son los números que multiplican a cada una de las incógnitas)"

**🗣️ En palabras simples:** "Desarmamos" el sistema de ecuaciones separando sus tres ingredientes en tres bloques matriciales:
1. **`A` (Matriz de los coeficientes):** una tabla con solo los números que multiplican a las letras (con su signo), sin las letras.
2. **`X` (Matriz o vector de las incógnitas):** una columna con las letras (incógnitas) en el orden elegido.
3. **`B` (Matriz o vector de los términos independientes):** una columna con los resultados que están del otro lado del igual.

**🔍 Desglose de la jerga:**
- **Coeficientes:** Son los números reales que multiplican a cada una de las incógnitas en el sistema ordenado y completo (incluyendo su signo; si una incógnita aparece sola como `+x`, su coeficiente es `1`; si aparece `-y`, es `-1`; si no figura en esa ecuación, es `0`).
- **Matriz de los coeficientes (`A`):** Matriz de orden `n × m`, donde cada fila `i` corresponde a la ecuación `i`-ésima (hay `n` ecuaciones) y cada columna `j` corresponde a la incógnita `j`-ésima (hay `m` incógnitas).
- **Matriz (o vector) de los términos independientes (`B`):** Matriz columna (vector columna) de orden `n × 1` formada por los números del segundo miembro de cada una de las `n` ecuaciones.
- **Matriz (o vector) de las incógnitas (`X`):** Matriz columna (vector columna) de orden `m × 1` formada por las `m` variables o incógnitas del sistema (por ejemplo, `x, y, z`).

**💡 Ejemplo (del material, Ejemplo N° 4, Págs. 2 y 3):**
Dado el sistema completo y ordenado:
- `1·x + 1·y + 1·z = 95`
- `5·x + 10·y + 20·z = 1175`
- `1·x - 2·y + 1·z = -10`

Las tres matrices son:
- **Matriz de los coeficientes `A` (de orden `3 × 3`):**
  - Fila 1: `[ 1   1   1 ]`
  - Fila 2: `[ 5  10  20 ]`
  - Fila 3: `[ 1  -2   1 ]`
- **Vector de los términos independientes `B` (de orden `3 × 1`):**
  - Columna: `[ 95 ; 1175 ; -10 ]`
- **Vector de las incógnitas `X` (de orden `3 × 1`):**
  - Columna: `[ x ; y ; z ]`

**🔗 Conexiones:**
- Con la **Clase 7 (Vectores fila y columna):** `B` y `X` se llaman indistintamente "matriz" o "vector" porque toda matriz de una sola columna (`n × 1` o `m × 1`) es un vector columna.
- Con las secciones **10.3** y **10.4**: Estas tres matrices permiten escribir la **forma matricial** (`A · X = B`) y construir la **matriz ampliada** (`A° = [ A : B ]`).

**⚠️ Precisiones / errores comunes:**
- **No poner las incógnitas dentro de `A`:** `A` contiene *únicamente números* (los coeficientes). En `A` jamás se escribe `5x` ni `2y`, sino `5` y `2`.
- **Dimensiones de `X` vs. dimensiones de `B`:** Si el sistema no es cuadrado (tiene `n` ecuaciones y `m` incógnitas con `n ≠ m`), `B` tiene `n` filas (una por ecuación) mientras que `X` tiene `m` filas (una por incógnita). Solo coinciden en tamaño cuando `n = m`.

**🎤 Cómo decirlo en el oral:**
> "Al desarmar un sistema lineal completo y ordenado de `n` ecuaciones con `m` incógnitas, formamos tres matrices: a la matriz `A` (de orden `n × m`) la llamamos **Matriz de los coeficientes**, formada por los números que multiplican a cada incógnita; a la matriz `B` (de orden `n × 1`) la llamamos **Matriz o vector de los términos independientes**; y a la matriz `X` (de orden `m × 1`) la llamamos **Matriz o vector de las incógnitas**."

---

## 10.3 Forma matricial del sistema de ecuaciones

> 📖 **Textual del material (Pág. 3):** "Vamos a ver qué sucede si resolvemos el siguiente producto. (para esto tendremos que recordar cómo se resuelve la multiplicación de matrices).
> En nuestro caso sería:
> A nxm . X mx1 = Bnx1
> A 3x3 . X 3x1 = B3x1
> Esto es la forma matricial *del sistema de ecuaciones y será la que nos permita resolverlo con el método general."

**🗣️ En palabras simples:** Si multiplicamos la matriz de los coeficientes `A` por el vector columna de las incógnitas `X` usando la regla común de multiplicación de matrices (fila por columna) e igualamos el resultado al vector de términos independientes `B`, recuperamos exactamente el sistema de ecuaciones original. Por eso la ecuación matricial `A · X = B` es otra manera —compacta y algebraica— de escribir todo el sistema.

**🔍 Desglose de la jerga:**
- **`A_(n×m) · X_(m×1) = B_(n×1)`:**
  - `n`: número de filas de `A` y de `B`, que representa la **cantidad de ecuaciones** del sistema.
  - `m`: número de columnas de `A` y número de filas de `X`, que representa la **cantidad de incógnitas** del sistema (como aclara textualmente la Pág. 8: *"Donde m es la cantidad de incógnitas"*).
  - **Conformabilidad del producto:** El producto `A · X` se puede realizar porque el número de columnas de `A` (`m`) coincide con el número de filas de `X` (`m`). El resultado es una matriz de orden `n × 1`, que coincide con el orden de `B_(n×1)`.
- **Forma matricial del sistema:** La expresión `A · X = B` (o desplegada con los elementos de `A`, `X` y `B`).

**💡 Ejemplo (del material, Pág. 3):**
Para el Ejemplo N° 4 (`3` ecuaciones y `3` incógnitas, `A_(3×3) · X_(3×1) = B_(3×1)`), la forma matricial es:
```
[ 1   1   1 ]   [ x ]   [  95  ]
[ 5  10  20 ] · [ y ] = [ 1175 ]
[ 1  -2   1 ]   [ z ]   [ -10  ]
```
*(Contexto adicional para verificar por qué funciona)*: Si multiplicamos la primera fila de `A` por la columna `X`, obtenemos `1·x + 1·y + 1·z`, y al igualarlo al primer elemento de `B` (`95`), tenemos `x + y + z = 95`, que es la primera ecuación del sistema.

**🔗 Conexiones:**
- Con la **Clase 7 (Multiplicación de matrices e igualdad de matrices):** La forma matricial descansa en la definición de producto matricial (`A_(n×m) · X_(m×1)`) y en que dos matrices del mismo orden (`n × 1`) son iguales si y solo si sus elementos homólogos son iguales (lo que genera las `n` ecuaciones escalares).
- Con la sección **10.11 (Sistemas homogéneos):** Cuando `B` es el vector nulo `0`, la forma matricial se escribe `A · X = 0`.

**⚠️ Precisiones / errores comunes:**
- **El orden de los factores NO es conmutativo:** Siempre es `A · X = B` y **nunca** `X · A = B`. De hecho, si `m > 1`, el producto `X_(m×1) · A_(n×m)` ni siquiera es conformable cuando `n > 1`.
- **Confundir `n` con `m` en la notación de la cátedra:** En este material de MD2, la matriz es de orden `n × m`, donde **`n` son las ecuaciones (filas)** y **`m` son las incógnitas (columnas)**. ¡Mucha atención en el oral porque en el cuadro de la Pág. 8 se compara el rango con `m` (cantidad de incógnitas)!

**🎤 Cómo decirlo en el oral:**
> "La **forma matricial** de un sistema de `n` ecuaciones lineales con `m` incógnitas es la expresión `A_(n×m) · X_(m×1) = B_(n×1)`, donde `A` es la matriz de los coeficientes de orden `n × m`, `X` es el vector de las incógnitas de orden `m × 1` y `B` es el vector de los términos independientes de orden `n × 1`. Al resolver el producto matricial `A · X` e igualar componente a componente con `B`, se obtiene el sistema de ecuaciones original."

---

## 10.4 Matriz ampliada del sistema (A°) y equivalencia de sistemas

> 📖 **Textual del material (Pág. 3):** "A continuación vamos a armar una nueva matriz: la matriz ampliada del sistema de ecuaciones dado, que se forma a partir de la matriz de los coeficientes y del vector de los términos independientes, quedando de la siguiente manera:
> Para el sistema dado, la matriz ampliada es: Aº = [ A : B ]
> Donde Aº es el símbolo que representa a la matriz ampliada."
>
> 📖 **Textual del material (Pág. 3):** "A partir de esta matriz ampliada, encontraremos, si tiene, la o las soluciones del sistema. Esto lo haremos llevándola a canónica y obteniendo así un sistema equivalente más sencillo de resolver, del cual sacaremos la o las soluciones.
> Podemos asegurar que el sistema que se obtiene es equivalente ya que si aplicamos operaciones elementales a la matriz ampliada, a cada una de las ecuaciones no le cambiarán las soluciones."

**🗣️ En palabras simples:** Para no tener que escribir las letras `x, y, z` ni el signo `=` en cada paso, pegamos la matriz `A` y la columna `B` en una sola tabla llamada **matriz ampliada (`A°`)**, separadas por dos puntos (`:`). Cada fila de `A°` representa una ecuación completa. Si le aplicamos operaciones elementales por filas a `A°` hasta llevarla a la forma canónica, el nuevo sistema que se lee al final es muchísimo más simple (casi despejado) pero **tiene exactamente las mismas soluciones** que el sistema original.

**🔍 Desglose de la jerga:**
- **`A°` (o `Ao`):** Símbolo oficial que utiliza la cátedra para representar a la **matriz ampliada** del sistema.
- **`[ A : B ]`:** Notación que indica que a las `m` columnas de la matriz de los coeficientes `A` se les adjunta, a la derecha y separada por una línea vertical de dos puntos (`:`), la columna `B` de los términos independientes. *(Contexto adicional: si `A` es de orden `n × m`, entonces `A°` tiene orden `n × (m + 1)`).*
- **Llevar a canónica:** Aplicar una sucesión finita de operaciones elementales de fila (`H_i(k)`, `H_(i,j)(k)`, `H_(i,j)`) sobre toda la matriz ampliada `A°` hasta que la parte izquierda (correspondiente a `A`, o toda `A°`) cumpla las condiciones de matriz canónica.
- **Sistema equivalente:** Dos sistemas de ecuaciones son equivalentes cuando tienen exactamente el mismo conjunto de soluciones.
- **Justificación teórica (por qué no cambian las soluciones):** Aplicar operaciones elementales a las filas de `A°` equivale a intercambiar ecuaciones de lugar (`H_(i,j)`), multiplicar ambos miembros de una ecuación por una constante no nula (`H_i(k)` con `k ≠ 0`), o sumarle a una ecuación un múltiplo de otra ecuación del mismo sistema (`H_(i,j)(k)`). Ninguna de estas operaciones altera las soluciones de las ecuaciones.

**💡 Ejemplo (del material, Ejemplo N° 4, Pág. 3):**
Para el sistema del Ejemplo N° 4, la matriz ampliada `A° = [ A : B ]` es:
```
     [ 1   1   1  :   95  ]
A° = [ 5  10  20  :  1175 ]
     [ 1  -2   1  :  -10  ]
```

**🔗 Conexiones:**
- Con la **Clase 8 (Operaciones elementales y matriz canónica equivalente):** Se utiliza exactamente el mismo procedimiento de Gauss-Jordan visto en la Unidad 2, pero ahora toda operación de fila afecta simultáneamente a las columnas de `A` y a la última columna (`B`).
- Con la sección **10.7 (Lectura del rango):** Sobre la forma canónica de `A°` se leen de un vistazo tanto el rango de `A` (ignorando la última columna) como el rango de `A°` (incluyendo la última columna).

**⚠️ Precisiones / errores comunes:**
- **Olvidar operar sobre la columna `B`:** Cuando se aplica una operación elemental de fila (por ejemplo, `H_(2,1)(-5)`), **toda la fila** de `A°` debe transformarse, incluido el término independiente a la derecha de los dos puntos (`:`). Si no se transforma la columna `B`, el sistema deja de ser equivalente.
- **Notación:** Respetar el símbolo `A°` y el separador `:` (`A° = [ A : B ]`) tal como los escribe el material.

**🎤 Cómo decirlo en el oral:**
> "La **matriz ampliada** de un sistema de ecuaciones, simbolizada `A°`, es la matriz que se forma a partir de la matriz de los coeficientes `A` y del vector de los términos independientes `B`, escribiéndose `A° = [ A : B ]`. Al llevar `A°` a la forma canónica mediante operaciones elementales de fila, podemos asegurar que el sistema que se obtiene es **equivalente** al original —es decir, tiene las mismas soluciones— porque al aplicar operaciones elementales a la matriz ampliada no cambian las soluciones de las ecuaciones."

---

## 10.5 Algoritmo: Método general de resolución de sistemas de ecuaciones lineales

> 📖 **Textual del material (recuadro destacado, Pág. 4):** "En resumen, para resolver un sistema de ecuaciones utilizando el método general hay que:
> 1ero| Completar y ordenar el sistema dado.
> 2do| Armar la matriz ampliada correspondiente.
> 3ero| Llevar dicha matriz a la forma canónica.
> 4to| Clasificar el sistema.
> 5to| Armar el vector solución."
>
> 📖 **Textual del material (rearme del sistema desde la canónica, Pág. 4):** "Una vez que llegamos a la matriz canónica, es posible que rearmemos nuevamente el sistema de ecuaciones, quedando en este caso:
> 1.x + 0.y + 0.z = 25
> 0.x + 1.y + 0.z = 35
> 0.x + 0.y + 1.z = 35
> Y si tenemos en cuenta que cualquier número multiplicado por 0, da como resultado 0, y además que un número multiplicado por 1 da como resultado el mismo número, entonces el sistema quedaría:
> x = 25
> y = 35
> z = 35
> Que es la solución del sistema de ecuaciones planteado."

**🗣️ En palabras simples:** Este es el procedimiento estándar de 5 pasos (basado en eliminación de Gauss-Jordan) que resuelve **cualquier** sistema de ecuaciones lineales:
1. Ordenás y completás las ecuaciones.
2. Armás la matriz ampliada `A° = [ A : B ]`.
3. Aplicás operaciones elementales de fila hasta llegar a la matriz canónica.
4. Mirás los rangos en la matriz canónica para clasificar el sistema (ver si tiene solución única, infinitas o ninguna).
5. Si tiene solución, rearmás el sistema desde la matriz canónica para despejar las incógnitas y escribís el vector solución `X*`.

**🔍 Desglose de los pasos y por qué funcionan:**
- **Qué problema resuelve:** Permite hallar el conjunto solución (y clasificar) cualquier sistema de `n` ecuaciones lineales con `m` incógnitas, sin importar si es cuadrado (`n = m`) o rectangular (`n ≠ m`).
- **Por qué funciona el Paso 3 y el Paso 5 (Rearme del sistema):**
  - En un **Sistema Compatible Determinado** de `m` incógnitas, la parte izquierda de la matriz canónica se convierte en la matriz identidad de orden `m × m` (con `1` en la diagonal principal y `0` en el resto).
  - Al rearmar el sistema multiplicando cada fila por las incógnitas (`1·x + 0·y + 0·z = c_1`, etc.), como todo número multiplicado por `0` da `0` y multiplicado por `1` da el mismo número, cada ecuación queda directamente despejada (`x = c_1`, `y = c_2`, `z = c_3`).
- **Vector solución (`X*`):** En la Pág. 11 (Respuestas al Desempeño N° 5), el material simboliza al vector columna formado por los valores numéricos de la solución como `X*` (para distinguirlo del vector de variables simbólicas `X`).

**💡 Ejemplo mínimo completo (síntesis del Ejemplo N° 4, Págs. 3 y 4):**
1. **Completar y ordenar:**
   - `x + y + z = 95`
   - `5x + 10y + 20z = 1175`
   - `x - 2y + z = -10`
2. **Armar `A°`:**
   - Fila 1: `[ 1   1   1 :   95 ]`
   - Fila 2: `[ 5  10  20 : 1175 ]`
   - Fila 3: `[ 1  -2   1 :  -10 ]`
3. **Llevar a canónica:** Aplicando sucesivamente `H_(2,1)(-5)` y `H_(3,1)(-1)`, luego `H_2(1/5)`, luego `H_(1,2)(-1)` y `H_(3,2)(3)`, luego `H_3(1/9)` y finalmente `H_(1,3)(2)` y `H_(2,3)(-3)`, se obtiene la canónica:
   - Fila 1: `[ 1  0  0 : 25 ]`
   - Fila 2: `[ 0  1  0 : 35 ]`
   - Fila 3: `[ 0  0  1 : 35 ]`
4. **Clasificar:** `ρ(A) = 3`, `ρ(A°) = 3`, número de incógnitas `m = 3`. Como `ρ(A) = ρ(A°) = m = 3`, es un **Sistema Compatible Determinado**.
5. **Armar el vector solución:** Rearmando el sistema queda `x = 25`, `y = 35`, `z = 35`, por lo que el vector solución es `X* = [ 25 ; 35 ; 35 ]` (columna).

**🔗 Conexiones:**
- Con el **Desempeño 1, pregunta c (Pág. 9):** *"¿Qué se debe hacer (pasos) para resolver un sistema por el método general?"* — Se responde literalmente con los 5 pasos del recuadro de la Pág. 4.
- Con el **Desempeño 1, pregunta a (Pág. 9):** *"¿Qué condición debe cumplir una matriz para ser canónica?"* — Conecta directamente el Paso 3 con la definición de matriz canónica de la Clase 8 (1: el primer elemento no nulo de cada fila no nula es `1`, llamado `1` principal o conductor; 2: en la columna de cada `1` principal todos los demás elementos son `0`; 3: los `1` principales se escalonan hacia la derecha al bajar de fila; 4: las filas nulas, si existen, se ubican al final de la matriz).

**⚠️ Precisiones / errores comunes:**
- **Saltearse el Paso 4 (Clasificar):** El profesor pide los 5 pasos en orden exacto: 1° Completar y ordenar, 2° Armar la matriz ampliada, 3° Llevar a la forma canónica, 4° Clasificar el sistema, 5° Armar el vector solución. Clasificar va **antes** de armar el vector solución, porque primero debemos saber si existe solución y de qué tipo es.
- *(Nota sobre errata tipográfica en el PDF, Pág. 6, recuadro [2])*: En el último paso de reducción del Ejemplo N° 5, el PDF anota al pie `H_(1,3)(-1)` cuando en realidad la operación efectuada para pasar de la fila 2 `[0  1  1 : 25]` a `[0  1  0 : 15]` usando la fila 3 `[0  0  1 : 10]` es `H_(2,3)(-1)`.

**🎤 Cómo decirlo en el oral:**
> "Para resolver un sistema de ecuaciones utilizando el **método general**, se deben seguir cinco pasos en orden:
> **1°** Completar y ordenar el sistema dado.
> **2°** Armar la matriz ampliada correspondiente `A° = [ A : B ]`.
> **3°** Llevar dicha matriz a la forma canónica mediante operaciones elementales de fila.
> **4°** Clasificar el sistema (comparando los rangos de `A`, de `A°` y el número de incógnitas).
> **5°** Armar el vector solución."

---

## 10.6 Definición de Sistema Compatible y Sistema Compatible Determinado (según sus soluciones)

> 📖 **Textual del material (Pág. 4):** "Este es un sistema que tiene solución, por lo que es un sistema COMPATIBLE, y además es un sistema que tiene una única solución (es decir, que cada una de las incógnitas, puede tomar un único valor) por lo tanto es un sistema DETERMINADO."
>
> 📖 **Textual del material (Pág. 6):** "Nuevamente encontramos un sistema de ecuaciones que tiene una única solución, por lo que es un Sistema Compatible Determinado en el que: x = 50   y = 15   y   z = 10"

**🗣️ En palabras simples:**
- Decimos que un sistema es **Compatible** cuando **tiene solución** (por lo menos una).
- Decimos que además es **Determinado** cuando esa solución es **única**, lo que significa que cada incógnita toma un único valor numérico posible.

**🔍 Desglose de la jerga:**
- **Compatible:** Equivale a decir "tiene solución" (el conjunto solución no es vacío).
- **Determinado:** Dentro de los sistemas compatibles, significa que tiene **una única solución**; es decir, cada una de las incógnitas puede tomar un único valor.
- **Unicidad del vector solución vs. igualdad entre incógnitas:** Que "cada incógnita tome un único valor" significa que `x` tiene un solo valor posible, `y` tiene un solo valor posible y `z` tiene un solo valor posible; **no** impide que dos incógnitas distintas coincidan en ese valor numérico (por ejemplo, en el Ejemplo N° 4, `y = 35` y `z = 35`, y sigue siendo una única solución `X* = [25 ; 35 ; 35]`).

**💡 Ejemplo (del material, Ejemplo N° 5, Pág. 6):**
Al llegar a `x = 50`, `y = 15`, `z = 10`, existe un único valor para `x`, un único valor para `y` y un único valor para `z`. Por eso es un **Sistema Compatible Determinado**.

**🔗 Conexiones:**
- Con la **Clase 9:** Retoma la clasificación según la cantidad de soluciones vista en la Clase 9 y la prepara para traducirla al lenguaje de **rangos matriciales** en las secciones **10.8** y **10.9**.
- Con la **Clase 11:** En la Clase 10 solo se resuelven hasta el vector solución final los sistemas compatibles determinados (por eso en la respuesta al Desempeño 4e de la Pág. 10 dice: *"no corresponde a un sistema compatible determinado… Este problema será resuelto en la clase siguiente"*).

**⚠️ Precisiones / errores comunes:**
- **No confundir "única solución" con "una sola incógnita":** Un sistema de 3 incógnitas tiene *una única solución* cuando existe una única terna ordenada `(x, y, z)` (un único vector `X*`) que verifica todas las ecuaciones a la vez.

**🎤 Cómo decirlo en el oral:**
> "Desde el punto de vista de sus soluciones, un sistema es **Compatible** cuando tiene solución, y es **Determinado** cuando tiene una única solución, es decir, cuando cada una de las incógnitas puede tomar un único valor."

---

## 10.7 Rango de una matriz y cómo observar ρ(A) y ρ(A°) en la matriz ampliada canónica

> 📖 **Textual del material (recuadro destacado, Pág. 7):** "El RANGO de una matriz es el número de filas no nulas de la canónica equivalente."
>
> 📖 **Textual del material (recuadro destacado, Pág. 7):** "Una vez llevada la matriz ampliada a la canónica, el rango de A se observa sin tener en cuenta la última columna. Para obtener el rango de la ampliada si se tiene en cuenta dicha columna."

**🗣️ En palabras simples:**
- El **rango** de cualquier matriz (simbolizado con la letra griega ro: `ρ`) es simplemente **cuántas filas que no sean todas de ceros** quedan cuando llevás la matriz a su forma canónica.
- Lo genial del método general es que no necesitás reducir `A` por un lado y `A°` por otro: reducís una sola vez la matriz ampliada `A°` a la canónica. Ahí mismo:
  - Si **tapás la última columna** (la de los términos independientes) y contás cuántas filas no nulas hay, tenés el **rango de `A` (`ρ(A)`)**.
  - Si **destapás la última columna** (mirando toda la matriz ampliada) y contás cuántas filas no nulas hay, tenés el **rango de la matriz ampliada (`ρ(A°)`)**.

**🔍 Desglose de la jerga:**
- **Rango de una matriz (`ρ(A)`):** Número entero no negativo igual a la cantidad de filas no nulas (filas que tienen al menos un elemento distinto de `0`) que posee la matriz canónica equivalente a `A`.
- **Fila nula vs. fila no nula:** Una fila es nula si **todos** sus elementos son `0`. Basta con que un solo elemento de la fila sea distinto de `0` para que la fila sea **no nula** y sume `1` al rango.
- **Canónica equivalente:** La matriz en forma canónica que se obtiene a partir de la matriz dada mediante operaciones elementales de fila (`~`).
- **Observación simultánea de `ρ(A)` y `ρ(A°)`:**
  - `ρ(A)`: se cuenta cuántas filas tienen algún elemento no nulo a la izquierda de los dos puntos `:` (sin tener en cuenta la última columna).
  - `ρ(A°)`: se cuenta cuántas filas tienen algún elemento no nulo en toda la fila (teniendo en cuenta la última columna).

**💡 Ejemplo (del material, Ejemplo N° 5 en Págs. 6-7, y comparación con caso incompatible):**
1. **En el Ejemplo N° 5 (Págs. 6-7):** La matriz canónica de `A°` es:
   ```
   [ 1  0  0 : 50 ]
   [ 0  1  0 : 15 ]
   [ 0  0  1 : 10 ]
   ```
   - Sin mirar la última columna, hay `3` filas no nulas ⇒ `ρ(A) = 3`.
   - Teniendo en cuenta la última columna, hay `3` filas no nulas ⇒ `ρ(A°) = 3`.
2. **Ejemplo adicional (para ver cuándo cambian al mirar la última columna):** Supongamos que al llevar `A°` a canónica queda:
   ```
   [ 1  0  2 : 4 ]
   [ 0  1 -1 : 3 ]
   [ 0  0  0 : 7 ]
   ```
   - Sin tener en cuenta la última columna, la tercera fila es `[0  0  0]` (nula), así que solo hay `2` filas no nulas ⇒ `ρ(A) = 2`.
   - Teniendo en cuenta la última columna, la tercera fila es `[0  0  0 : 7]` (no nula, porque tiene un `7`), así que hay `3` filas no nulas ⇒ `ρ(A°) = 3`.

**🔗 Conexiones:**
- Con la **Clase 8 (Rango de una matriz):** Retoma textual la definición de rango dada en la Unidad 2 y la aplica como herramienta central para clasificar sistemas de ecuaciones.
- Con el **Desempeño 1, preguntas b y j (Pág. 9):**
  - Pregunta `b`: *"¿Qué es el rango de una matriz?"* → *"El RANGO de una matriz es el número de filas no nulas de la canónica equivalente."*
  - Pregunta `j`: *"¿Puede ser el rango de la matriz de los coeficientes mayor que el rango de la matriz ampliada?"* → **No, nunca.** Como `A°` contiene todas las columnas de `A` más una columna adicional (`B`), si una fila es no nula en `A` (sin mirar la última columna), seguirá siendo no nula en `A°` (mirando la última columna). A lo sumo, una fila que era toda de ceros en `A` puede tener un número distinto de cero en la última columna, haciendo que `ρ(A°)` supere en `1` a `ρ(A)`. Por lo tanto, siempre se cumple que **`ρ(A) ≤ ρ(A°)`**, y jamás puede ocurrir `ρ(A) > ρ(A°)`.

**⚠️ Precisiones / errores comunes:**
- **Omitir "de la canónica equivalente" al definir rango:** En el oral, si el profesor pregunta *"¿Qué es el rango de una matriz?"* y el alumno dice solo *"es el número de filas no nulas"*, **está mal**, porque una matriz sin llevar a canónica puede tener 3 filas no nulas pero que una sea combinación lineal de las otras y al llevarla a canónica se anule. Es obligatorio decir: **"de la canónica equivalente"**.

**🎤 Cómo decirlo en el oral:**
> "**El rango de una matriz es el número de filas no nulas de la canónica equivalente.** Una vez llevada la matriz ampliada a la canónica, el rango de `A` (`ρ(A)`) se observa sin tener en cuenta la última columna, mientras que para obtener el rango de la matriz ampliada (`ρ(A°)`) sí se tiene en cuenta dicha columna. Por esta razón, el rango de `A` nunca puede ser mayor que el rango de `A°`."

---

## 10.8 Criterio matricial de compatibilidad: Sistema Compatible vs. Sistema Incompatible

> 📖 **Textual del material (recuadro destacado, Pág. 7):** "El sistema de ecuaciones será Compatible (es decir, tendrá solución) si el rango de la matriz de los coeficientes es igual al rango de la matriz ampliada.
>
> Si esta igualdad no se verifica, el sistema es Incompatible, (es decir, no tendrá solución)."
>
> 📖 **Textual del material (Pág. 7):** "Esta condición se aplica a cualquier sistema de ecuaciones lineales puesto que no impone ninguna restricción sobre el número de ecuaciones, el número de variables ni el valor de los términos independientes, utilizando sólo el concepto de rango de una matriz."

**🗣️ En palabras simples:** Para saber si un sistema de ecuaciones tiene solución o no, comparás el rango de `A` con el rango de `A°`:
- Si **`ρ(A) = ρ(A°)`**, el sistema es **Compatible** (tiene solución).
- Si **`ρ(A) ≠ ρ(A°)`** (es decir, `ρ(A) < ρ(A°)`), el sistema es **Incompatible** (no tiene solución).
Y esta regla sirve para **cualquier** sistema lineal, tenga la cantidad de ecuaciones e incógnitas que tenga.

**🔍 Desglose de la jerga:**
- **`ρ(A) = ρ(A°)` (Condición de Compatibilidad):** Significa que ninguna fila que se haya anulado en la parte de los coeficientes tiene un número distinto de cero en la columna de términos independientes.
- **`ρ(A) ≠ ρ(A°)` (Condición de Incompatibilidad):** Significa que en la canónica de `A°` apareció al menos una fila de la forma `[ 0  0 ... 0 : k ]` con `k ≠ 0`, la cual suma al rango de `A°` pero no al rango de `A`.
- **Alcance universal de la condición:** Como destaca el párrafo de la Pág. 7, este criterio no exige que el sistema sea cuadrado (`n = m`) ni pone restricciones sobre `n`, `m` o `B`; vale para todo sistema lineal. *(Contexto adicional: en álgebra lineal, este resultado se conoce como el Teorema de Rouché-Frobenius).*

**🧩 Idea de la justificación / 🤔 Intuición de por qué es cierto:**
- **¿Por qué `ρ(A) ≠ ρ(A°)` implica que no hay solución?**
  Si `ρ(A) ≠ ρ(A°)`, como siempre `ρ(A) ≤ ρ(A°)`, quiere decir que en la matriz canónica existe una fila cuyos coeficientes en `A` son todos `0`, pero cuyo término independiente en `B` es un número `k ≠ 0`:
  `[ 0   0   ...   0  :  k ]` (con `k ≠ 0`).
  Al rearmar la ecuación correspondiente a esa fila, queda:
  `0·x_1 + 0·x_2 + ... + 0·x_m = k` ⇒ `0 = k` (con `k ≠ 0`),
  lo cual es un absurdo matemático (una contradicción) para cualquier valor de las incógnitas. Por eso el sistema no tiene solución (**Incompatible**).
- En cambio, si **`ρ(A) = ρ(A°)`**, toda fila que se anula a la izquierda también tiene `0` a la derecha (`0 = 0`), por lo que no hay ninguna contradicción y el sistema tiene al menos una solución (**Compatible**).

**💡 Ejemplo:**
En el Ejemplo N° 5 (Pág. 7), `ρ(A) = 3` y `ρ(A°) = 3`. Como `ρ(A) = ρ(A°)`, el sistema es **Compatible**.

**🔗 Conexiones:**
- Con el **Desempeño 1, preguntas d y f (Pág. 9):**
  - `d- ¿Cuándo un sistema de ecuaciones es Compatible? (desde el punto de vista matricial)` → Cuando el rango de la matriz de los coeficientes es igual al rango de la matriz ampliada (`ρ(A) = ρ(A°)`).
  - `f- ¿Cuándo un sistema es Incompatible, analizando la matriz ampliada?` → Cuando el rango de la matriz de los coeficientes es distinto del rango de la matriz ampliada (`ρ(A) ≠ ρ(A°)`).
- Con la sección **10.9:** Si el sistema resulta compatible (`ρ(A) = ρ(A°)`), pasamos al segundo nivel de clasificación para decidir si es determinado o indeterminado.

**⚠️ Precisiones / errores comunes:**
- **No meter la cantidad de incógnitas (`m`) al definir compatibilidad:** Para saber si un sistema es **Compatible** o **Incompatible**, **solo** se comparan entre sí `ρ(A)` y `ρ(A°)`. La cantidad de incógnitas `m` recién interviene después, cuando ya sabemos que es compatible y queremos saber si es *determinado* o *indeterminado*.

**🎤 Cómo decirlo en el oral:**
> "Desde el punto de vista matricial, un sistema de ecuaciones lineales será **Compatible** (tendrá solución) si el rango de la matriz de los coeficientes es igual al rango de la matriz ampliada: `ρ(A) = ρ(A°)`. Si esta igualdad no se verifica (`ρ(A) ≠ ρ(A°)`), el sistema es **Incompatible** (no tendrá solución). Esta condición se aplica a cualquier sistema de ecuaciones lineales, sin ninguna restricción sobre el número de ecuaciones, el número de variables ni el valor de los términos independientes."

---

## 10.9 Criterio matricial de determinación: Sistema Compatible Determinado vs. Indeterminado

> 📖 **Textual del material (Pág. 7):** "Por otro lado, podemos analizar lo siguiente:
> Si el sistema es compatible, sabemos que puede ser DETERMINADO o INDETERMINADO. Para que un sistema sea determinado o indeterminado, debe cumplir, también ciertas condiciones."
>
> 📖 **Textual del material (recuadro destacado, Pág. 7):** "Un sistema es determinado si el rango de la matriz ampliada es igual al número de incógnitas.
>
> Si dicho rango es menor que el número de incógnitas, entonces el sistema es indeterminado."

**🗣️ En palabras simples:** Una vez que ya comprobaste que el sistema es **Compatible** (`ρ(A) = ρ(A°)`), comparás ese rango con la cantidad de incógnitas (`m`):
- Si el rango es **igual** al número de incógnitas (`ρ(A°) = m`, o equivalentemente `ρ(A) = m`), el sistema es **Determinado** (tiene una única solución).
- Si el rango es **menor** que el número de incógnitas (`ρ(A°) < m`), el sistema es **Indeterminado** (tiene infinitas soluciones).

**🔍 Desglose de la jerga:**
- **Condición previa implícita:** Este criterio se aplica **dentro de los sistemas compatibles** (donde ya sabemos que `ρ(A) = ρ(A°)`). Por eso da lo mismo escribir `ρ(A°) = m` (como en el texto de la Pág. 7) o `ρ(A) = m` (como en el cuadro de la Pág. 8), ya que ambos rangos valen lo mismo.
- **Número de incógnitas (`m`):** Cantidad de variables distintas del sistema, que coincide con la cantidad de columnas de la matriz de los coeficientes `A`.
- **Determinado (`ρ(A°) = m`):** En la forma canónica quedan exactamente `m` filas no nulas, cada una con un `1` principal para una de las `m` incógnitas, despejando un único valor para cada incógnita.
- **Indeterminado (`ρ(A°) < m`):** Quedan menos filas no nulas (ecuaciones independientes) que incógnitas, por lo que hay incógnitas que no tienen `1` principal propio (quedan libres) y el sistema admite infinitas soluciones.

**🧩 Idea de la justificación / 🤔 Intuición de por qué es cierto:**
- Como `A` tiene `m` columnas (una por cada incógnita), su forma canónica no puede tener más de `m` unos principales (uno por columna). Por lo tanto, el rango de `A` nunca puede superar a `m` (`ρ(A) ≤ m`).
- Si el sistema es compatible (`ρ(A) = ρ(A°)`), solo hay dos posibilidades:
  1. Que `ρ(A°) = m`: hay exactamente un `1` principal en cada una de las `m` columnas de `A`, formando los vectores canónicos que despejan cada incógnita con un valor único (`x_1 = c_1, ..., x_m = c_m`).
  2. Que `ρ(A°) < m`: faltan ecuaciones independientes para fijar todas las incógnitas; al menos `m - ρ(A°)` incógnitas pueden tomar valores arbitrarios, generando infinitas soluciones.

**💡 Ejemplo (del material, Ejemplo N° 5, Pág. 7):**
En el Ejemplo N° 5:
- Cantidad de ecuaciones: `3`
- Cantidad de incógnitas: `m = 3`
- Rango de la matriz `A`: `ρ(A) = 3`
- Rango de la matriz Ampliada `A°`: `ρ(A°) = 3`

Como `ρ(A) = ρ(A°) = 3`, es **Compatible**; y como el rango de la matriz ampliada (`3`) es igual al número de incógnitas (`3`), el sistema es **Determinado**.

**🔗 Conexiones:**
- Con el **Desempeño 1, pregunta e (Pág. 9):** *"¿Qué condición debe cumplir un sistema de ecuaciones para ser Determinado? (desde el punto de vista matricial)"* → Que sea compatible (`ρ(A) = ρ(A°)`) y que el rango de la matriz ampliada (o de los coeficientes) sea igual al número de incógnitas (`ρ(A°) = m`).
- Con la **Clase 11:** En la Clase 11 se estudiará en detalle cómo armar el conjunto solución de los sistemas compatibles indeterminados (`ρ(A) = ρ(A°) < m`) y el análisis de los incompatibles.

**⚠️ Precisiones / errores comunes:**
- **Comparar el rango con el número de ecuaciones (`n`) en vez del número de incógnitas (`m`):** ¡Cuidado! La condición de sistema determinado o indeterminado compara el rango con el **número de incógnitas (`m`)**, **NO** con el número de ecuaciones (`n`). Por ejemplo, un sistema de 4 ecuaciones y 3 incógnitas con `ρ(A) = ρ(A°) = 3` tiene rango igual al número de incógnitas (`m = 3`), por lo que es Compatible Determinado aunque `3 < 4`.
- **¿Puede ser `ρ(A°) > m` en un sistema compatible?** No, porque en un sistema compatible `ρ(A°) = ρ(A)`, y el rango de `A` (que tiene `m` columnas) nunca puede superar su número de columnas `m`.

**🎤 Cómo decirlo en el oral:**
> "Si un sistema de ecuaciones es compatible (`ρ(A) = ρ(A°)`), será **Determinado** si el rango de la matriz ampliada es igual al número de incógnitas (`ρ(A°) = m`), teniendo en ese caso una única solución. En cambio, si dicho rango es menor que el número de incógnitas (`ρ(A°) < m`), entonces el sistema es **Indeterminado** y tiene infinitas soluciones."

---

## 10.10 Cuadro resumen de clasificación de sistemas de ecuaciones lineales

> 📖 **Textual del material (Esquema resumen, Pág. 8):**
> "En resumen:
> `A_(n x m) ∙ X_(m x 1) = B_(n x 1)`
> - **Compatible:** `ρ(A) = ρ(A°)`
>   - **Determinado:** `ρ(A) = m`
>   - **Indeterminado:** `ρ(A°) < m`
> - **Incompatible:** `ρ(A) ≠ ρ(A°)`
>
> Donde m es la cantidad de incógnitas."

*(Nota visual sobre el PDF en Pág. 8: en el gráfico original de la página 8, la punta de la flecha vertical que baja desde la palabra "Compatible" se superpone con la barra superior del signo `=` en `ρ(A) = ρ(A°)`; la condición que representa es la igualdad de rangos `ρ(A) = ρ(A°)` explicada en la página 7).*

**🗣️ En palabras simples:** Este esquema resume toda la teoría de clasificación matricial de sistemas lineales en un árbol de decisión de dos pasos a partir de `A_(n×m) · X_(m×1) = B_(n×1)`:
1. **Primer filtro (`ρ(A)` vs `ρ(A°)`):** ¿Son iguales? Si no (`ρ(A) ≠ ρ(A°)`), es **Incompatible**. Si sí (`ρ(A) = ρ(A°)`), es **Compatible**.
2. **Segundo filtro (rango vs `m`):** Dentro de Compatible, ¿el rango alcanza a `m` (`ρ(A) = m`)? Entonces es **Determinado**. ¿Es menor que `m` (`ρ(A°) < m`)? Entonces es **Indeterminado**.

### Tabla comparativa completa de clasificación

| Clasificación del sistema | Condición de rangos (fiel al material) | Relación en la matriz canónica de A° | Cantidad de soluciones |
| :--- | :--- | :--- | :--- |
| **Compatible Determinado (SCD)** | `ρ(A) = ρ(A°)` y `ρ(A) = m` (o `ρ(A°) = m`) | Quedan `m` filas no nulas con un `1` principal para cada una de las `m` incógnitas (y si `n > m`, `n - m` filas nulas `[0 ... 0 : 0]` abajo). | **Única solución** (cada incógnita toma un único valor). |
| **Compatible Indeterminado (SCI)** | `ρ(A) = ρ(A°)` y `ρ(A°) < m` | Ninguna fila contradice (`0 = k`), pero quedan menos filas no nulas que incógnitas (`< m`). | **Infinitas soluciones**. |
| **Incompatible (SI)** | `ρ(A) ≠ ρ(A°)` (siempre `ρ(A) < ρ(A°)`) | Aparece al menos una fila `[0  0 ... 0 : k]` con `k ≠ 0` (es decir, `0 = k`, absurdo). | **No tiene solución** (conjunto solución vacío). |

**🎤 Cómo decirlo en el oral:**
> "Dado un sistema en forma matricial `A_(n×m) · X_(m×1) = B_(n×1)` donde `m` es la cantidad de incógnitas:
> 1. Si `ρ(A) ≠ ρ(A°)`, el sistema es **Incompatible** (no tiene solución).
> 2. Si `ρ(A) = ρ(A°)`, el sistema es **Compatible** (tiene solución), y a su vez se subdivide en:
>    - **Determinado** si `ρ(A) = ρ(A°) = m` (única solución).
>    - **Indeterminado** si `ρ(A) = ρ(A°) < m` (infinitas soluciones)."

---

## 10.11 Sistemas de ecuaciones lineales homogéneos: compatibilidad, solución trivial y soluciones no triviales

> 📖 **Textual del material (Pág. 8):** "¿Qué sucede con los sistemas homogéneos? Sistemas homogéneos, siempre compatibles.
> Sea A.X = 0 un sistema de ecuaciones lineales homogéneo la matriz A es de orden (nxm).
> Si un sistema de ecuaciones es homogéneo siempre tiene solución, o sea el sistema siempre es compatible.
> La explicación es sencilla, puesto que la matriz ampliada es de la forma: Aº = [ A : 0 ]
> Y el rango de la misma es igual al rango de A, puesto que el vector que se agrega es el vector nulo, no pudiendo en consecuencia aumentar el rango de la matriz Aº.
> El hecho de que un sistema de ecuaciones homogéneo siempre sea compatible, quiere decir que en todos los casos existe por lo menos un vector solución. En cualquier sistema de ecuaciones homogéneo el vector nulo siempre es solución, ya que A.0 = 0
> Cualquiera sea la matriz A.
> Esta solución del sistema, que significa dar el valor cero a todas las variables, se denomina solución trivial y generalmente no interesa.
> Las soluciones que interesan son las llamadas no triviales, y que están representadas por vectores distintos del vector nulo y se obtienen utilizando el método general."

**🗣️ En palabras simples:** Un sistema es **homogéneo** cuando todos sus términos independientes valen `0` (`A · X = 0`). Estos sistemas tienen una propiedad fundamental: **jamás pueden ser incompatibles; siempre son compatibles** (siempre tienen solución).
¿Por qué? Por dos razones equivalentes:
1. **Por rangos:** La última columna de la matriz ampliada `A° = [ A : 0 ]` está llena de ceros, y por más operaciones elementales de fila que hagas, una columna de ceros sigue siendo toda de ceros; nunca puede aparecer `[0 ... 0 : k]` con `k ≠ 0`. Por ende, `ρ(A) = ρ(A°)` siempre.
2. **Algebraicamente:** Si reemplazás todas las incógnitas por `0` (`X = 0`), como cualquier matriz multiplicada por el vector nulo da el vector nulo (`A · 0 = 0`), la igualdad se cumple siempre. Esa solución donde todas las incógnitas valen `0` se llama **solución trivial**, y las soluciones donde al menos una incógnita no vale `0` se llaman **soluciones no triviales**.

**🔍 Desglose de la jerga:**
- **Sistema de ecuaciones lineales homogéneo (`A · X = 0`):** Sistema lineal en el cual el vector de los términos independientes `B` es el vector nulo `0` (todos los términos independientes son iguales a `0`).
- **Matriz ampliada de un homogéneo (`A° = [ A : 0 ]`):** Matriz formada por `A` y una última columna compuesta exclusivamente por ceros.
- **Solución trivial (`X = 0`):** Es el vector nulo de orden `m × 1`, que consiste en **dar el valor cero a todas las variables** (`x_1 = 0, x_2 = 0, ..., x_m = 0`). Siempre es solución de todo sistema homogéneo porque `A · 0 = 0` cualquiera sea la matriz `A`.
- **Soluciones no triviales (`X ≠ 0`):** Son las soluciones representadas por **vectores distintos del vector nulo** (es decir, soluciones en las que al menos una variable toma un valor distinto de `0`). Solo existen cuando el sistema homogéneo es **Compatible Indeterminado** (`ρ(A) < m`), y se obtienen utilizando el método general.

**🧩 Idea de la demostración (exactamente como la desarrolla el material en Pág. 8):**
1. Sea el sistema homogéneo `A · X = 0`, con `A` de orden `n × m`.
2. Su matriz ampliada tiene la forma `A° = [ A : 0 ]`.
3. Al agregar el vector nulo `0` como última columna, dicha columna no puede aportar ninguna fila no nula que no fuera ya no nula en `A` (no puede aumentar el rango de `A°`).
4. Por lo tanto, `ρ(A°) = ρ(A)` siempre.
5. Por la condición de compatibilidad (**10.8**), todo sistema homogéneo **siempre es compatible**, existiendo en todos los casos por lo menos un vector solución: el vector nulo `X = 0` (solución trivial), dado que `A · 0 = 0` cualquiera sea `A`.

**🤔 Intuición:**
En una ecuación lineal sin término independiente, como `3x - 2y + 5z = 0`, si ponés `x = 0, y = 0, z = 0`, la cuenta da `3·0 - 2·0 + 5·0 = 0`, que es verdadera sin importar qué coeficientes tenga la ecuación. Por eso el origen `(0, 0, ..., 0)` verifica gratis todas las ecuaciones de cualquier sistema homogéneo.

**💡 Ejemplo (basado en el Ejemplo N° 5 y Desempeño 3, Págs. 5 y 9):**
En el Desempeño 3a (Pág. 9), tenemos el sistema:
- `4x + 2y = 3z`
- `2z - x = 3y`
- `3x - y - z = 0`

Al ordenarlo pasando todas las incógnitas al primer miembro queda:
- `4x + 2y - 3z = 0`
- `-x - 3y + 2z = 0`
- `3x - y - z = 0`

Todos los términos independientes son `0`: es un sistema homogéneo `A · X = 0`. Sin hacer ninguna cuenta, ya sabemos que **es compatible** y que `(x, y, z) = (0, 0, 0)` es su **solución trivial**. La única duda en un homogéneo nunca es si es compatible o incompatible, sino si es **Determinado** (solo tiene la solución trivial) o **Indeterminado** (tiene la solución trivial más infinitas soluciones no triviales).

**🔗 Conexiones:**
- Con el **Desempeño 1, preguntas g y h (Pág. 9):**
  - `g- ¿Qué se puede asegurar de un sistema homogéneo?` → Que siempre tiene solución, o sea, que el sistema **siempre es compatible** (y que el vector nulo siempre es solución).
  - `h- ¿Qué es la solución trivial?` → Es la solución del sistema homogéneo que significa **dar el valor cero a todas las variables** (representada por el vector nulo `X = 0`).
- Con la sección **10.12:** Caso particular cuando el sistema homogéneo además es cuadrado (`A` de orden `n × n`).

**⚠️ Precisiones / errores comunes:**
- **Confundir "solución no trivial" con "ninguna variable vale cero":** Que una solución sea no trivial significa que el vector solución es **distinto del vector nulo** (`X ≠ 0`), es decir, que *al menos una* variable es distinta de cero (pueden algunas variables valer `0` y otras no, por ejemplo `(0, 2, -1)` es una solución no trivial).
- **Si un sistema NO tiene todos sus términos independientes nulos (como el Ejemplo N° 5, que tiene `0, 0, 150`):** Con que **un solo** término independiente sea distinto de `0` (como `150`), el sistema **NO es homogéneo** (y el vector nulo `X = 0` no es solución, porque `0 + 0 + 0 ≠ 150`).

**🎤 Cómo decirlo en el oral:**
> "Sea `A · X = 0` un sistema de ecuaciones lineales homogéneo, donde `A` es de orden `n × m`. Si un sistema es homogéneo **siempre tiene solución, o sea siempre es compatible**, puesto que su matriz ampliada es de la forma `A° = [ A : 0 ]` y su rango es siempre igual al rango de `A`, ya que el vector que se agrega es el vector nulo y no puede aumentar el rango de `A°`. En cualquier sistema homogéneo el vector nulo siempre es solución (`A · 0 = 0` cualquiera sea `A`); esta solución, que significa dar el valor cero a todas las variables, se denomina **solución trivial**. Las soluciones representadas por vectores distintos del vector nulo se llaman **soluciones no triviales** y se obtienen utilizando el método general cuando el sistema es indeterminado."

---

## 10.12 Sistemas homogéneos cuadrados y criterio del determinante

> 📖 **Textual del material (Págs. 8 y 9):** "Sistemas homogéneos cuadrados
> Sea el sistema de ecuaciones homogéneo cuadrado: 12 A.X = 0 donde A es de orden (nxn).
> La condición que debe cumplirse para que el sistema dado tenga soluciones no triviales, es que el determinante de la matriz A sea igual a cero.
> Esto surge del hecho que si el determinante de A es igual a cero, el rango de A es menor que n, luego se cumple la condición para que el sistema sea indeterminado.
> Debe notarse que en este caso existen infinitas soluciones para el sistema dado, una de las cuales es la solución trivial que es solución de todo el sistema de ecuaciones homogéneo, en tanto que las otras son soluciones no triviales.
> Si la condición dada no se cumple, es decir, el determinante de A es distinto de cero, el rango de A es igual a n, luego se cumple la condición para que el sistema sea determinado. En este caso, la única solución que existe, es la solución trivial."

*(Nota sobre el PDF en Pág. 8: el número "12" delante de `A.X = 0` es un carácter tipográfico errático del módulo impreso; la expresión matemática es `A · X = 0` donde `A` es de orden `n × n`).*

**🗣️ En palabras simples:** Cuando el sistema homogéneo `A · X = 0` tiene **la misma cantidad de ecuaciones que de incógnitas** (`A` es cuadrada de orden `n × n`), no hace falta llevar la matriz a la forma canónica para clasificarlo: basta con calcular el **determinante de `A` (`|A|`)**:
- Si **`|A| = 0`**, el rango de `A` es menor que `n` (`ρ(A) < n`), así que el sistema es **Compatible Indeterminado** y tiene **infinitas soluciones** (la solución trivial más infinitas **soluciones no triviales**).
- Si **`|A| ≠ 0`**, el rango de `A` es igual a `n` (`ρ(A) = n`), así que el sistema es **Compatible Determinado** y tiene **una única solución**, que es exclusivamente la **solución trivial** (`X = 0`).

**🔍 Desglose de la jerga:**
- **Sistema homogéneo cuadrado:** Sistema de la forma `A · X = 0` donde la matriz de los coeficientes `A` es cuadrada de orden `n × n` (tiene `n` ecuaciones y `n` incógnitas).
- **Condición para que tenga soluciones no triviales:** `|A| = 0` (el determinante de la matriz `A` es igual a cero).
- **Cadena lógica cuando `|A| = 0`:**
  `|A| = 0` ⇒ `ρ(A) < n` (el rango es menor que el número de incógnitas `n`) ⇒ el sistema es **Indeterminado** ⇒ existen **infinitas soluciones** (1 solución trivial + infinitas soluciones no triviales).
- **Cadena lógica cuando `|A| ≠ 0`:**
  `|A| ≠ 0` ⇒ `ρ(A) = n` (el rango es igual al número de incógnitas `n`) ⇒ el sistema es **Determinado** ⇒ existe **una única solución**, que es la **solución trivial** (`X = 0`).

### Tabla comparativa: Clasificación de sistemas homogéneos cuadrados (`A_(n×n) · X = 0`)

| Valor del determinante de A | Rango de A | Clasificación del sistema | Soluciones que posee |
| :--- | :--- | :--- | :--- |
| **`∣A∣ = 0`** | `ρ(A) < n` | **Compatible Indeterminado** | **Infinitas soluciones:** la solución trivial (`X = 0`) **y soluciones no triviales** (`X ≠ 0`). |
| **`∣A∣ ≠ 0`** | `ρ(A) = n` | **Compatible Determinado** | **Única solución:** únicamente la **solución trivial** (`X = 0`). No tiene soluciones no triviales. |

**🧩 Idea de la demostración (paso a paso según el material, Págs. 8-9):**
1. Todo sistema homogéneo `A · X = 0` es siempre compatible (`ρ(A) = ρ(A°)`). Como `A` es de orden `n × n`, la cantidad de incógnitas es `n`.
2. **Caso 1 (`|A| = 0`):** Si el determinante de `A` es igual a cero, al llevar `A` a la canónica al menos una fila se anula, por lo que el rango de `A` es menor que `n` (`ρ(A) < n`). Se cumple así la condición para que el sistema sea **indeterminado**, existiendo infinitas soluciones (una de ellas es la solución trivial y las demás son soluciones no triviales).
3. **Caso 2 (`|A| ≠ 0`):** Si el determinante de `A` es distinto de cero, ninguna fila se anula en la canónica, por lo que el rango de `A` es igual a `n` (`ρ(A) = n`). Se cumple la condición para que el sistema sea **determinado**, y como sabemos que el vector nulo siempre es solución de todo homogéneo, esa única solución que existe es necesariamente la **solución trivial**.

**💡 Ejemplo (del material, Desempeño 3a, Págs. 9 y 10):**
El Desempeño 3 pide: *"Sin la necesidad de resolver los sistemas homogéneos diga si son determinados o indeterminados"*.
Para el ítem `a`, una vez ordenado:
- `4x + 2y - 3z = 0`
- `-x - 3y + 2z = 0`
- `3x - y - z = 0`

La matriz `A` es cuadrada de orden `3 × 3`:
- Fila 1: `[  4   2  -3 ]`
- Fila 2: `[ -1  -3   2 ]`
- Fila 3: `[  3  -1  -1 ]`

*(Observación rápida: la Fila 3 es igual a la suma de la Fila 1 más la Fila 2: `4 + (-1) = 3`, `2 + (-3) = -1`, `-3 + 2 = -1`)*. Por propiedades del determinante (o calculando por Sarrus: `4·(3 - (-2)) - 2·(1 - 6) - 3·(1 - (-9)) = 20 + 10 - 30 = 0`), resulta **`|A| = 0`**.
Como `|A| = 0`, sin necesidad de resolver el sistema concluimos que `ρ(A) < 3` y el sistema es **Indeterminado** (admite soluciones no triviales además de la trivial).

**🔗 Conexiones:**
- Con la **Clase 8 y Clase 9 (Determinantes):** Solo las matrices **cuadradas** (`n × n`) tienen determinante, y una matriz cuadrada tiene determinante nulo (`|A| = 0`) si y solo si su rango es menor que `n`.
- Con el **Desempeño 1, pregunta i (Pág. 9):** *"¿Cómo se puede saber qué tipo de solución tiene un sistema homogéneo cuadrado?"* → Calculando el determinante de la matriz de los coeficientes `A`: si `|A| = 0`, el sistema es indeterminado y tiene infinitas soluciones (la trivial y soluciones no triviales); si `|A| ≠ 0`, el sistema es determinado y su única solución es la solución trivial.

**⚠️ Precisiones / errores comunes:**
- **¡Trampa clásica de examen oral!** Muchos alumnos confunden la regla de sistemas generales (o de matriz inversa/Cramer) con la de soluciones no triviales en homogéneos cuadrados:
  - Si el profesor pregunta: *"¿Qué condición debe cumplirse para que un sistema homogéneo cuadrado tenga **soluciones no triviales**?"*, la respuesta es que **el determinante de `A` sea igual a cero (`|A| = 0`)**, **NO** distinto de cero. Porque si `|A| ≠ 0`, el sistema es determinado y su única solución es la trivial (`0, 0, ..., 0`), que es justamente la que *no* es no trivial.
- **Solo aplica a sistemas homogéneos CUADRADOS:** Si el sistema homogéneo no es cuadrado (`n ≠ m`), `A` no tiene determinante y hay que analizar su rango `ρ(A)` comparándolo con `m`.

**🎤 Cómo decirlo en el oral:**
> "En un **sistema de ecuaciones homogéneo cuadrado** `A · X = 0`, donde `A` es de orden `n × n`, la condición que debe cumplirse para que el sistema tenga **soluciones no triviales** es que el **determinante de la matriz `A` sea igual a cero (`|A| = 0`)**. Esto surge del hecho de que si `|A| = 0`, el rango de `A` es menor que `n`, cumpliéndose la condición para que el sistema sea **indeterminado** (tiene infinitas soluciones: la solución trivial y las soluciones no triviales). Si en cambio el determinante de `A` es **distinto de cero (`|A| ≠ 0`)**, el rango de `A` es igual a `n`, por lo que el sistema es **determinado** y la única solución que existe es la **solución trivial**."

---

## 10.13 Validación de la respuesta en problemas aplicados (Solución del sistema vs. Solución del problema)

> 📖 **Textual del material (Pág. 1, Objetivos):** "Buscar soluciones a problemas y validar su respuesta."
>
> 📖 **Textual del material (Pág. 10, Respuesta al Desempeño N° 4 d):** "La solución obtenida es: B = 31/3 R = 16/3 y OC = 40/3 Como se puede observar, el sistema tiene solución y es única, es decir que es un sistema compatible Determinado. Pero si se presta atención al resultado, y se vuelve a leer el problema planteado, no es posible que haya 31/3 hinchas de Boca, (ni 16/3 hinchas de River, como tampoco 40/3 hinchas de otros clubes). Este nos está indicando que el sistema SI tiene solución y es única, pero no es acorde al problema planteado, por lo tanto, no es solución al problema, aunque si sea solución al sistema planteado. Esto significa validar la respuesta. La solución obtenida, tiene que estar acorde a la situación problemática trabajada."

**🗣️ En palabras simples:** Cuando resolvés un problema real (de personas, billetes, tornillos, días de viaje) planteando un sistema de ecuaciones, hacer bien las cuentas y encontrar la solución matemática del sistema no alcanza: al final hay que **validar la respuesta**, que significa fijarse si los números obtenidos tienen sentido en la realidad del problema. Puede pasar que el sistema matemático sea Compatible Determinado (tenga solución única, por ejemplo `31/3` personas), pero como no pueden existir `31/3` personas, **es solución del sistema planteado, pero NO es solución del problema planteado**.

**🔍 Desglose de la jerga:**
- **Solución al sistema planteado:** Vector numérico `X*` que satisface algebraicamente todas las ecuaciones del sistema `A · X = B`.
- **Solución al problema planteado:** Solución del sistema que, además de verificar las ecuaciones, cumple las restricciones de dominio y sentido físico/contextual del enunciado (por ejemplo, que una cantidad de personas, billetes o bicicletas sea un número natural o entero no negativo).
- **Validar la respuesta:** Contrastar la solución matemática obtenida al resolver el sistema contra la situación problemática trabajada para verificar que sea acorde a ella.

**💡 Ejemplo (del material, Desempeño 4d, Pág. 10):**
El problema plantea un curso de `29` alumnos con hinchas de River (`R`), de Boca (`B`) y de otros clubes (`OC`). Al resolver el sistema lineal resultante, es un **Sistema Compatible Determinado** cuya única solución algebraica es:
`B = 31/3`, `R = 16/3`, `OC = 40/3`.
Aunque `31/3 + 16/3 + 40/3 = 87/3 = 29` verifica exactamente las ecuaciones del sistema, no puede haber una cantidad fraccionaria de personas (`31/3` hinchas). Por lo tanto, al **validar la respuesta**, concluimos que el sistema tiene solución única, pero el problema planteado no tiene solución porque el resultado no es acorde a la situación problemática.

**🔗 Conexiones:**
- Con la **Clase 9 (Planteo de sistemas de ecuaciones):** Los problemas del Desempeño 4 de la Clase 10 son exactamente los problemas cuyo planteo se trabajó en la Clase 9; aquí se cierra el ciclo resolviéndolos con el método general y validando sus respuestas.

**⚠️ Precisiones / errores comunes:**
- **No confundir "verificar la solución" con "validar la respuesta":**
  - *Verificar la solución* es reemplazar los valores obtenidos (`x, y, z`) en las ecuaciones originales para comprobar que no hubo errores de cálculo y que se cumplen las igualdades numéricas.
  - *Validar la respuesta* es analizar si esos valores (aunque verifiquen las ecuaciones) son acordes a la naturaleza de la situación problemática trabajada.
- **No decir que el sistema es incompatible cuando la respuesta no valida:** Como aclara expresamente la Pág. 10, el sistema de ecuaciones **sí tiene solución y es única (es Compatible Determinado)**; lo que no tiene solución acorde es el problema concreto de las personas.

**🎤 Cómo decirlo en el oral:**
> "**Validar la respuesta** significa comprobar que la solución obtenida al resolver el sistema esté acorde a la situación problemática trabajada. Puede suceder que el sistema planteado sea **Compatible Determinado** (tenga solución y sea única, por ejemplo números fraccionarios), pero si las incógnitas representan cantidades enteras como personas, esa solución **sí es solución al sistema planteado, pero no es solución al problema planteado**."

---

## 🧠 Resumen esquemático de la clase

- **Preparación del sistema:** Antes de armar las matrices, el sistema debe estar **completo y ordenado**: términos con incógnitas en el primer miembro y términos independientes en el segundo miembro.
- **Las tres matrices del sistema:** `A` = **Matriz de los coeficientes** (`n × m`), `B` = **Matriz (o vector) de los términos independientes** (`n × 1`), `X` = **Matriz (o vector) de las incógnitas** (`m × 1`).
- **Forma matricial:** `A_(n×m) · X_(m×1) = B_(n×1)`, donde `n` es el número de ecuaciones y `m` es la cantidad de incógnitas.
- **Matriz ampliada (`A°`):** `A° = [ A : B ]`. Aplicarle operaciones elementales de fila produce un **sistema equivalente** porque no cambian las soluciones de las ecuaciones.
- **Pasos del Método General (en orden):** `1°` Completar y ordenar el sistema dado → `2°` Armar la matriz ampliada correspondiente → `3°` Llevar dicha matriz a la forma canónica → `4°` Clasificar el sistema → `5°` Armar el vector solución (`X*`).
- **Rango de una matriz (`ρ`):** Es el **número de filas no nulas de la canónica equivalente**. En la canónica de `A°`, `ρ(A)` se observa sin tener en cuenta la última columna y `ρ(A°)` teniendo en cuenta dicha columna (siempre `ρ(A) ≤ ρ(A°)`).
- **Sistema Compatible vs. Incompatible:** Es **Compatible** (tiene solución) si `ρ(A) = ρ(A°)`; es **Incompatible** (no tiene solución) si `ρ(A) ≠ ρ(A°)`. Vale para cualquier sistema lineal sin restricciones.
- **Sistema Determinado vs. Indeterminado (dentro de los compatibles):** Es **Determinado** (única solución) si `ρ(A°) = m` (o `ρ(A) = m`); es **Indeterminado** (infinitas soluciones) si `ρ(A°) < m`, donde `m` es el número de incógnitas.
- **Sistemas homogéneos (`A · X = 0`):** **Siempre son compatibles** porque `A° = [ A : 0 ]` y el vector nulo agregado no puede aumentar el rango (`ρ(A°) = ρ(A)`).
- **Solución trivial vs. no trivial:** La **solución trivial** es el vector nulo (`X = 0`, dar el valor cero a todas las variables), que siempre es solución porque `A · 0 = 0` cualquiera sea `A`. Las **soluciones no triviales** son vectores distintos del nulo (`X ≠ 0`).
- **Sistemas homogéneos cuadrados (`A` de orden `n × n`):** Tiene **soluciones no triviales** (es indeterminado, infinitas soluciones) si y solo si **`|A| = 0`** (pues `ρ(A) < n`). Si **`|A| ≠ 0`**, entonces `ρ(A) = n`, es determinado y su única solución es la **solución trivial**.
- **Validar la respuesta:** Verificar que la solución matemática del sistema sea acorde a la situación problemática trabajada (una solución puede ser solución del sistema planteado pero no del problema planteado).

---

## ❓ Preguntas probables del oral

*(Incluye las 10 preguntas oficiales del **Desempeño 1 de la Pág. 9** de la guía más preguntas integradoras de examen oral).*

**1. (Desempeño 1a) ¿Qué condición debe cumplir una matriz para ser canónica?**
> **Respuesta:** Para ser canónica (escalonada reducida por filas), una matriz debe cumplir cuatro condiciones:
> 1) Si una fila no consta completamente de ceros, su primer elemento no nulo (leído de izquierda a derecha) es un `1` (llamado `1` principal).
> 2) Si existen filas que constan completamente de ceros (filas nulas), se agrupan en la parte inferior de la matriz.
> 3) En dos filas no nulas consecutivas cualesquiera, el `1` principal de la fila inferior aparece más a la derecha que el `1` principal de la fila superior.
> 4) Cada columna que contiene un `1` principal tiene ceros en todas las demás posiciones de esa columna.

**2. (Desempeño 1b) ¿Qué es el rango de una matriz? ¿Cómo se observa el rango de `A` y el de `A°` al resolver un sistema?**
> **Respuesta:** **El rango de una matriz es el número de filas no nulas de la canónica equivalente.** Una vez llevada la matriz ampliada `A°` a la forma canónica, el rango de `A` (`ρ(A)`) se observa sin tener en cuenta la última columna, mientras que para obtener el rango de la matriz ampliada (`ρ(A°)`) sí se tiene en cuenta dicha columna.

**3. (Desempeño 1c) ¿Qué se debe hacer (pasos) para resolver un sistema por el método general?**
> **Respuesta:** Para resolver un sistema de ecuaciones utilizando el método general hay que seguir 5 pasos:
> `1ero|` Completar y ordenar el sistema dado.
> `2do|` Armar la matriz ampliada correspondiente (`A° = [ A : B ]`).
> `3ero|` Llevar dicha matriz a la forma canónica.
> `4to|` Clasificar el sistema.
> `5to|` Armar el vector solución.

**4. (Desempeño 1d) ¿Cuándo un sistema de ecuaciones es Compatible desde el punto de vista matricial? ¿Tiene alguna restricción esta condición?**
> **Respuesta:** El sistema de ecuaciones será **Compatible** (es decir, tendrá solución) si **el rango de la matriz de los coeficientes es igual al rango de la matriz ampliada (`ρ(A) = ρ(A°)`)**. Esta condición se aplica a cualquier sistema de ecuaciones lineales puesto que no impone ninguna restricción sobre el número de ecuaciones, el número de variables ni el valor de los términos independientes, utilizando sólo el concepto de rango de una matriz.

**5. (Desempeño 1e) ¿Qué condición debe cumplir un sistema de ecuaciones para ser Determinado o Indeterminado desde el punto de vista matricial?**
> **Respuesta:** Si el sistema es compatible (`ρ(A) = ρ(A°)`), **un sistema es determinado si el rango de la matriz ampliada es igual al número de incógnitas (`ρ(A°) = m` o `ρ(A) = m`)**, teniendo una única solución. **Si dicho rango es menor que el número de incógnitas (`ρ(A°) < m`), entonces el sistema es indeterminado** y tiene infinitas soluciones.

**6. (Desempeño 1f) ¿Cuándo un sistema es Incompatible, analizando la matriz ampliada?**
> **Respuesta:** Un sistema es **Incompatible** (es decir, no tendrá solución) cuando **no se verifica la igualdad entre el rango de la matriz de los coeficientes y el rango de la matriz ampliada (`ρ(A) ≠ ρ(A°)`)**. Esto ocurre cuando en la matriz ampliada canónica aparece al menos una fila con todos ceros en la parte de `A` y un elemento no nulo en la última columna (`B`).

**7. (Desempeño 1g) ¿Qué se puede asegurar de un sistema homogéneo y por qué?**
> **Respuesta:** Si un sistema de ecuaciones es homogéneo (`A · X = 0`), **siempre tiene solución, o sea el sistema siempre es compatible**. La explicación es que la matriz ampliada es de la forma `A° = [ A : 0 ]` y el rango de la misma es siempre igual al rango de `A`, puesto que el vector que se agrega es el vector nulo, no pudiendo en consecuencia aumentar el rango de la matriz `A°`.

**8. (Desempeño 1h) ¿Qué es la solución trivial y qué son las soluciones no triviales?**
> **Respuesta:** En cualquier sistema de ecuaciones homogéneo `A · X = 0`, el vector nulo siempre es solución, ya que `A · 0 = 0` cualquiera sea la matriz `A`. **Esta solución del sistema, que significa dar el valor cero a todas las variables, se denomina solución trivial** y generalmente no interesa. Las soluciones que interesan son las llamadas **no triviales**, que están representadas por **vectores distintos del vector nulo** y se obtienen utilizando el método general cuando el sistema es indeterminado.

**9. (Desempeño 1i) ¿Cómo se puede saber qué tipo de solución tiene un sistema homogéneo cuadrado?**
> **Respuesta:** En un sistema de ecuaciones homogéneo cuadrado `A · X = 0` donde `A` es de orden `n × n`, se analiza el **determinante de la matriz `A`**:
> - Si **el determinante de `A` es igual a cero (`|A| = 0`)**, el rango de `A` es menor que `n`, por lo que el sistema es **indeterminado** y tiene **infinitas soluciones**: la solución trivial y **soluciones no triviales**.
> - Si **el determinante de `A` es distinto de cero (`|A| ≠ 0`)**, el rango de `A` es igual a `n`, por lo que el sistema es **determinado** y la única solución que existe es la **solución trivial**.

**10. (Desempeño 1j) ¿Puede ser el rango de la matriz de los coeficientes mayor que el rango de la matriz ampliada?**
> **Respuesta:** **No, nunca puede ser mayor (`ρ(A) ≤ ρ(A°)` siempre).** Como la matriz ampliada `A° = [ A : B ]` contiene todas las columnas de `A` más la columna `B`, toda fila que sea no nula sin mirar la última columna (`A`) seguirá siendo no nula al incluir la última columna (`A°`). Agregar una columna a lo sumo puede mantener igual el rango o aumentarlo en `1`, pero jamás disminuirlo.

**11. ¿Por qué podemos asegurar que al aplicar operaciones elementales a la matriz ampliada `A°` el sistema que se obtiene al final es equivalente al original?**
> **Respuesta:** Textual del material: *"Podemos asegurar que el sistema que se obtiene es equivalente ya que si aplicamos operaciones elementales a la matriz ampliada, a cada una de las ecuaciones no le cambiarán las soluciones."*

**12. ¿Cuáles son las tres matrices en que se "desarma" un sistema de ecuaciones y cómo se escribe su forma matricial?**
> **Respuesta:** Las tres matrices son: la **Matriz de los coeficientes (`A`)**, de orden `n × m` (formada por los números que multiplican a cada incógnita); la **Matriz o vector de los términos independientes (`B`)**, de orden `n × 1`; y la **Matriz o vector de las incógnitas (`X`)**, de orden `m × 1`. Para armarlas el sistema debe estar completo y ordenado. Su **forma matricial** es el producto `A_(n×m) · X_(m×1) = B_(n×1)`.

**13. ¿Qué significa "validar la respuesta" al resolver un problema mediante un sistema de ecuaciones?**
> **Respuesta:** **Validar la respuesta** significa verificar que la solución obtenida del sistema sea acorde a la situación problemática trabajada. Un sistema puede ser Compatible Determinado (tener solución única), pero si los valores obtenidos no tienen sentido en el contexto del problema (por ejemplo, una cantidad fraccionaria de personas), entonces **es solución al sistema planteado, pero no es solución al problema planteado**.

---

## 📚 Glosario de la clase

| Término | Definición breve fiel al material |
| :--- | :--- |
| **Sistema completo y ordenado** | Sistema reacomodado de tal manera que en el primer miembro quedan los términos con las incógnitas (en el mismo orden y completando con `0` las ausentes) y en el segundo miembro quedan los términos independientes. |
| **Coeficientes** | Los números que multiplican a cada una de las incógnitas. |
| **Matriz de los coeficientes (`A`)** | Matriz de orden `n × m` formada por los coeficientes que multiplican a cada una de las incógnitas en el sistema completo y ordenado. |
| **Matriz (o vector) de los términos independientes (`B`)** | Matriz columna de orden `n × 1` formada por los términos independientes ubicados en el segundo miembro del sistema. |
| **Matriz (o vector) de las incógnitas (`X`)** | Matriz columna de orden `m × 1` formada por las incógnitas del sistema. |
| **Forma matricial del sistema** | Expresión `A_(n×m) · X_(m×1) = B_(n×1)` que representa al sistema de ecuaciones mediante el producto de la matriz de coeficientes por el vector de incógnitas igualado al vector de términos independientes. |
| **Matriz ampliada (`A°`)** | Matriz que se forma a partir de la matriz de los coeficientes y del vector de los términos independientes: `A° = [ A : B ]`. |
| **Sistema equivalente** | Sistema obtenido a partir de otro (por ejemplo, llevando `A°` a la canónica mediante operaciones elementales de fila) que conserva exactamente las mismas soluciones. |
| **Rango de una matriz (`ρ(A)`)** | El número de filas no nulas de la canónica equivalente. |
| **Sistema Compatible** | Sistema de ecuaciones que tiene solución. Matricialmente, se verifica cuando el rango de la matriz de los coeficientes es igual al rango de la matriz ampliada: `ρ(A) = ρ(A°)`. |
| **Sistema Incompatible** | Sistema de ecuaciones que no tiene solución. Matricialmente, ocurre cuando el rango de la matriz de los coeficientes no es igual al rango de la matriz ampliada: `ρ(A) ≠ ρ(A°)`. |
| **Sistema Compatible Determinado** | Sistema compatible que tiene una única solución (cada una de las incógnitas puede tomar un único valor). Matricialmente, se cumple cuando el rango de la matriz ampliada es igual al número de incógnitas: `ρ(A) = ρ(A°) = m`. |
| **Sistema Compatible Indeterminado** | Sistema compatible que tiene infinitas soluciones. Matricialmente, se cumple cuando el rango de la matriz ampliada es menor que el número de incógnitas: `ρ(A) = ρ(A°) < m`. |
| **Sistema de ecuaciones lineales homogéneo** | Sistema de la forma `A · X = 0` (todos sus términos independientes son nulos). Siempre tiene solución, o sea, siempre es compatible (`ρ(A) = ρ(A°)`). |
| **Solución trivial** | Solución de todo sistema homogéneo que significa dar el valor cero a todas las variables (representada por el vector nulo `X = 0`, ya que `A · 0 = 0` cualquiera sea `A`). |
| **Soluciones no triviales** | Soluciones de un sistema homogéneo representadas por vectores distintos del vector nulo (`X ≠ 0`); existen cuando el sistema homogéneo es indeterminado. |
| **Sistema homogéneo cuadrado** | Sistema homogéneo `A · X = 0` donde `A` es cuadrada de orden `n × n`. Tiene soluciones no triviales (es indeterminado) si y solo si `∣A∣ = 0`; si `∣A∣ ≠ 0`, es determinado y su única solución es la trivial. |
| **Validar la respuesta** | Comprobar que la solución matemática obtenida del sistema esté acorde a la situación problemática trabajada (distinguiendo entre solución al sistema planteado y solución al problema planteado). |
