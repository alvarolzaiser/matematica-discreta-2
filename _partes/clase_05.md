# Clase 5 — Matrices y Determinantes

## 🗺️ Mapa de la clase

### Estructura y orden de los temas
Esta clase inaugura la **Unidad 2: Matrices y Determinantes** (primera clase del Álgebra Matricial). El recorrido va desde la necesidad práctica de organizar datos en tablas hasta la formalización algebraica de las matrices y su clasificación completa:

1. **Ubicación en la Unidad 2 y motivación práctica**
   - **5.1 Esquema general de la Unidad 2 (Matrices y Determinantes):** panorama de las dos grandes secciones de la unidad (el ente matemático *matriz* con sus operaciones básicas y elementales, y el *determinante* de matrices cuadradas).
   - **5.2 Organización de información y concepto preliminar de Matriz:** paso de enunciados verbales con datos numéricos a disposiciones rectangulares en filas y columnas; significado asignado a filas y columnas.
2. **Definición formal, notación y estructura de una matriz**
   - **5.3 Definición formal de Matriz y Orden de una matriz:** conjunto de n·m números dispuestos en n filas y m columnas; concepto de orden n × m.
   - **5.4 Notación matricial, expresión general y subíndices (aᵢⱼ):** delimitadores (corchetes, paréntesis, doble barra), letras mayúsculas, matriz general Aₙₓₘ y rol posicional del par de subíndices i (fila) y j (columna).
   - **5.5 Vectores como caso particular de matrices (Vector columna y Vector fila):** matrices de orden n × 1 y 1 × n.
   - **5.6 Segunda definición de Matriz (como conjunto ordenado de vectores):** la matriz vista como un conjunto ordenado de vectores filas o de vectores columnas.
3. **Clasificación de matrices (Matrices Especiales)**
   - **5.7 Clasificación de matrices y Matriz Rectangular:** criterio doble de clasificación (según su forma y según sus elementos) y el caso general rectangular.
   - **5.8 Matriz Nula:** definición verbal y simbólica (0, todos sus elementos iguales a cero).
   - **5.9 Matriz Cuadrada, Orden n, Diagonal Principal y Diagonal Secundaria:** igualdad entre cantidad de filas y columnas, simplificación del orden y definición geométrica de ambas diagonales.
   - **5.10 Matriz Diagonal:** matriz cuadrada con elementos nulos fuera de la diagonal principal.
   - **5.11 Matriz Escalar:** matriz diagonal con todos los elementos de la diagonal principal iguales entre sí.
   - **5.12 Matriz Identidad o Matriz Unidad (Iₙ):** matriz cuadrada con unos en la diagonal principal y ceros en el resto.
   - **5.13 Matriz Triangular (Triangular Superior y Triangular Inferior):** matriz cuadrada con ceros a un mismo lado de la diagonal principal.
   - **5.14 Matriz Escalonada (o Matriz Canónica o Escalonada):** presentación preliminar del formato escalonado.
4. **Relación fundamental entre matrices**
   - **5.15 Igualdad de Matrices y Elementos Correspondientes:** condiciones necesarias y suficientes para que A = B y definición de elementos correspondientes (igual par de subíndices ij).

### Prerrequisitos
- **Conjuntos numéricos básicos (ℕ, ℤ, ℝ):** distinguir entre los números que forman los elementos de la matriz (que pueden ser reales cualesquiera: enteros, negativos, decimales, irracionales como π) y los números que indican cantidades o posiciones de filas y columnas (que son números naturales: 1, 2, 3, ..., n, m).
- **Conectivos lógicos y cuantificadores:** uso de la equivalencia lógica o bicondicional (`⇔`, "si y sólo si") y del cuantificador universal ("para todo i, j") para expresar rigurosamente cuándo una matriz cumple una propiedad (ser nula, ser identidad, ser igual a otra).

---

## 5.1 Esquema general de la Unidad 2 (Matrices y Determinantes)

> 📖 **Textual del material:** "En esta unidad vas a distinguir dos secciones.
> En la primera se define el ente matemático objeto de estudio de esta unidad: LA MATRIZ. Aquí se aclara terminología, se definirán las operaciones matemáticas básicas: adición, sustracción y multiplicación y operaciones elementales, que no son las habituales, por el contrario son características de las matrices.
> En la segunda sección estudiaremos el determinante de las matrices cuadradas, su definición y métodos para calcularlos, así como algunas propiedades."

> 📖 **Textual del material (Esquema conceptual):**
> "MATRICES → Definición | Operaciones → Básicas (Adición, Producto por un número, Producto) | Elementales (Matríz canónica)
> DETERMINANTES → Concepto | Cálculo → Métodos, Propiedades"

**🗣️ En palabras simples:** Presenta la hoja de ruta de toda la Unidad 2. Primero se estudia qué es una matriz y cómo se opera con ella (tanto con cuentas parecidas a las de los números comunes —suma, resta, multiplicación— como con "operaciones elementales" propias de las matrices que sirven para llegar a la matriz canónica). Luego, exclusivamente para las matrices cuadradas, se estudia cómo calcular un número asociado a ellas llamado *determinante*.

**🔍 Desglose de la jerga:**
- **Ente matemático:** objeto abstracto con una definición precisa sobre el cual se construyen propiedades y operaciones (en este caso, la matriz).
- **Operaciones matemáticas básicas:** la adición (suma), sustracción (resta), producto por un número (escalar) y producto entre matrices.
- **Operaciones elementales:** transformaciones sobre las filas o columnas de una matriz que "no son las habituales, por el contrario son características de las matrices" y permiten obtener una **matriz canónica**.
- **Determinante:** concepto que se aplica únicamente a las **matrices cuadradas**.

**💡 Ejemplo:** (Del recorrido de la unidad) En esta Clase 5 se aborda la rama "MATRICES → Definición" (incluyendo su clasificación). Las ramas de "Operaciones" y "DETERMINANTES" se desarrollan en las clases siguientes de la unidad.

**🔗 Conexiones:** Conecta directamente esta Clase 5 con las Clases 6, 7 y 8 (operaciones matriciales, operaciones elementales, matriz canónica, inversa y determinantes).

**⚠️ Precisiones / errores comunes:**
- Notar desde el primer momento que el **determinante** sólo se estudia para **matrices cuadradas**, mientras que las operaciones básicas y elementales aplican a matrices en general (según sus órdenes).

**🎤 Cómo decirlo en el oral:** "La Unidad 2 se divide en dos secciones: en la primera estudiamos el ente matemático llamado matriz, su terminología, las operaciones básicas (adición, sustracción, producto por un número y producto) y las operaciones elementales características de las matrices para llegar a la matriz canónica; en la segunda sección estudiamos el determinante de las matrices cuadradas, su concepto, métodos de cálculo y propiedades."

---

## 5.2 Organización de información y concepto preliminar de Matriz

> 📖 **Textual del material:** "Hay infinidad de situaciones donde es conveniente arreglar la información numérica en filas y columnas:
> • Notas obtenidas en distintas evaluaciones por un grupo de alumnos.
> • Los puntos del monitor de una computadora.
> • La tabla de cotizaciones de la Bolsa en cada uno de los días de la semana.
> • La ubicación de personas en un espectáculo.
> • Gastos realizados en distintos rubros durante el mes.
> • Cantidad de casos clínicos de ciertas enfermedades en distintas regiones del país.
> • Etc…
> Esta disposición rectangular de números se denomina MATRIZ."

> 📖 **Textual del material (sobre el ordenamiento de filas y columnas):** "cambia la forma de ordenar estos elementos, que tienen que ver con lo que se elige como “fila” o como “columna” de la matriz. Pero como la matriz se puede ordenar según la necesidad de lo que hay que plantear, mientras se tenga en claro eso, el orden puede variar, asignándole un significado a cada fila o a cada columna…"

**🗣️ En palabras simples:** Antes de dar la definición con letras `n` y `m`, el material explica por qué existen las matrices: cuando un problema tiene muchos datos numéricos mezclados con palabras, leerlo y operar se vuelve engorroso. Si acomodamos esos números en un cuadro rectangular de filas (horizontales) y columnas (verticales), la información queda limpia y lista para operar. A ese arreglo rectangular de números se lo llama **matriz**. Además, no hay una única forma de armar la tabla: lo que alguien pone en las filas, otra persona puede ponerlo en las columnas, siempre que quede claro qué representa cada fila y cada columna.

**🔍 Desglose de la jerga:**
- **Disposición rectangular de números:** conjunto de números acomodados formando un rectángulo (todas las filas tienen la misma cantidad de elementos y todas las columnas tienen la misma cantidad de elementos; no quedan "huecos" vacíos).
- **Fila:** cada línea horizontal de números de la matriz.
- **Columna:** cada línea vertical de números de la matriz.

**💡 Ejemplo:** (Situación 1 del material) Una empresa fabrica estanterías modelos A, B y C en tamaños grande y pequeño: A (1000 grandes, 8000 pequeñas), B (8000 grandes, 6000 pequeñas), C (4000 grandes, 6000 pequeñas). Se puede organizar asignando los modelos A, B, C a las 3 filas y los tamaños (Grandes, Pequeñas) a las 2 columnas:
- Fila A: `1000   8000`
- Fila B: `8000   6000`
- Fila C: `4000   6000`

O bien invirtiendo el criterio (como se muestra en la Situación 4 del material con los viajes a Buenos Aires, Rosario, Mendoza y Tilisarao): si se intercambian los significados de filas y columnas, los números significan exactamente lo mismo en la realidad, pero cambia la ubicación de los elementos en la matriz.

**🔗 Conexiones:** Cambiar lo que se elige como "fila" por lo que se elige como "columna" es la base intuitiva del concepto de **matriz traspuesta** que se verá en las clases siguientes, y la coherencia entre filas y columnas es la clave para poder **multiplicar matrices** (como se anticipa en el Desempeño 18 con las salas de cine y los precios de las entradas).

**⚠️ Precisiones / errores comunes:**
- Decir "Esta disposición rectangular de números se denomina matriz" sirve como introducción intuitiva en el oral, pero **no reemplaza** a la definición formal con `n × m` y `n.m` números que sigue inmediatamente después.

**🎤 Cómo decirlo en el oral:** "Cuando arreglamos información numérica en filas y columnas, esa disposición rectangular de números se denomina matriz. Al armarla a partir de un problema, se puede elegir qué representa cada fila y cada columna según la necesidad, siempre manteniendo claro el significado asignado a cada una."

---

## 5.3 Definición formal de Matriz y Orden de una matriz

> 📖 **Textual del material:** "Definiremos MATRIZ, n x m a un conjunto de n.m números dispuestos en n filas y m columnas. Diremos que n x m es el ORDEN de la matriz (se lee “ene por eme”).
> Una matriz 2 x 3 es un conjunto de 2 . 3 = 6 números dispuestos en 2 filas y 3 columnas. Es de orden 2 x 3."

**🗣️ En palabras simples:** Una matriz `n × m` es un grupo de `n · m` números ordenados en `n` líneas horizontales (filas) y `m` líneas verticales (columnas). La expresión `n × m` (sin resolver la multiplicación) se llama **orden** de la matriz y nos dice su tamaño exacto: primero cuántas filas tiene y segundo cuántas columnas tiene. En cambio, si resolvemos la multiplicación `n · m`, obtenemos la cantidad total de números (elementos) que hay adentro de la matriz.

**🔍 Desglose de la jerga:**
- **MATRIZ, n x m:** el nombre del ente matemático acompañado de sus dimensiones (primero filas `n`, después columnas `m`).
- **Conjunto de n.m números:** la cantidad total de elementos que componen la matriz es el producto entre el número de filas `n` y el número de columnas `m`.
- **Dispuestos en n filas y m columnas:** los números no están sueltos como en un conjunto común, sino ubicados en una grilla de `n` filas (horizontales) por `m` columnas (verticales).
- **ORDEN de la matriz (`n x m`):** es la dimensión o tamaño de la matriz, leído literalmente *"ene por eme"*. Siempre el primer número indica las filas y el segundo indica las columnas.

**💡 Ejemplo:**
- **Del material:** "Una matriz 2 x 3 es un conjunto de 2 . 3 = 6 números dispuestos en 2 filas y 3 columnas. Es de orden 2 x 3."
- **Del Desempeño 19 del material (cantidad de elementos según el orden):**
  - En una matriz `1 × 1` hay `1 · 1 = 1` elemento.
  - En una matriz `3 × 5` hay `3 · 5 = 15` elementos.
  - En una matriz `m × n` hay `m · n` elementos.
  - En una matriz `r × r` hay `r²` elementos.

**🔗 Conexiones:** El concepto de **orden** es la primera condición obligatoria para definir la **igualdad de matrices** (sección 5.15), la compatibilidad en la **suma de matrices** (Clase 6) y la condición de conformabilidad en el **producto de matrices** (Clase 6). Además, cuando `n = m`, da lugar al concepto de **matriz cuadrada de orden n** (sección 5.9).

**⚠️ Precisiones / errores comunes:**
- **Nunca invertir el orden:** `2 × 3` NO es el mismo orden que `3 × 2`. Aunque ambas tienen `6` elementos, una matriz `2 × 3` tiene 2 filas y 3 columnas, mientras que una `3 × 2` tiene 3 filas y 2 columnas. Siempre es **Filas × Columnas**.
- **No confundir "orden" con "cantidad de elementos":** el *orden* se deja indicado como `n × m` (por ejemplo, `2 × 3`); la *cantidad de elementos* es el resultado del producto `n · m` (por ejemplo, `6`).

**🎤 Cómo decirlo en el oral:** "Definimos matriz n por m a un conjunto de n por m (n.m) números dispuestos en n filas y m columnas. Decimos que n x m (leído 'ene por eme') es el orden de la matriz, donde el primer número indica siempre la cantidad de filas y el segundo la cantidad de columnas."

---

## 5.4 Notación matricial, expresión general y subíndices (aᵢⱼ)

> 📖 **Textual del material:** "A los elementos de las matrices los pondremos entre corchetes (pueden ser paréntesis o doble barra) y las designaremos con letras mayúsculas."

> 📖 **Textual del material:** "El orden de una matriz y los números que la forman pueden ser cualesquiera, por esto en forma general a una matriz n x m la escribiremos:
>
>          ⎛ a₁₁  a₁₂  a₁₃  ...  a₁ₘ ⎞
>          ⎜ a₂₁  a₂₂  a₂₃  ...  a₂ₘ ⎟
>          ⎜ a₃₁  a₃₂  a₃₃  ...  a₃ₘ ⎟
> Aₙₓₘ =   ⎜  :                      ⎟
>          ⎜  :                      ⎟
>          ⎜  :                      ⎟
>          ⎝ aₙ₁  aₙ₂  aₙ₃  ...  aₙₘ ⎠
>
> No es para asustarse, solo para generalizar la expresión de cualquier matriz.
> En donde los elementos a₁₁, a₁₂, a₁₃ ... aₙₘ representan cualquier número.
> Observemos además que el elemento a₁₁ que está en la fila 1 y la columna 1. El a₁₂ en la fila 1, columna 2. El a₂₃ es el está está en la fila 2 columna 3. Es decir que los subíndices nos indican la posición del elemento.
> En general, el elemento aᵢⱼ de la fila i y la columna j. En resumen:
> En Aₙₓₘ: n = Cantidad de filas, m = Cantidad de columnas.
> Y en aᵢⱼ: i = N° de fila, j = N° de columna."

**🗣️ En palabras simples:** Para escribir una matriz encerramos sus números entre corchetes `[ ]` (también vale usar paréntesis `( )` o doble barra `‖ ‖`) y llamamos a la matriz con una letra mayúscula (`A`, `B`, `D`, `P`, etc.). Adentro, para hablar de un elemento genérico sin darle un valor fijo, usamos la misma letra en minúscula con dos numeritos abajo (subíndices): `aᵢⱼ`. Esos dos subíndices son como las coordenadas de una batalla naval: el primer subíndice (`i`) dice en qué número de fila está el elemento, y el segundo subíndice (`j`) dice en qué número de columna está.

**🔍 Desglose de la jerga:**
- **Corchetes, paréntesis o doble barra:** los signos tipográficos que encierran la disposición rectangular para indicar que es una matriz.
- **Letra mayúscula (`Aₙₓₘ`):** representa a la matriz completa; su subíndice `n × m` indica `n` = *Cantidad de filas* totales y `m` = *Cantidad de columnas* totales.
- **Letra minúscula con doble subíndice (`aᵢⱼ`):** representa a un **elemento** individual de la matriz `A`, ubicado en la intersección de la fila `i` (`i` = *N° de fila*) y la columna `j` (`j` = *N° de columna*).
- **Separación de subíndices con punto y coma (`p₃;₄`):** cuando los subíndices pueden prestarse a confusión o en ejercicios prácticos (como en el Desempeño 17 del material), también se anota el par como `(3;4)` o `p₃;₄` para indicar fila 3 y columna 4.

**💡 Ejemplo:** (Del material, páginas 7, 8, 9 y 15)
1. En la matriz de orden `3 × 2`:
   ```
       ⎡ 50   45 ⎤
   D = ⎢ 30   10 ⎥
       ⎣ 80   25 ⎦
   ```
   Tenemos que `d₁₁ = 50` (fila 1, columna 1) y `d₁₂ = 45` (fila 1, columna 2).
2. En el Desempeño 18 del material, para una matriz `A` de orden `3 × 3` (3 salas de cine × 3 tipos de entradas), si nos piden el elemento `a₁₄`, la respuesta textual del material es: *"Ese elemento no existe, no pertenece a la matriz A"*, porque la matriz sólo tiene 3 columnas (`m = 3`), por lo que el subíndice `j` no puede valer `4`.

**🔗 Conexiones:** La notación `aᵢⱼ` es el lenguaje universal con el que se escriben en símbolos todas las definiciones posteriores de la clase: matriz nula (`aᵢⱼ = 0`), matriz identidad (`aᵢⱼ = 1` cuando `i = j` y `aᵢⱼ = 0` cuando `i ≠ j`), matrices triangulares (`i > j` o `i < j`) e igualdad de matrices (`aᵢⱼ = bᵢⱼ`).

**⚠️ Precisiones / errores comunes:**
- **Diferenciar el subíndice de la matriz del subíndice del elemento:** En `Aₙₓₘ`, `n` y `m` indican el **tamaño total** (cantidad de filas y cantidad de columnas de toda la matriz). En `aᵢⱼ`, `i` y `j` indican la **posición particular** (número de fila y número de columna de ese único elemento, con `1 ≤ i ≤ n` y `1 ≤ j ≤ m`).
- **Cómo se leen los subíndices:** `a₁₂` se lee *"a sub uno dos"* (fila 1, columna 2), **nunca** *"a sub doce"* (porque "doce" confundiría con una fila 12 o columna 12).

**🎤 Cómo decirlo en el oral:** "A las matrices las designamos con letras mayúsculas y encerramos sus elementos entre corchetes, paréntesis o doble barra. En la expresión general Aₙₓₘ, los subíndices de la letra mayúscula indican la cantidad total de filas (n) y la cantidad total de columnas (m); mientras que a cada elemento lo designamos con la letra minúscula aᵢⱼ, donde los subíndices indican la posición del elemento: i es el número de fila y j es el número de columna."

---

## 5.5 Vectores (un caso particular de matrices): Vector columna y Vector fila

> 📖 **Textual del material:** "VECTORES (UN CASO PARTICULAR DE MATRICES)
> Cuando una matriz tiene 1 columna o 1 fila se la llama VECTOR.
> Es decir que un vector es una matriz de orden n x 1 ó 1 x n. En el caso de tener una columna (n x 1) se lo llama vector columna. Ejemplo:
>
> ⎛  1 ⎞
> ⎜  3 ⎟
> ⎜  5 ⎟
> ⎝ -4 ⎠ ₄ₓ₁
>
> En general:
> ⎛ a₁₁ ⎞
> ⎜ a₂₁ ⎟
> ⎜  :  ⎟
> ⎜  :  ⎟
> ⎝ aₙ₁ ⎠ ₙₓ₁
>
> En caso de tener una fila (1 x n) se llama vector fila.
> Ejemplo: [1 0 4 8 2] ₁ₓ₅
> En general: [a₁₁ a₂₁ ... aₙ₁ ] ₁ₓₙ"

**🗣️ En palabras simples:** Si una matriz es "flaca" de una sola columna o "chata" de una sola fila, recibe el nombre especial de **vector** (también llamado *matriz columna* o *matriz fila* en la pág. 10 del apunte). Si tiene varias filas pero **una sola columna** (orden `n × 1`), es un **vector columna**. Si tiene **una sola fila** y varias columnas (orden `1 × n`), es un **vector fila**.

**🔍 Desglose de la jerga:**
- **VECTOR:** toda matriz donde al menos una de sus dimensiones vale `1` (orden `n × 1` ó `1 × n`).
- **Vector columna (o matriz columna):** matriz de orden `n × 1` (`n` filas y `1` sola columna).
- **Vector fila (o matriz fila):** matriz de orden `1 × n` (`1` sola fila y `n` columnas).

**💡 Ejemplo:** (Del material, pág. 8 y Desempeño 20 en págs. 13 y 15)
- Vector columna de orden `4 × 1`: transpuesto verticalmente con elementos `1, 3, 5, -4`.
- En el Desempeño 20, `D` con elementos `6, -1, 0` dispuestos verticalmente se clasifica como: *"D: Vector columna de orden 3 (3x1)"*.
- Vector fila de orden `1 × 5`: `[1 0 4 8 2]₁ₓ₅`. En el Desempeño 20, `E = [3 -2 5 6 1]` se clasifica como: *"E: Vector fila de orden 5 (1x5)"*.

**🔗 Conexiones:** Los vectores permiten formular inmediatamente la **segunda definición de matriz** (sección 5.6) y son esenciales para el producto de matrices (donde se multiplican vectores fila de la primera matriz por vectores columna de la segunda).

**⚠️ Precisiones / errores comunes:**
- **Detalle de notación en el material para el vector fila general:** Observá que en la página 8 el material escribe para el vector fila general `[a₁₁ a₂₁ ... aₙ₁] ₁ₓₙ` (reutilizando los subíndices `11, 21, ..., n1` del vector columna), aunque estrictamente en una matriz de `1` fila y `n` columnas los subíndices fila-columna de la primera fila son `a₁₁, a₁₂, ..., a₁ₙ`. En el oral podés mencionar la expresión exacta del apunte y aclarar que cada elemento está en la fila 1 y varía su columna de 1 a `n`.
- Notar que en las respuestas del Desempeño 20 (pág. 15) el material también dice *"Vector columna de orden 3 (3x1)"* y *"Vector fila de orden 5 (1x5)"*, abreviando a un solo número porque el otro ya se sabe que es `1` por las palabras "columna" o "fila".

**🎤 Cómo decirlo en el oral:** "Cuando una matriz tiene 1 columna o 1 fila se la llama vector; es decir, un vector es una matriz de orden n x 1 ó 1 x n. Si tiene una sola columna (orden n x 1) se lo llama vector columna, y si tiene una sola fila (orden 1 x n) se lo llama vector fila."

---

## 5.6 Matrices (otra definición): como conjunto ordenado de vectores

> 📖 **Textual del material:** "MATRICES (OTRA DEFINICIÓN)
> Suele ser útil ver a las matrices como un conjunto de vectores. Esto da lugar a otra definición:
> • Una matriz es un conjunto ordenado de vectores filas ó
> • Una matriz es un conjunto ordenado de vectores columnas.
> En los ejemplos analizados podemos pensar a las matrices formadas por vectores filas o por vectores columnas.
> La ventaja de visualizar de esta manera a las matrices es en cada fila o columna hay reunida información del mismo tipo. En las matrices de la actividad n° 3, los vectores columnas contienen información de cada persona, en cambio los vectores filas contienen información acerca del dinero acreditado (fila 1), del dinero depositado (fila 2) y del dinero extraído (fila 3)."

**🗣️ En palabras simples:** En lugar de pensar una matriz de `n × m` como `n · m` números individuales sueltos en una grilla, podemos pensarla como una lista ordenada de "tiras" completas: o bien como `n` vectores fila apilados uno debajo del otro, o bien como `m` vectores columna puestos uno al lado del otro. Se exige que sea un conjunto **ordenado** porque no da lo mismo cambiar la fila 1 por la fila 2.

**🔍 Desglose de la jerga:**
- **Conjunto ordenado:** a diferencia de un conjunto matemático común donde el orden no importa (`{a, b} = {b, a}`), aquí el orden de ubicación de los vectores es fundamental: cuál es el primer vector fila, cuál el segundo, etc.
- **De vectores filas ó de vectores columnas:** son dos formas equivalentes de descomponer la misma matriz (por cortes horizontales o por cortes verticales).
- **Información del mismo tipo:** cada vector fila (o cada vector columna) agrupa todos los datos que comparten una misma categoría o individuo en las aplicaciones reales.

**💡 Ejemplo:** (Del material, Actividad n° 3 en págs. 7, 8 y 9)
En la matriz de diciembre `D`:
```
    ⎡ 50   45 ⎤
D = ⎢ 30   10 ⎥
    ⎣ 80   25 ⎦
```
- **Vista como conjunto ordenado de 2 vectores columnas:** la columna 1 `[50; 30; 80]` reúne toda la información de **Matías**, y la columna 2 `[45; 10; 25]` reúne toda la información de **Florencia**.
- **Vista como conjunto ordenado de 3 vectores filas:** la fila 1 `[50  45]` reúne el **dinero acreditado**, la fila 2 `[30  10]` el **dinero depositado**, y la fila 3 `[80  25]` el **dinero extraído**.

**🔗 Conexiones:** Esta definición es vital cuando se estudian las **operaciones elementales entre filas (o entre columnas)** para escalonar matrices y hallar la matriz canónica, ya que allí se opera con filas completas tratándolas como vectores.

**⚠️ Precisiones / errores comunes:**
- **No olvidar la palabra "ordenado":** Si en el oral decís solamente "una matriz es un conjunto de vectores filas", el profesor puede objetar que en un conjunto no hay orden. Siempre decí: **"un conjunto ordenado de vectores filas ó un conjunto ordenado de vectores columnas"**.

**🎤 Cómo decirlo en el oral:** "Además de la definición por elementos, existe otra definición que ve a la matriz como un conjunto de vectores: una matriz es un conjunto ordenado de vectores filas, o bien una matriz es un conjunto ordenado de vectores columnas. La ventaja de esta visualización es que en cada fila o columna queda reunida información del mismo tipo."

---

## 5.7 Clasificación de matrices y Matriz Rectangular

> 📖 **Textual del material:** "MATRICES ESPECIALES
> Entre la gran variedad de matrices que podemos considerar, existen algunas que por tener características especiales reciben nombres especiales y aparecen con frecuencia en diversas situaciones y también en el desarrollo de los contenidos teóricos. Concretamente es posible realizar una clasificación de ellas según su forma y según los elementos que tengan.
> Las matrices, en general son RECTANGULARES pero según cuales sean sus elementos o cantidad de filas y columnas tengan, reciben un nombre en particular que las identifica:"

**🗣️ En palabras simples:** A las matrices las clasificamos mirando dos cosas: **su forma** (qué relación hay entre la cantidad de filas `n` y de columnas `m`) y **sus elementos** (qué valores tienen adentro, especialmente dónde hay ceros o unos). En el caso general (y particularmente cuando `n ≠ m` y no encaja en ningún caso especial), decimos que la matriz es **rectangular**.

**🔍 Desglose de la jerga:**
- **Clasificación según su forma:** depende de la cantidad de filas y columnas (por ejemplo: rectangular en general, vector fila `1 × n`, vector columna `n × 1`, o matriz cuadrada `n × n`).
- **Clasificación según los elementos que tengan:** depende de los valores numéricos particulares en ciertas posiciones (por ejemplo: matriz nula, diagonal, escalar, identidad, triangular superior, triangular inferior, escalonada).

**💡 Ejemplo:** (Del Desempeño 20 del material, págs. 13 y 15)
```
    ⎡ 3  -2 ⎤
B = ⎢ 6   0 ⎥
    ⎣ 5   4 ⎦
```
En las respuestas oficiales (pág. 15), el material la clasifica como: **"B: Matriz rectangular de orden 3x2"**.

**🔗 Conexiones:** A partir de esta introducción se despliega toda la jerarquía de matrices especiales de las secciones 5.8 a 5.14.

**⚠️ Precisiones / errores comunes:**
- Si el profesor pregunta *"¿Según qué criterios se clasifican las matrices especiales?"*, la respuesta textual exacta es: **"según su forma y según los elementos que tengan"**.

**🎤 Cómo decirlo en el oral:** "A las matrices en general las llamamos rectangulares, y podemos realizar una clasificación de las matrices especiales según dos criterios: según su forma (cantidad de filas y columnas) y según los elementos que tengan."

---

## 5.8 Matriz Nula

> 📖 **Textual del material:** "MATRIZ NULA
> Una matriz cuyos elementos son todos ceros se llama matriz nula y se simboliza por 0 Una matriz nula no necesita ser cuadrada.
> En símbolos:
> A ₙ ₓ ₘ es nula ⇔ aᵢⱼ = 0 para todo i,j
> Ejemplo:
>
>         ⎡ 0  0  0 ⎤
> 0₃ₓ₃ =  ⎢ 0  0  0 ⎥          0₁ₓ₃ = [ 0  0  0 ]
>         ⎣ 0  0  0 ⎦
>
> La matriz nula puede ser también una matriz fila o una matriz columna."

**🗣️ En palabras simples:** Es cualquier matriz que tenga absolutamente todos sus casilleros llenos con el número `0`. Se la nombra con un `0` grande (a menudo con el subíndice de su orden, como `0₃ₓ₃` o `0₁ₓ₃`). No hace falta que sea cuadrada: puede tener cualquier orden `n × m`, incluso ser una sola fila o una sola columna de ceros.

**🔍 Desglose de la jerga:**
- **Simboliza por `0`:** a diferencia de las demás matrices que usan letras mayúsculas, la matriz nula se simboliza con el símbolo `0`.
- **`⇔` (si y sólo si):** indica que la condición que sigue es la definición exacta (necesaria y suficiente).
- **`aᵢⱼ = 0 para todo i,j`:** el cuantificador universal *"para todo i,j"* exige que en **todas** las filas `i` y en **todas** las columnas `j` sin excepción el elemento valga `0` (basta que un solo elemento sea distinto de cero para que ya no sea la matriz nula).

**💡 Ejemplo:** (Del material, pág. 10)
- `0₃ₓ₃`: matriz nula cuadrada de 3 filas y 3 columnas (9 ceros).
- `0₁ₓ₃ = [ 0  0  0 ]`: matriz nula de orden `1 × 3`, que es a la vez una **matriz fila** (o vector fila).

**🔗 Conexiones:** La matriz nula cumple en la adición de matrices el rol de **elemento neutro aditivo** (sumarle la matriz nula del mismo orden a una matriz `A` deja a `A` igual), como se estudia en la Clase 6.

**⚠️ Precisiones / errores comunes:**
- **Error típico de examen:** Creer que todas las matrices especiales (nula, diagonal, escalar, identidad, triangular) tienen que ser cuadradas. ¡Falso! La **matriz nula** (al igual que los vectores y la matriz escalonada) **no necesita ser cuadrada**.

**🎤 Cómo decirlo en el oral:** "Una matriz cuyos elementos son todos ceros se llama matriz nula y se simboliza por 0. En símbolos: Aₙₓₘ es nula si y sólo si aᵢⱼ = 0 para todo i, j. Una matriz nula no necesita ser cuadrada; puede ser rectangular, e incluso ser una matriz fila o una matriz columna."

---

## 5.9 Matriz Cuadrada, Orden n, Diagonal Principal y Diagonal Secundaria

> 📖 **Textual del material:** "MATRIZ CUADRADA
> Llamaremos matriz cuadrada a aquella que tiene el mismo número de filas que de columnas.
> Ejemplo:
>
>         ⎡ 2  8  7 ⎤
> A₃ₓ₃ =  ⎢ 1  3  5 ⎥
>         ⎣ 3  2  1 ⎦
>
> En el caso de una matriz cuadrada no es necesario indicar el número de filas y de columnas porque ambas son iguales. Basta decir que es una matriz cuadrada de orden n.
> Además, en una matriz cuadrada distinguimos la diagonal principal y la secundaria. Los elementos de la “diagonal principal” son los que están desde el ángulo superior izquierdo al inferior derecho y los elementos de la “diagonal secundaria” son los que están desde el ángulo inferior izquierdo al superior derecho. Esto es válido sólo para matrices cuadradas."

**🗣️ En palabras simples:** Una matriz es **cuadrada** cuando tiene la misma cantidad de filas que de columnas (`n = m`). Como los dos números del orden son iguales (por ejemplo `3 × 3`), en vez de decir "de orden 3 por 3" alcanza con decir **"matriz cuadrada de orden 3"** (en general, **de orden n**). Únicamente cuando la matriz es cuadrada se forman dos diagonales de esquina a esquina:
1. La **diagonal principal**: baja desde arriba a la izquierda hasta abajo a la derecha (`a₁₁, a₂₂, a₃₃, ..., aₙₙ`, es decir, los elementos que tienen igual número de fila que de columna: `i = j`).
2. La **diagonal secundaria**: sube desde abajo a la izquierda hasta arriba a la derecha (`aₙ₁, ..., a₃₁/a₂₂/a₁₃` según el orden `n`).

**🔍 Desglose de la jerga:**
- **Mismo número de filas que de columnas:** `n = m`, por lo que la matriz es de tipo `n × n` y tiene `n²` elementos.
- **Matriz cuadrada de orden n:** forma abreviada y estándar de nombrar el orden de una matriz `n × n`.
- **Diagonal principal:** elementos ubicados desde el ángulo superior izquierdo (`a₁₁`) al inferior derecho (`aₙₙ`). Todos ellos cumplen `i = j` (`a₁₁, a₂₂, a₃₃, ..., aₙₙ`).
- **Diagonal secundaria:** elementos ubicados desde el ángulo inferior izquierdo (`aₙ₁`) al superior derecho (`a₁ₙ`).
- **"Esto es válido sólo para matrices cuadradas":** una matriz rectangular que no sea cuadrada NO tiene diagonal principal ni diagonal secundaria.

**💡 Ejemplo:** (Del material, pág. 11, recuadro *"Por si quedó duda"*)
En la matriz cuadrada de orden 3:
```
⎛ 1  2  0 ⎞
⎜ 3  1  4 ⎟
⎝ 3  0  1 ⎠
```
- Los elementos de la **Diagonal Principal** son: `1, 1, 1` (correspondientes a `a₁₁ = 1`, `a₂₂ = 1`, `a₃₃ = 1`).
- Los elementos de la **Diagonal Secundaria** son: `3, 1, 0` (desde abajo a la izquierda `a₃₁ = 3`, pasando por `a₂₂ = 1`, hasta arriba a la derecha `a₁₃ = 0`).

**🔗 Conexiones:** La matriz cuadrada y su **diagonal principal** son el prerrequisito directo para definir **matriz diagonal**, **matriz escalar**, **matriz identidad** y **matriz triangular** (secciones 5.10 a 5.13), y en la segunda parte de la unidad, para definir el **determinante**.

**⚠️ Precisiones / errores comunes:**
- **Detalle visual del PDF (pág. 10 vs. pág. 11):** En el final de la página 10 del PDF aparece pegada por error de edición la imagen genérica `Aₙₓₘ`, pero inmediatamente arriba de la página 11 el texto aclara que ambas cantidades son iguales (orden `n`) y muestra el diagrama correcto hasta `aₙₙ` (`a₁₁, a₂₂, a₃₃, ..., aₙₙ`).
- **Condición innegociable:** Jamás hablar de diagonal principal o secundaria sin antes aclarar que la matriz es **cuadrada**.

**🎤 Cómo decirlo en el oral:** "Llamamos matriz cuadrada a aquella que tiene el mismo número de filas que de columnas; por eso basta decir que es una matriz cuadrada de orden n. Sólo en las matrices cuadradas distinguimos dos diagonales: los elementos de la diagonal principal son los que están desde el ángulo superior izquierdo al inferior derecho (a₁₁, a₂₂, ..., aₙₙ), y los elementos de la diagonal secundaria son los que están desde el ángulo inferior izquierdo al superior derecho."

---

## 5.10 Matriz Diagonal

> 📖 **Textual del material:** "MATRIZ DIAGONAL
> Es una matriz cuadrada en la que los elementos que NO pertenecen a la diagonal principal son nulos (o sea iguales a 0). Ejemplo: (dicen que una imagen dice más que mil palabras…)
>
>           ⎛ 7   0   0 ⎞
> A₍₃ₓ₃₎ =  ⎜ 0  -2   0 ⎟
>           ⎝ 0   0   0 ⎠"

**🗣️ En palabras simples:** Es una matriz que primero tiene que ser **cuadrada**, y además todos los elementos que están **afuera** de la diagonal principal tienen que valer obligatoriamente `0`. ¿Y los elementos que están *sobre* la diagonal principal? Sobre ellos la definición no impone ninguna prohibición: pueden ser cualquier número, ¡incluso alguno o varios de ellos también pueden ser `0`!

**🔍 Desglose de la jerga:**
- **Es una matriz cuadrada:** primera condición obligatoria (`n × n`).
- **Los elementos que NO pertenecen a la diagonal principal son nulos (o sea iguales a 0):** en notación de subíndices (contexto adicional coherente con el material), significa que `aᵢⱼ = 0` cuando `i ≠ j`.
- **Sobre la diagonal principal (`i = j`):** no se exige nada; pueden ser distintos de cero o iguales a cero.

**💡 Ejemplo:** (Del material, pág. 11 y Desempeño 20 en pág. 13)
- En el ejemplo de la pág. 11: `A₍₃ₓ₃₎` tiene en la diagonal principal `7, -2, 0` y todos los demás elementos son `0`. ¡Fijate que el elemento `a₃₃ = 0` pertenece a la diagonal principal y vale cero, y aun así la matriz es diagonal!
- En el Desempeño 20 (pág. 13):
  ```
      ⎡ 3   0   0   0 ⎤
  C = ⎢ 0  -5   0   0 ⎥
      ⎢ 0   0   0   0 ⎥
      ⎣ 0   0   0   7 ⎦
  ```
  se clasifica en la pág. 15 como: **"C: Matriz diagonal de orden 4"** (nuevamente con un `0` en `c₃₃`).

**🔗 Conexiones:** La matriz diagonal es el género del cual se desprenden como casos particulares la **matriz escalar** (sección 5.11) y la **matriz identidad** (sección 5.12). Además, toda matriz diagonal es simultáneamente triangular superior e inferior.

**⚠️ Precisiones / errores comunes:**
- **Trampa clásica de examen oral:** El profesor pregunta: *"En una matriz diagonal, ¿pueden haber ceros en la diagonal principal?"*. Muchos alumnos responden que no. La respuesta correcta es **SÍ**, porque la definición sólo exige que los elementos que **NO pertenecen** a la diagonal principal sean nulos (como lo demuestran `A₍₃ₓ₃₎` de la pág. 11 y la matriz `C` del Desempeño 20).

**🎤 Cómo decirlo en el oral:** "Una matriz diagonal es una matriz cuadrada en la que los elementos que no pertenecen a la diagonal principal son nulos, o sea iguales a 0."

---

## 5.11 Matriz Escalar

> 📖 **Textual del material:** "MATRIZ ESCALAR
> Es una matriz diagonal, con todos sus elementos de la diagonal, iguales.
>
>     ⎡ 12   0 ⎤          ⎡ 5  0  0 ⎤
> Q = ⎣  0  12 ⎦      T = ⎢ 0  5  0 ⎥
>                         ⎣ 0  0  5 ⎦"

**🗣️ En palabras simples:** Es un caso particular de **matriz diagonal** (y por lo tanto, también es cuadrada y tiene todos ceros fuera de la diagonal principal) donde, además, todos los números de la diagonal principal son exactamente el mismo número repetido (`12 y 12`, `5, 5 y 5`, `-7, -7, -7 y -7`, etc.).

**🔍 Desglose de la jerga:**
- **Es una matriz diagonal:** al empezar diciendo esto, hereda automáticamente dos propiedades: (1) es **cuadrada**, y (2) todos los elementos fuera de la diagonal principal valen `0`.
- **Con todos sus elementos de la diagonal, iguales:** `a₁₁ = a₂₂ = ... = aₙₙ = k` (para un mismo número fijo).

**💡 Ejemplo:** (Del material, pág. 11 y Desempeño 20 en pág. 13)
- `Q` (matriz escalar de orden 2 con diagonal igual a `12`) y `T` (matriz escalar de orden 3 con diagonal igual a `5`).
- En el Desempeño 20, `G` (orden 3 con diagonal de `2`) y `L` (orden 4 con diagonal de `-7`) son matrices escalares.

**🔗 Conexiones:** Es el escalón intermedio entre la **matriz diagonal** (donde la diagonal tiene números cualesquiera) y la **matriz identidad** (que es una matriz escalar donde ese número repetido en la diagonal es específicamente el `1`). En la Clase 6 se ve que multiplicar una matriz por una matriz escalar equivale a multiplicarla por el número (escalar) de su diagonal.

**⚠️ Precisiones / errores comunes:**
- Si te preguntan *"¿Qué es una matriz escalar?"*, no digas solamente "la que tiene la diagonal igual" porque te faltaría decir qué pasa afuera de la diagonal. Al decir como el apunte **"Es una matriz diagonal, con todos sus elementos de la diagonal, iguales"**, la palabra *diagonal* ya garantiza que es cuadrada y que fuera de la diagonal principal son todos ceros.

**🎤 Cómo decirlo en el oral:** "Una matriz escalar es una matriz diagonal con todos sus elementos de la diagonal iguales."

---

## 5.12 Matriz Identidad o Matriz Unidad (Iₙ)

> 📖 **Textual del material:** "MATRIZ IDENTIDAD O MATRIZ UNIDAD
> Definiremos matriz identidad como una matriz cuadrada que tiene los elementos de la diagonal principal iguales a uno y los restantes son ceros.
> En símbolos:
> A ₙ ₓ ₙ es identidad ⇔ { aᵢⱼ = 1 cuando i = j ; aᵢⱼ = 0 cuando i ≠ j }
> Se la simboliza en general con una i mayúscula y un subíndince para indicarnos el orden: I ₙ.
> En cada orden matricial existe una matriz unidad, por ejemplo:
>
>      ⎡ 1  0 ⎤          ⎡ 1  0  0 ⎤
> I₂ = ⎣ 0  1 ⎦     I₃ = ⎢ 0  1  0 ⎥
>                        ⎣ 0  0  1 ⎦"

> 📖 **Textual del material (recuadro de ejemplos en pág. 12):**
> "Existe una matriz identidad para cada tamaño de matriz cuadrada nxn.
> Ejemplos:
> La matriz identidad 2x2 es; I = [ 1 0 ; 0 1 ]
> La matriz identidad 3x3 es; I = [ 1 0 0 ; 0 1 0 ; 0 0 1 ]
> La matriz identidad 4x4 es; I = [ 1 0 0 0 ; 0 1 0 0 ; 0 0 1 0 ; 0 0 0 1 ]"

**🗣️ En palabras simples:** Es la matriz cuadrada más famosa del álgebra matricial: tiene todos `1` en la diagonal principal y todos `0` en el resto de las posiciones. Se la llama indistintamente **matriz identidad** o **matriz unidad**, y tiene letra reservada propia: `I` mayúscula con el subíndice `n` que indica su orden (`I₂`, `I₃`, `I₄`, ..., `Iₙ`). En realidad, es un caso particularísimo de matriz escalar (y por ende diagonal) donde los elementos de la diagonal principal valen todos `1`.

**🔍 Desglose de la jerga:**
- **Matriz identidad o matriz unidad:** ambos nombres son sinónimos exactos en la cátedra.
- **`Aₙₓₙ`:** destaca desde el símbolo que la matriz debe ser **cuadrada** de orden `n`.
- **`aᵢⱼ = 1 cuando i = j`:** cuando el número de fila coincide con el número de columna (es decir, sobre la diagonal principal: `a₁₁, a₂₂, ..., aₙₙ`), el elemento vale `1`.
- **`aᵢⱼ = 0 cuando i ≠ j`:** cuando el número de fila es distinto del número de columna (es decir, fuera de la diagonal principal), el elemento vale `0`.
- **Simbolización `Iₙ`:** `I` mayúscula por *Identidad* y `n` por el orden de la matriz cuadrada.

**💡 Ejemplo:** (Del material, pág. 12 y Desempeño 20 en pág. 13)
- `I₂` (identidad de orden 2), `I₃` (identidad de orden 3, llamada `H` en el Desempeño 20) e `I₄` (identidad de orden 4, llamada `K` en el Desempeño 20).

**🔗 Conexiones:** Se llama "identidad" o "unidad" porque en la multiplicación de matrices (Clase 6) cumple el mismo papel que el número `1` en la multiplicación de números reales (**elemento neutro del producto**: `A · I = I · A = A`), y es clave para definir la **matriz inversa** (`A · A⁻¹ = I`) y la reducción por operaciones elementales.

**⚠️ Precisiones / errores comunes:**
- **No existe matriz identidad rectangular:** "Existe una matriz identidad para cada tamaño de matriz cuadrada n x n".
- En el oral es muy probable que el profesor pida tanto la definición verbal como la **definición en símbolos** distinguiendo los dos casos (`i = j` e `i ≠ j`).

**🎤 Cómo decirlo en el oral:** "Definimos matriz identidad o matriz unidad como una matriz cuadrada que tiene los elementos de la diagonal principal iguales a uno y los restantes son ceros. En símbolos: Aₙₓₙ es identidad si y sólo si aᵢⱼ = 1 cuando i = j, y aᵢⱼ = 0 cuando i ≠ j. Se la simboliza con una I mayúscula y un subíndice que indica el orden: Iₙ."

---

## 5.13 Matriz Triangular (Triangular Superior y Triangular Inferior)

> 📖 **Textual del material:** "MATRIZ TRIANGULAR
> Es una matriz cuadrada que tiene nulos todos los elementos que están a un mismo lado de la diagonal principal. Las matrices triangulares pueden ser de dos tipos:
> Triangular Superior: Si los elementos que están por debajo de la diagonal principal son todos nulos. ( En símbolos: aᵢⱼ > j )
>
>     ⎡ 1  0  -2 ⎤
> A = ⎢ 0  3   1 ⎥
>     ⎣ 0  0   2 ⎦
>
> Triangular Inferior: Si los elementos que están por encima de la diagonal principal son todos nulos. (En símbolos: aᵢⱼ = 0 para todo i < j )
>
>     ⎡  1  0  0 ⎤
> A = ⎢  3  3  0 ⎥
>     ⎣ -1  0  2 ⎦"

**🗣️ En palabras simples:** Una matriz cuadrada es **triangular** cuando todos los elementos de uno de los dos "triángulos" que quedan a un lado u otro de la diagonal principal son ceros:
- Es **Triangular Superior** cuando los datos potencialmente no nulos están en la parte *superior* (de la diagonal principal hacia arriba) y **todo lo que está por debajo de la diagonal principal es cero** (son los casilleros donde el número de fila `i` es mayor que el de columna `j`, como `a₂₁, a₃₁, a₃₂`).
- Es **Triangular Inferior** cuando los datos potencialmente no nulos están en la parte *inferior* (de la diagonal principal hacia abajo) y **todo lo que está por encima de la diagonal principal es cero** (son los casilleros donde el número de fila `i` es menor que el de columna `j`, como `a₁₂, a₁₃, a₂₃`).

**🔍 Desglose de la jerga:**
- **Por debajo de la diagonal principal (`i > j`):** al bajar de fila, el índice `i` crece; por eso los elementos debajo de la diagonal principal tienen número de fila mayor que el número de columna (`a₂₁, a₃₁, a₃₂, a₄₁, ...`).
- **Por encima de la diagonal principal (`i < j`):** al moverse hacia la derecha, el índice de columna `j` crece; por eso los elementos encima de la diagonal principal tienen número de fila menor que el número de columna (`a₁₂, a₁₃, a₂₃, ...`).

**💡 Ejemplo:** (Del Desempeño 20 del material, págs. 13 y 15)
- **Triangular superior de orden 4 (`I` en Desempeño 20):**
  ```
      ⎡ 3   1   2   3 ⎤
  I = ⎢ 0   5   0  -1 ⎥
      ⎢ 0   0   6   π ⎥
      ⎣ 0   0   0  -2 ⎦
  ```
  (Notar que `i₂₃ = 0` está por encima de la diagonal principal y vale `0`, ¡lo cual está totalmente permitido! Lo único obligatorio es que por debajo de la diagonal principal sean todos ceros).
- **Triangular inferior de orden 4 (`J` en Desempeño 20):**
  ```
      ⎡  4   0   0   0 ⎤
  J = ⎢  7   4   0   0 ⎥
      ⎢ -1   π   1   0 ⎥
      ⎣  0   2   2   9 ⎦
  ```
  (Todos los elementos por encima de la diagonal principal son nulos).

**🔗 Conexiones:** Las matrices triangulares son importantísimas en el cálculo de **determinantes** (el determinante de una matriz triangular es simplemente el producto de los elementos de su diagonal principal) y en la resolución de sistemas de ecuaciones lineales (eliminación gaussiana).

**⚠️ Precisiones / errores comunes:**
- **¡ATENCIÓN A LA ERRATA DEL APUNTE EN TRIANGULAR SUPERIOR!:** En la página 12 del PDF, al final de Triangular Superior dice textualmente `( En símbolos: aᵢⱼ > j )`. Se trata de un error tipográfico de imprenta donde se comieron `= 0 para todo i`, quedando pegado `aᵢⱼ` con `> j`. La expresión simbólica completa (análoga a la de Triangular Inferior que está dos renglones más abajo) es: **`aᵢⱼ = 0 para todo i > j`**. En el oral, decí la expresión correcta `aᵢⱼ = 0 para todo i > j` (y si el profesor mira el apunte, sabés que en el PDF quedó truncado como `aᵢⱼ > j`).
- **No confundir los nombres:** "Triangular **Superior**" tiene los ceros **abajo** (porque el triángulo de números queda *arriba*). "Triangular **Inferior**" tiene los ceros **arriba** (porque el triángulo de números queda *abajo*).

**🎤 Cómo decirlo en el oral:** "Una matriz triangular es una matriz cuadrada que tiene nulos todos los elementos que están a un mismo lado de la diagonal principal. Puede ser de dos tipos: Triangular Superior, si los elementos que están por debajo de la diagonal principal son todos nulos (en símbolos, aᵢⱼ = 0 para todo i > j); y Triangular Inferior, si los elementos que están por encima de la diagonal principal son todos nulos (en símbolos, aᵢⱼ = 0 para todo i < j)."

---

## 5.14 Matriz Escalonada (o Matriz Canónica o Escalonada)

> 📖 **Textual del material:** "Matriz escalonada
>
>     ⎡ 2   1   0   7  -3 ⎤
> A = ⎢ 0   5   1  -4   1 ⎥
>     ⎣ 0   0   0   3   0 ⎦
>
> Y les presento otro tipo de matriz que veremos más adelante Matriz canónica o escalonada."

**🗣️ En palabras simples:** El material cierra el cuadro de matrices especiales presentando de forma visual la **matriz escalonada** (también mencionada aquí como **matriz canónica o escalonada**, tal como aparecía en el esquema de la página 2 bajo "Operaciones Elementales → Matríz canónica"). Se caracteriza porque al mirar las filas de arriba hacia abajo, la cantidad de ceros iniciales a la izquierda de cada fila va aumentando, formando el dibujo de una "escalera" debajo de los primeros elementos no nulos (`2`, `5` y `3` en el ejemplo). Además, como se ve en el ejemplo `A` de orden `3 × 5`, **no necesita ser cuadrada**.

**🔍 Desglose de la jerga:**
- **Matriz escalonada / Matriz canónica o escalonada:** matriz donde los ceros al comienzo de cada fila forman escalones descendentes de izquierda a derecha.

**💡 Ejemplo:** (Del material, pág. 13)
En la matriz `A` de orden `3 × 5`:
- La fila 1 empieza directamente con `2` (0 ceros a la izquierda).
- La fila 2 empieza con un `0` y luego `5` (1 cero a la izquierda).
- La fila 3 empieza con tres ceros (`0, 0, 0`) y luego `3` (3 ceros a la izquierda).
Los elementos `2`, `5` y `3` marcan los peldaños de la escalera y todo lo que queda debajo y a la izquierda de esa escalera son ceros.

**🔗 Conexiones:** Es el puente directo con el tema de **Operaciones Elementales** y **Matriz Canónica** de las clases siguientes (anunciado en el Esquema de la Unidad de la página 2).

**⚠️ Precisiones / errores comunes:**
- En esta Clase 5 el material sólo la presenta visualmente como anticipo ("que veremos más adelante"). Su tratamiento algorítmico mediante operaciones elementales corresponde a las clases posteriores de la unidad.

**🎤 Cómo decirlo en el oral:** "En la Clase 5 también se presenta como anticipo la matriz escalonada (o matriz canónica o escalonada), que puede ser rectangular y en la cual los ceros al comienzo de cada fila van formando escalones hacia abajo y a la derecha, a la cual se llega mediante las operaciones elementales que se estudian más adelante en la unidad."

---

### 📊 Tabla comparativa de la Clasificación de Matrices (Síntesis teórica)

| Tipo de matriz | ¿Debe ser cuadrada (`n × n`)? | Condición sobre sus dimensiones / elementos (según el material) | Expresión simbólica en el material |
| :--- | :--- | :--- | :--- |
| **Matriz Rectangular** | No (en general `n × m`) | Conjunto de `n.m` números dispuestos en `n` filas y `m` columnas. | `Aₙₓₘ` |
| **Vector Columna** | No (`n × 1`, salvo `1 × 1`) | Matriz que tiene `1` sola columna. | `[a₁₁; a₂₁; ...; aₙ₁]ₙₓ₁` |
| **Vector Fila** | No (`1 × n`, salvo `1 × 1`) | Matriz que tiene `1` sola fila. | `[a₁₁ a₂₁ ... aₙ₁]₁ₓₙ` |
| **Matriz Nula (`0`)** | **No** (`n × m` cualquiera) | Todos sus elementos son ceros. | `Aₙₓₘ es nula ⇔ aᵢⱼ = 0 para todo i,j` |
| **Matriz Cuadrada** | **Sí** (orden `n`) | Tiene el mismo número de filas que de columnas. | `Aₙₓₙ` (orden `n`) |
| **Matriz Diagonal** | **Sí** (orden `n`) | Los elementos que NO pertenecen a la diagonal principal son nulos (`0`). | *(Elementos con `i ≠ j` son `0`)* |
| **Matriz Escalar** | **Sí** (orden `n`) | Matriz diagonal con todos sus elementos de la diagonal iguales. | *(Diagonal con `a₁₁ = ... = aₙₙ`)* |
| **Matriz Identidad o Unidad (`Iₙ`)** | **Sí** (orden `n`) | Matriz cuadrada con los elementos de la diagonal principal iguales a `1` y los restantes `0`. | `Aₙₓₙ es identidad ⇔ aᵢⱼ = 1 cuando i = j ; aᵢⱼ = 0 cuando i ≠ j` |
| **Matriz Triangular Superior** | **Sí** (orden `n`) | Los elementos que están por debajo de la diagonal principal son todos nulos. | `aᵢⱼ > j` *(errata por `aᵢⱼ = 0 para todo i > j`)* |
| **Matriz Triangular Inferior** | **Sí** (orden `n`) | Los elementos que están por encima de la diagonal principal son todos nulos. | `aᵢⱼ = 0 para todo i < j` |
| **Matriz Escalonada** | **No** (`n × m` cualquiera) | Los ceros iniciales de cada fila forman escalones de izquierda a derecha. | *(Presentada gráficamente)* |

---

## 5.15 Igualdad de Matrices y Elementos Correspondientes

> 📖 **Textual del material:** "IGUALDAD DE MATRICES
> Dada dos matrices A y B, estas serán iguales si:
> 1| Son del mismo orden.
> 2| Si los elementos correspondientes (los que ocupan el mismo lugar) son iguales.
> Elementos correspondientes en matrices son aquellos que tienen igual par de subíndices ij.
>
>     ⎛ a₁₁  a₁₂  ...  a₁ₙ ⎞         ⎛ b₁₁  b₁₂  ...  b₁ₙ ⎞
> A = ⎜ a₂₁  a₂₂  ...  a₂ₙ ⎟    Y    B = ⎜ b₂₁  b₂₂  ...  b₂ₙ ⎟
>     ⎜ ...                ⎟         ⎜ ...                ⎟
>     ⎝ aₘ₁  aₘ₂  ...  aₘₙ ⎠         ⎝ bₘ₁  bₘ₂  ...  bₘₙ ⎠
>
> Son elementos correspondientes a₁₁ y b₁₁ a₁₂ y b₁₂; a₂₁ y b₂₁; a₂₂ y b₂₂; ... am1 y bₘ₁; ... aₘ₂ y bₘ₂, etc. No son correspondientes por ejemplo: a₂₁ y b₁₂; a₃₂ y b₂₃; ... amn y bnm, etc.
> No necesariamente, para hablar de igualdad de matrices tenemos que referirnos a matrices cuadradas.
> En símbolos diremos que: A = B ⇔ aᵢⱼ = bᵢⱼ para todo i,j."

**🗣️ En palabras simples:** ¿Cuándo dos matrices `A` y `B` son exactamente la misma matriz (`A = B`)? Tienen que cumplirse **dos requisitos a la vez**:
1. Tienen que tener exactamente el **mismo tamaño** (mismo orden: la misma cantidad de filas y la misma cantidad de columnas).
2. Si las superponemos, cada casillero de `A` tiene que valer exactamente lo mismo que el casillero de `B` que ocupa **el mismo lugar** (la misma fila `i` y la misma columna `j`). A esos elementos que ocupan el mismo lugar se los llama **elementos correspondientes**.

**🔍 Desglose de la jerga:**
- **1| Son del mismo orden:** si `A` es de orden `2 × 3` y `B` es de orden `3 × 2`, jamás pueden ser iguales, aunque tengan los mismos seis números adentro.
- **2| Elementos correspondientes:** son los elementos que ocupan el mismo lugar en ambas matrices; formalmente, **"aquellos que tienen igual par de subíndices ij"** (por ejemplo, `a₂₁` con `b₂₁`, pero **no** `a₂₁` con `b₁₂`).
- **No necesariamente matrices cuadradas:** la igualdad está definida para matrices de cualquier orden `m × n` (siempre que `A` y `B` tengan el mismo orden entre sí).
- **`A = B ⇔ aᵢⱼ = bᵢⱼ para todo i,j`:** asumiendo que tienen el mismo orden, para toda fila `i` y toda columna `j`, el elemento `aᵢⱼ` de `A` debe ser igual al elemento `bᵢⱼ` de `B`.

**💡 Ejemplo:** (Del Desempeño 22 del material, págs. 14 y 15)
Si nos dan la igualdad entre dos vectores columna de orden `2 × 1`:
```
⎡ x - 1 ⎤   ⎡ 2 ⎤
⎣ 5 + y ⎦ = ⎣ 0 ⎦
```
Como ambas matrices tienen el mismo orden (`2 × 1`), para que sean iguales sus **elementos correspondientes** deben ser iguales:
- Primer elemento (`i = 1, j = 1`): `x - 1 = 2  ⇒  x = 3`
- Segundo elemento (`i = 2, j = 1`): `5 + y = 0  ⇒  y = -5`

**🔗 Conexiones:** El concepto de **elementos correspondientes** (igual par de subíndices `ij`) se vuelve a usar inmediatamente en la Clase 6 para definir la **adición y sustracción de matrices** (donde se suman o restan justamente los elementos correspondientes de dos matrices del mismo orden).

**⚠️ Precisiones / errores comunes:**
- **No olvidarse de la condición 1 (mismo orden) al dar la definición en símbolos:** Si en el oral escribís `A = B ⇔ aᵢⱼ = bᵢⱼ para todo i,j`, aclarale siempre al profesor que eso presupone la condición 1: que `A` y `B` **son del mismo orden**.
- **No confundir subíndices invertidos:** `a₂₁` y `b₁₂` **no** son elementos correspondientes, porque el primero está en la fila 2, columna 1 y el segundo está en la fila 1, columna 2.

**🎤 Cómo decirlo en el oral:** "Dadas dos matrices A y B, serán iguales si cumplen dos condiciones: primero, que sean del mismo orden; y segundo, que los elementos correspondientes (es decir, los que ocupan el mismo lugar, aquellos que tienen igual par de subíndices ij) sean iguales. En símbolos: A = B si y sólo si aᵢⱼ = bᵢⱼ para todo i, j. Además, no es necesario que las matrices sean cuadradas para hablar de igualdad de matrices."

---

## 🧠 Resumen esquemático de la clase

- **Disposición preliminar:** Toda disposición rectangular de números en filas y columnas se denomina **matriz**.
- **Matriz `n × m` (Definición formal):** Conjunto de `n.m` números dispuestos en `n` filas y `m` columnas.
- **Orden de una matriz:** Es `n × m` (se lee *"ene por eme"*), donde `n` es la cantidad de filas y `m` la cantidad de columnas.
- **Notación:** Letras mayúsculas para las matrices (`Aₙₓₘ`); corchetes, paréntesis o doble barra para encerrar los elementos; minúsculas con doble subíndice (`aᵢⱼ`) para cada elemento (`i` = N° de fila, `j` = N° de columna).
- **Vector:** Matriz que tiene 1 columna o 1 fila (orden `n × 1` ó `1 × n`). Si es `n × 1` es **vector columna**; si es `1 × n` es **vector fila**.
- **Matriz (otra definición):** Conjunto ordenado de vectores filas, ó conjunto ordenado de vectores columnas.
- **Criterio de clasificación de matrices especiales:** Según su **forma** y según los **elementos que tengan**. En general son **rectangulares**.
- **Matriz nula (`0`):** Matriz cuyos elementos son todos ceros (`Aₙₓₘ es nula ⇔ aᵢⱼ = 0 para todo i,j`). No necesita ser cuadrada.
- **Matriz cuadrada (de orden `n`):** Aquella que tiene el mismo número de filas que de columnas.
- **Diagonales (sólo en matrices cuadradas):** **Diagonal principal** (desde el ángulo superior izquierdo al inferior derecho: `a₁₁, ..., aₙₙ`) y **Diagonal secundaria** (desde el ángulo inferior izquierdo al superior derecho: `aₙ₁, ..., a₁ₙ`).
- **Matriz diagonal:** Matriz cuadrada en la que los elementos que NO pertenecen a la diagonal principal son nulos (iguales a 0).
- **Matriz escalar:** Matriz diagonal con todos sus elementos de la diagonal iguales.
- **Matriz identidad o matriz unidad (`Iₙ`):** Matriz cuadrada con los elementos de la diagonal principal iguales a `1` y los restantes `0` (`aᵢⱼ = 1` cuando `i = j`; `aᵢⱼ = 0` cuando `i ≠ j`).
- **Matriz triangular:** Matriz cuadrada que tiene nulos todos los elementos a un mismo lado de la diagonal principal: **Triangular Superior** (nulos por debajo de la diagonal principal: `aᵢⱼ = 0 ∀ i > j`) y **Triangular Inferior** (nulos por encima de la diagonal principal: `aᵢⱼ = 0 ∀ i < j`).
- **Matriz canónica o escalonada:** Matriz cuyos ceros iniciales por fila forman escalones descendentes de izquierda a derecha.
- **Elementos correspondientes:** Aquellos que ocupan el mismo lugar en dos matrices, es decir, que tienen igual par de subíndices `ij`.
- **Igualdad de matrices (`A = B`):** Dos matrices `A` y `B` son iguales si: 1) son del mismo orden, y 2) sus elementos correspondientes son iguales (`A = B ⇔ aᵢⱼ = bᵢⱼ para todo i,j`).

---

## ❓ Preguntas probables del oral

1. **¿Qué es una matriz y qué es el orden de una matriz?** *(Pregunta 1 y 2 del Desempeño 23)*
   - **Respuesta:** Definimos **matriz `n × m`** a un conjunto de `n.m` números dispuestos en `n` filas y `m` columnas. Decimos que **`n × m`** (se lee *"ene por eme"*) es el **orden** de la matriz.

2. **¿Cómo se puede definir una matriz utilizando el concepto de vector, y qué ventaja tiene esa visualización?**
   - **Respuesta:** Se puede definir diciendo que **una matriz es un conjunto ordenado de vectores filas**, o bien que **una matriz es un conjunto ordenado de vectores columnas**. La ventaja de visualizarla así es que en cada fila o columna hay reunida información del mismo tipo.

3. **¿Qué diferencia hay entre los subíndices de `Aₙₓₘ` y los subíndices de `aᵢⱼ`?**
   - **Respuesta:** En `Aₙₓₘ`, `n` indica la **cantidad de filas** y `m` la **cantidad de columnas** que tiene la matriz en total (su orden). En cambio, en el elemento `aᵢⱼ`, los subíndices indican la **posición del elemento**: `i` es el **N° de fila** y `j` es el **N° de columna** donde se ubica ese elemento.

4. **¿A qué se llama vector? Distinga sus dos casos.** *(Pregunta 3 del Desempeño 23)*
   - **Respuesta:** Cuando una matriz tiene 1 columna o 1 fila se la llama **vector**; es decir, un vector es una matriz de orden `n × 1` ó `1 × n`. En el caso de tener una columna (`n × 1`) se lo llama **vector columna**, y en caso de tener una fila (`1 × n`) se llama **vector fila**.

5. **¿Bajo qué criterios se clasifican las matrices especiales y qué es una matriz rectangular?** *(Pregunta 4 del Desempeño 23)*
   - **Respuesta:** Es posible realizar una clasificación de las matrices **según su forma** y **según los elementos que tengan**. Las matrices, en general, son **rectangulares** (disposición rectangular de números en `n` filas y `m` columnas), y según cuáles sean sus elementos o qué cantidad de filas y columnas tengan, reciben un nombre en particular que las identifica.

6. **¿Qué es la matriz nula? Enúnciela en palabras y en símbolos. ¿Debe ser cuadrada?** *(Pregunta 7 del Desempeño 23)*
   - **Respuesta:** Una matriz cuyos elementos son todos ceros se llama **matriz nula** y se simboliza por `0`. En símbolos: `Aₙₓₘ es nula ⇔ aᵢⱼ = 0 para todo i,j`. Una matriz nula **no necesita ser cuadrada**; puede ser también una matriz fila o una matriz columna.

7. **¿Cuándo una matriz es cuadrada y por qué basta indicar un solo número para su orden?** *(Pregunta 5 del Desempeño 23)*
   - **Respuesta:** Llamamos **matriz cuadrada** a aquella que tiene el mismo número de filas que de columnas. No es necesario indicar el número de filas y de columnas por separado porque ambas son iguales; basta decir que es una **matriz cuadrada de orden n**.

8. **¿Cuál es la diagonal principal y cuál es la diagonal secundaria? ¿En qué matrices existen?** *(Pregunta 6 del Desempeño 23)*
   - **Respuesta:** Existen **sólo para matrices cuadradas**. Los elementos de la **diagonal principal** son los que están desde el ángulo superior izquierdo al inferior derecho (`a₁₁, a₂₂, ..., aₙₙ`), y los elementos de la **diagonal secundaria** son los que están desde el ángulo inferior izquierdo al superior derecho.

9. **Defina matriz diagonal y matriz escalar. ¿Qué relación hay entre ellas?**
   - **Respuesta:** Una **matriz diagonal** es una matriz cuadrada en la que los elementos que NO pertenecen a la diagonal principal son nulos (o sea iguales a 0). Una **matriz escalar** es una matriz diagonal, con todos sus elementos de la diagonal, iguales. Por lo tanto, toda matriz escalar es un caso particular de matriz diagonal.

10. **En una matriz diagonal, ¿puede haber algún cero en la diagonal principal?**
    - **Respuesta:** **Sí**, porque la definición de matriz diagonal sólo exige que los elementos que **no pertenecen** a la diagonal principal sean nulos (iguales a 0), sin imponer restricciones a los elementos que sí pertenecen a la diagonal principal.

11. **¿Cuál es la matriz identidad o matriz unidad? Enúnciela en palabras y en símbolos.** *(Pregunta 7 del Desempeño 23)*
    - **Respuesta:** Definimos **matriz identidad** (o **matriz unidad**) como una matriz cuadrada que tiene los elementos de la diagonal principal iguales a uno y los restantes son ceros. Se la simboliza con `Iₙ` (donde el subíndice indica el orden). En símbolos: `Aₙₓₙ es identidad ⇔ aᵢⱼ = 1 cuando i = j` y `aᵢⱼ = 0 cuando i ≠ j`.

12. **¿Qué es una matriz triangular y cuáles son sus dos tipos?**
    - **Respuesta:** Es una matriz cuadrada que tiene nulos todos los elementos que están a un mismo lado de la diagonal principal. Puede ser de dos tipos:
      - **Triangular Superior:** si los elementos que están por debajo de la diagonal principal son todos nulos (`aᵢⱼ = 0 para todo i > j`).
      - **Triangular Inferior:** si los elementos que están por encima de la diagonal principal son todos nulos (`aᵢⱼ = 0 para todo i < j`).

13. **¿Cuándo dos matrices A y B son iguales y qué son los elementos correspondientes?**
    - **Respuesta:** Dadas dos matrices `A` y `B` (no necesariamente cuadradas), serán iguales si: **1)** son del mismo orden, y **2)** los elementos correspondientes (los que ocupan el mismo lugar) son iguales. **Elementos correspondientes** en matrices son aquellos que tienen igual par de subíndices `ij`. En símbolos: `A = B ⇔ aᵢⱼ = bᵢⱼ para todo i,j`.

---

## 📚 Glosario de la clase

| Término | Definición breve fiel al material |
| :--- | :--- |
| **Matriz (concepto general)** | Disposición rectangular de números en filas y columnas. |
| **Matriz `n × m`** | Conjunto de `n.m` números dispuestos en `n` filas y `m` columnas. |
| **Matriz (como vectores)** | Conjunto ordenado de vectores filas, ó conjunto ordenado de vectores columnas. |
| **Orden de una matriz** | Expresión `n × m` (se lee "ene por eme") donde `n` indica la cantidad de filas y `m` la cantidad de columnas. |
| **Elemento `aᵢⱼ`** | Elemento de la matriz ubicado en la fila `i` (N° de fila) y la columna `j` (N° de columna). |
| **Vector** | Matriz que tiene 1 columna o 1 fila; es decir, una matriz de orden `n × 1` ó `1 × n`. |
| **Vector columna** | Vector que tiene una sola columna (matriz de orden `n × 1`). |
| **Vector fila** | Vector que tiene una sola fila (matriz de orden `1 × n`). |
| **Matriz nula (`0`)** | Matriz cuyos elementos son todos ceros (`Aₙₓₘ es nula ⇔ aᵢⱼ = 0 para todo i,j`). No necesita ser cuadrada. |
| **Matriz cuadrada** | Matriz que tiene el mismo número de filas que de columnas (se dice de orden `n`). |
| **Diagonal principal** | En una matriz cuadrada, los elementos que están desde el ángulo superior izquierdo al inferior derecho (`a₁₁, a₂₂, ..., aₙₙ`). |
| **Diagonal secundaria** | En una matriz cuadrada, los elementos que están desde el ángulo inferior izquierdo al superior derecho. |
| **Matriz diagonal** | Matriz cuadrada en la que los elementos que NO pertenecen a la diagonal principal son nulos (iguales a 0). |
| **Matriz escalar** | Matriz diagonal, con todos sus elementos de la diagonal, iguales. |
| **Matriz identidad o unidad (`Iₙ`)** | Matriz cuadrada que tiene los elementos de la diagonal principal iguales a uno (`aᵢⱼ = 1` cuando `i = j`) y los restantes son ceros (`aᵢⱼ = 0` cuando `i ≠ j`). |
| **Matriz triangular** | Matriz cuadrada que tiene nulos todos los elementos que están a un mismo lado de la diagonal principal. |
| **Matriz triangular superior** | Matriz cuadrada en la que los elementos que están por debajo de la diagonal principal son todos nulos (`aᵢⱼ = 0` para todo `i > j`; en el apunte impreso como `aᵢⱼ > j`). |
| **Matriz triangular inferior** | Matriz cuadrada en la que los elementos que están por encima de la diagonal principal son todos nulos (`aᵢⱼ = 0` para todo `i < j`). |
| **Matriz canónica o escalonada** | Matriz en la que los ceros al comienzo de cada fila forman escalones descendentes hacia la derecha. |
| **Elementos correspondientes** | Elementos de dos matrices que ocupan el mismo lugar, es decir, aquellos que tienen igual par de subíndices `ij`. |
| **Igualdad de matrices (`A = B`)** | Relación entre dos matrices `A` y `B` que se cumple si: 1) son del mismo orden y 2) los elementos correspondientes son iguales (`A = B ⇔ aᵢⱼ = bᵢⱼ para todo i,j`). |
