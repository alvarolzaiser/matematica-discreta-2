# Clase 3 — Funciones Booleanas

## 🗺️ Mapa de la clase

- **Unidad 01 — Álgebra de Boole (Clase 03: Funciones Booleanas)**
  - **Objetivo explícito del material:** *"Al finalizar la clase los alumnos: • Funciones Booleanas y su modo de escribirlas."*
  - **1. Definición y naturaleza de las Funciones Booleanas (Pág. 2)**
    - Concepto general de función heredado de Matemática Discreta 1 (relación entre variable independiente y una única variable dependiente).
    - Definición de **Función Booleana** como combinación de variables mediante las tres operaciones ya definidas (suma, producto, complemento).
    - Diferencia fundamental con las funciones numéricas ordinarias: restricción binaria estricta (las variables y la función solo pueden tomar el valor 0 ó 1).
    - Evaluación de funciones Booleanas de 1, 2, 3, 4 o más variables.
  - **2. Tablas de Verdad para Funciones Booleanas (Págs. 2–3)**
    - Definición y finalidad de las **Tablas de verdad** (mostrar todos los resultados posibles según las combinaciones de entrada).
    - Regla de la cantidad de combinaciones posibles: siempre es **2ⁿ** (también escrito 2^n), donde *n* es la cantidad de variables.
    - Método paso a paso para confeccionar una tabla de verdad (columnas de variables, columnas de resultados parciales y última columna con el valor de la función).
    - Lectura directa (de entradas a salida) y lectura inversa (de derecha a izquierda: qué entradas hacen que la función valga 1 ó 0).
  - **3. Circuitos Lógicos y Compuertas Lógicas (Págs. 3–5)**
    - Definición de **circuitos lógicos** y **compuertas lógicas** como símbolos que representan operaciones.
    - Clasificación de las **5 compuertas lógicas**: tres correspondientes a las operaciones definidas (**OR**, **AND**, **NOT**) y dos correspondientes al complemento de la suma y del producto (**NOR**, **NAND**).
    - Propiedad estructural: casi todas admiten más de una entrada, pero **siempre tienen una sola salida**.
    - Construcción de circuitos lógicos a partir de la expresión algebraica ("implementar con compuertas lógicas") y obtención de la función a partir del circuito.
  - **4. Los tres modos de representar una Función Booleana y conexión con Formas Canónicas (Págs. 4–5)**
    - Las tres representaciones equivalentes: **expresión algebraica**, **tabla de verdad** y **circuito lógico**.
    - Pasaje entre representaciones y anticipo del concepto de **forma canónica** (necesaria para obtener la expresión algebraica desde la tabla de verdad, tema de la Clase 4).
    - Vínculo con la simplificación (Desempeños 8 y 9): una expresión original y su versión simplificada comparten la misma tabla de verdad, pero producen circuitos lógicos más simples.

- **Prerrequisitos (de MD1 y Clases 1–2 de MD2):**
  - **De MD1:** Concepto de *relación* y de *función* (existencia y unicidad de imagen para cada valor de la variable independiente), y confección de tablas de verdad para fórmulas bien formadas (FBF) en lógica proposicional.
  - **De Clase 1 y Clase 2 de MD2:** Definición axiomática del Álgebra de Boole sobre el conjunto {0, 1}, las tres operaciones básicas (**suma booleana** `+`, **producto booleano** `·` o `.`, y **complemento** representado con barra superior `Ā`), sus tablas de operación, la representación mediante circuitos eléctricos (serie/paralelo) y la simplificación algebraica mediante postulados, propiedades y Leyes de De Morgan.

---

## 3.1 Definición de Función y de Función Booleana

> 📖 **Textual del material:** "Así como vimos en la MD1, una función es una relación entre dos variables, para la que se debe cumplir que una variable independiente se debe relacionar con una y solo una variable dependiente, en el Álgebra de Boole también existen funciones, que llamamos justamente Booleanas, que resultan de combinar un número de variables mediante las tres operaciones ya definidas."

> 📖 **Textual del material (diferencia con funciones numéricas):** "Un ejemplo de función como las que vimos en el cuatrimestre anterior sería f (x) = 2 x + 3 en ella decimos que si x toma el valor 1, la función vale 5, f (1) = 5; si x toma el valor 4 la función vale 11, f (4) = 11; y así con cualquier valor que le querramos dar a la variable x será otro valor el de la función.
> La gran diferencia entre estas funciones y las Booleanas es que, como ya lo dijimos desde el principio, las variables solo pueden tomar el valor 0 ó 1. Entonces si una variable vale 0, la función podría ser 0 ó 1, y si la variable fuera 1, la función podría ser solo 0 ó 1."

**🗣️ En palabras simples:**
Una función común (como las de análisis matemático o MD1) es una máquina que recibe un número, le hace cuentas (multiplicar, sumar) y devuelve **un único** resultado. Una **Función Booleana** es exactamente la misma idea de máquina, pero viviendo dentro del mundo binario del Álgebra de Boole: las variables que entran solo pueden valer **0 ó 1**, las cuentas que se les hacen adentro son únicamente las **tres operaciones booleanas** (suma `+`, producto `.` y complemento `¯`), y el resultado final que sale de la función también es única y obligatoriamente **0 ó 1**.

**🔍 Desglose de la jerga:**
- **"relación entre dos variables"**: En el sentido general visto en MD1, vincula un conjunto de partida (las entradas o variables independientes) con un conjunto de llegada (la salida o variable dependiente, que es el valor de la función F).
- **"una variable independiente se debe relacionar con una y solo una variable dependiente"**: Es la condición de **existencia y unicidad** que define a toda función. Para cada combinación fija de valores de entrada, la función no puede quedar indecisa ni devolver dos resultados a la vez: devuelve o bien 0, o bien 1 (uno y solo uno).
- **"combinar un número de variables"**: Una función Booleana puede depender de una sola variable, como F(B), o de varias variables independientes simultáneamente, como F(A, B), F(A, B, C), F(A, B, C, D), etc.
- **"mediante las tres operaciones ya definidas"**: Se refiere exclusivamente a las tres operaciones fundamentales del Álgebra de Boole definidas en las clases anteriores:
  1. **Suma booleana** (`+`)
  2. **Producto booleano** (`.` o `•`)
  3. **Complemento o inversión** (barra superior, p. ej. `Ā`)
- **"las variables solo pueden tomar el valor 0 ó 1"**: Tanto el dominio de cada variable de entrada como la imagen (valor de salida de la función) pertenecen al conjunto binario B = {0, 1}. En notación matemática formal (contexto adicional): si hay *n* variables, es una función F: {0, 1}^n → {0, 1}.

**💡 Ejemplo:**
- **Función numérica (MD1):** `f (x) = 2 x + 3`. Si `x = 1`, `f (1) = 5`; si `x = 4`, `f (4) = 11`. Admite infinitos valores posibles de entrada y de salida.
- **Función Booleana de una variable (del material):** `F (B) = B̄`.
  - Si `B = 0`, entonces `F (0) = 0̄ = 1`.
  - Si `B = 1`, entonces `F (1) = 1̄ = 0`.
  No existen más valores posibles para evaluar.

**🔗 Conexiones:**
- **Con Matemática Discreta 1 (Relaciones y Funciones):** Recupera la definición exacta de función como relación funcional (unicidad de imagen).
- **Con Clase 1 y Clase 2 (Álgebra de Boole):** Las expresiones algebraicas que simplificábamos en la Clase 2 empleando postulados y teoremas son las expresiones que definen a estas funciones Booleanas.
- **Con Clase 4 (Formas Canónicas):** Toda función Booleana, sin importar cuán compleja sea su expresión, quedará unívocamente determinada por los 0 y 1 que devuelve, lo que permitirá escribirla en forma canónica (minitérminos y maxitérminos).

**⚠️ Precisiones / errores comunes:**
- **No olvidar la condición de función al definirla en el oral:** Si el profesor pregunta "¿Qué es una función Booleana?", no basta con decir "son letras con sumas y productos". Hay que mencionar primero qué es una función (relación en la que cada variable independiente se relaciona con **una y solo una** variable dependiente) y luego especificar que en el Álgebra de Boole resulta de **combinar un número de variables mediante las tres operaciones ya definidas**, donde tanto las variables como la función **solo pueden tomar el valor 0 ó 1**.
- **No confundir suma y producto booleanos con aritmética común:** En `f(x) = 2x + 3` el `+` es suma aritmética; en una función Booleana nunca aparecen coeficientes como `2` ni `3`, porque los únicos elementos del conjunto son `0` y `1` y `1 + 1 = 1`.

**🎤 Cómo decirlo en el oral:**
> *"Como vimos en MD1, una función es una relación entre variables en la que cada valor de la variable independiente se relaciona con uno y solo un valor de la variable dependiente. En el Álgebra de Boole, las funciones Booleanas son aquellas que resultan de combinar un número de variables mediante las tres operaciones ya definidas: suma, producto y complemento. La gran diferencia con las funciones numéricas comunes es que en las funciones Booleanas tanto las variables como el resultado de la función solo pueden tomar el valor 0 ó 1."*

---

## 3.2 Funciones Booleanas de Una, Dos o Más Variables y su Evaluación

> 📖 **Textual del material:** "Un ejemplo de función Booleana con una sola variable puede ser: F (B) = B̄
> Para esta función, si B toma el valor 0, la función vale 1, y viceversa, es decir: F (0) = 1 y F (1) = 0
>
> Pero lo más común no es que las funciones sean de una sola variable sino dos o más. Por ejemplo la siguiente: F (A, B) = A . B̄
> En este caso entonces, ya no solo es una variable la que puede tomar los valores 0 ó 1, sino dos, por lo que las posibles combinaciones que se pueden dar para los valores de las variables son 4. Por ejemplo si A vale 0 y B vale 0, la función valdría 0, es decir F (0,0) = 0 . 0̄ = 0 . 1 = 0.
> Si A vale 1 y B vale 0, la función valdría 1, es decir: F (1,0) = 1 . 0̄ = 1 . 1 = 1
> Le dejo como actividad para resolver ahora mismo, encuentre el valor de la función anterior para las dos posibles combinaciones que faltan.
> Así mismo podemos seguir escribiendo funciones Booleanas con tres, cuatro, cinco o más variables, como por ejemplo:
> F (A, B, C) = (A + C) . B + Ā
> F (A, B, C, D) = D . B̄ + C + A . B
> Encuentre el valor las funciones arriba escritas, para los siguientes valores de las variables:
> F (1,1,0) y F (0,1,0)
> F (0,1,0,1) y F (1,0,1,1)"

**🗣️ En palabras simples:**
La notación `F(A, B, C)` indica cómo se llama la función (`F`) y cuáles son las variables de entrada de las que depende (`A`, `B` y `C`, en ese orden). **Evaluar** una función Booleana en una combinación particular (por ejemplo `F(1, 1, 0)`) consiste simplemente en reemplazar cada letra por su valor (0 ó 1) respetando el orden en que están escritas entre paréntesis, y calcular el resultado aplicando las reglas de complemento, producto y suma del Álgebra de Boole.

**🔍 Desglose de la jerga:**
- **`F (A, B, C)`**: Encabezado o firma de la función. `F` (o `G`, etc.) es el nombre de la función (variable dependiente); la lista entre paréntesis `(A, B, C)` declara las variables independientes de entrada y fija su **orden posicional**.
- **`F (1, 1, 0)`**: Evaluación puntual de la función cuando la primera variable (`A`) vale 1, la segunda (`B`) vale 1 y la tercera (`C`) vale 0.
- **Notación de producto**: El material utiliza indistintamente el punto bajo `.` (como en `A . B̄`), el punto medio `•` o `·` (como en `A • B`) o la yuxtaposición sin símbolo (como en `ABC` en el Desempeño 7) para indicar el producto booleano.
- **Notación de letras mayúsculas o minúsculas**: El material usa habitualmente mayúsculas (`A, B, C, D`), pero también admite minúsculas (`F(a, b, c)` en el Desempeño 9).

**💡 Ejemplo (incluyendo la resolución de las actividades breves planteadas en la cita):**
1. **Para `F (A, B) = A . B̄`:**
   - Del material: `F (0,0) = 0 . 0̄ = 0 . 1 = 0` y `F (1,0) = 1 . 0̄ = 1 . 1 = 1`.
   - Las dos combinaciones restantes (explicación adicional completando la pregunta del texto):
     - Si `A = 0` y `B = 1`: `F (0,1) = 0 . 1̄ = 0 . 0 = 0`.
     - Si `A = 1` y `B = 1`: `F (1,1) = 1 . 1̄ = 1 . 0 = 0`.
2. **Para `F (A, B, C) = (A + C) . B + Ā`:**
   - `F (1,1,0) = (1 + 0) . 1 + 1̄ = 1 . 1 + 0 = 1 + 0 = 1`.
   - `F (0,1,0) = (0 + 0) . 1 + 0̄ = 0 . 1 + 1 = 0 + 1 = 1`.
3. **Para `F (A, B, C, D) = D . B̄ + C + A . B`:**
   - `F (0,1,0,1)` (donde `A=0, B=1, C=0, D=1`): `1 . 1̄ + 0 + 0 . 1 = 1 . 0 + 0 + 0 = 0`.
   - `F (1,0,1,1)` (donde `A=1, B=0, C=1, D=1`): `1 . 0̄ + 1 + 1 . 0 = 1 . 1 + 1 + 0 = 1 + 1 + 0 = 1`.

**🔗 Conexiones:**
- **Con Tablas de Verdad (Sección 3.3 y 3.4):** Evaluar la función una por una en todas las combinaciones posibles de sus variables es exactamente lo que se sistematiza al construir su tabla de verdad.
- **Con Jerarquía de Operaciones (Clases 1 y 2):** Al evaluar numéricamente una expresión booleana se respeta la precedencia: primero paréntesis y barras que abarcan toda una subexpresión, luego complementos individuales, luego productos (`.`) y finalmente sumas (`+`).

**⚠️ Precisiones / errores comunes:**
- **Respetar el orden de las variables en `F(A, B, C, D)`:** En `F(A, B, C, D) = D . B̄ + C + A . B`, aunque en la fórmula la primera letra que aparece escrita a la izquierda es `D`, al evaluar `F(0, 1, 0, 1)` el primer valor (`0`) corresponde a `A` y el cuarto valor (`1`) corresponde a `D`, porque manda el orden declarado en el paréntesis `F(A, B, C, D)`.
- **Diferencia entre `Ā + B̄` y `(A + B)̄` [con barra única sobre `A + B`]:**
  - Si la barra está cortada sobre cada letra (`Ā + B̄`), primero se complementa cada variable y después se suma.
  - Si la barra es continua sobre toda la operación (como en `(A + C)̄` de la página 3), primero se resuelve la operación de adentro (`A + C`) y al resultado final se le calcula el complemento.

**🎤 Cómo decirlo en el oral:**
> *"Una función Booleana puede depender de una, dos, tres o más variables. Se escribe indicando el nombre de la función y entre paréntesis las variables que intervienen, por ejemplo F(A, B, C). Para encontrar el valor de la función en una combinación dada, se reemplaza cada variable por su valor 0 ó 1 respetando el orden del paréntesis y se resuelven las operaciones de complemento, producto y suma."*

---

## 3.3 Tablas de Verdad para Funciones Booleanas

> 📖 **Textual del material:** "Así como las funciones toman un valor dependiendo el valor 0 o 1 que tome cada variable que interviene en ella, a los fines de conocer el resultado para todas las posibles combinaciones resulta mucho más práctico la confección de tablas, denominadas Tablas de verdad, que nos mostrarán todos los resultados."

> 📖 **Textual del material (lectura e interpretación de la tabla):** "Entonces en esta tabla podemos ver todos los resultados de la función a partir de las diferentes entradas (valores de las variables). Así por ejemplo si A = 1, B = 1 y C = 0, la función toma el valor 0. Si lo miramos de derecha a izquierda, podemos ver que la función es 1, si A = 0, B = 0 y C = 0, entre otras posibilidades."

**🗣️ En palabras simples:**
En lugar de calcular el valor de una función Booleana en combinaciones sueltas al azar, armamos un cuadro ordenado llamado **Tabla de verdad** donde listamos **absolutamente todas** las combinaciones posibles de 0 y 1 de las variables de entrada y calculamos qué valor devuelve la función en cada fila. Como la cantidad de variables es finita y solo toman valores 0 ó 1, la tabla de verdad describe a la función de manera **total y exhaustiva**.

**🔍 Desglose de la jerga:**
- **"todas las posibles combinaciones"**: El conjunto exhaustivo de asignaciones de 0 y 1 a las variables independientes. Ninguna combinación queda afuera.
- **"Tablas de verdad"**: Nombre heredado de la lógica proposicional (MD1), adaptado aquí a funciones del Álgebra de Boole con valores 0 y 1.
- **"entradas (valores de las variables)"**: Cada fila de valores asignados a las variables independientes (por ejemplo `A = 1, B = 1, C = 0`).
- **Lectura de izquierda a derecha vs. lectura de derecha a izquierda**:
  - **De izquierda a derecha (evaluación):** Dada una entrada conocida, buscamos su fila y leemos en la última columna cuánto vale la función.
  - **De derecha a izquierda (análisis inverso):** Miramos en la última columna dónde la función vale 1 (o dónde vale 0) y leemos hacia la izquierda qué combinaciones de entrada produjeron ese resultado.

**💡 Ejemplo (del material, Pág. 3):**
Para la función `F (A, B, C) = B . C + Ā`:
- **Mirando de izquierda a derecha:** En la fila donde la entrada es `A = 1, B = 1, C = 0`, buscamos el final de la fila y vemos que la función toma el valor `0`.
- **Mirando de derecha a izquierda:** Si preguntamos "¿cuándo la función vale 1?", miramos los `1` de la última columna y vemos hacia la izquierda que ocurre cuando `A = 0, B = 0, C = 0` (y también en `(0,0,1)`, `(0,1,0)`, `(0,1,1)` y `(1,1,1)`).

**🔗 Conexiones:**
- **Con Matemática Discreta 1 (Lógica Proposicional):** El propio material destaca: *"Esto es muy similar a lo que realizábamos en MD 1, al hacer las tablas de verdad para las fórmulas bien formadas… se acuerdan?"*. En MD1 usábamos V/F (o 1/0) con conectivos lógicos (`∧, ∨, ¬`); aquí usamos `0` y `1` con operaciones booleanas (`. , + , ¯`).
- **Con Clase 4 (Formas Canónicas):** Esa lectura "de derecha a izquierda" (identificar exactamente en qué filas la función da `1` o da `0`) es el paso clave que usaremos en la Clase 4 para armar la forma canónica de una función a partir de su tabla de verdad.
- **Con Equivalencia de Funciones (Desempeño 9):** Dos expresiones booleanas distintas (por ejemplo, una función sin simplificar y su versión simplificada) representan la **misma función Booleana** si y solo si sus tablas de verdad dan exactamente la misma columna final de resultados.

**⚠️ Precisiones / errores comunes:**
- **Nota sobre una errata tipográfica en la Pág. 3 del PDF:** En el renglón previo a la tabla de la página 3, el texto impreso dice *"A partir de la función F (A, B, C) = B . C + A realizaremos su tabla de verdad"* (sin la barra sobre la A), pero inmediatamente adentro del cuadro de la tabla las columnas son `Ā` y `B . C + Ā`, y todos los valores calculados corresponden a `B . C + Ā`. En el oral, si mencionás este ejemplo, aclaralo como `F(A, B, C) = B . C + Ā`.

**🎤 Cómo decirlo en el oral:**
> *"Una tabla de verdad para una función Booleana es una tabla que muestra los resultados de la función para todas las posibles combinaciones de valores 0 y 1 que pueden tomar las variables que intervienen en ella. Nos permite tanto ver qué valor toma la función a partir de una entrada determinada (leyendo de izquierda a derecha), como identificar para qué combinaciones de las variables la función vale 1 ó 0 (leyendo de derecha a izquierda)."*

---

## 3.4 Regla de la Cantidad de Combinaciones (2ⁿ) y Método de Confección de la Tabla de Verdad

> 📖 **Textual del material:** "Para confeccionarlas, se deberán colocar las variables que intervienen, una por columna y debajo de ellas todas las combinaciones de 0 y 1 posibles. Deberá tener en cuenta que la cantidad de posibilidades será siempre 2ⁿ donde n es la cantidad de variables. Así por ejemplo si en la función hay 2 variables serán 2² es decir 4 combinaciones, si en la función intervienen 3 variables la cantidad de combinaciones será 8, ya que 2³ = 8, y así para cualquier cantidad.
> A partir de allí, en columnas siguientes se irán completando los resultados parciales según las operaciones que vinculan a las variables. La última columna debería indicar el valor de la función, para cada combinación de entrada."

> 📖 **Textual del material (reglas operativas recordadas en la tabla de la Pág. 3):**
> - "Recuerde que en el producto si hay un 0 el resultado será 0"
> - "Recuerde que el complemento es lo contrario"
> - "Y por último no olvide que en la suma si hay un 1 el resultado es 1"

**🗣️ En palabras simples:**
Este es el procedimiento estándar (algoritmo) para armar cualquier tabla de verdad sin olvidarse ninguna fila ni equivocarse en las cuentas:
1. Primero contás cuántas variables distintas tiene la función (llamemos *n* a esa cantidad) y calculás **2ⁿ** (2 elevado a la *n*) para saber cuántas filas tendrá la tabla.
2. Ponés una columna por cada variable de entrada y llenás las 2ⁿ filas con todas las combinaciones posibles de 0 y 1.
3. Agregás columnas intermedias para cada operación parcial de la fórmula.
4. En la última columna ponés la expresión completa de la función y calculás su resultado final fila por fila usando las tres reglas rápidas: en el producto un solo `0` anula todo a `0`; el complemento invierte `0 ↔ 1`; en la suma un solo `1` hace que todo dé `1`.

**🔍 Desglose de la jerga y del método paso a paso:**
- **Fórmula `2ⁿ` (o `2^n`)**:
  - `2` es la base porque cada variable booleana tiene exactamente **2 posibilidades** (`0` ó `1`).
  - `n` es el exponente y representa la **cantidad de variables** de entrada que intervienen en la función.
  - Ejemplos directos:
    - Si `n = 1` variable → `2¹ = 2` combinaciones (filas).
    - Si `n = 2` variables → `2² = 4` combinaciones (filas).
    - Si `n = 3` variables → `2³ = 8` combinaciones (filas).
    - Si `n = 4` variables → `2⁴ = 16` combinaciones (filas).
- **"resultados parciales según las operaciones que vinculan a las variables"**: Son las columnas intermedias (por ejemplo, calcular primero `B . C` en una columna y `Ā` en otra antes de sumarlos). En la actividad de la página 3 el material pide explícitamente: *"utilizando una columna para cada operación que intervenga, y que la última sea la correspondiente al resultado de la función"*.
- **Ordenamiento sistemático de las filas (contexto práctico reflejado en la tabla del material):**
  Observando la tabla de 3 variables (`A, B, C`) de la página 3, las 8 filas están ordenadas en conteo binario creciente del `000` al `111`:
  - La primera columna (`A`) tiene cuatro `0` seguidos y luego cuatro `1` seguidos (mitad y mitad: 4 y 4).
  - La segunda columna (`B`) alterna de a dos: `0, 0, 1, 1, 0, 0, 1, 1`.
  - La tercera columna (`C`) alterna de a uno: `0, 1, 0, 1, 0, 1, 0, 1`.
  Este patrón garantiza no repetir ni omitir ninguna de las `2ⁿ` combinaciones.

**🧩 Justificación / Idea de por qué la cantidad de combinaciones es 2ⁿ:**
*(Contexto adicional basado en combinatoria básica vista en MD1):* Como cada una de las *n* variables independientes puede elegir su valor de forma independiente entre 2 opciones (`0` ó `1`), por el principio multiplicativo del conteo tenemos `2 × 2 × ... × 2` (*n* veces) = `2ⁿ` combinaciones posibles en total.

**🤔 Intuición de las tres reglas rápidas del cuadro (Pág. 3):**
- **En el producto (`B . C`), "si hay un 0 el resultado será 0":** Porque el `0` es el elemento absorbente del producto booleano (`x . 0 = 0`). Solo da `1` cuando **todas** las factores valen `1`.
- **En el complemento (`Ā`), "es lo contrario":** Porque por definición de complemento, `0̄ = 1` y `1̄ = 0`.
- **En la suma (`B . C + Ā`), "si hay un 1 el resultado es 1":** Porque el `1` es el elemento absorbente de la suma booleana (`x + 1 = 1`). Solo da `0` cuando **todos** los sumandos valen `0`.

**💡 Ejemplo completo (Tabla de verdad textual de la Pág. 3 para `F (A, B, C) = B . C + Ā`):**

| A | B | C | B . C | Ā | B . C + Ā |
| :-: | :-: | :-: | :-: | :-: | :-: |
| 0 | 0 | 0 | 0 | 1 | 1 |
| 0 | 0 | 1 | 0 | 1 | 1 |
| 0 | 1 | 0 | 0 | 1 | 1 |
| 0 | 1 | 1 | 1 | 1 | 1 |
| 1 | 0 | 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 0 | 0 | 0 |
| 1 | 1 | 0 | 0 | 0 | 0 |
| 1 | 1 | 1 | 1 | 0 | 1 |

**🔗 Conexiones:**
- **Con Clase 1 (Tablas de las operaciones básicas):** Las tres notas al margen de la tabla en la página 3 son el resumen práctico de las tablas de verdad del producto, complemento y suma vistas en la Clase 1.
- **Con Clase 4 (Minitérminos y Maxitérminos):** Cada una de las `2ⁿ` filas de la tabla de verdad se corresponderá en la Clase 4 con un único minitérmino y un único maxitérmino.

**⚠️ Precisiones / errores comunes:**
- **Confundir `2ⁿ` con `2 . n` o `n²`:** Con 3 variables no son `2 × 3 = 6` ni `3² = 9` combinaciones, sino `2³ = 8`. Con 4 variables no son `4² = 16` por elevar al cuadrado, sino `2⁴ = 16` (si fueran 5 variables serían `2⁵ = 32`, no `5² = 25`). Siempre la base es 2 y el exponente es *n*.
- **Saltarse columnas de operaciones parciales:** El material insiste en colocar una columna para cada operación parcial antes de la columna final para evitar errores de precedencia (especialmente cuando hay complementos que abarcan sumas o productos completos, como en `F(A, B, C) = ((A + C)̄ + B) . C`).

**🎤 Cómo decirlo en el oral:**
> *"Para confeccionar una tabla de verdad se coloca una columna por cada variable que interviene y debajo todas las combinaciones posibles de 0 y 1. La cantidad de combinaciones es siempre 2ⁿ, donde n es la cantidad de variables (por ejemplo, para 2 variables son 2² = 4 combinaciones; para 3 variables son 2³ = 8). En las columnas siguientes se completan los resultados parciales de cada operación que vincula a las variables —recordando que en el producto si hay un 0 el resultado es 0, el complemento es lo contrario, y en la suma si hay un 1 el resultado es 1— y la última columna indica el valor final de la función para cada combinación de entrada."*

---

## 3.5 Circuitos Lógicos y Compuertas Lógicas: Definición y Propiedades

> 📖 **Textual del material:** "Así como pudimos asociar a las diferentes operaciones, de suma, producto y complemento con algunos circuitos eléctricos, existe otra manera de representar las funciones Booleanas, por medio de los circuitos lógicos, los que se realizan empleando las llamadas “compuertas lógicas”. Cada compuerta lógica es un símbolo que representa a una operación, hay tres que corresponden a las tres operaciones definidas y dos que corresponden al complemento de la suma y del producto."

> 📖 **Textual del material (sobre entradas y salidas):** "Si observas bien podrás notar que en casi todos los casos puede haber más de una entrada, pero siempre habrá una sola salida."

> 📖 **Textual del material (sinonimia en Desempeño 7, Pág. 5):** "Implementa con compuertas lógicas las siguientes funciones, que es lo mismo que decir realice el circuito lógico correspondiente"

**🗣️ En palabras simples:**
En las Clases 1 y 2 dibujábamos circuitos eléctricos con llaves (interruptores en serie o en paralelo) y una lámpara. Ahora damos un paso hacia la electrónica digital moderna: representamos las funciones Booleanas mediante **circuitos lógicos**, que son diagramas formados por bloques simbólicos llamados **compuertas lógicas**. Cada compuerta es un dibujo estándar que recibe una o varias señales de entrada (variables o resultados previos) por la izquierda, les aplica una operación booleana específica, y entrega **un único resultado** por su línea de salida a la derecha.

**🔍 Desglose de la jerga:**
- **"circuitos eléctricos" vs. "circuitos lógicos"**:
  - Los *circuitos eléctricos* (Clases 1–2) usan interruptores/llaves en paralelo (suma) o en serie (producto).
  - Los *circuitos lógicos* (Clase 3) usan **compuertas lógicas** (OR, AND, NOT, NOR, NAND).
- **"compuerta lógica"**: Es un **símbolo** gráfico normalizado que representa a una operación booleana.
- **"tres que corresponden a las tres operaciones definidas"**: Son las compuertas básicas **OR** (suma), **AND** (producto) y **NOT** (complemento).
- **"dos que corresponden al complemento de la suma y del producto"**: Son las compuertas compuestas o negadas **NOR** (complemento de la suma) y **NAND** (complemento del producto).
- **"en casi todos los casos puede haber más de una entrada, pero siempre habrá una sola salida"**:
  - ¿Por qué dice *"en casi todos los casos"* puede haber más de una entrada? Porque la única excepción es la compuerta **NOT** (complemento), que opera sobre **una sola** variable y por lo tanto tiene **una sola entrada** (y una sola salida). En cambio, las compuertas OR, AND, NOR y NAND tienen **dos o más entradas** (por ejemplo, en el circuito de la página 4 aparece una compuerta OR de 3 entradas).
  - ¿Por qué dice *"siempre habrá una sola salida"*? Porque cada compuerta representa una operación funcional que devuelve un único valor booleano (0 ó 1) para las entradas recibidas.
- **"Implementar con compuertas lógicas"**: Expresión técnica equivalente a *"realizar el circuito lógico correspondiente"* a una función Booleana.

**💡 Ejemplo:**
Si una función suma tres términos, como `B . C + Ā + B`, no hace falta usar dos compuertas OR de 2 entradas encadenadas: se puede usar directamente **una sola compuerta OR con 3 líneas de entrada** y **1 sola línea de salida** (tal como hace el material en el circuito de la página 4).

**🔗 Conexiones:**
- **Con Clase 1 y 2 (Circuitos Eléctricos):** Es la evolución directa de la representación física: el paralelo pasa a ser la compuerta OR y la serie pasa a ser la compuerta AND, con la gran ventaja de que en los circuitos lógicos el complemento (`NOT`, `NOR`, `NAND`) tiene su propio símbolo directo (el triángulo o el circulito inversor), mientras que en llaves eléctricas requería llaves acopladas inversamente.

**⚠️ Precisiones / errores comunes:**
- **No confundir "circuito eléctrico" con "circuito lógico" en el oral:** Si el profesor pide representar una función mediante un *circuito lógico*, hay que hablar de **compuertas lógicas** (AND, OR, NOT, etc.), no de llaves en serie y paralelo.
- **Recordar la frase exacta del porqué de "casi todos los casos":** Un profesor atento suele preguntar: *"¿Todas las compuertas lógicas pueden tener varias entradas?"*. La respuesta exacta según el material es: **casi todas** (OR, AND, NOR, NAND pueden tener 2, 3 o más entradas), **excepto la compuerta NOT**, que solo tiene una entrada; y **todas sin excepción tienen una sola salida**.

**🎤 Cómo decirlo en el oral:**
> *"Los circuitos lógicos son otra manera de representar las funciones Booleanas, empleando símbolos llamados compuertas lógicas. Cada compuerta lógica es un símbolo que representa a una operación: hay tres que corresponden a las tres operaciones definidas (OR para la suma, AND para el producto y NOT para el complemento) y dos que corresponden al complemento de la suma y del producto (NOR y NAND). En casi todos los casos una compuerta puede tener más de una entrada —salvo la NOT que tiene una sola—, pero siempre tendrá una sola salida."*

---

## 3.6 Clasificación de las Cinco Compuertas Lógicas (OR, AND, NOT, NOR, NAND)

> 📖 **Textual del material:** "Las compuertas lógicas para cada operación son las siguientes:
>
> | Función | Compuerta | Símbolo |
> | :--- | :---: | :--- |
> | F(A,B) = A + B | OR | [Entradas A, B → símbolo OR → salida A+B] |
> | F(A,B) = A • B | AND | [Entradas A, B → símbolo AND → salida A•B] |
> | F(A) = Ā | NOT | [Entrada A → símbolo NOT → salida Ā] |
> | F(A,B) = (A + B)̄ [barra continua sobre A+B] | NOR | [Entradas A, B → símbolo OR con círculo en la salida → salida (A+B)̄] |
> | F(A,B) = (A · B)̄ [barra continua sobre A·B] | NAND | [Entradas A, B → símbolo AND con círculo en la salida → salida (A·B)̄] |"

**🗣️ En palabras simples:**
Son los 5 "ladrillos" con los que se dibuja cualquier circuito lógico en la materia:
1. **OR (Suma):** Suma las entradas (`A + B`). Su dibujo tiene la entrada curvada hacia adentro y termina en punta curva (como un escudo).
2. **AND (Producto):** Multiplica las entradas (`A · B`). Su dibujo tiene la pared izquierda totalmente **recta vertical** y el frente derecho redondeado (como una letra **D** mayúscula).
3. **NOT (Complemento):** Invierte su única entrada (`Ā`). Su dibujo es un **triángulo** apuntando a la derecha con un **circulito (burbuja)** en la punta.
4. **NOR (No-OR, complemento de la suma):** Hace la suma y niega el resultado final (`(A + B)̄`). Su dibujo es exactamente una compuerta **OR con el circulito** de negación pegado en su punta de salida.
5. **NAND (No-AND, complemento del producto):** Hace el producto y niega el resultado final (`(A · B)̄`). Su dibujo es exactamente una compuerta **AND con el circulito** de negación pegado en su punta de salida.

**🔍 Desglose detallado y tabla comparativa completa:**

| Compuerta | Operación que representa | Expresión algebraica del material | Cantidad de entradas y salidas | Descripción exacta del símbolo gráfico (Págs. 4–5) | Cuándo su salida vale 1 / Cuándo vale 0 (Contexto de tabla de verdad) |
| :---: | :--- | :---: | :---: | :--- | :--- |
| **OR** | Suma booleana | `F(A,B) = A + B` | 2 o más entradas, 1 salida | Dorso izquierdo **curvo (cóncavo)** y frente derecho terminado en **punta ojival**. | Vale **1** si al menos una entrada es 1. Solo vale **0** cuando todas son 0. |
| **AND** | Producto booleano | `F(A,B) = A • B` | 2 o más entradas, 1 salida | Dorso izquierdo **recto vertical** y frente derecho **semicircular** (forma de letra **D**). | Solo vale **1** cuando todas las entradas son 1. Vale **0** si hay algún 0. |
| **NOT** | Complemento | `F(A) = Ā` | **1 sola entrada**, 1 salida | **Triángulo** con un **pequeño círculo** en el vértice de salida (en diagramas a veces se coloca vertical sobre la línea de la variable). | Invierte la entrada: si entra 0 sale **1**; si entra 1 sale **0**. |
| **NOR** | Complemento de la suma | `F(A,B) = (A + B)̄` *(barra sobre toda la suma)* | 2 o más entradas, 1 salida | Símbolo de la compuerta **OR** con un **pequeño círculo** en el vértice de salida. | Es lo contrario de OR: solo vale **1** cuando todas las entradas son 0; si hay algún 1, vale **0**. |
| **NAND** | Complemento del producto | `F(A,B) = (A · B)̄` *(barra sobre todo el producto)* | 2 o más entradas, 1 salida | Símbolo de la compuerta **AND** con un **pequeño círculo** en el extremo de salida. | Es lo contrario de AND: vale **0** únicamente cuando todas las entradas son 1; si hay algún 0, vale **1**. |

**💡 Ejemplo (Tablas de verdad de las 5 compuertas para dos entradas A y B — contexto adicional de apoyo para el oral):**

| A | B | OR: `A + B` | AND: `A · B` | NOT: `Ā` | NOR: `(A + B)̄` | NAND: `(A · B)̄` |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| 0 | 0 | 0 | 0 | 1 | 1 | 1 |
| 0 | 1 | 1 | 0 | 1 | 0 | 1 |
| 1 | 0 | 1 | 0 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 0 | 0 | 0 |

**🔗 Conexiones:**
- **Con las Leyes de De Morgan (Clase 2):**
  - La compuerta **NOR** calcula `(A + B)̄`, que por Primera Ley de De Morgan equivale a `Ā · B̄`.
  - La compuerta **NAND** calcula `(A · B)̄`, que por Segunda Ley de De Morgan equivale a `Ā + B̄`.
  Esta conexión es fundamental en los Desempeños 7, 8 y 9: cuando en una fórmula aparece una barra larga sobre una suma `(A + B)̄`, se implementa directamente con una **NOR** (o con una OR seguida de un NOT); y cuando aparece una barra larga sobre un producto `(A · B)̄`, se implementa con una **NAND**.

**⚠️ Precisiones / errores comunes:**
- **Error clásico nº 1: Confundir `(A + B)̄` (NOR) con `Ā + B̄`:**
  - `F(A,B) = (A + B)̄` tiene una **barra continua** sobre toda la suma: es una sola compuerta **NOR**.
  - En cambio, `Ā + B̄` tiene barras separadas sobre cada letra: eso en circuito son dos compuertas **NOT** (una en A y otra en B) cuyas salidas entran a una compuerta **OR**. ¡No son la misma función! (Por De Morgan, `Ā + B̄` equivale a `(A · B)̄`, que es una **NAND**, no una NOR).
- **Error clásico nº 2: Confundir `(A · B)̄` (NAND) con `Ā · B̄`:**
  - `F(A,B) = (A · B)̄` tiene **barra continua** sobre el producto: es una compuerta **NAND**.
  - `Ā · B̄` tiene barras separadas: son dos **NOT** entrando a una **AND** (que por De Morgan equivale a `(A + B)̄`, o sea una **NOR**).
- **Cómo distinguir visualmente OR de AND sin dudar:** Mirá la línea de atrás (por donde entran los cables A y B): si es **recta** como una pared (`|`), es **AND**; si es **curva** (`)`), es **OR**. Y el **circulito en la salida** siempre significa **"negar / complementar el resultado de esa compuerta"** (la N inicial de **N**OT, **N**OR, **N**AND).

**🎤 Cómo decirlo en el oral:**
> *"Existen cinco compuertas lógicas: tres para las operaciones básicas y dos para el complemento de la suma y del producto. La compuerta OR representa la suma booleana F(A,B) = A + B; la compuerta AND representa el producto booleano F(A,B) = A · B; la compuerta NOT representa el complemento F(A) = Ā; la compuerta NOR representa el complemento de la suma F(A,B) = (A + B)̄ [con barra sobre toda la suma]; y la compuerta NAND representa el complemento del producto F(A,B) = (A · B)̄ [con barra sobre todo el producto]. Gráficamente, la NOR y la NAND se simbolizan igual que la OR y la AND respectivamente, agregando un pequeño círculo en la salida que indica el complemento."*

---

## 3.7 Construcción y Lectura de Circuitos Lógicos

> 📖 **Textual del material:** "Veamos entonces un ejemplo, en el que debamos hacer el circuito lógico para una función.
> Tomemos la función F (A, B, C) = Ā + B + B . C
> Entonces a partir de las tres variables de entrada armamos el siguiente circuito:
> [Diagrama del circuito:
> - Entrada: tres líneas verticales correspondientes a las variables A, B y C.
> - De las líneas B y C salen dos conexiones hacia una compuerta AND, cuya salida es B . C.
> - De la línea A sale una conexión que pasa por una compuerta NOT, cuya salida es Ā.
> - De la línea B sale además una conexión directa.
> - Las tres señales (B . C, la conexión directa de B, y Ā) ingresan a una compuerta OR de tres entradas, cuya única Salida es B . C + Ā + B.]"

**🗣️ En palabras simples:**
- **Armar el circuito desde la función (Desempeño 7):** Se colocan a la izquierda las líneas verticales de las variables de entrada (`A, B, C...`). Luego, siguiendo el orden de las operaciones de la fórmula (de adentro hacia afuera: primero complementos individuales, luego productos/paréntesis, y al final la operación principal que une todo), se van "tirando cables" desde las variables hacia las compuertas correspondientes, conectando la salida de una compuerta a la entrada de la siguiente hasta llegar a una única salida final.
- **Obtener la función desde el circuito (Desempeño 8):** Se hace el camino inverso leyendo el dibujo **de izquierda a derecha**: se etiqueta qué señal sale de cada compuerta intermedia hasta escribir la expresión algebraica completa en la salida final (y luego se simplifica algebraicamente si se pide).

**🔍 Desglose paso a paso del método (Algoritmo de implementación y lectura):**
1. **De Expresión Algebraica a Circuito Lógico ("Implementar con compuertas lógicas"):**
   - **Paso 1 (Líneas de entrada):** Trazar a la izquierda una línea vertical por cada variable que interviene en la función (`A, B, C...`).
   - **Paso 2 (Complementos de variables sueltas):** Si una variable aparece negada sola (como `Ā`), sacar una derivación de su línea y pasarla por una compuerta **NOT** (en el Desempeño 8 el material también dibuja el NOT directamente sobre la línea vertical de la variable al inicio).
   - **Paso 3 (Operaciones parciales / términos):** Para cada producto (como `B . C`) o subexpresión entre paréntesis, llevar cables desde las líneas correspondientes a una compuerta **AND** (o **OR** / **NAND** / **NOR** si tiene barra completa encima).
   - **Paso 4 (Operación final):** Conectar las salidas de las compuertas parciales y las variables directas a la compuerta que representa la operación principal de la función, obteniendo la única **Salida**.
2. **De Circuito Lógico a Expresión Algebraica (Desempeño 8):**
   - Seguir cada línea desde las entradas `A, B, C`.
   - En cada compuerta, escribir a su salida la operación que realiza sobre sus entradas:
     - Si pasan por NOT → poner barra sobre la entrada.
     - Si entran a AND → multiplicar las entradas (`X · Y`).
     - Si entran a OR → sumar las entradas (`X + Y`).
     - Si entran a NOR → sumar las entradas y poner una barra larga sobre toda la suma (`(X + Y)̄`).
     - Si entran a NAND → multiplicar las entradas y poner una barra larga sobre todo el producto (`(X · Y)̄`).

**💡 Ejemplo 1 (El del material en Pág. 4):**
Para `F (A, B, C) = Ā + B + B . C`:
- Vemos que es una **suma de tres términos**: `Ā`, `B` y `B . C`. Por lo tanto, la compuerta final de salida tiene que ser una **OR de 3 entradas**.
- ¿Qué necesita esa OR en sus 3 entradas?
  1. El producto `B . C` → se obtiene conectando `B` y `C` a una compuerta **AND**.
  2. La variable `B` sin modificar → se saca un cable directo desde la línea de `B`.
  3. El complemento `Ā` → se saca un cable desde `A` y se lo pasa por una compuerta **NOT**.
- Esas tres líneas entran a la compuerta **OR**, cuya salida es `B . C + Ā + B` (que por conmutatividad de la suma es exactamente `Ā + B + B . C`).

**💡 Ejemplo 2 (Lectura de circuito del Desempeño 8a, Pág. 5 — breve ilustración del proceso inverso):**
En el circuito `a-` del Desempeño 8 hay tres entradas `A, B, C` (donde `C` pasa por un NOT vertical quedando `C̄`):
- Arriba: `B` y `C̄` entran a una compuerta OR → sale `(B + C̄)`. Esa salida junto con `A` entran a una compuerta AND → sale `A · (B + C̄)`.
- Abajo: `B` y `C̄` entran a una compuerta AND → sale `B · C̄`.
- Final: Ambas ramas entran a una compuerta **NOR** (OR con circulito en la salida) → la función obtenida es `F(A, B, C) = (A · (B + C̄) + B · C̄)̄` [con barra sobre toda la suma final].

**🔗 Conexiones:**
- **Con Propiedad Conmutativa y Asociativa (Clase 2):** En el ejemplo de la página 4, la función original está escrita como `Ā + B + B . C` y en la salida del dibujo aparece escrita como `B . C + Ā + B`. Son idénticas gracias a la propiedad conmutativa de la suma booleana.
- **Con Simplificación Algebraica (Clase 2 y Desempeño 9):** Observá en el propio ejemplo de la página 4 (`F(A, B, C) = Ā + B + B . C`) que por propiedad de absorción vista en Clase 2 (`B + B . C = B`), esa función se podría simplificar a `Ā + B`, ahorrando por completo la compuerta AND de `B . C` y dejando una OR de solo 2 entradas. ¡Eso es exactamente lo que el Desempeño 9 invita a descubrir!

**⚠️ Precisiones / errores comunes:**
- **Cuidado con el orden de los paréntesis al pasar de expresión a circuito:**
  En `F(A, B, C) = (Ā + C) • (Ā • B + A • C)` (Desempeño 7c), la operación principal que une los dos grandes bloques es el **producto `•`**, por lo que la última compuerta antes de la salida es una **AND** (y no una OR). Adentro del segundo paréntesis hay dos compuertas AND (`Ā • B` y `A • C`) que se unen en una OR antes de llegar a la AND final.

**🎤 Cómo decirlo en el oral:**
> *"Para implementar una función Booleana con compuertas lógicas (es decir, armar su circuito lógico), partimos de las líneas de entrada de las variables y vamos representando cada operación parcial mediante su compuerta correspondiente: los complementos con NOT, los productos con AND, las sumas con OR, y los complementos de sumas o productos completos con NOR o NAND, conectando las salidas parciales hasta llegar a la compuerta de la operación principal que nos da la única salida del circuito."*

---

## 3.8 Los Tres Modos de Representar una Función Booleana, Conversión entre Ellos y Forma Canónica

> 📖 **Textual del material:** "De esta manera hemos llegado a poder escribir o representar una función Booleana de tres modos diferentes, mediante su expresión algebraica, su tabla de verdad y su circuito lógico. Es por esto que si hay tres maneras de escribir la misma función, seguramente se puede pasar de una a otra, es decir si tengo la expresión algebraica poder hacer el circuito y la tabla, o si tengo la tabla hacer el circuito y la expresión algebraica, y lo mismo si tengo el circuito lógico. Para poder escribir la expresión algebraica a partir de los resultados de la tabla de verdad, necesitamos ver un modo especial de escribir una función Booleana, que llamamos forma canónica de ella...pero ese será tema de la próxima clase."

**🗣️ En palabras simples:**
Este párrafo cierra la teoría de la Clase 3 con una idea central de toda la unidad: una misma función Booleana tiene **tres caras o representaciones equivalentes**:
1. **Su expresión algebraica** (la fórmula con letras, `+`, `.` y barras).
2. **Su tabla de verdad** (el cuadro con las 2ⁿ combinaciones de 0 y 1 y sus resultados).
3. **Su circuito lógico** (el diagrama con compuertas AND, OR, NOT, NOR, NAND).

Como las tres representan al mismo objeto matemático, podemos traducir de cualquiera de las tres a las otras dos. En esta Clase 3 ya aprendimos a ir de la **expresión algebraica → tabla de verdad**, de la **expresión algebraica → circuito lógico**, y del **circuito lógico → expresión algebraica** (y de ahí a la tabla). El único puente que todavía falta explicar es cómo ir desde los resultados de la **tabla de verdad → expresión algebraica** (y de ahí al circuito): para lograr eso hace falta escribir la función en un formato especial llamado **forma canónica**, que es el tema central de la Clase 4.

**🔍 Desglose de la jerga y cuadro de conversiones:**
- **"tres modos diferentes [de escribir o representar una función Booleana]"**:
  1. **Expresión algebraica**
  2. **Tabla de verdad**
  3. **Circuito lógico**
- **"forma canónica"**: Es el *"modo especial de escribir una función Booleana"* que permite obtener la expresión algebraica directamente a partir de los resultados (los 1 o los 0) de la tabla de verdad.

| Conversión (De → A) | ¿Cómo se realiza según el material? | ¿En qué clase se estudia? |
| :--- | :--- | :---: |
| **Expresión algebraica → Tabla de verdad** | Se colocan las *n* variables (2ⁿ filas), columnas de operaciones parciales y se evalúa la expresión para cada fila. | **Clase 3** (Págs. 2–3) |
| **Expresión algebraica → Circuito lógico** | Se implementa cada operación de la fórmula con su compuerta lógica correspondiente (OR, AND, NOT, NOR, NAND). | **Clase 3** (Pág. 4, Desempeño 7) |
| **Circuito lógico → Expresión algebraica** | Se siguen las líneas de entrada a salida escribiendo la operación de cada compuerta hasta obtener la fórmula final. | **Clase 3** (Desempeño 8) |
| **Circuito lógico → Tabla de verdad** | Se obtiene primero la expresión algebraica del circuito (o se evalúan las compuertas paso a paso) y se confecciona la tabla. | **Clase 3** (Desempeños 8 y 9) |
| **Tabla de verdad → Expresión algebraica (y Circuito)** | Requiere escribir la función en su **forma canónica** a partir de los resultados de la tabla. | **Clase 4** (anticipado en Pág. 4 de Clase 3) |

**🤔 Intuición e importancia teórica de la comparación (Desempeño 9):**
En el Desempeño 9 (Pág. 5), el material pide para 7 funciones distintas:
1. Simplificar cada expresión algebraica (usando lo aprendido en Clase 2).
2. Realizar la tabla de verdad de la función original y de la simplificada.
3. Realizar el circuito lógico de las dos funciones.
4. **Analizar y comparar los resultados de tabla y circuito.**

¿Cuál es la conclusión teórica fundamental de esa comparación (que el profesor puede preguntar en el oral)?
- **Al comparar las tablas de verdad:** La tabla de verdad de la función original y la de la función simplificada dan **exactamente el mismo resultado** en su última columna para todas las combinaciones de entrada (porque son funciones equivalentes).
- **Al comparar los circuitos lógicos:** El circuito de la función simplificada es **mucho más sencillo y económico** (tiene menos compuertas lógicas y/o menos entradas) que el circuito de la función sin simplificar, a pesar de que ambos hacen exactamente el mismo trabajo lógico. **Para eso sirve simplificar funciones Booleanas en ingeniería y sistemas: para construir circuitos digitales más simples, baratos y rápidos que produzcan exactamente la misma salida.**

**💡 Ejemplo (aplicando el análisis del Desempeño 9g: `F(A,B,C) = A + B + A . B . C`):**
- **Simplificación algebraica:** En `A + B + A . B . C`, por absorción (`A + A . (B . C) = A`), el término `A . B . C` es absorbido por `A` (o por `B`), quedando la función simplificada `F(A,B,C) = A + B`.
- **Comparación de tablas de verdad:** Ambas funciones (`A + B + A . B . C` y `A + B`) valen `0` únicamente cuando `A = 0` y `B = 0` (filas `000` y `001`), y valen `1` en las otras 6 filas. Sus tablas coinciden al 100%.
- **Comparación de circuitos lógicos:**
  - El circuito original requiere una compuerta AND de 3 entradas (para `A . B . C`) más una compuerta OR de 3 entradas.
  - El circuito simplificado requiere **una sola compuerta OR de 2 entradas** (`A` y `B`), prescindiendo incluso de conectar la variable `C`.

**🔗 Conexiones:**
- **Con Clase 2 (Simplificación en Álgebra de Boole):** Le da sentido práctico e ingenieril a todos los teoremas de simplificación (idempotencia, absorción, De Morgan, etc.).
- **Con Clase 4 (Formas Canónicas - Minitérminos y Maxitérminos):** Conecta directamente el final de esta clase con el inicio de la Clase 4.

**⚠️ Precisiones / errores comunes:**
- **No olvidarse ninguno de los tres modos si preguntan "¿De cuántas formas se puede representar una función Booleana?":** Son exactamente **tres**:
  1. **Expresión algebraica**
  2. **Tabla de verdad**
  3. **Circuito lógico**
- **Saber nombrar la "forma canónica" cuando pregunten cómo pasar de la tabla a la expresión:** El material de la Clase 3 lo deja planteado textualmente con ese nombre exacto (*"un modo especial de escribir una función Booleana, que llamamos forma canónica de ella"*).

**🎤 Cómo decirlo en el oral:**
> *"Una función Booleana se puede escribir o representar de tres modos diferentes: mediante su expresión algebraica, su tabla de verdad y su circuito lógico. Como son tres maneras de representar la misma función, se puede pasar de una a otra: de la expresión algebraica a la tabla y al circuito, o del circuito a la expresión algebraica y a la tabla. Para poder pasar de los resultados de la tabla de verdad a la expresión algebraica, se utiliza un modo especial de escribir la función Booleana llamado forma canónica. Además, si simplificamos la expresión algebraica de una función, la función original y la simplificada tienen la misma tabla de verdad, pero la simplificada produce un circuito lógico con menos compuertas."*

---

## 🧠 Resumen esquemático de la clase

- **Función (repaso MD1):** Relación entre dos variables donde cada variable independiente se relaciona con **una y solo una** variable dependiente.
- **Función Booleana:** Función del Álgebra de Boole que resulta de **combinar un número de variables mediante las tres operaciones ya definidas** (suma `+`, producto `.`, complemento `¯`).
- **Dominio e imagen binarios:** A diferencia de las funciones numéricas comunes, en las funciones Booleanas tanto las variables como la función **solo pueden tomar el valor 0 ó 1**.
- **Tabla de verdad:** Tabla que muestra **todos los resultados** de una función Booleana para **todas las posibles combinaciones** de 0 y 1 de las variables que intervienen.
- **Cantidad de combinaciones:** Siempre es **2ⁿ** (2^n), donde **n** es la cantidad de variables de la función (`n=2 → 4`, `n=3 → 8`, `n=4 → 16`, etc.).
- **Reglas operativas para completar la tabla:**
  - **Producto (`.`):** Si hay un `0`, el resultado será `0`.
  - **Complemento (`¯`):** Es lo contrario (`0̄ = 1`, `1̄ = 0`).
  - **Suma (`+`):** Si hay un `1`, el resultado es `1`.
- **Circuitos lógicos y compuertas lógicas:** Representación gráfica de funciones Booleanas mediante símbolos llamados **compuertas lógicas** (cada compuerta representa una operación; casi todas admiten más de una entrada, pero **siempre tienen una sola salida**).
- **Las 5 compuertas lógicas:**
  1. **OR:** `F(A,B) = A + B` (suma).
  2. **AND:** `F(A,B) = A • B` (producto).
  3. **NOT:** `F(A) = Ā` (complemento; única de 1 sola entrada).
  4. **NOR:** `F(A,B) = (A + B)̄` (complemento de la suma; símbolo OR con círculo en la salida).
  5. **NAND:** `F(A,B) = (A · B)̄` (complemento del producto; símbolo AND con círculo en la salida).
- **Tres modos de representar una función Booleana:** **1) Expresión algebraica**, **2) Tabla de verdad**, **3) Circuito lógico**.
- **Forma canónica (anticipo a Clase 4):** Modo especial de escribir una función Booleana necesario para obtener su expresión algebraica a partir de los resultados de la tabla de verdad.
- **Efecto de la simplificación (Desempeño 9):** La expresión original y la simplificada tienen la **misma tabla de verdad**, pero la simplificada genera un **circuito lógico más reducido**.

---

## ❓ Preguntas probables del oral

1. **¿Qué es una función (según lo visto en MD1) y qué es una función Booleana?**
   - **Respuesta:** Una función es una relación entre dos variables para la que se debe cumplir que una variable independiente se debe relacionar con una y solo una variable dependiente. En el Álgebra de Boole, las funciones Booleanas son aquellas que resultan de combinar un número de variables mediante las tres operaciones ya definidas (suma, producto y complemento).

2. **¿Cuál es la gran diferencia entre las funciones numéricas que veíamos antes (como f(x) = 2x + 3) y las funciones Booleanas?**
   - **Respuesta:** La gran diferencia es que en las funciones Booleanas las variables solo pueden tomar el valor 0 ó 1, y el resultado de la función también puede ser únicamente 0 ó 1 (tanto si la variable vale 0 como si vale 1, la función solo puede valer 0 ó 1).

3. **¿Qué es una Tabla de verdad para una función Booleana y para qué sirve?**
   - **Respuesta:** Es una tabla que muestra todos los resultados que toma la función Booleana para todas las posibles combinaciones de valores 0 y 1 de las variables que intervienen en ella. Sirve para conocer de manera práctica todos los resultados posibles de la función a partir de las diferentes entradas, o bien (mirándola de derecha a izquierda) saber para qué entradas la función toma el valor 1 ó 0.

4. **¿Cómo se confecciona una Tabla de verdad y cuántas combinaciones (filas) tiene?**
   - **Respuesta:** Se colocan las variables que intervienen, una por columna, y debajo de ellas todas las combinaciones posibles de 0 y 1. La cantidad de posibilidades es siempre **2ⁿ**, donde **n** es la cantidad de variables (por ejemplo, con 2 variables son 2² = 4 combinaciones; con 3 variables son 2³ = 8 combinaciones). En las columnas siguientes se completan los resultados parciales según las operaciones que vinculan a las variables, y en la última columna se indica el valor final de la función para cada combinación de entrada.

5. **¿Qué tres reglas prácticas recuerda el material al completar las columnas de producto, complemento y suma en una tabla de verdad?**
   - **Respuesta:**
     1. En el **producto**, si hay un 0 el resultado será 0.
     2. El **complemento** es lo contrario (de 0 es 1 y de 1 es 0).
     3. En la **suma**, si hay un 1 el resultado es 1.

6. **¿Qué es un circuito lógico y qué es una compuerta lógica?**
   - **Respuesta:** Un circuito lógico es una manera de representar las funciones Booleanas empleando las llamadas compuertas lógicas. Cada compuerta lógica es un símbolo que representa a una operación: hay tres que corresponden a las tres operaciones definidas y dos que corresponden al complemento de la suma y del producto.

7. **¿Cuáles son las cinco compuertas lógicas y qué función representa cada una?**
   - **Respuesta:**
     - **OR:** representa la suma booleana, `F(A,B) = A + B`.
     - **AND:** representa el producto booleano, `F(A,B) = A • B`.
     - **NOT:** representa el complemento, `F(A) = Ā`.
     - **NOR:** representa el complemento de la suma, `F(A,B) = (A + B)̄` (con barra sobre toda la suma).
     - **NAND:** representa el complemento del producto, `F(A,B) = (A · B)̄` (con barra sobre todo el producto).

8. **¿Cuántas entradas y cuántas salidas puede tener una compuerta lógica?**
   - **Respuesta:** En casi todos los casos puede haber más de una entrada (todas excepto la compuerta NOT, que tiene una sola entrada), pero **siempre habrá una sola salida**.

9. **¿Qué diferencia hay entre la función de una compuerta NOR y la expresión `Ā + B̄`, o entre una NAND y `Ā · B̄`?**
   - **Respuesta:** La compuerta NOR representa `(A + B)̄` (el complemento de toda la suma: primero se suma y al resultado se lo complementa), mientras que `Ā + B̄` es la suma de los complementos separados (que por Ley de De Morgan equivale a `(A · B)̄`, es decir, a una NAND). Análogamente, la compuerta NAND representa `(A · B)̄` (el complemento del producto), mientras que `Ā · B̄` es el producto de los complementos separados (que por De Morgan equivale a `(A + B)̄`, o sea a una NOR).

10. **¿Qué significa la consigna "implementar con compuertas lógicas una función"?**
    - **Respuesta:** Como indica textualmente el material en el Desempeño 7, implementar con compuertas lógicas una función es exactamente lo mismo que decir **realizar el circuito lógico correspondiente** a esa función.

11. **¿De cuántos modos diferentes se puede escribir o representar una función Booleana y cuáles son?**
    - **Respuesta:** Se puede escribir o representar de **tres modos diferentes**:
      1. Mediante su **expresión algebraica**.
      2. Mediante su **tabla de verdad**.
      3. Mediante su **circuito lógico**.
      Como representan la misma función, se puede pasar de cualquiera de ellos a los otros dos.

12. **¿Qué se necesita para poder escribir la expresión algebraica de una función Booleana a partir de los resultados de su tabla de verdad, y qué ocurre cuando comparamos la tabla y el circuito de una función original con los de su expresión simplificada?**
    - **Respuesta:** Para obtener la expresión algebraica a partir de los resultados de la tabla de verdad necesitamos un modo especial de escribir la función Booleana llamado **forma canónica**. Y al comparar una función original con su versión simplificada (Desempeño 9), comprobamos que ambas tienen **exactamente la misma tabla de verdad** (dan los mismos resultados para todas las entradas), pero la función simplificada da lugar a un **circuito lógico más simple** (con menor cantidad de compuertas o conexiones).

---

## 📚 Glosario de la clase

| Término | Definición breve fiel al material |
| :--- | :--- |
| **Función** | Relación entre dos variables para la que se debe cumplir que una variable independiente se debe relacionar con una y solo una variable dependiente. |
| **Función Booleana** | Función del Álgebra de Boole que resulta de combinar un número de variables (que solo pueden tomar el valor 0 ó 1) mediante las tres operaciones ya definidas (suma, producto y complemento), dando como resultado también 0 ó 1. |
| **Tabla de verdad** | Tabla que muestra todos los resultados de una función Booleana para todas las posibles combinaciones de valores 0 y 1 de las variables que intervienen en ella. |
| **2ⁿ (Regla de combinaciones)** | Fórmula que indica la cantidad de combinaciones posibles de entrada en una tabla de verdad, donde *n* es la cantidad de variables que intervienen en la función. |
| **Circuito lógico** | Representación gráfica de una función Booleana realizada empleando compuertas lógicas. |
| **Compuerta lógica** | Símbolo que representa a una operación booleana dentro de un circuito lógico; en casi todos los casos puede tener más de una entrada, pero siempre tiene una sola salida. |
| **Compuerta OR** | Compuerta lógica que representa la operación de suma booleana: `F(A,B) = A + B`. |
| **Compuerta AND** | Compuerta lógica que representa la operación de producto booleano: `F(A,B) = A • B`. |
| **Compuerta NOT** | Compuerta lógica de una sola entrada que representa la operación de complemento: `F(A) = Ā`. |
| **Compuerta NOR** | Compuerta lógica que representa el complemento de la suma: `F(A,B) = (A + B)̄` (símbolo OR con círculo de negación en la salida). |
| **Compuerta NAND** | Compuerta lógica que representa el complemento del producto: `F(A,B) = (A · B)̄` (símbolo AND con círculo de negación en la salida). |
| **Implementar con compuertas lógicas** | Expresión equivalente a realizar el circuito lógico correspondiente a una función Booleana. |
| **Tres modos de representación** | Las tres maneras equivalentes de escribir o representar una función Booleana: su **expresión algebraica**, su **tabla de verdad** y su **circuito lógico**. |
| **Forma canónica** | Modo especial de escribir una función Booleana que permite obtener su expresión algebraica a partir de los resultados de su tabla de verdad. |
