# Clase 8 — Matrices y Determinantes: Determinantes y Matriz Inversa

## 🗺️ Mapa de la clase

### Estructura y orden de los temas
1. **Introducción y alcance de la clase (Págs. 1–2):**
   - Restricción fundamental del dominio: en toda esta clase se trabaja **únicamente con matrices cuadradas** (igual número de filas que de columnas), porque tanto el **determinante** como la **matriz inversa** se definen exclusivamente para ellas.
   - Propósito matemático: el determinante permite decidir si una matriz tiene o no **inversa**, y en la unidad siguiente (Sistemas de Ecuaciones Lineales) permitirá determinar si un sistema cuadrado tiene **solución única**.
2. **El concepto de Determinante (Págs. 2–3):**
   - **8.1 Concepto de determinante de una matriz cuadrada de orden n** (definición por suma algebraica de productos de n elementos de distinta fila y columna).
   - **8.2 Observaciones del concepto y notación** (diferencia crucial entre matriz y determinante, notación con barras verticales `|A|` y nombre *determinante de enésimo orden*).
3. **Cálculo de determinantes — Métodos particulares (Págs. 3–5):**
   - **8.3 Método particular A — Determinante de una matriz cuadrada de orden 2:** regla de la diagonal principal menos la diagonal secundaria.
   - **8.4 Método particular B — Determinante de una matriz de orden 3 y Regla de Sarrus:** expresión algebraica general de los 6 productos y las **dos variantes visuales de la Regla de Sarrus** (repitiendo las dos primeras filas o usando diagonales y vértices opuestos).
4. **Propiedades de los determinantes (Págs. 6–9):**
   - Clasificación en dos grandes bloques:
     - **Bloque I — Propiedades referidas a las operaciones elementales por fila:**
       - **8.5 1º Propiedad:** intercambio de dos filas (`Hᵢ,ⱼ`) → cambia el signo del determinante (`|A| = -|B|`).
       - **8.6 2º Propiedad:** multiplicación de una fila por una constante no nula (`Hᵢ(k)`) → multiplica el determinante por `k` (`|B| = k · |A|`).
       - **8.7 3º Propiedad:** suma a una fila de otra multiplicada por una constante no nula (`Hᵢ,ⱼ(k)`) → el determinante **no varía** (`|A| = |B|`).
       - **8.8 Método de la columna de control para operaciones elementales por fila:** técnica de verificación aritmética paso a paso.
     - **Bloque II — Propiedades de cuándo un determinante vale cero:**
       - **8.9 4º Propiedad:** línea (fila o columna) con todos sus elementos nulos → `|A| = 0`.
       - **8.10 5º Propiedad:** dos líneas paralelas iguales → `|A| = 0`.
       - **8.11 6º Propiedad:** dos líneas paralelas proporcionales → `|A| = 0` (incluye la definición de **líneas proporcionales**).
5. **Clasificación según el determinante y Método General (Págs. 9–10):**
   - **8.12 Matriz Regular o No Singular:** matriz cuadrada cuyo determinante es no nulo (`|A| ≠ 0`).
   - **8.13 Método General: Regla de Chío:** algoritmo en 3 pasos para reducir el orden de un determinante de cualquier orden `n` a `n - 1` mediante operaciones elementales y las propiedades 1, 2 y 3.
6. **Cálculo de la Inversa de una Matriz (Págs. 11–12):**
   - **8.14 Condición de existencia de la matriz inversa:** relación entre matriz cuadrada, matriz regular (`|A| ≠ 0`) y existencia de `A⁻¹`.
   - **8.15 Método de cálculo de la inversa por operaciones elementales (o método de Gauss-Jordan) y verificación:** armado de la matriz rectangular `[ A : I ]`, reducción a la forma canónica `[ I : A⁻¹ ]` y comprobación mediante `A · A⁻¹ = I`.
7. **Cuestionario teórico oficial e integración de la Unidad 2 (Págs. 14–17):**
   - **8.16 Resolución completa del Desempeño 56 (las 15 preguntas teóricas de la clase) y preguntas conceptuales de los Desempeños Finales.**

### Prerrequisitos (de las Clases 5, 6 y 7 de la Unidad 2)
- **Matriz y orden (dimensión) `m × n`:** saber qué es una fila, una columna, la posición `aᵢⱼ` (fila `i`, columna `j`) y cuándo una matriz es **cuadrada** (`m = n`, orden `n`).
- **Diagonal principal y diagonal secundaria** en una matriz cuadrada, y concepto de **líneas paralelas** (filas entre sí, o columnas entre sí).
- **Matriz Identidad (`I`) y Matriz Canónica:** la identidad tiene `1` en la diagonal principal y `0` en el resto; actúa como elemento neutro multiplicativo (`A · I = I · A = A`).
- **Multiplicación de matrices y su Propiedad 6 (Clase 6/7):** existencia del elemento inverso multiplicativo `A⁻¹` tal que `A · A⁻¹ = A⁻¹ · A = I`.
- **Operaciones elementales por fila y matrices equivalentes (`A ~ B`) (Clase 7):**
  - `Hᵢ,ⱼ`: intercambiar la fila `i` con la fila `j`.
  - `Hᵢ(k)` con `k ≠ 0`: multiplicar todos los elementos de la fila `i` por una constante `k ≠ 0`.
  - `Hᵢ,ⱼ(k)` con `k ≠ 0`: sumarle a la fila `i` la fila `j` previamente multiplicada por una constante `k ≠ 0`.
- **Método de Gauss-Jordan (Clase 7):** reducción por filas para transformar una matriz en una matriz canónica llevando la submatriz cuadrada a la identidad.

---

## 8.1 Introducción y alcance: Matrices cuadradas, Determinante e Inversa

> 📖 **Textual del material:**
> "De todas las matrices que podemos crear, en la clase de hoy solo trabajaremos con aquellas cuyo número de filas y columnas es el mismo, es decir con matrices cuadradas, ya que los conceptos de determinante e inversa de una matriz, se definen para ellas solamente."
>
> "En esta sección no se dará una definición rigurosa de determinantes ya que no se cuentan con los elementos necesarios para hacerlo. Se verán, si, distintos métodos y propiedades para calcularlos.
> Las aplicaciones prácticas de este tema se dan principalmente en la misma Matemática.
> El determinante nos permitirá decir si una matriz tiene o no inversa (elemento neutro multiplicativo). En la unidad siguiente utilizamos a los determinantes para saber si los sistemas de ecuaciones cuadrados tienen solución única."
>
> "Para el cálculo de matriz inversa además de la aplicación de operaciones elementales, puedes hacerlo mediante la matriz adjunta como se explica en uno de los anexos."

**🗣️ En palabras simples:**
Antes de hacer cualquier cuenta, el material fija la **regla de oro** de toda la Clase 8: si una matriz **no es cuadrada** (por ejemplo, si es de `2 × 3` o de `5 × 6`), **no tiene determinante ni tiene matriz inversa**. El determinante es una herramienta matemática que nos devuelve un número a partir de una matriz cuadrada, y ese número funciona como un "detector": si da distinto de cero, la matriz tiene inversa (y, como se verá en la Unidad 3, el sistema de ecuaciones cuadrado asociado tendrá solución única); si da cero, no tiene inversa.

**🔍 Desglose de la jerga:**
- **"Matrices cuyo número de filas y columnas es el mismo, es decir matrices cuadradas":** condición necesaria de dominio (`m = n`). Si te piden el determinante o la inversa de una matriz rectangular con `m ≠ n`, la respuesta inmediata es **"no existe porque la matriz no es cuadrada"**.
- **"No se dará una definición rigurosa de determinantes":** en álgebra superior el determinante se define formalmente mediante permutaciones e inversiones de índices o como función multilineal alternada; en este curso se da un **concepto operativo** (como suma algebraica de productos).
- **"Para saber si los sistemas de ecuaciones cuadrados tienen solución única":** anticipa el Teorema de Cramer / condición de compatibilidad determinada de la Unidad 3.
- **"Mediante la matriz adjunta como se explica en uno de los anexos":** el material menciona que existe otro método (por matriz adjunta / cofactores), aunque en el cuerpo de la Clase 8 desarrolla el método **por operaciones elementales (o Gauss-Jordan)**.

**💡 Ejemplo:**
*(Ejemplo tomado del Desempeño 51c, pág. 13 y pág. 15)*:
Si nos dan una matriz `C` que tiene **4 filas y 5 columnas** (orden `4 × 5`) y nos piden calcular `|C|`, la respuesta oficial del material es: **`|C|` no existe**, porque `C` no es una matriz cuadrada.

**🔗 Conexiones:**
- Conecta con **Clase 5 y 6 (Clasificación de matrices y multiplicación)** donde se definió matriz cuadrada, matriz identidad y la propiedad de la matriz inversa.
- Conecta con **Clase 9 / Unidad 3 (Sistemas de Ecuaciones Lineales)** donde los sistemas cuadrados (`n` ecuaciones con `n` incógnitas) tienen solución única si y solo si el determinante de la matriz de coeficientes es distinto de cero.

**⚠️ Precisiones / errores comunes:**
- **Aclaración conceptual sobre el paréntesis "(elemento neutro multiplicativo)" del PDF:** En la página 2 el texto dice *"decir si una matriz tiene o no inversa (elemento neutro multiplicativo)"*. En rigor (según las clases anteriores de la misma cátedra), la **Matriz Identidad (`I`)** es el *elemento neutro multiplicativo*, mientras que la **Matriz Inversa (`A⁻¹`)** es el *elemento inverso multiplicativo* que al multiplicarse por `A` da como resultado el elemento neutro multiplicativo (`A · A⁻¹ = I`). En el oral, si mencionás ambas cosas con precisión ("la inversa `A⁻¹` es la matriz que multiplicada por `A` da la identidad `I`, que es el elemento neutro multiplicativo"), quedarás impecable.
- **Error común en el examen:** ponerse a aplicar Chío o Gauss-Jordan en una matriz sin antes contar cuántas filas y cuántas columnas tiene. En el Desempeño 51a (pág. 13), la matriz `A` parece triangular pero tiene **5 filas y 6 columnas** (`5 × 6`), por lo que **`|A|` no existe**.

**🎤 Cómo decirlo en el oral:**
> "Tanto el concepto de determinante como el de matriz inversa se definen **solamente para matrices cuadradas**, es decir, aquellas cuyo número de filas y columnas es el mismo. El determinante nos sirve principalmente dentro de la matemática para saber si una matriz cuadrada tiene o no inversa, y en la unidad siguiente para saber si un sistema de ecuaciones cuadrado tiene solución única."

---

## 8.2 Concepto de Determinante, Observaciones y Notación

> 📖 **Textual del material:**
> "**Concepto**
> Se llama DETERMINANTE de una matriz cuadrada de orden n al número que se obtiene al sumar algebraicamente* todos los productos posibles entre n elementos de la matriz que pertenezcan a distinta fila y columna.
>
> **Observaciones del concepto:**
> • El determinante sólo se calcula a matrices cuadradas.
> • El determinante es un número, por lo tanto no debe confundirse el determinante de una matriz con ella. No olvidemos que una matriz es un conjunto de números.
> • Como consecuencia del segundo punto, simbolizaremos el determinante de una matriz con barras del siguiente modo:
> Dada
>
>     [ a₁₁  a₁₂  ...  a₁ₙ ]
>     [ a₂₁  a₂₂  ...  a₂ₙ ]
> A = [  :              :  ]
>     [  :              :  ]
>     [ aₙ₁  aₙ₂  ...  aₙₙ ]
>
> Su determinante lo simbolizaremos:
>
>         | a₁₁  a₁₂  ...  a₁ₙ |
>         | a₂₁  a₂₂  ...  a₂ₙ |
> |A|  ó  |  :              :  |
>         |  :              :  |
>         | aₙ₁  aₙ₂  ...  aₙₙ |
>
> Y lo llamaremos determinante de enésimo orden.
> Suma algebraica indica adición y/o sustracción."

**🗣️ En palabras simples:**
El **determinante** de una matriz cuadrada de tamaño `n × n` es **un único número real** (un escalar). ¿Cómo se forma teóricamente ese número? Se arman todas las multiplicaciones posibles eligiendo `n` casilleros de la matriz con la condición de que **no haya dos en la misma fila ni dos en la misma columna** (es decir, exactamente un elemento por cada fila y uno por cada columna). Luego, esos productos se suman y se restan entre sí ("suma algebraica").
Es fundamental distinguir el objeto **matriz** (que es un cuadro/conjunto ordenado de números encerrado entre corchetes `[ ]` o paréntesis `( )`) del objeto **determinante** (que es **un número**, y se escribe encerrando a la letra o a los elementos entre **barras verticales** `|A|`).

**🔍 Desglose de la jerga:**
- **"Matriz cuadrada de orden n":** matriz que tiene `n` filas y `n` columnas (`n × n`).
- **"Al número que se obtiene":** palabra clave. El determinante **es un número** (escalar), nunca una matriz.
- **"Sumar algebraicamente*" / "Suma algebraica indica adición y/o sustracción":** significa una combinación de sumas (`+`) y restas (`-`), porque la mitad de esos productos llevan signo positivo y la otra mitad llevan signo negativo.
- **"Todos los productos posibles entre n elementos de la matriz que pertenezcan a distinta fila y columna":** cada término del desarrollo del determinante es una multiplicación de `n` factores (`a₁_j₁ · a₂_j₂ · ... · aₙ_jₙ`), donde elegimos un elemento de la fila 1, uno de la fila 2, ..., uno de la fila `n`, sin repetir ninguna columna. *(Contexto adicional: en una matriz de orden `n` existen exactamente `n!` —factorial de `n`— productos posibles de este tipo: en orden 2 hay `2! = 2` productos; en orden 3 hay `3! = 6` productos; en orden 4 hay `4! = 24` productos).*
- **"Determinante de enésimo orden":** si la matriz cuadrada es de orden `n`, su determinante se denomina *determinante de orden `n`* (o *de enésimo orden*).
- **Barras `|A|`:** notación del determinante de `A`. No confundir con valor absoluto: cuando `A` es una matriz, `|A|` se lee *"determinante de A"* y puede dar positivo, negativo o cero.

**💡 Ejemplo:**
- Si `A` es de orden `2`:
  - `A = [ 5  -2 ; 4  3 ]` es una **matriz** (un conjunto de 4 números dispuestos en 2 filas y 2 columnas).
  - `|A| = 5 · 3 - (-2) · 4 = 23` es el **determinante de A** (un único número).
  - Observá cómo intervienen los productos de `n = 2` elementos de distinta fila y distinta columna: `a₁₁ · a₂₂` (fila 1 col 1 con fila 2 col 2) y `a₁₂ · a₂₁` (fila 1 col 2 con fila 2 col 1). No se multiplica `a₁₁ · a₁₂` porque están en la misma fila.

**🔗 Conexiones:**
- Explica directamente la fórmula de **orden 2** (2 productos: `a₁₁·a₂₂ - a₁₂·a₂₁`) y la fórmula de **orden 3 / Sarrus** (6 productos de 3 elementos cada uno, ninguno compartiendo fila ni columna).
- También explica por qué valen la **2º Propiedad** (como en cada producto hay exactamente un elemento de la fila `i`, si toda la fila `i` se multiplica por `k`, todos los productos quedan multiplicados por `k`) y la **4º Propiedad** (si una fila o columna tiene todos ceros, en cada producto habrá un factor `0`, así que todos los productos dan `0`).

**⚠️ Precisiones / errores comunes:**
- **Jamás decir que el determinante es una matriz o un cuadro:** el profesor pregunta en el oral *"¿Qué es un determinante?"* esperando escuchar la palabra **"al número..."**. Si empezás diciendo *"es una matriz que..."*, está mal.
- **No confundir `A` con `|A|` al escribir:** escribir `A = 23` es un error conceptual grave (igualás una matriz a un número). Lo correcto es `|A| = 23`.
- **Errata tipográfica del PDF en Pág. 3 y Pág. 10:** aunque el texto de la página 2 dice textualmente *"simbolizaremos el determinante de una matriz con barras"*, en el dibujo de las páginas 3 y 10 el diseñador gráfico dejó paréntesis/corchetes `[ ]` en vez de barras rectas `| |` alrededor de los elementos. Recordá que para el determinante de la matriz desplegada corresponden **barras rectas verticales** `| |`.

**🎤 Cómo decirlo en el oral:**
> "Se llama **determinante** de una matriz cuadrada de orden `n` **al número** que se obtiene al sumar algebraicamente (es decir, mediante adición y/o sustracción) todos los productos posibles entre `n` elementos de la matriz que pertenezcan a distinta fila y columna. Se simboliza con barras verticales, `|A|`, y se lo llama determinante de enésimo orden. Es fundamental recordar que sólo se calcula a matrices cuadradas y que el determinante es un número, mientras que la matriz es un conjunto de números."

---

## 8.3 Métodos Particulares — A• Cálculo del determinante de una matriz cuadrada de orden 2

> 📖 **Textual del material:**
> "**MÉTODOS PARTICULARES**
> A continuación describiremos dos métodos para calcular determinantes, el primero para matrices de orden 2 solamente y el segundo para matrices de orden 3 solamente.
>
> **A• Cálculo del determinante de una matriz cuadrada de orden 2**
> En este caso el determinante se calcula multiplicando entre sí los elementos de la diagonal principal, y restándole el producto de los elementos de la diagonal secundaria, o sea:
> Si:
>
>     [ a₁₁  a₁₂ ]
> A = [ a₂₁  a₂₂ ]
>
> Entonces su determinante es:
>
>       | a₁₁  a₁₂ |
> |A| = | a₂₁  a₂₂ | = A₁₁ . A₂₂ - A₁₂ . A₂₁"

**🗣️ En palabras simples:**
Para una matriz de `2 × 2`, calcular el determinante es hacer un producto cruzado en forma de "X": multiplicás los dos números de la **diagonal principal** (de arriba a la izquierda hacia abajo a la derecha) y **le restás** la multiplicación de los dos números de la **diagonal secundaria** (de arriba a la derecha hacia abajo a la izquierda).

**🔍 Desglose de la jerga:**
- **"Método particular para matrices de orden 2 solamente":** solo sirve para matrices `2 × 2`. No se puede calcular un determinante de `3 × 3` o `4 × 4` restando solo las dos diagonales principales.
- **"Elementos de la diagonal principal":** `a₁₁` y `a₂₂` (los elementos `aᵢⱼ` con `i = j`). Su producto `a₁₁ · a₂₂` lleva signo `+` adelante.
- **"Elementos de la diagonal secundaria":** `a₁₂` y `a₂₁`. Su producto `a₁₂ · a₂₁` se **resta** (lleva signo `-` adelante).

**💡 Ejemplo:**
- **Ejemplo 1 del material (Pág. 3):**
  Dada la matriz:
  `A = [ 5  -2 ; 4  3 ]`
  Su determinante es:
  `|A| = 5 · 3 - (-2) · 4 = 15 - (-8) = 15 + 8 = 23`
  *(Nota sobre el PDF: en la pág. 3 del apunte quedó impreso `5 . 3 - (-2) = 15 + 8 = 23` omitiendo tipográficamente el factor `. 4` en el paso intermedio, aunque lo multiplica para obtener el `8`).*
- **Desempeño 47 del material (Pág. 3 y respuesta en Pág. 15):**
  `A = [ 2  -5 ; 3  -1 ]` → `|A| = 2 · (-1) - (-5) · 3 = -2 - (-15) = -2 + 15 = 13`.

**🔗 Conexiones:**
- Es un caso particular de la definición general (para `n = 2`, los únicos dos productos de elementos de distinta fila y columna son `a₁₁ · a₂₂` y `a₁₂ · a₂₁`).
- Es el "paso final" al que se llega cuando se aplica la **Regla de Chío** a una matriz de orden 3 (como en el Ejemplo 3 de la pág. 10).

**⚠️ Precisiones / errores comunes:**
- **Cuidado con el doble signo menos:** el método lleva un signo `-` por definición (`diagonal principal MENOS diagonal secundaria`). Si el producto de la diagonal secundaria ya es negativo (como `(-2) · 4 = -8`), al restarlo queda `- (-8) = + 8`.

**🎤 Cómo decirlo en el oral:**
> "El cálculo del determinante de una matriz cuadrada de orden 2 es un método particular exclusivo para orden 2: se calcula multiplicando entre sí los elementos de la diagonal principal y restándole el producto de los elementos de la diagonal secundaria; es decir, `|A| = a₁₁ · a₂₂ - a₁₂ · a₂₁`."

---

## 8.4 Métodos Particulares — B• Cálculo del determinante de una matriz de orden 3 y Regla de Sarrus

> 📖 **Textual del material:**
> "**B• Cálculo del determinante de una matriz de orden tres:**
> Una matriz genérica de orden 3 es:
>
>     [ a₁₁  a₁₂  a₁₃ ]
> A = [ a₂₁  a₂₂  a₂₃ ]
>     [ a₃₁  a₃₂  a₃₃ ]
>
> Armando todos los productos posibles con elementos de distintas filas y columnas, y realizando posteriormente su suma algebraica obtenemos que el determinante de A es:
>
> |A| = (a₁₁ . a₂₂ . a₃₃ + a₂₁ . a₃₂ . a₁₃ + a₃₁ . a₁₂ . a₂₃) – (a₁₃ . a₂₂ . a₃₁ – a₂₃ . a₃₂ . a₁₁ – a₃₃ . a₁₂ . a₂₁) [1]
>
> Me imagino, que no es fácil darse cuenta que es lo que se hizo para calcular estos productos. Para que te sea más sencillo, (ya vas a ver que si) vamos a ver un método que visualmente es fácil de recordar y para poder calcular el determinante. Este método se llama **Regla de Sarrus**. Consiste en lo siguiente:
> • Repitamos en la matriz genérica las dos primeras filas del siguiente modo:
>
>     [ a₁₁  a₁₂  a₁₃ ]
>     [ a₂₁  a₂₂  a₂₃ ]
> A = [ a₃₁  a₃₂  a₃₃ ]
>     [ a₁₁  a₁₂  a₁₃ ]
>     [ a₂₁  a₂₂  a₂₃ ]
>
> Observemos que los productos de la expresión [1] lo forman:
> • Los elementos de la diagonal principal y sus paralelas.
> • Los elementos de la diagonal secundaria y sus paralelas."
>
> *(Recuadro de la segunda forma de Sarrus, Pág. 5)*:
> "Si te gusta leer y buscar otra manera de calcular el determinante de una matriz de orden 3, hay otra forma de la Regla de Sarrus, es la siguiente:
> **Sumamos:** el producto de los elementos de la diagonal principal, el producto de una paralela a la diagonal principal con el vértice opuesto y el producto de la otra paralela a la diagonal principal con el otro vértice.
> A todo esto le **restamos:** el producto de los elementos de la diagonal secundaria, el producto de los elementos de una paralela a la diagonal secundaria con el vértice opuesto y el producto de la secundaria con el otro vértice.
> De las dos formas de Sarrus, puedes optar por una, la que te resulta más fácil."

**🗣️ En palabras simples:**
En una matriz de `3 × 3`, hay **6 maneras posibles** de elegir 3 elementos sin repetir fila ni columna: 3 de esos productos se **suman** (términos positivos) y los otros 3 se **restan** (términos negativos).
Como memorizar los subíndices de la fórmula `[1]` de memoria es engorroso, usamos la **Regla de Sarrus** (exclusiva para orden 3), que el material enseña en **dos formas equivalentes**:
1. **Forma 1 (repitiendo filas):** copiás la **fila 1** y la **fila 2** debajo de la fila 3. Ahora te quedan 3 diagonales completas de 3 elementos que bajan de izquierda a derecha (la diagonal principal y sus dos paralelas debajo: **se suman**) y 3 diagonales completas de 3 elementos que bajan de derecha a izquierda (la diagonal secundaria y sus dos paralelas debajo: **se restan**).
2. **Forma 2 (sin repetir filas, formando triángulos con los vértices opuestos):** sin agregar filas, multiplicás los 3 de la diagonal principal, más los 2 de una paralela junto con el elemento de la esquina ("vértice") opuesta, más los 2 de la otra paralela junto con la otra esquina opuesta; y a eso le restás lo análogo con la diagonal secundaria, sus dos paralelas y sus vértices opuestos.

**🔍 Desglose de la jerga:**
- **Términos positivos (los 3 productos que se suman):**
  1. `a₁₁ · a₂₂ · a₃₃` (diagonal principal).
  2. `a₂₁ · a₃₂ · a₁₃` (primera paralela debajo de la diagonal principal al repetir filas; o paralela `a₂₁, a₃₂` con el vértice opuesto `a₁₃`).
  3. `a₃₁ · a₁₂ · a₂₃` (segunda paralela debajo de la diagonal principal al repetir filas; o paralela `a₁₂, a₂₃` con el vértice opuesto `a₃₁`).
- **Términos negativos (los 3 productos que se restan):**
  4. `a₁₃ · a₂₂ · a₃₁` (diagonal secundaria).
  5. `a₂₃ · a₃₂ · a₁₁` (primera paralela a la secundaria: `a₂₃, a₃₂` con `a₁₁`).
  6. `a₃₃ · a₁₂ · a₂₁` (segunda paralela a la secundaria: `a₁₂, a₂₁` con `a₃₃`).
- **"Para matrices de orden 3 solamente":** la Regla de Sarrus **NO funciona** para matrices de orden 4, 5 o superior (porque en orden 4 hay `4! = 24` productos y las diagonales solo darían 8).

**💡 Ejemplo:**
- **Ejemplo 2 del material (Págs. 4–5):**
  Dada la matriz:
  ```
      [ -2   3   5 ]
  A = [  0   1   4 ]
      [ -1   2   2 ]
  ```
  Repetimos las dos primeras filas debajo:
  ```
      [ -2   3   5 ]
      [  0   1   4 ]
      [ -1   2   2 ]
      [ -2   3   5 ]
      [  0   1   4 ]
  ```
  - **Productos de la diagonal principal y sus paralelas:**
    `(-2) · 1 · 2 + 0 · 2 · 5 + (-1) · 3 · 4 = -4 + 0 - 12 = -16`
  - **Productos de la diagonal secundaria y sus paralelas:**
    `(-1) · 1 · 5 + (-2) · 2 · 4 + 0 · 3 · 2 = -5 + (-16) + 0 = -21`
  - **Resta final:**
    `|A| = (-16) - (-21) = -16 + 21 = 5`
  *(Nota de errata en el Ejemplo 2, pág. 5: en el esquema dibujado en pág. 5 el PDF puso un `-1` en la última fila `[0 -1 4]` en vez de `[0 1 4]`, y al sumar `-5 + (-2)·2·4` escribió `-5 + 16` en lugar de `-5 - 16`, por lo que obtuvo `-16 - (11) = -27` o impreso `5`. El planteo escrito en la línea `|A| = (-2).1.2 + 0.2.5 + (-1).3.4 - ((-1).1.5 + (-2).2.4 + 0.3.2)` es la estructura exacta del método).*
- **Desempeño 48 del material (Pág. 6 y respuesta en Pág. 15):**
  `B = [ 3  2  -1 ; 0  4  -3 ; -2  1  5 ]`
  `|B| = (3·4·5 + 0·1·(-1) + (-2)·2·(-3)) - ((-1)·4·(-2) + (-3)·1·3 + 5·2·0) = (60 + 0 + 12) - (8 - 9 + 0) = 72 - (-1) = 73`.

**🔗 Conexiones:**
- Se fundamenta directamente en el **Concepto de determinante (8.2)** para `n = 3`.
- Cuando resolvemos determinantes de orden 4 o mayor con la **Regla de Chío (8.13)**, una vez que bajamos el determinante a orden 3, podemos rematar el cálculo aplicando la **Regla de Sarrus**.

**⚠️ Precisiones / errores comunes:**
- **Errata tipográfica en la fórmula `[1]` de la Pág. 4:** En la página 4 aparece impreso:
  `|A| = (a₁₁ . a₂₂ . a₃₃ + a₂₁ . a₃₂ . a₁₃ + a₃₁ . a₁₂ . a₂₃) – (a₁₃ . a₂₂ . a₃₁ – a₂₃ . a₃₂ . a₁₁ – a₃₃ . a₁₂ . a₂₁)`
  ¡Ojo! Si hay un signo `–` delante del segundo paréntesis, adentro del paréntesis los tres productos de la diagonal secundaria y sus paralelas **se suman entre sí** (`+`), tal como el propio material escribe correctamente en la página 5:
  `|A| = [productos diag. principal y paralelas] - ( [1er prod. sec.] + [2do prod. sec.] + [3er prod. sec.] )`
  O bien, si se saca el paréntesis, los tres últimos términos van restando: `- a₁₃·a₂₂·a₃₁ - a₂₃·a₃₂·a₁₁ - a₃₃·a₁₂·a₂₁`.
- **No aplicar Sarrus a orden 4:** Si el profesor pregunta en el oral *"¿Puedo usar la Regla de Sarrus en una matriz de orden 4?"*, la respuesta tajante es **NO**: Sarrus es un **método particular para matrices de orden 3 solamente**. Para orden 4 o mayor se usa el método general (**Regla de Chío**).

**🎤 Cómo decirlo en el oral:**
> "Para calcular el determinante de una matriz de orden 3 utilizamos un método particular llamado **Regla de Sarrus**, que sirve únicamente para matrices de orden 3. Tiene dos formas visuales equivalentes:
> 1. **Repitiendo las dos primeras filas** debajo de la tercera: sumamos los tres productos de los elementos de la diagonal principal y sus dos paralelas, y a eso le restamos la suma de los tres productos de los elementos de la diagonal secundaria y sus dos paralelas.
> 2. **Sin repetir filas (por vértices opuestos):** sumamos el producto de la diagonal principal más los dos productos de cada paralela a la diagonal principal por el vértice opuesto, y le restamos el producto de la diagonal secundaria y los dos productos de cada paralela a la secundaria por su vértice opuesto."

---

## 8.5 Propiedades de los Determinantes — Clasificación General y 1º Propiedad (Intercambio de dos filas)

> 📖 **Textual del material:**
> "**PROPIEDADES DE LOS DETERMINANTES**
> Seguidamente enunciaremos propiedades, algunas de las cuales nos permitirán calcular determinantes en forma muy sencilla y otras servirán de fundamento en otros métodos. Agruparemos estas propiedades en dos bloques para que resulte más fácil recordarlas. Estos son:
> • Referidas a operaciones elementales.
> • Cuando un determinante vale cero.
>
> • **Referidas a las operaciones elementales:** Para que las propiedades no queden en el olvido, las vamos a ir descubriendo de a poco.
>
> **1º PROPIEDAD:** “Si se intercambian entre sí, dos filas, el determinante cambia de signo pero no de valor absoluto”.
>
> En símbolos Si: A ~ B → |A| = - |B|
>                    Hᵢ,ⱼ"

**🗣️ En palabras simples:**
Las 6 propiedades de los determinantes se dividen en **dos bloques**:
1. Las **3 primeras** nos dicen qué le pasa al determinante cuando le aplicamos a la matriz cada una de las **3 operaciones elementales por fila** (`Hᵢ,ⱼ`, `Hᵢ(k)`, `Hᵢ,ⱼ(k)`).
2. Las **3 últimas** nos dicen en qué casos podemos asegurar a simple vista que el **determinante vale cero** sin hacer cuentas.

La **1º Propiedad** corresponde a la primera operación elemental (`Hᵢ,ⱼ`, permutar o intercambiar dos filas de lugar): cada vez que intercambiás dos filas entre sí, el determinante mantiene exactamente el mismo número en valor absoluto, pero **cambia su signo** (si era `-5`, pasa a ser `5`; si era `12`, pasa a ser `-12`).

**🔍 Desglose de la jerga:**
- **`A ~ B` con `Hᵢ,ⱼ` debajo:** se lee *"la matriz A es equivalente por filas a la matriz B a través de la operación elemental `Hᵢ,ⱼ` (intercambio de la fila `i` con la fila `j`)"*.
- **"Cambia de signo pero no de valor absoluto":** significa que `|B| = -|A|`, o equivalentemente `|A| = -|B|`. Sus módulos son iguales (`||A|| = ||B||`), pero son números opuestos.

**💡 Ejemplo:**
- **Actividad 1 del material (Pág. 6):**
  Dada `A = [ 1  4 ; 2  3 ]`, su determinante es `|A| = 1 · 3 - 4 · 2 = 3 - 8 = -5`.
  Si aplicamos la operación elemental `H₁,₂` (intercambiamos fila 1 con fila 2), obtenemos la matriz equivalente:
  `B = [ 2  3 ; 1  4 ]`
  Al calcular su determinante: `|B| = 2 · 4 - 3 · 1 = 8 - 3 = 5`.
  Efectivamente, `|A| = -5` y `|B| = 5` (números opuestos: `|A| = -|B|`).

**🧩 Idea de la demostración / justificación e 🤔 Intuición:**
- **🤔 Intuición:** En una matriz `2 × 2`, intercambiar la fila 1 con la fila 2 transforma la diagonal principal (`a₁₁, a₂₂`) en la diagonal secundaria (`a₂₁, a₁₂`) y viceversa. Entonces la resta `diagonal principal - diagonal secundaria` se invierte a `diagonal secundaria - diagonal principal`, lo cual da exactamente el número opuesto. En orden `n`, intercambiar dos filas invierte el signo de todos los términos de la suma algebraica.

**🔗 Conexiones:**
- Si en la **Regla de Chío (8.13)** o en ejercicios de seguimiento de operaciones elementales (como los **Desempeños 52 y 53**, pág. 13) se intercambian filas `m` veces, el signo del determinante cambia `m` veces (si se intercambia una cantidad par de veces, vuelve al signo original; si es impar, queda con signo opuesto).

**⚠️ Precisiones / errores comunes:**
- Cada intercambio `Hᵢ,ⱼ` multiplica al determinante por `(-1)`. Si en una cadena de operaciones aparecen dos intercambios (como `H₂,₃` y luego `H₃,₁` en el Desempeño 52), el primer intercambio cambia el signo (`-`) y el segundo lo vuelve a cambiar (`+`), compensándose entre sí.

**🎤 Cómo decirlo en el oral:**
> "Las propiedades de los determinantes se agrupan en dos bloques: las referidas a las operaciones elementales y las de cuándo un determinante vale cero. La **1º Propiedad**, referida al intercambio de filas, dice textualmente: *'Si se intercambian entre sí, dos filas, el determinante cambia de signo pero no de valor absoluto'*. En símbolos: si `A` es equivalente a `B` mediante `Hᵢ,ⱼ`, entonces `|A| = -|B|`."

---

## 8.6 2º Propiedad de los Determinantes (Multiplicación de una fila por una constante no nula)

> 📖 **Textual del material:**
> "**2º PROPIEDAD:** “ Si se multiplican los elementos de una fila por un número distinto de cero, el determinante queda multiplicado por ese número”.
>
> En símbolos. Si: A = A ~ B → |B| = k . |A|
>                         Hᵢ(k)"

**🗣️ En palabras simples:**
Corresponde a la segunda operación elemental por fila (`Hᵢ(k)` con `k ≠ 0`): si a **una sola fila** de la matriz `A` la multiplicás por un número `k` (distinto de cero) para obtener la matriz `B`, el determinante de la nueva matriz `B` es igual a `k` veces el determinante de la matriz original `A` (`|B| = k · |A|`).

**🔍 Desglose de la jerga:**
- **"Los elementos de una fila":** ¡atención! Se multiplica **una única fila**, no toda la matriz.
- **"Por un número distinto de cero":** porque la operación elemental `Hᵢ(k)` exige por definición que el escalar `k` sea distinto de cero (`k ≠ 0`).
- **En símbolos `|B| = k · |A|`:** `|A|` es el determinante original (antes de multiplicar la fila) y `|B|` es el determinante nuevo (después de multiplicar la fila por `k`). Por lo tanto, si querés despejar el determinante original `|A|` a partir de `|B|`, debés **dividir por `k`**: `|A| = |B| / k`.

**💡 Ejemplo:**
- **Actividad 2 del material (Pág. 6):**
  Dada `A = [ 1  4 ; 2  3 ]`, sabemos que `|A| = -5`.
  Aplicamos la operación elemental `H₁(2)` (multiplicamos la fila 1 por `2`):
  `B = [ 2  8 ; 2  3 ]`
  Calculamos `|B| = 2 · 3 - 8 · 2 = 6 - 16 = -10`.
  Se verifica que `|B| = 2 · |A| = 2 · (-5) = -10`.

**🧩 Idea de la demostración / justificación e 🤔 Intuición:**
- **🤔 Intuición:** Por el concepto de determinante (8.2), cada producto de la suma algebraica contiene **exactamente un elemento de cada fila**, y en particular exactamente un elemento de la fila `i`. Si todos los elementos de la fila `i` se multiplican por `k`, entonces cada uno de los productos del determinante tendrá un factor `k`. Sacando factor común `k` en toda la suma algebraica, el determinante completo queda multiplicado por `k`.

**🔗 Conexiones:**
- Conecta con la **6º Propiedad** (líneas proporcionales): si una fila es `k` veces otra fila, podés "sacar factor `k`" afuera del determinante y te queda una matriz con dos filas iguales, cuyo determinante es `0` por la **5º Propiedad** (`k · 0 = 0`).
- Conecta con los **Desempeños 52 y 53 (Pág. 13)** y con el paso 3 de la **Regla de Chío (8.13)**.

**⚠️ Precisiones / errores comunes:**
- **¡El error más frecuente al despejar `|A|` desde `|B|`!**
  Mirá con lupa la fórmula: si pasás de `A` a `B` aplicando `Hᵢ(k)`, entonces **`|B| = k · |A|`**.
  - Si conocés `|A|` y buscás `|B|` (como en el **Desempeño 53**), **multiplicás** por `k`: `|B| = k · |A|`.
  - Pero si aplicaste `Hᵢ(k)` para llegar a `B`, calculaste `|B|` (por ejemplo en Chío o en el **Desempeño 52**), y querés recuperar `|A|`, tenés que **dividir por `k`**: **`|A| = |B| / k`**.
- *(Contexto adicional útil para preguntas trampa)*: ¿Qué pasa si multiplico **toda una matriz `A` de orden `n`** por un número `k` (`k · A`)? Como multiplicar una matriz por un escalar multiplica **sus `n` filas** por `k`, la 2º Propiedad se aplica `n` veces (una por cada fila), por lo que `|k · A| = kⁿ · |A|`. En cambio, la operación elemental `Hᵢ(k)` multiplica **una sola fila**, por lo que `|B| = k · |A|`.

**🎤 Cómo decirlo en el oral:**
> "La **2º Propiedad** dice textualmente: *'Si se multiplican los elementos de una fila por un número distinto de cero, el determinante queda multiplicado por ese número'*. En símbolos: si `A` es equivalente a `B` mediante la operación `Hᵢ(k)`, entonces `|B| = k · |A|`."

---

## 8.7 3º Propiedad de los Determinantes (Suma a una fila de otra multiplicada por una constante no nula)

> 📖 **Textual del material:**
> "**Esta es la propiedad más importante que tiene un determinante, y que permite abreviar considerablemente el trabajo de calcularlos.**"
>
> "**3º PROPIEDAD:** “Si a una fila de una matriz se le suma otra previamente multiplicada por una constante distinta de cero, el determinante no varía”.
>
> En símbolos. Si: A ~ B → |A| = |B|
>                     Hᵢ,ⱼ(k)"

**🗣️ En palabras simples:**
Corresponde a la tercera operación elemental por fila (`Hᵢ,ⱼ(k)` con `k ≠ 0`): si a la fila `i` le sumás un múltiplo de otra fila `j`, **el determinante queda exactamente igual** (`|A| = |B|`).
Por eso el material destaca que es **la propiedad más importante** para el cálculo de determinantes: nos permite fabricar todos los ceros que queramos en una columna (para aplicar la Regla de Chío) **sin que el determinante cambie de valor**, ahorrándonos tener que hacer correcciones al final.

**🔍 Desglose de la jerga:**
- **"A una fila de una matriz (`fila i`) se le suma otra (`fila j`) previamente multiplicada por una constante distinta de cero (`k`)"**: es exactamente la operación elemental `Hᵢ,ⱼ(k)`, donde la fila que cambia es la fila `i` (`Fila_i_nueva = Fila_i + k · Fila_j`), mientras que la fila `j` permanece igual.
- **"El determinante no varía" / `|A| = |B|`:** el determinante es invariante frente a la operación elemental `Hᵢ,ⱼ(k)`.

**💡 Ejemplo:**
- **Actividad 3 del material (Pág. 7):**
  Dada `A = [ 1  4 ; 2  3 ]`, sabemos que `|A| = 1 · 3 - 4 · 2 = -5`.
  Aplicamos la operación elemental `H₁,₂(-3)` (a la fila 1 le sumamos la fila 2 previamente multiplicada por `-3`):
  - Nueva fila 1: `[ 1 + (-3)·2 ,  4 + (-3)·3 ] = [ 1 - 6 ,  4 - 9 ] = [ -5 , -5 ]`
  - Fila 2 queda igual: `[ 2 , 3 ]`
  Obtenemos `B = [ -5  -5 ; 2  3 ]`.
  Calculamos `|B| = (-5) · 3 - (-5) · 2 = -15 - (-10) = -15 + 10 = -5`.
  Efectivamente, `|A| = -5` y `|B| = -5` (`|A| = |B|`).

**🧩 Idea de la demostración / justificación e 🤔 Intuición:**
- **🤔 Intuición:** En una matriz de `2 × 2`, si a la fila 1 (`a₁₁, a₁₂`) le sumamos `k` veces la fila 2 (`k·a₂₁, k·a₂₂`), el nuevo determinante es:
  `(a₁₁ + k·a₂₁)·a₂₂ - (a₁₂ + k·a₂₂)·a₂₁ = (a₁₁·a₂₂ - a₁₂·a₂₁) + k·(a₂₁·a₂₂ - a₂₂·a₂₁)`
  El segundo paréntesis vale `0` porque sus dos términos son idénticos y se cancelan (`a₂₁·a₂₂ - a₂₂·a₂₁ = 0`). Por lo tanto, el agregado `k · Fila_2` se anula por completo y el determinante no sufre ninguna alteración.

**🔗 Conexiones:**
- Es el corazón de la **Regla de Chío (8.13)**: en el Ejemplo 3 (pág. 10), para anular los elementos de la columna 1 se usan únicamente operaciones del tipo `Hᵢ,ⱼ(k)` (`H₂,₁(-1)` y `H₃,₁(-3/2)`). Gracias a la **3º Propiedad**, al final del cálculo directamente se concluye que `|A| = |B|`.
- Responde directamente a la **pregunta `o` del Desempeño 56 (Pág. 14)**: *"¿Cuál es la operación elemental por fila que no modifica el valor del determinante?"* → La tercera operación elemental, `Hᵢ,ⱼ(k)`: sumar a una fila otra fila previamente multiplicada por una constante distinta de cero.

**⚠️ Precisiones / errores comunes:**
- **Cuidado al aplicar `Hᵢ,ⱼ(k)`:** la fila que se multiplica por `k` es la fila auxiliar `j`, **no** la fila `i` que se modifica. Si por error multiplicás también la fila `i` que estás reemplazando (por ejemplo haciendo `2·Fila_i - 3·Fila_j`), estarías combinando una operación `Hᵢ(2)` con `Hᵢ,ⱼ(-3)`, y ahí el determinante **sí** quedaría multiplicado por `2` (por la 2º Propiedad). Para que el determinante no varíe, la fila `i` a modificar debe tener coeficiente `1`.
- Nota sobre la ubicación del recuadro en el PDF (Pág. 7): En la maquetación de la página 7, la frase destacada *"Esta es la propiedad más importante que tiene un determinante, y que permite abreviar considerablemente el trabajo de calcularlos"* quedó impresa en la parte superior junto con el texto de la columna de control, pero conceptualmente refiere a las propiedades de operaciones elementales (y en especial a cómo la 2º y sobre todo la 3º Propiedad permiten reducir determinantes sin desarrollar todos los productos).

### Tabla comparativa del Bloque I: Propiedades referidas a las operaciones elementales

| Propiedad | Operación elemental | Qué se le hace a la matriz `A` para obtener `B` | Efecto sobre el determinante | Fórmula simbólica | Cómo recuperar `\|A\|` desde `\|B\|` |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **1º Propiedad** | `Hᵢ,ⱼ` | Se intercambian entre sí dos filas (`i` y `j`) | Cambia de signo pero no de valor absoluto | `\|A\| = - \|B\|` | `\|A\| = - \|B\|` |
| **2º Propiedad** | `Hᵢ(k)` (`k ≠ 0`) | Se multiplican los elementos de una fila `i` por `k ≠ 0` | Queda multiplicado por ese número `k` | `\|B\| = k · \|A\|` | `\|A\| = \|B\| / k` |
| **3º Propiedad** | `Hᵢ,ⱼ(k)` (`k ≠ 0`) | A una fila `i` se le suma otra fila `j` multiplicada por `k ≠ 0` | **No varía** (se mantiene igual) | `\|A\| = \|B\|` | `\|A\| = \|B\|` |

**💡 Ejemplo integrador de las 3 propiedades (Desempeños 52 y 53, Pág. 13):**
Supongamos que `A ~ B` a través de la secuencia de 6 operaciones elementales:
`H₂,₃ ⇒ H₁(3) ⇒ H₃(2) ⇒ H₃,₁ ⇒ H₃,₂(6) ⇒ H₂,₃(5)`
Veamos qué hace cada operación al determinante partiendo de `|A|`:
1. `H₂,₃` (1º Propiedad, intercambio): cambia el signo → `- |A|`
2. `H₁(3)` (2º Propiedad, multiplica fila por 3): multiplica por `3` → `-3 · |A|`
3. `H₃(2)` (2º Propiedad, multiplica fila por 2): multiplica por `2` → `-6 · |A|`
4. `H₃,₁` (1º Propiedad, intercambio): vuelve a cambiar el signo → `+6 · |A|`
5. `H₃,₂(6)` (3º Propiedad, suma múltiplo de otra fila): no varía → `+6 · |A|`
6. `H₂,₃(5)` (3º Propiedad, suma múltiplo de otra fila): no varía → `+6 · |A|`
Por lo tanto, la relación final entre ambos determinantes es: **`|B| = 6 · |A|`**.
- **Desempeño 52:** Si sabemos que `|B| = -18`, entonces `-18 = 6 · |A| ⇒ |A| = -18 / 6 = -3`.
- **Desempeño 53:** Si sabemos que `|A| = 4`, entonces `|B| = 6 · 4 = 24`.

**🎤 Cómo decirlo en el oral:**
> "La **3º Propiedad** dice textualmente: *'Si a una fila de una matriz se le suma otra previamente multiplicada por una constante distinta de cero, el determinante no varía'*. En símbolos: si `A` es equivalente a `B` mediante `Hᵢ,ⱼ(k)`, entonces `|A| = |B|`. Es la propiedad más útil en la práctica porque nos permite anular elementos de una columna para aplicar la Regla de Chío sin alterar el valor del determinante."

---

## 8.8 Columna de Control en Operaciones Elementales por Fila

> 📖 **Textual del material:**
> "La columna de control SE OBTIENE sumando los elementos de cada fila de la matriz. Lo que resulta que:
> 1+2+3 = 6
> 4+5+6 = 15
> 5+7+8 = 20
> A partir de este paso, la columna de control se trabaja de la misma manera que el resto de la matriz, como si fuese una columna más, aplicando las operaciones propias de cada fila.
> En el paso 1*, el -9 se obtiene aplicando la operación 1*.
> Para corroborar si se aplicó bien la operación por fila, la suma de los elementos de cada fila, debe seguir dando igual, al elemento de la columna de control correspondiente. En este caso 0 + (-3) + (-6) = -9. Al dar el mismo resultado, quiere decir que la operación se ha resuelto correctamente. En el caso que no diera el mismo resultado, hay que revisar solo ese paso, ya que se supone que el resto está bien resuelto. Es un proceso que lleva más cálculos, pero garantiza que la matriz a la que se llega, sea la correcta.
> En el paso 2*, se aplica la operación para anular el elemento de la tercera fila, y también se le aplica al elemento de la columna de control (o sea al 20). Como se podrá comprobar, el resultado de -3 + (-7) = -10, lo que indica que el procedimiento se ha realizado ¡correctamente!
>
> **Así se debería realizar en todos los pasos, comprobando uno a uno que los cálculos están bien hechos. Te invito a que lo apliques en la matriz resuelta anteriormente, y verás que es posible realizar dichas operaciones con un alto porcentaje de exactitud.**"

**🗣️ En palabras simples:**
Cuando aplicamos muchas operaciones elementales por fila seguidas (por ejemplo, en Gauss-Jordan para hallar la inversa o en la Regla de Chío), es muy fácil equivocarse en un signo o en una suma y arrastrar el error hasta el final.
La **columna de control** es un "detector de errores" paso a paso:
1. Antes de empezar, agregás a la derecha una columna extra donde anotás la **suma de los elementos de cada fila**.
2. Cada vez que le hacés una operación elemental a una fila, **se la hacés también al número de la columna de control**.
3. Terminado el paso, sumás los nuevos elementos de esa fila: si esa suma coincide con el nuevo número de la columna de control, el paso está bien hecho; si no coincide, te equivocaste en ese renglón y lo corregís en el acto.

**🔍 Desglose de la jerga:**
- **"Se obtiene sumando los elementos de cada fila de la matriz":** para la fila `i`, el elemento inicial de control es `cᵢ = aᵢ₁ + aᵢ₂ + ... + aᵢₙ`.
- **"Se trabaja de la misma manera que el resto de la matriz, como si fuese una columna más":** si aplicás `H₂,₁(-4)` a la fila 2, también hacés `c₂_nuevo = c₂ + (-4) · c₁`.
- **Propiedad de linealidad subyacente:** como las operaciones elementales por fila son lineales, la suma de los elementos transformados de una fila siempre es igual a aplicarle la misma operación a las sumas de las filas originales.

**💡 Ejemplo:**
*(Son exactamente los números de la página 7, que corresponden a la matriz `A = [ 1  2  3 ; 4  5  6 ; 5  7  8 ]` del Ejemplo 4 de la pág. 11)*:
1. **Armado de la columna de control inicial:**
   - Fila 1: `1 + 2 + 3 = 6`
   - Fila 2: `4 + 5 + 6 = 15`
   - Fila 3: `5 + 7 + 8 = 20`
2. **Paso 1\* — Operación `H₂,₁(-4)`** (para anular el `4` de la fila 2):
   - Nueva Fila 2 de la matriz: `[ 4 - 4·1 ,  5 - 4·2 ,  6 - 4·3 ] = [ 0 , -3 , -6 ]`
   - Nueva Fila 2 en la columna de control: `15 + (-4) · 6 = 15 - 24 = -9`
   - **Control:** sumamos los elementos de la nueva Fila 2: `0 + (-3) + (-6) = -9`. ¡Coincide con `-9`!
3. **Paso 2\* — Operación `H₃,₁(-5)`** (para anular el `5` de la fila 3):
   - Nueva Fila 3 de la matriz: `[ 5 - 5·1 ,  7 - 5·2 ,  8 - 5·3 ] = [ 0 , -3 , -7 ]`
   - Nueva Fila 3 en la columna de control: `20 + (-5) · 6 = 20 - 30 = -10`
   - **Control:** sumamos los elementos de la nueva Fila 3: `0 + (-3) + (-7) = -10`. ¡Coincide con `-10`!

**🔗 Conexiones:**
- Viene del trabajo con operaciones elementales y Gauss-Jordan de la **Clase 7** y se aplica tanto al escalonamiento en **Regla de Chío (8.13)** como al **cálculo de la inversa por Gauss-Jordan (8.15)**.

**⚠️ Precisiones / errores comunes:**
- Si calculás la inversa con la matriz rectangular `[ A : I ]`, si querés usar columna de control debés sumar **todos** los elementos de la fila de la matriz rectangular (los de `A` más los de `I`), y verificar la suma contra todos ellos en cada paso.

**🎤 Cómo decirlo en el oral:**
> "La **columna de control** es un método de verificación para las operaciones elementales por fila. Se obtiene sumando los elementos de cada fila de la matriz y colocándolos en una columna adicional. Luego, cada operación elemental por fila se aplica también a la columna de control como si fuera una columna más, y en cada paso se corrobora que la suma de los nuevos elementos de la fila siga siendo igual al elemento correspondiente de la columna de control."

---

## 8.9 Propiedades de los Determinantes — Bloque II: Cuando un determinante vale cero — 4º Propiedad (Línea nula)

> 📖 **Textual del material:**
> "**Cuando un determinante vale cero**
>
> **4º PROPIEDAD:** “Si todos los elementos de una línea (fila o columna) son nulos, el determinante de la matriz es nulo”.
>
> Quedó claro? Sí, si una matriz tiene una fila o columna nula, no es necesario calcular el determinante, sea del orden que sea, ya que siempre nos va a dar 0."

**🗣️ En palabras simples:**
Si mirás una matriz cuadrada (de cualquier tamaño: `2 × 2`, `3 × 3`, `10 × 10`) y encontrás que **toda una fila está llena de ceros** o **toda una columna está llena de ceros**, no tenés que hacer ninguna cuenta: su determinante vale **`0`** automáticamente, justificando por la **4º Propiedad**.

**🔍 Desglose de la jerga:**
- **"Todos los elementos":** absolutamente todos los casilleros de esa fila o de esa columna deben ser `0` (no alcanza con que haya algunos ceros).
- **"De una línea (fila o columna)":** en la jerga de matrices y determinantes, la palabra **"línea"** abarca indistintamente a una **fila** o a una **columna**.
- **"El determinante de la matriz es nulo":** `|A| = 0` (y por lo tanto, la matriz no es regular y no tiene inversa).

**💡 Ejemplo:**
- **Actividad 4 del material (Pág. 8):**
  ```
      [ 3   4  -1 ]
  A = [ 0   0   0 ]    y    B = [ 1  4 ]
      [ 2   5  -7 ]             [ 0  0 ]
  ```
  Ambas matrices tienen su segunda fila íntegramente nula (`0 0 0` y `0 0`). Por la 4º Propiedad, sin hacer cálculos: `|A| = 0` y `|B| = 0`.
- **Desempeño 51e y 51f (Pág. 13):**
  Las matrices `E` y `F` de orden 4 tienen toda una fila de ceros (`E` tiene la fila 2 nula; `F` tiene la fila 3 nula), por lo que inmediatamente `|E| = 0` y `|F| = 0`.

**🧩 Idea de la demostración / justificación e 🤔 Intuición:**
- **🤔 Intuición:** Por la definición de determinante (8.2), cada producto de la suma algebraica toma **un elemento de cada fila y un elemento de cada columna**. Si una fila (o una columna) tiene todos sus elementos iguales a `0`, entonces **en todos y cada uno de los productos habrá obligatoriamente un factor `0`**. Como cualquier número multiplicado por `0` da `0`, todos los productos valen `0`, y su suma algebraica da `0`.

**🔗 Conexiones:**
- Conecta con el concepto de **rango** (Clase 7) y con **matriz inversa (8.14)**: si una matriz cuadrada tiene una línea nula, su determinante es `0`, por lo que **no es regular** y **no tiene inversa**.

**⚠️ Precisiones / errores comunes:**
- En el oral, usá la palabra exacta **"línea (fila o columna)"** tal como figura en el enunciado: *"Si todos los elementos de una línea (fila o columna) son nulos, el determinante de la matriz es nulo"*.

**🎤 Cómo decirlo en el oral:**
> "La **4º Propiedad**, primera del bloque de cuándo un determinante vale cero, enuncia textualmente: *'Si todos los elementos de una línea (fila o columna) son nulos, el determinante de la matriz es nulo'*. Esto ocurre porque en cada producto que forma el determinante interviene un elemento de cada fila y de cada columna, de modo que todos los productos tendrán al menos un factor cero."

---

## 8.10 5º Propiedad de los Determinantes (Dos líneas paralelas iguales)

> 📖 **Textual del material:**
> "**5º PROPIEDAD:** “Si una matriz tiene dos líneas paralelas iguales, su determinante es nulo”."

**🗣️ En palabras simples:**
Si una matriz cuadrada tiene **dos filas idénticas** (elemento a elemento en el mismo orden) o **dos columnas idénticas**, su determinante da **`0`** sin necesidad de hacer cuentas.

**🔍 Desglose de la jerga:**
- **"Dos líneas paralelas":** significa **dos filas entre sí** o **dos columnas entre sí**. Una fila y una columna **no** son líneas paralelas (son perpendiculares/transversales); si una fila es igual a una columna, el determinante **no** tiene por qué dar cero.
- **"Iguales":** tienen exactamente los mismos números en las mismas posiciones respectivas (por ejemplo, la fila 2 es `2  5  5` y la fila 3 también es `2  5  5`).

**💡 Ejemplo:**
- **Actividad 5 del material (Pág. 8):**
  ```
      [ 3   4   4 ]
  A = [ 2   5   5 ]    y    B = [ 1  4 ]
      [ 2   5   5 ]             [ 4  4 ]
  ```
  En `A`, la fila 2 y la fila 3 son líneas paralelas iguales (`[2  5  5]`), y además la columna 2 y la columna 3 también son líneas paralelas iguales (`[4 ; 5 ; 5]`). Por lo tanto, `|A| = 0`.
  *(Nota sobre el PDF en Pág. 8: en la matriz `B = [1 4 ; 4 4]` del PDF pusieron un `1` en `b₁₁` por error de tipeo cuando querían poner dos líneas iguales como `[4 4 ; 4 4]`, y en el renglón final de la página 8 se les copió por error el comentario de la 4º propiedad).*
- **Desempeño 51b (Pág. 13):**
  En la matriz `B` de orden 6, la **columna 1** (`-5, 3, -2, 2, 2, 0`) y la **columna 3** (`-5, 3, -2, 2, 2, 0`) son dos líneas paralelas iguales. Sin hacer un solo cálculo en esa matriz de `6 × 6`, por la 5º Propiedad sabemos que **`|B| = 0`**.

**🧩 Idea de la demostración / justificación e 🤔 Intuición:**
- **🧩 Idea de la demostración (a partir de las propiedades anteriores):**
  1. **Vía 1º Propiedad:** Si intercambiamos entre sí las dos filas iguales (`Hᵢ,ⱼ`), por la **1º Propiedad** el determinante debe cambiar de signo (`|A| = -|A|`). Pero como las dos filas eran idénticas, la matriz que queda después del intercambio es exactamente la misma matriz `A`. El único número real que es igual a su propio opuesto (`|A| = -|A| ⇒ 2·|A| = 0`) es el **`0`**.
  2. **Vía 3º Propiedad y 4º Propiedad:** Si a una de las filas iguales le restamos la otra (`Hᵢ,ⱼ(-1)`), por la **3º Propiedad** el determinante no varía, y nos queda una fila de todos ceros (`0 0 ... 0`), cuyo determinante es `0` por la **4º Propiedad**.

**🔗 Conexiones:**
- Se deduce directamente de la 1º Propiedad (o de la 3º + 4º Propiedad), y a su vez sirve para demostrar la **6º Propiedad** (líneas proporcionales).

**⚠️ Precisiones / errores comunes:**
- **No omitir la palabra "paralelas":** si en el oral decís *"Si una matriz tiene dos líneas iguales..."* sin decir **"paralelas"**, el profesor te puede retrucar: *"¿Y si la fila 1 es igual a la columna 1?"*. Por ejemplo, en `A = [ 1  2 ; 2  5 ]`, la fila 1 es `(1, 2)` y la columna 1 es `(1, 2)`, ¡pero su determinante es `1·5 - 2·2 = 1 ≠ 0`! Tienen que ser **dos líneas paralelas** (dos filas o dos columnas).

**🎤 Cómo decirlo en el oral:**
> "La **5º Propiedad** dice textualmente: *'Si una matriz tiene dos líneas paralelas iguales, su determinante es nulo'*. Decimos líneas paralelas porque deben ser dos filas iguales entre sí, o dos columnas iguales entre sí."

---

## 8.11 6º Propiedad de los Determinantes (Dos líneas paralelas proporcionales) y Definición de Líneas Proporcionales

> 📖 **Textual del material:**
> "Por otro lado las filas de ambas matrices tienen algo particular. Una fila es múltiplo escalar de otra fila. Es decir, una fila se puede obtener a partir de multiplicar una fila por un escalar. Por ejemplo, para la matriz A la columna 2 se puede obtener de multiplicar la columna 1 por 3.
> En el caso de la matriz B, la fila 3 se puede obtener a partir de multiplicar la fila 2 por el escalar 5.
> Simplificando, así sería la próxima propiedad…
>
> **6º PROPIEDAD:** "Si dos líneas paralelas son proporcionales*, el determinante es nulo". En general:
>
> **Referencia.** Dos líneas son proporcionales, cuando una de ellas es la otra multiplicada por un cierto número."

**🗣️ En palabras simples:**
Si una matriz cuadrada tiene **dos filas** (o **dos columnas**) tales que una es **múltiplo escalar** de la otra (es decir, todos los elementos de una línea se obtienen multiplicando a los de otra línea paralela por un mismo número fijo `k`), entonces el determinante vale **`0`** directamente.

**🔍 Desglose de la jerga:**
- **"Dos líneas paralelas":** dos filas entre sí, o dos columnas entre sí.
- **"Son proporcionales" / "Cuando una de ellas es la otra multiplicada por un cierto número" / "Múltiplo escalar":** significa que existe una constante `k` tal que cada elemento de una línea es `k` veces el elemento correspondiente de la otra línea paralela.
- **Caso particular:** Notá que la 4º Propiedad (cuando `k = 0`) y la 5º Propiedad (cuando `k = 1`) pueden verse como casos particulares de proporcionalidad.

**💡 Ejemplo:**
- **Actividad 6 del material (Pág. 9):**
  ```
      [ 5  15 ]                   [ 3   4  -1 ]
  A = [ 2   6 ]    y la matriz B = [ 1   4   3 ]
                                  [ 5  20  15 ]
  ```
  - En `A`: la columna 2 (`15, 6`) es igual a la columna 1 (`5, 2`) multiplicada por `3` (y también la fila 1 es `(5/2)` veces la fila 2). Por la 6º Propiedad, `|A| = 0` (verificación: `5·6 - 15·2 = 30 - 30 = 0`).
  - En `B`: la fila 3 (`5, 20, 15`) se obtiene de multiplicar la fila 2 (`1, 4, 3`) por el escalar `5`. Como tiene dos filas proporcionales, por la 6º Propiedad, `|B| = 0`.
- **Desempeño 51g y 54a (Págs. 13–14):**
  En la matriz `G` de orden 4 (`[ 3 -6 2 -1 ; -2 4 1 3 ; 0 0 1 1 ; 1 -2 1 0 ]`), mirá la **columna 1** (`3, -2, 0, 1`) y la **columna 2** (`-6, 4, 0, -2`): la columna 2 es exactamente la columna 1 multiplicada por `-2`. ¡Son dos columnas proporcionales! Por la 6º Propiedad, sin hacer Chío ni cuentas, **`|G| = 0`**.

**🧩 Idea de la demostración / justificación e 🤔 Intuición:**
- **🧩 Idea de la demostración:** Si la fila `i` es `k` veces la fila `j` (`Fila_i = k · Fila_j`), por la **2º Propiedad** ese factor `k` sale multiplicando afuera del determinante: `|A| = k · |A'|`, donde `A'` tiene la fila `i` y la fila `j` **iguales**. Y por la **5º Propiedad**, como `A'` tiene dos líneas paralelas iguales, `|A'| = 0`, de modo que `|A| = k · 0 = 0`. (O bien, aplicando `Hᵢ,ⱼ(-k)` por la 3º Propiedad, la fila `i` se anula toda y por la 4º Propiedad da `0`).

### Tabla comparativa del Bloque II: Cuando un determinante vale cero

| Propiedad | Condición en la matriz cuadrada `A` | Ejemplo visual rápido | Resultado |
| :--- | :--- | :--- | :--- |
| **4º Propiedad** | Todos los elementos de una **línea (fila o columna) son nulos**. | Una fila o columna es `0, 0, ..., 0` | `\|A\| = 0` |
| **5º Propiedad** | Tiene **dos líneas paralelas iguales** (dos filas iguales o dos columnas iguales). | `Fila 2 = [2, 5, 5]` y `Fila 3 = [2, 5, 5]` | `\|A\| = 0` |
| **6º Propiedad** | Tiene **dos líneas paralelas proporcionales** (una es la otra multiplicada por un cierto número). | `Fila 2 = [1, 4, 3]` y `Fila 3 = [5, 20, 15] = 5 · Fila 2` | `\|A\| = 0` |

**🎤 Cómo decirlo en el oral:**
> "La **6º Propiedad** dice textualmente: *'Si dos líneas paralelas son proporcionales, el determinante es nulo'*. Y dos líneas son proporcionales cuando una de ellas es la otra multiplicada por un cierto número (es decir, cuando una línea es múltiplo escalar de otra línea paralela)."

---

## 8.12 Matriz Regular o No Singular

> 📖 **Textual del material:**
> "**Si una matriz tiene el determinante no nulo se dice que la matriz es REGULAR o NO SINGULAR.**"

**🗣️ En palabras simples:**
Es el nombre propio con el que se clasifica a las matrices cuadradas según cuánto da su determinante:
- Si `|A| ≠ 0` (el determinante da cualquier número distinto de cero, positivo o negativo), la matriz `A` se llama **REGULAR** o **NO SINGULAR**.
- *(Contraparte)*: Si `|A| = 0` (el determinante es nulo), la matriz **no es regular** (se la llama *singular* o *no regular*).

**🔍 Desglose de la jerga:**
- **"Determinante no nulo":** `|A| ≠ 0` (implícitamente exige que `A` sea cuadrada, porque si no es cuadrada ni siquiera existe `|A|`).
- **"REGULAR o NO SINGULAR":** son **sinónimos exactos**. En matemáticas "singular" significa "especial/degenerado" (cuando el determinante se anula y no se puede invertir); por eso, cuando el determinante **no** es cero y la matriz se comporta bien, se dice que es **regular** o **no singular**.

**💡 Ejemplo:**
- En el **Desempeño 55 (Pág. 14)**:
  - `A = [ 4  5/2 ; 3  5/2 ]` → `|A| = 4·(5/2) - (5/2)·3 = 10 - 15/2 = 5/2 ≠ 0` → `A` **es regular** (tiene inversa).
  - `C = [ 1  -2 ; -2  4 ]` → `|C| = 1·4 - (-2)·(-2) = 4 - 4 = 0` (o por 6º Propiedad, la fila 2 es `-2` veces la fila 1) → `C` **no es regular** (no tiene inversa).

**🔗 Conexiones:**
- Es el puente directo hacia el **Cálculo de la Inversa de una Matriz (8.14)**: **"UNA MATRIZ TIENE INVERSA SI ES REGULAR"**.
- Conecta con el **rango** de una matriz cuadrada de orden `n` (Clase 7): una matriz cuadrada de orden `n` es regular (`|A| ≠ 0`) si y solo si su rango es máximo (`R(A) = n`) y su forma canónica por Gauss-Jordan es la matriz identidad `Iₙ`.

**⚠️ Precisiones / errores comunes:**
- **Cuidado con el "NO" de "NO SINGULAR":** muchos alumnos se confunden pensando que *"no singular"* significa *"no regular"*. ¡Al revés!
  - **Regular = No singular** ⇔ `|A| ≠ 0` ⇔ **Tiene inversa**.
  - **No regular = Singular** ⇔ `|A| = 0` ⇔ **No tiene inversa**.

**🎤 Cómo decirlo en el oral:**
> "Si una matriz cuadrada tiene el determinante no nulo (`|A| ≠ 0`), se dice que la matriz es **regular** o **no singular**."

---

## 8.13 Método General para el Cálculo de Determinantes: Regla de Chío

> 📖 **Textual del material:**
> "**MÉTODO GENERAL**
> A continuación veremos un método que permite calcular el determinante a matrices cuadradas de cualquier orden, inclusive de orden 2 y 3. Este es la Regla de Chio:
>
> **Regla de Chio**
> El primer paso de este método consiste en aplicar una serie de operaciones elementales en la matriz con el fin de conseguir que una columna (cualquiera) tenga todos sus elementos nulos excepto uno.
> Una vez logrado esto, hacemos la multiplicación de los siguientes tres factores:
> • El elemento no nulo de la columna elegida.
> • El (-1)ⁱ⁺ʲ, donde i,j corresponden a la posición del elemento no nulo elegido.
> • El determinante de la matriz que surge al sacar la fila y la columna del elemento elegido en el primer paso.
> El resultado de la multiplicación, es el determinante buscado, previamente verificando, si es necesario aplicar las propiedades correspondientes (1, 2 o 3) según las operaciones usadas para lograr los ceros.
>
> **En resumen:**
> La Regla de Chio consta de tres pasos:
> **1ᵉʳ|** Aplicamos operaciones elementales hasta lograr que una columna (cualquiera) tenga nulos todos sus elementos excepto uno.
> **2ᵈᵒ|** Realizamos la multiplicación de los factores indicados.
> **3ᵉʳ|** Aplicamos las propiedades correspondientes (1, 2 o 3) según las operaciones usadas para lograr los ceros, si es necesario."

**🗣️ En palabras simples:**
¿Cómo calculamos el determinante de una matriz de `4 × 4`, `5 × 5` o `6 × 6` si no existe Sarrus para esos órdenes? (O incluso de una de `3 × 3` si no queremos usar Sarrus). Usamos el **Método General: la Regla de Chío**.
La idea de la Regla de Chío es **bajar un escalón el orden del determinante** (pasar de orden `n` a orden `n - 1`):
1. Elegís una columna cualquiera (conviene elegir la que ya tenga más ceros o tenga un `1`) y elegís un elemento no nulo `aᵢⱼ` de esa columna como "pivote". Usando operaciones elementales por fila (preferentemente la tercera operación, `H_f,i(k)`), convertís en **`0` todos los demás elementos de esa columna**.
2. Una vez que esa columna tiene un solo elemento no nulo `aᵢⱼ` y todos los demás son ceros, el determinante de esa matriz reducida `B` es igual al producto de **3 factores**:
   `|B| = (elemento no nulo aᵢⱼ) · (-1)ⁱ⁺ʲ · (determinante de orden n-1 que queda al tachar la fila i y la columna j)`
3. Por último, revisás qué operaciones elementales usaste en el paso 1: si solo usaste la tercera operación (`Hᵢ,ⱼ(k)`), por la 3º Propiedad el determinante no varió (`|A| = |B|`); si en cambio intercambiaste filas (`Hᵢ,ⱼ`) o multiplicaste alguna fila por una constante (`Hᵢ(k)`), ajustás el resultado aplicando la 1º o 2º Propiedad.

**🔍 Desglose de la jerga y de los 3 factores del Paso 2:**
- **"Permite calcular el determinante a matrices cuadradas de cualquier orden, inclusive de orden 2 y 3":** por eso se clasifica como **Método General**, a diferencia de la regla de las diagonales de orden 2 y la Regla de Sarrus de orden 3 que son **Métodos Particulares**.
- **Factor 1 — "El elemento no nulo de la columna elegida" (`aᵢⱼ`):** el número que quedó vivo (distinto de cero) en la columna donde anulaste el resto. *(¡No tiene obligación de valer 1! En el Ejemplo 3 vale `2`).*
- **Factor 2 — "El `(-1)ⁱ⁺ʲ`, donde `i,j` corresponden a la posición del elemento no nulo elegido":** es el signo de posición:
  - Si la suma `i + j` (número de fila más número de columna) es **par**, entonces `(-1)ⁱ⁺ʲ = +1`.
  - Si la suma `i + j` es **impar**, entonces `(-1)ⁱ⁺ʲ = -1`.
  - *(Visualmente sigue un tablero de ajedrez de signos empezando con `+` en `a₁₁`: `+ - + - ...`).*
- **Factor 3 — "El determinante de la matriz que surge al sacar la fila y la columna del elemento elegido en el primer paso":** si la matriz original era de orden `n`, al tachar la fila `i` y la columna `j` queda un determinante de orden `n - 1`.
  - Si `A` era de orden 3, queda un determinante de orden 2 (se resuelve directo).
  - Si `A` era de orden 4, queda un determinante de orden 3 (se resuelve por Sarrus o aplicando Chío otra vez).
  - Si `A` era de orden 6 (pregunta `m` del Desempeño 56), se aplica la Regla de Chío sucesivamente: de orden 6 baja a orden 5, luego a orden 4, luego a orden 3 (y ahí Sarrus o nuevamente Chío).

**💡 Ejemplo:**
- **Ejemplo Nº 3 del material (Pág. 10):**
  Calcular por Regla de Chío el determinante de:
  ```
      [ 2   4   2 ]
  A = [ 2   7   8 ]
      [ 3   5   8 ]
  ```
  - **1| Primer paso:** Elegimos el elemento `2` de la fila 1, columna 1 (`i = 1, j = 1`). Anulamos los elementos restantes de la columna 1 aplicando operaciones elementales de tipo 3:
    - Aplicamos `H₂,₁(-1)` (a la fila 2 le restamos la fila 1): la fila 2 pasa a ser `[ 0   3   6 ]`.
    - Aplicamos `H₃,₁(-3/2)` (a la fila 3 le sumamos la fila 1 multiplicada por `-3/2`): la fila 3 pasa a ser `[ 0  -1   5 ]`.
    Obtenemos la matriz equivalente:
    ```
        [ 2   4   2 ]
    B = [ 0   3   6 ]
        [ 0  -1   5 ]
    ```
    Ya logramos que la columna 1 tenga todos sus elementos nulos excepto uno (el `2`).
  - **2| Segundo paso:** Multiplicamos los 3 factores para calcular `|B|`:
    - **Elemento no nulo:** `2`
    - **Signo de posición `(-1)ⁱ⁺ʲ`:** como está en fila 1, columna 1 (`i = 1, j = 1`), es `(-1)¹⁺¹ = (-1)² = 1`
    - **Determinante que surge de sacar la fila 1 y la columna 1:**
      `| 3   6 |`
      `| -1  5 | = 3 · 5 - 6 · (-1) = 15 + 6 = 21`
    Multiplicamos los tres factores:
    `|B| = 2 · (-1)¹⁺¹ · 21 = 2 · 1 · 21 = 42`.
  - **3| Tercer paso:** Aplicamos las propiedades correspondientes según las operaciones usadas:
    Como solo aplicamos dos veces la tercera operación elemental (`H₂,₁(-1)` y `H₃,₁(-3/2)`), según la **3º Propiedad** esta operación no cambia el determinante. Por lo tanto:
    `|A| = |B| = 42`.

**🧩 Por qué funciona el algoritmo e 🤔 Intuición:**
- **🤔 Intuición:** Si en una columna todos los elementos son `0` excepto el elemento `aᵢⱼ`, cuando armamos todos los productos posibles de `n` elementos de distinta fila y columna (concepto 8.2), cualquier producto que elija alguno de los ceros de esa columna se anulará (`0`). Los únicos productos que sobreviven son los que eligen obligatoriamente a `aᵢⱼ` en esa columna y a `n - 1` elementos de las demás filas y columnas (la submatriz que queda al tachar la fila `i` y la columna `j`), afectados por el signo de posición `(-1)ⁱ⁺ʲ`.

**🔗 Conexiones:**
- Combina las **operaciones elementales por fila** (Clase 7) con las **Propiedades 1, 2 y 3 de los determinantes (8.5–8.7)** y los **métodos particulares de orden 2 y 3 (8.3–8.4)**.
- Responde directamente a las preguntas `e`, `i` y `m` del **Desempeño 56 (Pág. 14)**.

**⚠️ Precisiones / errores comunes:**
- **Error clásico 1: Olvidarse del factor `(-1)ⁱ⁺ʲ`:** Si el elemento no nulo elegido está en una posición donde `i + j` es impar (por ejemplo, fila 1 columna 2, o fila 2 columna 1, o fila 3 columna 2), entonces `(-1)ⁱ⁺ʲ = -1` y cambia el signo del producto. ¡Nunca te olvides de escribir el factor `(-1)ⁱ⁺ʲ`!
- **Error clásico 2: Olvidarse del Paso 3 cuando se usaron `Hᵢ,ⱼ` o `Hᵢ(k)`:** Si para evitar fracciones multiplicaste una fila por `2` (`Hᵢ(2)`) o intercambiaste dos filas (`Hᵢ,ⱼ`), entonces `|B|` **no** es igual a `|A|`: en el paso 3 tenés que corregir el signo (1º Propiedad) o dividir por `2` (2º Propiedad). Por eso siempre conviene usar únicamente operaciones de tipo `Hᵢ,ⱼ(k)` (3º Propiedad), que no alteran el determinante.
- *(Nota sobre la fórmula impresa en Pág. 10 del PDF)*: En el diagrama de la página 10 pusieron un signo `=` entre `(-1)¹⁺¹` y el determinante `2 × 2` cuando la llave superior indica **"Factores"** que se multiplican entre sí, tal como lo hace en el renglón siguiente: `|B| = 2 . 1 . 21 = 42`.

**🎤 Cómo decirlo en el oral:**
> "La **Regla de Chío** es el método general que permite calcular el determinante de matrices cuadradas de cualquier orden (inclusive de orden 2 y 3). Consta de tres pasos:
> 1. **Primer paso:** Aplicamos operaciones elementales por fila hasta lograr que una columna cualquiera tenga todos sus elementos nulos excepto uno.
> 2. **Segundo paso:** Multiplicamos tres factores: el elemento no nulo de la columna elegida, el factor de posición `(-1)ⁱ⁺ʲ` (donde `i, j` son la fila y columna de dicho elemento), y el determinante de orden `n - 1` que surge al suprimir la fila y la columna del elemento elegido.
> 3. **Tercer paso:** Aplicamos las propiedades 1, 2 o 3 según las operaciones elementales usadas para lograr los ceros, si es necesario."

---

## 8.14 Condición de Existencia de la Matriz Inversa

> 📖 **Textual del material:**
> "Vamos a ver ahora como se puede encontrar la matriz inversa. Esto nos va a servir para resolver sistemas de ecuaciones (ya falta poco, en la próxima unidad lo vamos a aplicar) Como ya se dijo anteriormente (propiedad 6 del producto de matrices), las únicas matrices que pueden tener inversa son las matrices cuadradas; y podemos asegurar que la tienen si la matriz cuadrada es REGULAR (es decir que tiene determinante no nulo).
>
> **O sea: UNA MATRIZ TIENE INVERSA SI ES REGULAR.**"
>
> "Primero calculamos el determinante (si es distinto de cero sabemos que tiene inversa. Si es igual a cero la inversa no existe y no se continúa el ejercicio)."

**🗣️ En palabras simples:**
¿Cuándo existe la matriz inversa `A⁻¹` de una matriz `A`? Tienen que cumplirse dos cosas (en realidad la segunda ya incluye a la primera):
1. Que `A` sea **cuadrada** (de orden `n × n`).
2. Que `A` sea **regular** (o no singular), es decir, que su **determinante sea distinto de cero** (`|A| ≠ 0`).

Por eso, antes de ponerte a calcular la inversa de una matriz por Gauss-Jordan, el **primer paso obligatorio** es calcular su determinante `|A|`:
- Si `|A| ≠ 0` → `A` es regular → **existe `A⁻¹`** y procedemos a calcularla.
- Si `|A| = 0` → `A` no es regular → **no existe `A⁻¹`** y el ejercicio termina ahí.

**🔍 Desglose de la jerga:**
- **"Propiedad 6 del producto de matrices":** refiere a la propiedad vista en la clase de multiplicación de matrices: dada una matriz cuadrada `A`, si existe su inversa `A⁻¹`, cumple `A · A⁻¹ = A⁻¹ · A = I` (donde `I` es la matriz identidad del mismo orden).
- **"UNA MATRIZ TIENE INVERSA SI ES REGULAR":** condición necesaria y suficiente de invertibilidad (`∃ A⁻¹ ⇔ A es cuadrada y |A| ≠ 0`).

**💡 Ejemplo:**
- **Ejemplo 4 del material (Pág. 11):**
  Dada `A = [ 1  2  3 ; 4  5  6 ; 5  7  8 ]`, antes de buscar `A⁻¹` calculamos `|A|`.
  Por Sarrus: `|A| = (1·5·8 + 4·7·3 + 5·2·6) - (3·5·5 + 6·7·1 + 8·2·4) = (40 + 84 + 60) - (75 + 42 + 64) = 184 - 181 = 3`.
  Como `|A| = 3 ≠ 0`, la matriz `A` es **regular**, por lo tanto **existe su inversa `A⁻¹`**.

**🔗 Conexiones:**
- Conecta el concepto de **Determinante (8.2)** y **Matriz Regular (8.12)** con el **Producto de matrices (Clase 6)** y la resolución de **Sistemas de Ecuaciones Lineales por método matricial (Unidad 3)**.

**⚠️ Precisiones / errores comunes:**
- **Pregunta clásica de Verdadero o Falso (DF 8b, Pág. 17):** *"La inversa de una matriz `m × n` es una matriz `m × n`"*. **FALSO**, porque las matrices rectangulares con `m ≠ n` **no tienen inversa**; solo las matrices cuadradas (`n × n`) que además sean regulares (`|A| ≠ 0`) tienen inversa (y su inversa es del mismo orden `n × n`).

**🎤 Cómo decirlo en el oral:**
> "Las únicas matrices que pueden tener inversa son las matrices cuadradas, y podemos asegurar que una matriz cuadrada tiene inversa si y solo si es **regular** (o no singular), es decir, si su determinante es distinto de cero (`|A| ≠ 0`). Si el determinante es igual a cero, la matriz inversa no existe."

---

## 8.15 Método de Cálculo de la Matriz Inversa por Operaciones Elementales (o Gauss-Jordan) y Verificación

> 📖 **Textual del material:**
> "Veremos un método para calcular la inversa de una matriz:
> **Por operaciones elementales.** Con la matriz cuadrada a la que le queremos calcular la inversa y con la matriz identidad de orden adecuado, formamos una matriz rectangular.
> Luego aplicamos a esta matriz rectangular operaciones elementales (o el método de Gauss-Jordan) hasta obtener una matriz canónica. Volvemos a pensar a la matriz rectangular como dos matrices cuadradas, una va a ser la Identidad, la otra (a la derecha) la inversa buscada.
>
> **Puede usarse el método de Gauss-Jordan para calcular la inversa de una matriz.**"
>
> "Primero calculamos el determinante (si es distinto de cero sabemos que tiene inversa. Si es igual a cero la inversa no existe y no se continúa el ejercicio)."
>
> "Formamos la matriz rectangular con A y la Identidad de orden 3: [1]
> [ A : I ] (Matriz rectangular que se forma con A y la identidad)
> A esta le aplicamos las operaciones elementales (o Gauss-Jordan) hasta llegar a canónica:"
>
> "Llegamos a la canónica. A la izquierda de la línea de puntos está la Identidad, a la derecha la inversa de A."
>
> "Podemos verificar que el resultado es correcto haciendo A . A⁻¹, este producto debe dar la Identidad:"

**🗣️ En palabras simples:**
Una vez que comprobaste que `|A| ≠ 0` (es regular), el procedimiento para hallar `A⁻¹` consta de estos pasos:
1. **Armar la matriz rectangular `[ A : I ]`:** ponés a la izquierda tu matriz cuadrada `A` (de orden `n × n`), trazás una línea vertical punteada, y a la derecha pegás la **Matriz Identidad `I`** del mismo orden `n × n`. Te queda una matriz rectangular de `n` filas y `2n` columnas (`n × 2n`).
2. **Aplicar operaciones elementales por fila (o el método de Gauss-Jordan) a toda la fila completa:** vas eligiendo los pivotes de la diagonal principal de la izquierda para convertirlos en `1` y anular todos los demás elementos de su columna (arriba y abajo), aplicando cada operación a los `2n` elementos de la fila (tanto del lado izquierdo como del lado derecho).
3. **Llegar a la matriz canónica `[ I : A⁻¹ ]`:** cuando del lado izquierdo de la línea de puntos lograste formar la **Matriz Identidad `I`**, la matriz cuadrada que quedó formada a la derecha de la línea de puntos es exactamente la **matriz inversa `A⁻¹`**.
4. **Verificación:** para estar 100% seguro de que no hubo errores de cuentas, multiplicás la matriz original `A` por la inversa obtenida `A⁻¹`, y el producto **`A · A⁻¹` debe dar la Matriz Identidad `I`**.

**🔍 Desglose de la jerga:**
- **"Matriz identidad de orden adecuado":** si `A` es de orden `2 × 2`, se usa `I₂ = [ 1  0 ; 0  1 ]`; si `A` es de orden `3 × 3`, se usa `I₃ = [ 1  0  0 ; 0  1  0 ; 0  0  1 ]`; en general, si `A` es de orden `n`, se usa `Iₙ`.
- **"Formamos una matriz rectangular `[ A : I ]`":** al yuxtaponer dos matrices cuadradas de `n × n`, se obtiene una matriz de `n` filas por `2n` columnas (que no es cuadrada, sino rectangular).
- **"Hasta obtener una matriz canónica":** recordemos de la Clase 7 que llevar una matriz a su forma canónica mediante Gauss-Jordan consiste en obtener vectores canónicos (columnas con un `1` como pivote y `0` en el resto). Como `A` es regular de orden `n`, sus `n` columnas se transforman en las `n` columnas de la matriz identidad `I`.
- **Diferencia importantísima entre usar operaciones elementales para determinantes vs. para la inversa:**
  - En **determinantes (Chío)**, las operaciones `Hᵢ,ⱼ` y `Hᵢ(k)` alteraban el valor del determinante y había que compensarlas al final con las Propiedades 1 y 2.
  - En el **cálculo de la inversa (`[ A : I ] ~ [ I : A⁻¹ ]`)**, **podés usar libremente las 3 operaciones elementales (`Hᵢ,ⱼ`, `Hᵢ(k)` y `Hᵢ,ⱼ(k)`) sin hacer ninguna compensación al final**, porque todo lo que le hacés a `A` del lado izquierdo queda automáticamente registrado en la transformación de `I` del lado derecho.

**💡 Ejemplo:**
- **Ejemplo Nº 4 del material (Págs. 11–12):**
  Hallar `A⁻¹` para `A = [ 1  2  3 ; 4  5  6 ; 5  7  8 ]`.
  1. **Existencia:** `|A| = 3 ≠ 0` ⇒ `A` es regular, existe `A⁻¹`.
  2. **Armado de la matriz rectangular `[ A : I ]` (de orden `3 × 6`):**
     ```
     [ 1   2   3  :  1   0   0 ]
     [ 4   5   6  :  0   1   0 ]
     [ 5   7   8  :  0   0   1 ]
     ```
  3. **Aplicación de operaciones elementales (Gauss-Jordan):**
     - `H₂,₁(-4)` y `H₃,₁(-5)` (anulan debajo del primer `1` en columna 1):
       ```
       [ 1    2    3  :   1   0   0 ]
       [ 0   -3   -6  :  -4   1   0 ]
       [ 0   -3   -7  :  -5   0   1 ]
       ```
     - `H₂(-1/3)` (convierte en `1` el pivote de la fila 2, columna 2):
       ```
       [ 1    2    3  :    1     0    0 ]
       [ 0    1    2  :   4/3  -1/3   0 ]
       [ 0   -3   -7  :   -5     0    1 ]
       ```
     - `H₁,₂(-2)` y `H₃,₂(3)` (anulan arriba y abajo del pivote de columna 2):
       ```
       [ 1    0   -1  :  -5/3   2/3   0 ]
       [ 0    1    2  :   4/3  -1/3   0 ]
       [ 0    0   -1  :   -1    -1    1 ]
       ```
     - `H₃(-1)` (convierte en `1` el pivote de la fila 3, columna 3):
       ```
       [ 1    0   -1  :  -5/3   2/3   0 ]
       [ 0    1    2  :   4/3  -1/3   0 ]
       [ 0    0    1  :    1     1   -1 ]
       ```
     - `H₁,₃(1)` y `H₂,₃(-2)` (anulan arriba del pivote de columna 3):
       ```
       [ 1    0    0  :  -2/3   5/3  -1 ]
       [ 0    1    0  :  -2/3  -7/3   2 ]
       [ 0    0    1  :    1     1   -1 ]
       ```
  4. **Lectura del resultado:** A la izquierda quedó `I`, por lo tanto a la derecha está `A⁻¹`:
     ```
            [ -2/3    5/3   -1 ]
     A⁻¹ =  [ -2/3   -7/3    2 ]
            [   1      1    -1 ]
     ```
  5. **Verificación (`A · A⁻¹ = I`):**
     ```
     [ 1  2  3 ]   [ -2/3   5/3  -1 ]   [ 1  0  0 ]
     [ 4  5  6 ] · [ -2/3  -7/3   2 ] = [ 0  1  0 ]
     [ 5  7  8 ]   [   1     1   -1 ]   [ 0  0  1 ]
     ```
     *(Nota sobre pequeñas erratas de imprenta en Pág. 12 del PDF: en el primer dibujo arriba de todo copiaron `[A : A]` en vez de `[A : I]`, en la tercera matriz escribieron `0 0 -1` en lugar de `-5 0 1` aunque en la cuarta matriz ya pusieron el resultado correcto `-1 -1 1`, y debajo de la matriz final pusieron la etiqueta `[A : I]` donde ya se había llegado a `[I : A⁻¹]`).*

**🧩 Por qué funciona el método e 🤔 Intuición:**
- **🤔 Intuición:** Buscar `A⁻¹` equivale a resolver simultáneamente el sistema matricial `A · X = I`. Al aplicar operaciones elementales por fila que transforman a `A` en la matriz identidad `I`, estamos multiplicando implícitamente a izquierda por `A⁻¹`: lo que transforma a `A` en `A⁻¹ · A = I` transforma simultáneamente a `I` (del lado derecho) en `A⁻¹ · I = A⁻¹`.

**🔗 Conexiones:**
- Utiliza la **equivalencia por filas y el método de Gauss-Jordan** de la **Clase 7**.
- Se conecta con la **pregunta `b` del DF 4 (Pág. 16)**: *"¿Qué puedes decir sobre dos matrices, si sabes que multiplicadas dan la matriz identidad?"* → Que una es la **matriz inversa** de la otra (`B = A⁻¹` y `A = B⁻¹`), y que ambas son matrices cuadradas regulares del mismo orden.

**⚠️ Precisiones / errores comunes:**
- **La Identidad siempre va a la izquierda al final (`[ I : A⁻¹ ]`):** al empezar, se arma `[ A : I ]` (`A` a la izquierda, `I` a la derecha). Al terminar, `I` debe quedar **a la izquierda** (con su diagonal principal de unos de arriba a la izquierda hacia abajo a la derecha), y a la derecha queda `A⁻¹`.

**🎤 Cómo decirlo en el oral:**
> "Para calcular la inversa de una matriz cuadrada por operaciones elementales, primero calculamos su determinante para verificar que sea distinto de cero (que sea regular). Luego, con la matriz cuadrada `A` y la matriz identidad `I` del mismo orden, formamos una matriz rectangular `[ A : I ]`. Aplicamos a esta matriz rectangular operaciones elementales por fila (o el método de Gauss-Jordan) hasta llegar a una matriz canónica donde la submatriz de la izquierda sea la Identidad `I`. Entonces, la matriz cuadrada que queda a la derecha de la línea de puntos es la matriz inversa `A⁻¹`. Finalmente, podemos verificar el resultado comprobando que `A · A⁻¹ = I`."

---

## 8.16 Cuestionario Oficial Resuelto (Desempeño 56 y Desempeños Finales)

En la página 14 del material aparece el **Desempeño 56**, cuyas 15 preguntas resumen exactamente lo que la cátedra exige dominar en la teoría de la Clase 8 (y en la página 15 indica: *"Respuesta al desempeño 56: Las respuestas, las encontraras en la clase n° 8!"*). Aquí tenés las **15 respuestas oficiales exactas** con la jerga literal del material, seguidas de las preguntas conceptuales de los **Desempeños Finales (Págs. 16–17)**:

### Respuestas al Desempeño 56 (Pág. 14)

- **a- ¿Qué es el determinante de una matriz?**
  Se llama **determinante** de una matriz cuadrada de orden `n` **al número** que se obtiene al sumar algebraicamente (adición y/o sustracción) todos los productos posibles entre `n` elementos de la matriz que pertenezcan a distinta fila y columna.
- **b- ¿A qué tipo de matrices se le puede calcular el determinante?**
  **Solamente a las matrices cuadradas** (aquellas cuyo número de filas y columnas es el mismo).
- **c- ¿Cómo se calcula el determinante de matrices de orden 2?**
  Multiplicando entre sí los elementos de la diagonal principal y restándole el producto de los elementos de la diagonal secundaria (`|A| = a₁₁ · a₂₂ - a₁₂ · a₂₁`). *(También puede calcularse mediante el método general de la Regla de Chío).*
- **d- ¿Cómo se calcula el determinante de matrices de orden 3?**
  Por el método particular llamado **Regla de Sarrus** (en cualquiera de sus dos formas: repitiendo las dos primeras filas debajo de la tercera y restando a la suma de los productos de la diagonal principal y sus paralelas la suma de los productos de la diagonal secundaria y sus paralelas; o mediante las diagonales y las paralelas con los vértices opuestos), o bien por el método general (**Regla de Chío**).
- **e- ¿Cómo se calcula el determinante de matrices de orden n?**
  Mediante el método general llamado **Regla de Chío** (aplicando operaciones elementales por fila para lograr que una columna tenga todos sus elementos nulos excepto uno, multiplicando el elemento no nulo por `(-1)ⁱ⁺ʲ` y por el determinante de orden `n - 1` que surge al sacar la fila y columna de dicho elemento, y aplicando las propiedades 1, 2 o 3 según las operaciones usadas si es necesario).
- **f- ¿El método utilizado en el cálculo de un determinante, varía su resultado?**
  **No.** El determinante de una matriz cuadrada es un único número; cualquiera sea el método válido que se utilice para calcularlo (métodos particulares como orden 2 o Sarrus en orden 3, Regla de Chío eligiendo cualquier columna, o propiedades), el resultado es siempre el mismo.
- **g- ¿Cuál será el determinante de matriz identidad?**
  El determinante de la matriz identidad `I` (de cualquier orden `n`) es siempre igual a **`1`** (`|I| = 1`), ya que todos los elementos fuera de la diagonal principal son ceros y el único producto no nulo de elementos de distinta fila y columna es el de la diagonal principal: `1 · 1 · ... · 1 = 1`.
- **h- ¿A qué se llama matriz regular?**
  Si una matriz cuadrada tiene el **determinante no nulo** (`|A| ≠ 0`), se dice que la matriz es **regular** (o **no singular**).
- **i- ¿Qué se debe tener en cuenta al momento de aplicar la regla de Chío a una matriz para calcular su determinante?**
  Se deben tener en cuenta tres cosas fundamentales:
  1. Que la matriz sea **cuadrada**.
  2. Al multiplicar los tres factores del segundo paso, no olvidar el signo de posición **`(-1)ⁱ⁺ʲ`** correspondiente a la fila `i` y columna `j` del elemento no nulo elegido.
  3. En el tercer paso, **tener en cuenta qué operaciones elementales se utilizaron** para lograr los ceros y aplicar las **propiedades 1, 2 o 3** si es necesario (si se intercambió filas con `Hᵢ,ⱼ`, cambia el signo; si se multiplicó una fila por `k` con `Hᵢ(k)`, el determinante quedó multiplicado por `k`; si solo se usó `Hᵢ,ⱼ(k)`, el determinante no varía).
- **j- ¿Cuándo una matriz tiene inversa?**
  Una matriz tiene inversa cuando es **cuadrada** y es **regular** (es decir, cuando tiene **determinante no nulo**, `|A| ≠ 0`). En palabras textuales del material: **"UNA MATRIZ TIENE INVERSA SI ES REGULAR"**.
- **k- ¿Cómo se puede calcular la inversa de una matriz?**
  **Por operaciones elementales (o mediante el método de Gauss-Jordan):** se forma una matriz rectangular `[ A : I ]` con la matriz cuadrada `A` y la matriz identidad `I` del mismo orden, y se le aplican operaciones elementales por fila hasta obtener una matriz canónica donde a la izquierda quede la Identidad `I` y a la derecha quede la matriz inversa buscada `A⁻¹` (`[ I : A⁻¹ ]`). *(El material también menciona en las Claves de Estudio que puede calcularse mediante la matriz adjunta).*
- **l- ¿Para qué se utiliza aplicar las operaciones elementales a una matriz?**
  En el contexto de la Unidad 2, aplicar operaciones elementales por fila a una matriz se utiliza para:
  1. Obtener **matrices equivalentes** y llevar una matriz a su **forma escalonada o canónica** (Gauss / Gauss-Jordan).
  2. Determinar el **rango** de una matriz (Clase 7).
  3. Anular todos los elementos de una columna excepto uno para calcular determinantes mediante la **Regla de Chío** (Clase 8).
  4. Transformar la matriz rectangular `[ A : I ]` en `[ I : A⁻¹ ]` para hallar la **matriz inversa** (Clase 8).
- **m- ¿Cómo se calcula el determinante de una matriz de orden 6?**
  Primero se observa si cumple alguna de las **propiedades de cuándo un determinante vale cero** (línea nula, dos líneas paralelas iguales o dos líneas paralelas proporcionales, como ocurre en el Desempeño 51b). Si no se anula por propiedad, se aplica sucesivamente el método general (**Regla de Chío**): con la primera aplicación se reduce de orden 6 a un determinante de orden 5; luego a uno de orden 4; y luego a uno de orden 3 (que se termina de resolver por Regla de Sarrus o nuevamente por Regla de Chío).
- **n- ¿En qué casos el determinante de una matriz da cero?**
  Según el segundo bloque de propiedades (Propiedades 4º, 5º y 6º), el determinante de una matriz cuadrada es nulo cuando:
  1. **4º Propiedad:** Todos los elementos de una línea (fila o columna) son nulos.
  2. **5º Propiedad:** La matriz tiene dos líneas paralelas iguales.
  3. **6º Propiedad:** La matriz tiene dos líneas paralelas proporcionales (una línea es la otra multiplicada por un cierto número).
  *(Contexto adicional de conexión con Clase 7: en general, cuando una línea es combinación lineal de otras líneas paralelas, es decir, cuando el rango de la matriz es menor que su orden `n`).*
- **o- ¿Cuál es la operación elemental por fila que no modifica el valor del determinante?**
  La **tercera operación elemental por fila, `Hᵢ,ⱼ(k)`** (con `k ≠ 0`), que consiste en **sumarle a una fila de una matriz otra fila previamente multiplicada por una constante distinta de cero** (3º Propiedad: `Si A ~ B mediante Hᵢ,ⱼ(k) → |A| = |B|`).

---

### Preguntas Conceptuales de los Desempeños Finales de la Unidad 2 (Págs. 16–17)

- **DF 4a- ¿Qué puedes decir sobre dos matrices, si sabes que sumadas dan la matriz nula?**
  Que son matrices del **mismo orden** (`m × n`) y que una es la **matriz opuesta** de la otra (`B = -A`), es decir, sus elementos homólogos (en la misma posición `i, j`) son números opuestos (`bᵢⱼ = -aᵢⱼ`).
- **DF 4b- ¿Qué puedes decir sobre dos matrices, si sabes que multiplicadas dan la matriz identidad?**
  Que ambas son **matrices cuadradas del mismo orden `n`**, ambas son **regulares** (tienen determinante no nulo), y una es la **matriz inversa** de la otra (`B = A⁻¹` y `A = B⁻¹`).
- **DF 4c- ¿Qué operación representa `#` si sabes que la siguiente igualdad entre matrices es válida: `A # B = B # A`?**
  Representa la **Adición (suma) de matrices** (`A + B = B + A`), ya que la adición de matrices cumple la propiedad **conmutativa**, mientras que la multiplicación de matrices en general **no es conmutativa** (`A · B ≠ B · A`).
- **DF 5- Cuadro comparativo de operaciones entre matrices:**

| Operaciones | ¿Cuándo puede realizarse? | ¿Cuál es el orden del resultado? |
| :--- | :--- | :--- |
| **Adición** (`A + B`) | Cuando las matrices tienen el **mismo orden** (`A` de `m × n` y `B` de `m × n`). | El **mismo orden** que las matrices sumadas (`m × n`). |
| **Producto por número** (`k · A`) | **Siempre** (para cualquier matriz `A` de orden `m × n` y cualquier número real `k`). | El **mismo orden** de la matriz original (`m × n`). |
| **Producto entre matrices** (`A · B`) | Cuando son **conformables**: el número de **columnas de la primera matriz (`A`)** es igual al número de **filas de la segunda matriz (`B`)** (`A` de `m × p` y `B` de `p × n`). | Tiene tantas filas como la primera matriz y tantas columnas como la segunda (**`m × n`**). |

- **DF 8- Verdadero o Falso con justificación teórica (Pág. 17):**
  - **a- "Si dos matrices pueden multiplicarse y sumarse, podemos asegurar que son cuadradas." → VERDADERO.**
    *Justificación:* Para que `A` (de orden `m × n`) y `B` (de orden `p × q`) puedan **sumarse**, deben tener el mismo orden, es decir, `m = p` y `n = q` (ambas son `m × n`). Y para que además puedan **multiplicarse** (`A · B`), el número de columnas de `A` (`n`) debe ser igual al número de filas de `B` (`m`), de modo que `n = m`. Por lo tanto, ambas matrices tienen igual número de filas que de columnas (`n × n`), es decir, **son cuadradas** (y del mismo orden).
  - **b- "La inversa de una matriz `m × n` es una matriz `m × n`." → FALSO.**
    *Justificación:* La inversa de una matriz se define **solamente para matrices cuadradas** (`m = n`) que además sean **regulares** (`|A| ≠ 0`). Si `m ≠ n`, la matriz no es cuadrada y no tiene inversa; e incluso si `m = n`, si su determinante es nulo (`|A| = 0`), tampoco tiene inversa.
  - **c- "Si dos matrices son conformables entonces se pueden sumar." → FALSO.**
    *Justificación:* Dos matrices `A` y `B` son conformables (para el producto `A · B`) cuando el número de columnas de `A` coincide con el número de filas de `B` (por ejemplo, `A` de orden `2 × 3` y `B` de orden `3 × 4`). Sin embargo, para poder sumarse deben tener exactamente el mismo orden (misma cantidad de filas y misma cantidad de columnas), lo cual no se cumple en general entre matrices conformables.
  - **d- "Tanto en la Adición como en la Multiplicación de matrices se cumplen las propiedades asociativa y conmutativa." → FALSO.**
    *Justificación:* La propiedad **asociativa** se cumple tanto en la adición como en la multiplicación de matrices, pero la propiedad **conmutativa** sólo se cumple en la **adición** (`A + B = B + A`); la multiplicación de matrices **no es conmutativa** en general (`A · B ≠ B · A`).
  - **e- "A una matriz se le puede calcular el determinante o no, según la cantidad de elementos que tenga." → FALSO.**
    *Justificación:* Que a una matriz se le pueda calcular el determinante depende de que sea **cuadrada** (igual número de filas que de columnas, `m = n`), y no simplemente de la cantidad total de elementos que tenga. Por ejemplo, una matriz de 4 elementos puede ser de orden `2 × 2` (es cuadrada y tiene determinante) o de orden `1 × 4` o `4 × 1` (tiene la misma cantidad de elementos, 4, pero no es cuadrada y **no** tiene determinante); o una matriz de 9 elementos puede ser de `3 × 3` (tiene determinante) o de `1 × 9` (no tiene determinante).

---

## 🧠 Resumen esquemático de la clase

- **Dominio obligatorio:** Determinante e Inversa se definen **solamente para matrices cuadradas** (orden `n × n`).
- **Determinante (`|A|`):** Es **el número** que se obtiene al sumar algebraicamente (adición y/o sustracción) todos los productos posibles entre `n` elementos de la matriz que pertenezcan a distinta fila y columna.
- **Diferencia Matriz vs. Determinante:** La matriz `A` es un conjunto de números; el determinante `|A|` es un único número y se simboliza entre barras verticales.
- **Método particular — Orden 2:** Producto de la diagonal principal menos producto de la diagonal secundaria: `|A| = a₁₁ · a₂₂ - a₁₂ · a₂₁`.
- **Método particular — Orden 3 (Regla de Sarrus):** Suma de los 3 productos de la diagonal principal y sus paralelas menos la suma de los 3 productos de la diagonal secundaria y sus paralelas (ya sea repitiendo las dos primeras filas debajo, o usando paralelas con vértices opuestos).
- **1º Propiedad (intercambio de filas `Hᵢ,ⱼ`):** Si se intercambian entre sí dos filas, el determinante cambia de signo pero no de valor absoluto (`|A| = -|B|`).
- **2º Propiedad (fila por escalar `Hᵢ(k)`, `k ≠ 0`):** Si se multiplican los elementos de una fila por un número distinto de cero, el determinante queda multiplicado por ese número (`|B| = k · |A|`).
- **3º Propiedad (suma de múltiplo de otra fila `Hᵢ,ⱼ(k)`, `k ≠ 0`):** Si a una fila se le suma otra previamente multiplicada por una constante distinta de cero, el determinante **no varía** (`|A| = |B|`).
- **Columna de control:** Se obtiene sumando los elementos de cada fila; se le aplican las mismas operaciones elementales que a las filas para verificar paso a paso que la suma de la fila coincida con el elemento de control.
- **4º Propiedad (línea nula):** Si todos los elementos de una línea (fila o columna) son nulos, el determinante es nulo (`|A| = 0`).
- **5º Propiedad (líneas paralelas iguales):** Si una matriz tiene dos líneas paralelas iguales, su determinante es nulo (`|A| = 0`).
- **6º Propiedad (líneas paralelas proporcionales):** Si dos líneas paralelas son proporcionales (una es la otra multiplicada por un cierto número), el determinante es nulo (`|A| = 0`).
- **Matriz Regular o No Singular:** Es toda matriz cuadrada que tiene el **determinante no nulo** (`|A| ≠ 0`).
- **Método General — Regla de Chío (cualquier orden `n`):** (1) Aplicar operaciones elementales hasta que una columna tenga todos sus elementos nulos excepto uno (`aᵢⱼ`); (2) Multiplicar los 3 factores: `aᵢⱼ · (-1)ⁱ⁺ʲ · (determinante de orden n-1 al sacar fila i y columna j)`; (3) Aplicar las propiedades 1, 2 o 3 según las operaciones usadas si es necesario.
- **Existencia de la Matriz Inversa (`A⁻¹`):** **Una matriz tiene inversa si es regular** (cuadrada y con `|A| ≠ 0`).
- **Cálculo de la Inversa por operaciones elementales (Gauss-Jordan):** Armar la matriz rectangular `[ A : I ]`, aplicar operaciones elementales por fila hasta llegar a la canónica `[ I : A⁻¹ ]` (Identidad a la izquierda, inversa `A⁻¹` a la derecha) y verificar que `A · A⁻¹ = I`.

---

## ❓ Preguntas probables del oral

1. **Profesor: "Defina exactamente qué es el determinante de una matriz."**
   - **Respuesta:** "Se llama **determinante** de una matriz cuadrada de orden `n` **al número** que se obtiene al sumar algebraicamente (es decir, mediante adición y/o sustracción) todos los productos posibles entre `n` elementos de la matriz que pertenezcan a distinta fila y columna."

2. **Profesor: "¿Qué diferencia hay entre una matriz y un determinante, y cómo se los simboliza?"**
   - **Respuesta:** "Una matriz es un conjunto ordenado de números dispuestos en filas y columnas (simbolizado con corchetes o paréntesis), mientras que el determinante **es un número** que sólo se calcula a matrices cuadradas, y por eso lo simbolizamos encerrando el nombre o los elementos de la matriz entre **barras verticales**, `|A|`. Si la matriz es de orden `n`, lo llamamos determinante de enésimo orden."

3. **Profesor: "¿Cuáles son los métodos particulares para calcular determinantes y por qué se llaman particulares?"**
   - **Respuesta:** "Se llaman métodos particulares porque sirven únicamente para un orden específico:
     - El primero es para **matrices cuadradas de orden 2 solamente**: se multiplica entre sí los elementos de la diagonal principal y se le resta el producto de los elementos de la diagonal secundaria (`|A| = a₁₁ · a₂₂ - a₁₂ · a₂₁`).
     - El segundo es la **Regla de Sarrus**, que sirve para **matrices de orden 3 solamente**: consiste en repetir las dos primeras filas debajo de la tercera (o usar el esquema de paralelas con vértices opuestos) y restarle a la suma de los tres productos de la diagonal principal y sus paralelas la suma de los tres productos de la diagonal secundaria y sus paralelas."

4. **Profesor: "¿Cómo se clasifican las propiedades de los determinantes? Enuncie las tres propiedades referidas a las operaciones elementales."**
   - **Respuesta:** "Las propiedades se agrupan en dos bloques: las **referidas a operaciones elementales** y las de **cuándo un determinante vale cero**.
     Las tres referidas a las operaciones elementales son:
     - **1º Propiedad (`Hᵢ,ⱼ`):** *'Si se intercambian entre sí, dos filas, el determinante cambia de signo pero no de valor absoluto'*. En símbolos: si `A ~ B` por `Hᵢ,ⱼ`, entonces `|A| = -|B|`.
     - **2º Propiedad (`Hᵢ(k)`):** *'Si se multiplican los elementos de una fila por un número distinto de cero, el determinante queda multiplicado por ese número'*. En símbolos: si `A ~ B` por `Hᵢ(k)`, entonces `|B| = k · |A|`.
     - **3º Propiedad (`Hᵢ,ⱼ(k)`):** *'Si a una fila de una matriz se le suma otra previamente multiplicada por una constante distinta de cero, el determinante no varía'*. En símbolos: si `A ~ B` por `Hᵢ,ⱼ(k)`, entonces `|A| = |B|`."

5. **Profesor: "Enuncie las tres propiedades de cuándo un determinante vale cero y defina cuándo dos líneas son proporcionales."**
   - **Respuesta:**
     - **4º Propiedad:** *'Si todos los elementos de una línea (fila o columna) son nulos, el determinante de la matriz es nulo'*.
     - **5º Propiedad:** *'Si una matriz tiene dos líneas paralelas iguales, su determinante es nulo'*.
     - **6º Propiedad:** *'Si dos líneas paralelas son proporcionales, el determinante es nulo'*.
     Y según la referencia del material, **dos líneas son proporcionales cuando una de ellas es la otra multiplicada por un cierto número** (es decir, cuando una línea es múltiplo escalar de otra línea paralela)."

6. **Profesor: "¿Por qué en la 5º y 6º propiedad se exige que las dos líneas sean 'paralelas'? ¿Qué significa 'líneas' y qué significa 'paralelas'?"**
   - **Respuesta:** "La palabra **'línea'** se refiere tanto a una fila como a una columna. Y **'paralelas'** significa que deben ser **dos filas entre sí** o **dos columnas entre sí**. No alcanza con que una fila sea igual o proporcional a una columna, porque una fila y una columna no son paralelas y en ese caso el determinante no tiene por qué anularse."

7. **Profesor: "¿Cuándo se dice que una matriz es regular o no singular?"**
   - **Respuesta:** "Textualmente: *'Si una matriz tiene el determinante no nulo se dice que la matriz es REGULAR o NO SINGULAR'* (`|A| ≠ 0`)."

8. **Profesor: "Explique paso a paso el método general para calcular determinantes (Regla de Chío)."**
   - **Respuesta:** "La **Regla de Chío** permite calcular el determinante a matrices cuadradas de cualquier orden (inclusive de orden 2 y 3) y consta de tres pasos:
     1. **Primer paso:** Aplicamos operaciones elementales por fila en la matriz hasta lograr que una columna cualquiera tenga todos sus elementos nulos excepto uno.
     2. **Segundo paso:** Realizamos la multiplicación de tres factores:
        - El elemento no nulo de la columna elegida.
        - El factor `(-1)ⁱ⁺ʲ`, donde `i, j` corresponden a la posición (fila y columna) del elemento no nulo elegido.
        - El determinante de la matriz de orden `n - 1` que surge al sacar la fila y la columna del elemento elegido en el primer paso.
     3. **Tercer paso:** Aplicamos las propiedades correspondientes (1, 2 o 3) según las operaciones elementales usadas para lograr los ceros, si es necesario."

9. **Profesor: "Si aplico a una matriz `A` de determinante `|A| = 4` un intercambio de filas `H₂,₃`, luego multiplico la fila 1 por 3 con `H₁(3)`, y luego le sumo a la fila 2 cinco veces la fila 3 con `H₂,₃(5)` llegando a una matriz `B`, ¿cuánto vale `|B|`?"**
   - **Respuesta:** "Partimos de `|A| = 4`:
     - Al aplicar `H₂,₃`, por la **1º Propiedad** el determinante cambia de signo: pasa a valer `-4`.
     - Al aplicar `H₁(3)`, por la **2º Propiedad** el determinante queda multiplicado por `3`: pasa a valer `-4 · 3 = -12`.
     - Al aplicar `H₂,₃(5)`, por la **3º Propiedad** el determinante no varía: sigue valiendo `-12`.
     Por lo tanto, `|B| = -12`."

10. **Profesor: "¿Cuándo una matriz tiene inversa y cómo se calcula por operaciones elementales?"**
    - **Respuesta:** "Las únicas matrices que pueden tener inversa son las matrices cuadradas, y una matriz cuadrada **tiene inversa si es regular** (es decir, si su determinante es no nulo, `|A| ≠ 0`).
      Para calcularla por operaciones elementales:
      1. Primero calculamos `|A|` para asegurarnos de que sea distinto de cero (si es cero, la inversa no existe y no se continúa).
      2. Con la matriz cuadrada `A` y la matriz identidad `I` de orden adecuado, formamos una matriz rectangular `[ A : I ]`.
      3. Aplicamos a esta matriz rectangular operaciones elementales por fila (o el método de Gauss-Jordan) hasta obtener una matriz canónica.
      4. Volvemos a pensar a la matriz rectangular como dos matrices cuadradas: a la izquierda de la línea de puntos queda la Identidad `I`, y a la derecha queda la inversa buscada `A⁻¹` (`[ I : A⁻¹ ]`).
      5. Finalmente, podemos verificar el resultado comprobando que el producto `A · A⁻¹` da la matriz Identidad `I`."

11. **Profesor: "¿Qué es y cómo funciona la columna de control al aplicar operaciones elementales por fila?"**
    - **Respuesta:** "La columna de control se obtiene sumando los elementos de cada fila de la matriz original. Luego se trabaja como si fuese una columna más de la matriz, aplicándole las mismas operaciones elementales propias de cada fila. Para corroborar en cada paso si se aplicó bien la operación por fila, la suma de los elementos de cada fila debe seguir dando igual al elemento correspondiente de la columna de control."

12. **Profesor: "Dada una matriz `A` de orden `5 × 6` cuya última columna tiene todos sus elementos iguales a cero, ¿su determinante vale cero por la 4º Propiedad?"**
    - **Respuesta:** "**No, es una trampa:** su determinante **no existe** (y no vale cero), porque una matriz de orden `5 × 6` no es cuadrada, y el determinante se define solamente para matrices cuadradas. Antes de aplicar cualquier propiedad de determinantes, siempre hay que verificar que la matriz sea cuadrada."

---

## 📚 Glosario de la clase

| Término | Definición breve fiel al material |
| :--- | :--- |
| **Determinante de una matriz cuadrada de orden `n`** | Número que se obtiene al sumar algebraicamente todos los productos posibles entre `n` elementos de la matriz que pertenezcan a distinta fila y columna. Se simboliza `\|A\|`. |
| **Determinante de enésimo orden** | Nombre que recibe el determinante de una matriz cuadrada de orden `n`. |
| **Suma algebraica** | Expresión que indica adición y/o sustracción de términos. |
| **Método particular para orden 2** | Cálculo del determinante de una matriz cuadrada de orden 2 multiplicando entre sí los elementos de la diagonal principal y restándole el producto de los elementos de la diagonal secundaria (`\|A\| = a₁₁ · a₂₂ - a₁₂ · a₂₁`). |
| **Regla de Sarrus** | Método particular para calcular el determinante de una matriz de orden 3 solamente, sumando los productos de la diagonal principal y sus paralelas y restándole los productos de la diagonal secundaria y sus paralelas (repitiendo las dos primeras filas o usando paralelas con los vértices opuestos). |
| **1º Propiedad de los determinantes** | *"Si se intercambian entre sí, dos filas, el determinante cambia de signo pero no de valor absoluto"* (`Si A ~ B mediante Hᵢ,ⱼ → \|A\| = -\|B\|`). |
| **2º Propiedad de los determinantes** | *"Si se multiplican los elementos de una fila por un número distinto de cero, el determinante queda multiplicado por ese número"* (`Si A ~ B mediante Hᵢ(k) → \|B\| = k · \|A\|`). |
| **3º Propiedad de los determinantes** | *"Si a una fila de una matriz se le suma otra previamente multiplicada por una constante distinta de cero, el determinante no varía"* (`Si A ~ B mediante Hᵢ,ⱼ(k) → \|A\| = \|B\|`). |
| **Columna de control** | Columna auxiliar que se obtiene sumando los elementos de cada fila de la matriz y a la que se aplican las mismas operaciones elementales de cada fila para corroborar paso a paso la exactitud de los cálculos. |
| **Línea de una matriz** | Término general que designa indistintamente a una fila o a una columna de la matriz. |
| **Líneas paralelas** | Dos o más filas entre sí, o dos o más columnas entre sí. |
| **Líneas proporcionales** | Dos líneas tales que una de ellas es la otra multiplicada por un cierto número (múltiplo escalar). |
| **4º Propiedad de los determinantes** | *"Si todos los elementos de una línea (fila o columna) son nulos, el determinante de la matriz es nulo"*. |
| **5º Propiedad de los determinantes** | *"Si una matriz tiene dos líneas paralelas iguales, su determinante es nulo"*. |
| **6º Propiedad de los determinantes** | *"Si dos líneas paralelas son proporcionales, el determinante es nulo"*. |
| **Matriz Regular o No Singular** | Matriz cuadrada cuyo determinante es no nulo (`\|A\| ≠ 0`). Tiene matriz inversa. |
| **Regla de Chío** | Método general para calcular el determinante de matrices cuadradas de cualquier orden: (1) anular con operaciones elementales todos los elementos de una columna excepto uno (`aᵢⱼ`), (2) multiplicar `aᵢⱼ · (-1)ⁱ⁺ʲ · (determinante al sacar fila i y columna j)`, y (3) aplicar las propiedades 1, 2 o 3 según las operaciones usadas si es necesario. |
| **Condición de existencia de la matriz inversa** | *"Una matriz tiene inversa si es regular"* (debe ser cuadrada y tener determinante distinto de cero, `\|A\| ≠ 0`). |
| **Cálculo de la inversa por operaciones elementales (o Gauss-Jordan)** | Método que forma la matriz rectangular `[ A : I ]` con `A` y la Identidad `I` de igual orden, y aplica operaciones elementales por fila hasta llegar a la matriz canónica `[ I : A⁻¹ ]`, obteniendo la Identidad a la izquierda y la inversa `A⁻¹` a la derecha. |
