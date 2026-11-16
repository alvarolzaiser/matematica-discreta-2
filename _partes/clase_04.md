# Clase 4 — Funciones Booleanas (Forma Canónica y Simplificación)

## 🗺️ Mapa de la clase

- **Ubicación en el programa:** Unidad 01 (Álgebra de Boole) — Clase 04 (cierre de la unidad).
- **Objetivo oficial del material:**
  > 📖 **Textual del material:** "Al finalizar la clase los alumnos: • Escribir las funciones Booleanas en su forma canónica. • Álgebra de Boole"
- **Recorrido de temas y cómo se conectan entre sí:**
  1. **Concepto de Forma Canónica y Términos Canónicos (Secciones 4.1 a 4.5):**
     - Se define qué significa que una función Booleana esté en **forma canónica** (suma o producto de términos canónicos).
     - Se define qué es un **término canónico** y se lo clasifica según su operación en **Maxitérmino** (suma canónica) y **minitérmino** (producto canónico).
     - Se reformula la definición de forma canónica como **suma de minitérminos** o **producto de Maxitérminos**, analizando casos válidos e inválidos.
  2. **Existencia y Obtención de las Formas Canónicas (Secciones 4.6 a 4.8):**
     - Principio de existencia: toda función Booleana tiene su forma canónica y puede llevarse a ella por dos vías: **procedimiento algebraico** o **tabla de verdad**.
     - Método por **Tabla de Verdad**: uso del número de secuencia decimal (`Sec. Dec.`), identificación de los `0` para el **Producto de Sumas (`PS` / `IIM`)** y de los `1` para la **Suma de Productos (`SP` / `∑m`)**, y reglas de lectura de las variables (directas o negadas en cada caso).
     - Método por **Procedimiento Algebraico**: cómo completar variables faltantes utilizando los axiomas del Álgebra de Boole.
  3. **Diseño de Funciones desde una Tabla y Simplificación para Eficiencia de Circuitos (Secciones 4.9 y 4.10):**
     - **Aplicación principal (síntesis):** dada una tabla con los resultados deseados a la salida para cada combinación de entrada, hallar la función Booleana que los produce mediante su forma canónica.
     - **Motivación física y lógica:** relación entre cantidad de operaciones en la función, cantidad de compuertas lógicas en el circuito y eficiencia (costo y velocidad).
     - **Simplificación de funciones Booleanas:** reducción algebraica de una expresión más extensa (como la forma canónica) justificando cada paso exclusivamente con los axiomas y teoremas enunciados.
- **Prerrequisitos (de las Clases 1, 2 y 3):**
  - Definición axiomática del Álgebra de Boole sobre el conjunto `{0, 1}` con las operaciones suma (`+`), producto (`.` o `•`) y complemento/negación (barra superior `Ā`).
  - **Axiomas y teoremas del Álgebra de Boole** (en especial: Axioma 2 de distributividad/conmutatividad, Axioma 3 de elementos neutros `0` y `1`, Axioma 4 de complementación `A + Ā = 1` y `A . Ā = 0`, idempotencia, absorción, De Morgan).
  - Construcción de **Tablas de Verdad** de funciones Booleanas, combinaciones binarias de entrada (`2^n` filas) y representación mediante **circuitos lógicos / compuertas lógicas**.

---

## 4.1 Forma canónica de una función Booleana

> 📖 **Textual del material:** "Una función Booleana está escrita en forma canónica, cuando es una suma o un producto de términos canónicos."
>
> 📖 **Textual del material:** "Si volvemos a la definición de forma canónica, diremos que una función está en forma canónica cuando es una suma de minitérminos o es un producto de Maxitérminos."

**🗣️ En palabras simples:**
Una función Booleana está en forma canónica cuando está expresada de manera "estándar" y uniforme: o bien son varios bloques multiplicativos (donde en cada bloque aparecen absolutamente todas las variables de la función) que se suman entre sí, o bien son varios bloques aditivos (donde en cada paréntesis aparecen todas las variables de la función) que se multiplican entre sí. No puede faltar ninguna variable en ningún término ni pueden mezclarse los tipos de términos.

**🔍 Desglose de la jerga:**
- **"Función Booleana":** expresión algebraica formada por variables binarias (que toman valores `0` o `1`) vinculadas mediante las operaciones del Álgebra de Boole (`+`, `.`, `¯`).
- **"Forma canónica":** representación normalizada y única (salvo el orden de los términos/factores) de una función Booleana que permite comparar funciones y construirlas directamente desde una tabla de verdad.
- **"Suma o un producto de términos canónicos":** el conectivo "o" es excluyente respecto de los dos formatos canónicos posibles:
  1. **Suma de minitérminos** (también llamada *Suma de Productos*, `SP`, o *sumatoria de minitérminos*, `∑m`).
  2. **Producto de Maxitérminos** (también llamado *Producto de Sumas*, `PS`, o *productoria de maxitérminos*, `IIM` / `∏M`).
- **"Todos los términos deben ser canónicos":** basta con que un solo término de la suma no sea minitérmino (o que un solo factor del producto no sea Maxitérmino) para que toda la función **no** esté en forma canónica.

**💡 Ejemplo:**
- Para una función de dos variables `F(A, B)`:
  - `F(A, B) = Ā . B̄ + A . B̄ + A . B` **sí** está en forma canónica (es una suma de minitérminos).
  - `F(A, B) = Ā . B + A` **no** está en forma canónica, porque al segundo término (`A`) le falta la variable `B`.

**🔗 Conexiones:**
- Depende directamente de las definiciones de **término canónico** (4.2), **Maxitérmino** (4.3) y **minitérmino** (4.4).
- Se opone en longitud a la **función simplificada** (4.10): la forma canónica explicita todas las variables en cada término, mientras que la simplificación busca eliminar variables y operaciones redundantes.

**⚠️ Precisiones / errores comunes:**
- **No confundir "Suma de Productos" con "Forma Canónica Suma de Productos":** una expresión como `F(X,Y,Z) = X . Z + Y . Z + X . Ȳ` es una suma de productos, pero **no** está en forma canónica porque cada producto no contiene a las 3 variables `X, Y, Z`. En el oral, aclarar siempre que debe ser suma de *minitérminos* (o producto de *Maxitérminos*), o suma/producto de *términos canónicos*.
- **Caso de un único término:** una función formada por un único minitérmino (por ejemplo, `F(A,B) = A . B`) o un único Maxitérmino (por ejemplo, `F(X,Y) = X + Y` en `F(X,Y)`) **sí** está en forma canónica (es una suma o producto de un solo término canónico).

**🎤 Cómo decirlo en el oral:**
> "Profesor, una función Booleana está escrita en forma canónica cuando es una suma o un producto de términos canónicos; o dicho de manera equivalente luego de clasificar dichos términos, cuando es una suma de minitérminos o es un producto de Maxitérminos."

---

## 4.2 Término canónico

> 📖 **Textual del material:** "Un término canónico es una expresión que relaciona a todas las variables (ya sea directa o complementada) una sola vez mediante una sola operación. Es decir si hay tres variables en la función sería cualquier terna de ellas todas sumadas o todas multiplicadas."

**🗣️ En palabras simples:**
Es el "ladrillo básico" de las formas canónicas. Para que un grupo de variables sea un término canónico de una función de `n` variables, tiene que cumplir tres reglas estrictas:
1. Tienen que estar **todas** las variables de la función (ni una menos).
2. Cada variable puede aparecer **una sola vez** (ya sea sin barra o con barra de negación, pero no repetida).
3. Todas las variables dentro de ese término deben estar unidas por **la misma operación** (o todas sumadas con `+`, o todas multiplicadas con `.`).

**🔍 Desglose de la jerga:**
- **"Relaciona a todas las variables":** las variables que deben figurar las define la declaración de la función. Si la función se declara como `F(X, Y, Z)`, el término tiene que tener sí o sí `X`, `Y` y `Z`. Si es `F(P, Q, R, S)`, debe tener las 4 variables.
- **"(ya sea directa o complementada)":**
  - **Variable directa (o sin complementar):** la variable escrita tal cual, p. ej. `X`.
  - **Variable complementada (o negada):** la variable afectada por la operación de complementación o inversión (barra superior), p. ej. `X̄`.
- **"Una sola vez":** prohíbe repeticiones dentro del mismo término, como `A + Ā` o `A . A . B`.
- **"Mediante una sola operación":** dentro del término canónico solo puede haber sumas lógicas (`+`) o solo productos lógicos (`.`), nunca una combinación de suma y producto dentro del mismo término.

**💡 Ejemplo:**
- Si la función depende de tres variables `X, Y, Z`:
  - `X + Ȳ + Z` es un término canónico (están las 3 variables, una sola vez cada una, todas sumadas).
  - `X̄ . Y . Z̄` es un término canónico (están las 3 variables, una sola vez cada una, todas multiplicadas).
  - `X + Y` **no** es término canónico de `F(X,Y,Z)` porque falta `Z`.
  - `A + Ā` **no** es término canónico de `F(A,B)` porque se repite `A` y falta `B`.

**🔗 Conexiones:**
- Al especificar cuál es esa "única operación" que vincula a las variables, el término canónico se divide en dos subtipos exactos: **Maxitérmino** (si la operación es la suma, Sección 4.3) y **minitérmino** (si la operación es el producto, Sección 4.4).

**⚠️ Precisiones / errores comunes:**
- **Cuidado con las barras que abarcan varias variables:** en un término canónico, cada variable está "directa o complementada" individualmente (por ejemplo `X . Ȳ . Z̄`). Si una barra de negación cubre simultáneamente el producto o la suma de varias variables (como `X . Y̅.̅Z̅` en el Desempeño 10), la operación global sobre esas variables ya no es simplemente el producto de literales individuales sino la negación de un producto (que por De Morgan equivale a una suma), por lo que no cumple la estructura directa de término canónico hasta ser operada.
- En el oral, no olvidar ninguna de las tres condiciones de la cita textual: **todas las variables**, **una sola vez** (directa o complementada) y **mediante una sola operación**.

**🎤 Cómo decirlo en el oral:**
> "Un término canónico es una expresión que relaciona a todas las variables de la función —ya sea en forma directa o complementada— una sola vez mediante una sola operación. Por ejemplo, si la función tiene tres variables, es cualquier terna de ellas todas sumadas o todas multiplicadas."

---

## 4.3 Maxitérmino (o Suma canónica)

> 📖 **Textual del material:** "Cuando todas las variables se relacionan con la operación suma, a ese término canónico se lo llama Maxitérmino.
> Un par de ejemplos de éstos para las variables X, Y, Z podrían ser:
> X + Y + Z; X̄ + Y + Z̄"
>
> 📖 **Textual del material:** "1| Las sumas canónicas son aquellas combinaciones para las cuales la función vale 0 y conforman la productoria de maxitérminos.
> NOTA: Las variables que valen ‘1’ se leen negadas y las que valen ‘0’, directas."

**🗣️ En palabras simples:**
Un **Maxitérmino** (también llamado **suma canónica** en la síntesis de la página 4) es un término canónico donde todas las variables de la función aparecen **sumadas** entre sí (una sola vez cada una, directa o negada). Cuando armamos una función desde su tabla de verdad, fabricamos un Maxitérmino por cada fila donde el resultado de la función da **`0`**, leyendo al revés el valor binario de las variables: si la variable vale `0` la escribimos normal (directa), y si vale `1` la escribimos negada (con barra).

**🔍 Desglose de la jerga:**
- **"Operación suma":** la operación `+` del Álgebra de Boole (disyunción / compuerta OR).
- **"Maxitérmino" (denotado con `M` mayúscula en `IIM`):** recibe este nombre (contexto adicional) porque para las `2^n` combinaciones posibles de entrada, una suma de todas las variables vale `1` en casi todas las filas (en `2^n - 1` filas, el máximo número posible de unos para una cláusula) y vale `0` en **una única combinación**.
- **"Sumas canónicas":** sinónimo que utiliza el material en la página 4 para referirse a los Maxitérminos.
- **"Conforman la productoria de maxitérminos":** como cada Maxitérmino es una suma, para unir varios Maxitérminos en una función canónica se los **multiplica** entre sí (Producto de Sumas, `PS` o `IIM`).
- **"Las variables que valen ‘1’ se leen negadas y las que valen ‘0’, directas":** regla de correspondencia entre la combinación binaria de una fila de la tabla (donde `F = 0`) y la escritura del Maxitérmino.

**🤔 Intuición (¿por qué en los Maxitérminos el `0` va directo y el `1` va negado?):**
*(Explicación adicional para comprender el porqué):*
En el Producto de Sumas (`PS`), estamos seleccionando las filas donde la función debe valer **`0`**. Como toda la función es una **multiplicación** de paréntesis `(Maxitérmino 1) • (Maxitérmino 2) • ...`, para que ese producto dé `0` en una fila específica, necesitamos que el paréntesis de esa fila **se anule (valga `0`)** exactamente cuando ingresan esos valores de `A, B, C`.
Ahora bien, una suma Booleana (`X + Y + Z`) solo da `0` cuando **todos sus sumandos son `0`** (`0 + 0 + 0 = 0`).
- Si en esa fila la variable `A` ya vale `0`, la dejamos **directa** (`A`) para que aporte un `0` a la suma.
- Si en esa fila la variable `C` vale `1`, no podemos dejarla directa porque `... + 1` haría que todo el paréntesis valga `1` en vez de `0`; por eso debemos **negarla** (`C̄`), de modo que `1̄ = 0` y toda la suma dé `0 + 0 + 0 = 0`.

**💡 Ejemplo (del material):**
- Para las variables `X, Y, Z`:
  - `X + Y + Z` y `X̄ + Y + Z̄` son Maxitérminos.
- En la tabla de verdad de `F(A,B,C) = A + B • C` (Pág. 4):
  - Fila `0` (`A=0, B=0, C=0`, donde `F=0`) → Maxitérmino `M_0 = (A + B + C)` (todas valen `0`, todas van directas).
  - Fila `1` (`A=0, B=0, C=1`, donde `F=0`) → Maxitérmino `M_1 = (A + B + C̄)` (`C` vale `1`, va negada).
  - Fila `2` (`A=0, B=1, C=0`, donde `F=0`) → Maxitérmino `M_2 = (A + B̄ + C)` (`B` vale `1`, va negada).

**🔗 Conexiones:**
- Es el concepto dual del **minitérmino** (4.4).
- Al multiplicar los Maxitérminos de las filas donde `F = 0`, se obtiene la forma canónica **Producto de Sumas (`PS` / `IIM`)** (4.7).

**⚠️ Precisiones / errores comunes:**
- **El error número 1 en los exámenes:** usar los `0` de la tabla para armar Maxitérminos pero asignar las variables igual que en los minitérminos (`1` directa y `0` negada), o viceversa. Recordar siempre la regla del material: en Maxitérminos (sumas canónicas), **miramos donde `F = 0`, y las variables que valen `1` van negadas y las que valen `0` van directas**.

**🎤 Cómo decirlo en el oral:**
> "Cuando en un término canónico todas las variables se relacionan mediante la operación suma, a ese término canónico se lo llama Maxitérmino o suma canónica. En la tabla de verdad, las sumas canónicas corresponden a aquellas combinaciones para las cuales la función vale 0 y conforman la productoria de maxitérminos, leyendo negadas las variables que valen 1 y directas las que valen 0."

---

## 4.4 Minitérmino (o Producto canónico)

> 📖 **Textual del material:** "Del mismo modo, si todas las variables se relacionan con la operación producto, a ese término canónico se lo llama minitérmino.
> Un par de ejemplos de minitérminos para esas tres variables podrían ser:
> X̄ . Y . Z; X . Ȳ . Z̄"
>
> 📖 **Textual del material:** "2| Los productos canónicos son aquellas combinaciones para las cuales la función vale 1 y conforman la sumatoria de minitérminos.
> NOTA: Las variables que valen ‘1’ se leen directas y las que valen ‘0’, negadas."

**🗣️ En palabras simples:**
Un **minitérmino** (también llamado **producto canónico** en la síntesis de la página 4) es un término canónico donde todas las variables de la función aparecen **multiplicadas** entre sí (una sola vez cada una, directa o negada). En la tabla de verdad, armamos un minitérmino por cada fila donde el resultado de la función da **`1`**, y acá la lectura de las variables es directa e intuitiva: si la variable vale `1` se escribe normal (directa), y si vale `0` se escribe negada (con barra).

**🔍 Desglose de la jerga:**
- **"Operación producto":** la operación `.` o `•` del Álgebra de Boole (conjunción / compuerta AND). A veces en el material se omite el punto y se escriben las letras juntas (p. ej. `ĀBC`), lo cual significa igualmente producto lógico `Ā . B . C`.
- **"minitérmino" (denotado con `m` minúscula en `∑m`):** recibe este nombre (contexto adicional) porque de las `2^n` combinaciones posibles de entrada, un producto de todas las variables vale `1` en **una única combinación** (el mínimo número posible de unos no nulo) y vale `0` en todas las demás.
- **"Productos canónicos":** sinónimo que emplea el material en la página 4 para referirse a los minitérminos.
- **"Conforman la sumatoria de minitérminos":** como cada minitérmino es un producto, para unir varios minitérminos en una función canónica se los **suma** entre sí (Suma de Productos, `SP` o `∑m`).
- **"Las variables que valen ‘1’ se leen directas y las que valen ‘0’, negadas":** regla de correspondencia entre la combinación binaria de una fila de la tabla (donde `F = 1`) y la escritura del minitérmino.

**🤔 Intuición (¿por qué en los minitérminos el `1` va directo y el `0` va negado?):**
*(Explicación adicional para comprender el porqué):*
En la Suma de Productos (`SP`), buscamos que la función valga **`1`** exactamente en las filas donde la tabla tiene un `1`. Como la función es una **suma** de términos (`minitérmino 1 + minitérmino 2 + ...`), basta con que el minitérmino correspondiente a esa fila se "encienda" (valga `1`) cuando entra esa combinación.
Pero un producto Booleano (`A . B . C`) solo da `1` cuando **todos sus factores valen `1`** (`1 . 1 . 1 = 1`).
- Si en esa fila una variable ya vale `1`, la dejamos **directa** para que aporte un `1` al producto.
- Si en esa fila una variable vale `0`, la escribimos **negada** (`0̄ = 1`) para convertir ese `0` en `1` y lograr que el producto dé `1 . 1 . 1 = 1` en esa fila.

**💡 Ejemplo (del material):**
- Para las variables `X, Y, Z`:
  - `X̄ . Y . Z` y `X . Ȳ . Z̄` son minitérminos.
- En la tabla de verdad de `F(A,B,C) = A + B • C` (Pág. 4):
  - Fila `3` (`0 1 1`, donde `F=1`) → minitérmino `m_3 = Ā B C` (`A=0` va negada; `B=1, C=1` van directas).
  - Fila `4` (`1 0 0`, donde `F=1`) → minitérmino `m_4 = A B̄ C̄` (`A=1` va directa; `B=0, C=0` van negadas).
  - Fila `7` (`1 1 1`, donde `F=1`) → minitérmino `m_7 = A B C` (todas valen `1`, todas van directas).

**🔗 Conexiones:**
- Es el dual del **Maxitérmino** (4.3).
- Al sumar los minitérminos de las filas donde `F = 1`, se obtiene la forma canónica **Suma de Productos (`SP` / `∑m`)** (4.7).

**⚠️ Precisiones / errores comunes:**
- **El orden de los factores dentro del minitérmino:** por la propiedad conmutativa del producto Booleano (`A . B . C = B . A . C`), aunque las variables dentro de un término estén desordenadas (como en el Desempeño 10: `F(ABC) = ABC + ABC̄ + B̄AC + CBĀ`), cada término sigue relacionando a todas las variables una sola vez mediante el producto, por lo que sigue siendo un minitérmino (si bien por prolijidad suele ordenarse alfabéticamente `A, B, C`).
- **Términos repetidos en una suma de minitérminos:** en la página 3 aparece `F(X,Y,Z) = XYZ + X̄YZ + X̄YZ + X̄ȲZ`, que el material clasifica como forma canónica ("es una suma de 4 minitérminos"), aunque por idempotencia (`X̄YZ + X̄YZ = X̄YZ`) los dos términos centrales son el mismo minitérmino.

**🎤 Cómo decirlo en el oral:**
> "Cuando todas las variables de la función se relacionan con la operación producto (una sola vez cada una, directa o complementada), a ese término canónico se lo llama minitérmino o producto canónico. En la tabla de verdad, los productos canónicos son aquellas combinaciones para las cuales la función vale 1 y conforman la sumatoria de minitérminos, leyendo directas las variables que valen 1 y negadas las que valen 0."

### Tabla comparativa: Maxitérmino vs. Minitérmino

| Característica | Maxitérmino (Suma canónica) | Minitérmino (Producto canónico) |
| :--- | :--- | :--- |
| **Operación interna del término** | Suma lógica (`+`), ej.: `(A + B + C̄)` | Producto lógico (`.` o `•`), ej.: `Ā . B . C` |
| **Valor de `F` que se toma en la tabla** | Filas donde la función vale **`0`** | Filas donde la función vale **`1`** |
| **Cómo se lee una variable que vale `0`** | **Directa** (sin complementar, ej.: `A`) | **Negada** (complementada, ej.: `Ā`) |
| **Cómo se lee una variable que vale `1`** | **Negada** (complementada, ej.: `Ā`) | **Directa** (sin complementar, ej.: `A`) |
| **Operación que une a los términos** | Producto (`.`) → **Producto de Sumas (`PS`)** | Suma (`+`) → **Suma de Productos (`SP`)** |
| **Símbolo de la forma canónica** | Productoria de maxitérminos: **`IIM`** (o **`∏M`**) | Sumatoria de minitérminos: **`∑m`** |

---

## 4.5 Reconocimiento de funciones en forma canónica (Casos de análisis del material)

> 📖 **Textual del material:** "Veamos algunos ejemplos así nos queda más claro:
> F(A,B) = Ā . B + A
> No está forma canónica, ya que el segundo término no es minitérmino ya que no están las dos variables multiplicadas.
> F(A,B) = (A + B) . (A + Ā)
> No está en forma canónica ya que en el segundo factor no es un maxitérmino, ya que una variable se repite y falta la otra.
> F̄ (XYZ) = X . Z + Y . Z + X . Ȳ
> Tampoco está en forma canónica, ya que para ser una suma de minitérminos, estarían faltando en cada término una variable, ya que debería haber 3 por cada minitérmino.
> F(A,B) = A . B
> Sí está en forma canónica, ya que sería un minitérmino solo.
> F (X,Y,Z) = (X + Y + Z) . (X + Ȳ + Z)
> Sí lo está, ya que es un producto de dos maxitérminos
> F (X,Y,Z) = XYZ + X̄YZ + X̄YZ + X̄ȲZ
> También está en forma canónica porque es una suma de 4 minitérminos."

**🗣️ En palabras simples:**
Para decidir si una función dada está o no en forma canónica, primero hay que mirar el paréntesis de declaración `F(...)` para saber **cuántas y cuáles son las variables de la función**. Después se revisa término por término (si es una suma) o factor por factor (si es un producto): si en todos y cada uno de ellos están todas las variables exactamente una vez y con la operación correcta, está en forma canónica; si falla aunque sea en un término, no lo está.

**🔍 Desglose de la jerga y criterios de rechazo/aceptación:**
1. **Falta alguna variable en algún término:** como en `F(A,B) = Ā . B + A` (falta `B` en el segundo término) o en `F̄(XYZ) = X . Z + Y . Z + X . Ȳ` (son 3 variables y cada término tiene solo 2).
2. **Se repite una variable y falta otra:** como en `F(A,B) = (A + B) . (A + Ā)` (en el segundo factor se repite `A` y falta `B`).
3. **Se agrupan variables en factores incompletos:** como en `F(PQRS) = (P + Q) . (R + S)` (del Desempeño 10): aunque entre toda la función aparecen las 4 variables `P, Q, R, S`, ningún factor tiene las 4 variables juntas (`P, Q, R, S`), por lo que ninguno de los dos paréntesis es un Maxitérmino de 4 variables.
4. **Un único término canónico es válido:** como en `F(A,B) = A . B` (un solo minitérmino) o `F(XY) = X + Y` (del Desempeño 10, un solo Maxitérmino).

**💡 Ejemplo (aplicado al Desempeño 10 de la Pág. 3):**
- `F(XY) = X + Y` → **Sí** está en forma canónica (es un único Maxitérmino de las dos variables `X, Y`).
- `F(XYZ) = X . Y̅.̅Z̅` → **No** está en forma canónica (la barra de negación abarca conjuntamente al producto `Y . Z` en lugar de afectar a cada variable de forma individual).
- `F(ABC) = ABC + ABC̄ + B̄AC + CBĀ` → **Sí** está en forma canónica (es una suma de 4 minitérminos; en cada uno figuran las 3 variables `A, B, C` una sola vez multiplicadas, sin importar que en `B̄AC` y `CBĀ` los factores estén escritos en otro orden por conmutatividad).
- `F(PQRS) = (P + Q) . (R + S)` → **No** está en forma canónica (la función es de 4 variables y cada factor suma solo 2 variables en vez de las 4).

**🔗 Conexiones:**
- Aplica directamente las definiciones 4.1, 4.2, 4.3 y 4.4.
- Si una función **no** está en forma canónica (como en los primeros tres ejemplos), la propiedad 4.6 garantiza que igualmente **puede ser llevada** a su forma canónica.

**⚠️ Precisiones / errores comunes:**
- **Mirar siempre la firma `F(...)` antes de responder:** la expresión `(P + Q)` sí sería canónica para `F(P,Q)`, pero **no** lo es para `F(P,Q,R,S)`.
- Detalle tipográfico del PDF en el sexto ejemplo de la página 3: el último término de `F(X,Y,Z) = XYZ + X̄YZ + X̄YZ + X̄ȲZ` tiene una barra continua sobre `XY`, que el autor usa allí para indicar `X̄ . Ȳ . Z` ("suma de 4 minitérminos"). Conviene saber que en el texto del módulo a veces dos variables negadas contiguas se imprimieron con barra unida, pero conceptualmente en un minitérmino cada variable está complementada por separado (`X̄ . Ȳ . Z`), que por De Morgan no es lo mismo que `X̅.̅Y̅ . Z`.

**🎤 Cómo decirlo en el oral:**
> "Para verificar si una función está en forma canónica, observo primero de cuántas variables depende la función. Luego compruebo que sea íntegramente una suma de minitérminos o un producto de Maxitérminos: en cada término o factor deben figurar todas las variables de la función, una sola vez cada una (directa o complementada) y vinculadas por una única operación. Incluso si consta de un solo minitérmino, como `F(A,B) = A . B`, sí está en forma canónica."

---

## 4.6 Existencia de la forma canónica de toda función Booleana

> 📖 **Textual del material:** "Toda función, aunque no esté escrita en la forma canónica, puede ser llevada mediante procedimientos algebraicos o por medio de tablas de verdad, a dicha forma. Debe quedar claro que toda función tiene su forma canónica."

**🗣️ En palabras simples:**
No importa cuán desordenada, corta o mezclada esté escrita una función Booleana: **siempre** tiene forma canónica, y **siempre** podemos encontrarla usando uno de dos caminos posibles: haciendo cuentas con los axiomas y propiedades (camino algebraico) o armando su tabla de verdad y leyendo los `0` y los `1` de la columna de resultados (camino por tabla).

**🔍 Desglose de la jerga:**
- **"Toda función ... tiene su forma canónica":** afirma la existencia universal de la representación canónica para cualquier función Booleana.
- **"Mediante procedimientos algebraicos":** aplicando axiomas del Álgebra de Boole (neutro, complemento, distributiva, idempotencia) para incorporar las variables ausentes en cada término sin alterar la equivalencia lógica de la función (ver Sección 4.8).
- **"Por medio de tablas de verdad":** evaluando la función en las `2^n` combinaciones de entrada y extrayendo la sumatoria de minitérminos (`∑m`) de las filas con resultado `1` y la productoria de maxitérminos (`IIM`) de las filas con resultado `0` (ver Sección 4.7).

**🤔 Intuición:**
¿Por qué toda función Booleana tiene forma canónica? Porque cualquier función Booleana de `n` variables queda completamente determinada por su tabla de verdad (qué devuelve para cada una de las `2^n` entradas posibles), y a partir de cualquier tabla de verdad se pueden leer directamente los minitérminos (donde da `1`) y los Maxitérminos (donde da `0`). *(Única excepción teórica extrema: la función constante `0` no tiene filas con `1` para minitérminos, y la función constante `1` no tiene filas con `0` para Maxitérminos, pero toda función no constante posee ambas expresiones no vacías).*

**💡 Ejemplo:**
- La función `F(A,B,C) = A + B . C` no está en forma canónica (al primer término le faltan `B` y `C`, y al segundo le falta `A`), pero tiene dos formas canónicas equivalentes:
  - Productoria de Maxitérminos: `F(A,B,C) = IIM_(0,1,2) = (A+B+C) • (A+B+C̄) • (A+B̄+C)`
  - Sumatoria de minitérminos: `F(A,B,C) = ∑m_(3,4,5,6,7) = ĀBC + AB̄C̄ + AB̄C + ABC̄ + ABC`

**🔗 Conexiones:**
- Conecta el reconocimiento de formas canónicas (4.5) con los dos métodos constructivos de la clase: el método por **Tabla de Verdad** (4.7) y el **Procedimiento Algebraico** (4.8).

**⚠️ Precisiones / errores comunes:**
- Cuando el profesor pregunta *"¿Cuántas formas canónicas tiene una función Booleana?"*, recordar que existen **dos tipos** de formas canónicas para una misma función: la **Suma de Productos** (sumatoria de minitérminos) y el **Producto de Sumas** (productoria de maxitérminos), y que ambas son equivalentes a la función original porque **tienen la misma tabla de verdad**.

**🎤 Cómo decirlo en el oral:**
> "Toda función Booleana, aunque no esté escrita en forma canónica, tiene su forma canónica y puede ser llevada a dicha forma mediante dos caminos: mediante procedimientos algebraicos o por medio de tablas de verdad."

---

## 4.7 Método 1: Forma canónica a partir de la Tabla de Verdad (Notaciones IIM y ∑m)

> 📖 **Textual del material:** "Como ya vimos, a partir de una función Booleana podemos encontrar la tabla de verdad, ahora veremos cómo escribir su forma canónica utilizando los resultados de la tabla. Mediante un ejemplo con la función F(A,B,C) = A + B . C
> Se construye una Tabla de Verdad de la función dada y se observa la última columna que es la de resultado de la función: Las filas donde la función da ‘0’ conformarán la expresión productoria de sumas y las filas donde la función toma valor ‘1’ conformarán la expresión sumatoria de productos. Para ubicarnos mejor en la tabla, utilizamos el número de secuencia decimal en el extremo izquierdo de la tabla, que coincide con las combinaciones binarias de las variables."
>
> 📖 **Textual del material:** "Entonces las formas canónicas de f(A,B,C) = A + B • C
> Son:
> F (A,B,C) = IIM_(0,1,2) = (A+B+C) • (A+B+ C̄ ) • (A+ B̄ +C)
> F (A,B,C) = ∑m_(3,4,5,6,7) = ĀBC + AB̄C̄ + AB̄C + ABC̄ + ABC
> Estas tres expresiones tienen la misma tabla de verdad. Observe que las formas canónicas por lo general, son mucho más extensas que la función original.
> En síntesis:
> 1| Las sumas canónicas son aquellas combinaciones para las cuales la función vale 0 y conforman la productoria de maxitérminos.
> NOTA: Las variables que valen ‘1’ se leen negadas y las que valen ‘0’, directas.
> 2| Los productos canónicos son aquellas combinaciones para las cuales la función vale 1 y conforman la sumatoria de minitérminos.
> NOTA: Las variables que valen ‘1’ se leen directas y las que valen ‘0’, negadas."

**🗣️ En palabras simples:**
Este algoritmo transforma cualquier función en sus dos formas canónicas usando su tabla de verdad:
1. Armás la tabla de verdad de la función y le agregás a la izquierda una columna llamada `Sec. Dec.` (Secuencia Decimal: `0, 1, 2, ..., 2^n - 1`, que es el valor en base 10 de cada fila binaria).
2. Mirás la última columna (el resultado final de la función):
   - **Para el Producto de Sumas (`PS` / `IIM`):** elegís las filas donde el resultado dio **`0`**. Por cada una armás una suma con todas las variables (si la variable en esa fila tiene un `0` va directa; si tiene un `1` va negada) y multiplicás todos esos paréntesis.
   - **Para la Suma de Productos (`SP` / `∑m`):** elegís las filas donde el resultado dio **`1`**. Por cada una armás un producto con todas las variables (si la variable en esa fila tiene un `1` va directa; si tiene un `0` va negada) y sumás todos esos términos.

**🔍 Desglose de la jerga y de la notación del material:**
- **`Sec. Dec.` (Número de secuencia decimal):** número entero desde `0` hasta `2^n - 1` ubicado en el extremo izquierdo de la tabla que equivale a traducir la combinación binaria de las variables de esa fila al sistema decimal (por ejemplo, `0 1 1` en binario es `3` en decimal). Sirve para identificar por su índice a cada Maxitérmino y a cada minitérmino.
- **`PS` (Términos Producto de Sumas) / `Expresión productoria de sumas` / `Productoria de maxitérminos`:** forma canónica conjuntiva obtenida multiplicando los Maxitérminos de las filas donde `F = 0`.
- **`IIM_(...)` (o `∏M(...)`):** notación compacta de la productoria (`∏`, escrita como `II` en la tipografía del módulo) de Maxitérminos (`M`), donde entre paréntesis como subíndice se listan los números de secuencia decimal de las filas en que la función vale `0`. Ejemplo: `IIM_(0,1,2)`.
- **`SP` (Términos Suma de Productos) / `Expresión sumatoria de productos` / `Sumatoria de minitérminos`:** forma canónica disyuntiva obtenida sumando los minitérminos de las filas donde `F = 1`.
- **`∑m_(...)` (o `∑_m(...)`):** notación compacta de la sumatoria (`∑`) de minitérminos (`m`), donde entre paréntesis se listan los números de secuencia decimal de las filas en que la función vale `1`. Ejemplo: `∑m_(3,4,5,6,7)`.

**💡 Ejemplo completo del material (`F(A,B,C) = A + B • C`, Pág. 4):**

| Categoría en el material | Sec. Dec. | A | B | C | B . C | A + B • C | Término canónico asociado |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Términos Producto de Sumas. (PS)** | **0** | 0 | 0 | 0 | 0 | **0** | Maxitérmino `(0)`: `(A + B + C)` |
| **Términos Producto de Sumas. (PS)** | **1** | 0 | 0 | 1 | 0 | **0** | Maxitérmino `(1)`: `(A + B + C̄)` |
| **Términos Producto de Sumas. (PS)** | **2** | 0 | 1 | 0 | 0 | **0** | Maxitérmino `(2)`: `(A + B̄ + C)` |
| **Términos Suma de Productos. (SP)** | **3** | 0 | 1 | 1 | 1 | **1** | minitérmino `(3)`: `Ā B C` |
| **Términos Suma de Productos. (SP)** | **4** | 1 | 0 | 0 | 0 | **1** | minitérmino `(4)`: `A B̄ C̄` |
| **Términos Suma de Productos. (SP)** | **5** | 1 | 0 | 1 | 0 | **1** | minitérmino `(5)`: `A B̄ C` |
| **Términos Suma de Productos. (SP)** | **6** | 1 | 1 | 0 | 0 | **1** | minitérmino `(6)`: `A B C̄` |
| **Términos Suma de Productos. (SP)** | **7** | 1 | 1 | 1 | 1 | **1** | minitérmino `(7)`: `A B C` |

- **Producto de sumas `IIM_(0,1,2)`:**
  - `F (A,B,C) = IIM_(0,1,2) = (A+B+C) • (A+B+ C̄ ) • (A+ B̄ +C)`
- **Suma de Productos `∑m_(3,4,5,6,7)`:**
  - `F (A,B,C) = ∑m_(3,4,5,6,7) = ĀBC + AB̄C̄ + AB̄C + ABC̄ + ABC`

**🔗 Conexiones:**
- Es el procedimiento inverso a evaluar una función en una tabla: permite pasar de la tabla a la expresión algebraica (base de la Sección 4.9).
- Muestra por qué hace falta la **simplificación de funciones** (Sección 4.10): como subraya el material, *"las formas canónicas por lo general, son mucho más extensas que la función original"* (`A + B • C` tiene solo 2 operaciones, mientras que `∑m_(3,4,5,6,7)` tiene 5 términos de 3 variables cada uno).

**⚠️ Precisiones / errores comunes:**
- **Partición complementaria de los índices:** observar que los números de secuencia decimal que van en `IIM` y los que van en `∑m` son mutuamente excluyentes y entre ambos completan todas las filas de la tabla (`{0, 1, 2}` para los `0` y `{3, 4, 5, 6, 7}` para los `1`, completando los `2^3 = 8` estados de `0` a `7`). Si una función de 3 variables tiene 3 Maxitérminos, obligatoriamente tendrá `8 - 3 = 5` minitérminos.
- **Respetar el orden de las variables al armar la tabla:** para que el número de secuencia decimal coincida con la combinación binaria (`A B C`), la tabla debe estar ordenada en binario creciente (`000` a `111`), siendo `A` el bit más significativo y `C` el menos significativo.

**🎤 Cómo decirlo en el oral:**
> "Para hallar la forma canónica a partir de la tabla de verdad, construimos la tabla de la función numerando las filas con el número de secuencia decimal (que coincide con las combinaciones binarias de las variables) y observamos la última columna de resultado:
> 1. Las filas donde la función vale `0` determinan las sumas canónicas y conforman la **productoria de maxitérminos** (`IIM`), donde las variables que valen `1` se leen negadas y las que valen `0`, directas.
> 2. Las filas donde la función vale `1` determinan los productos canónicos y conforman la **sumatoria de minitérminos** (`∑m`), donde las variables que valen `1` se leen directas y las que valen `0`, negadas.
> Tanto la función original como sus dos formas canónicas tienen exactamente la misma tabla de verdad."

---

## 4.8 Método 2: Obtención de la forma canónica mediante procedimiento algebraico

> 📖 **Textual del material:** "En esta clase veremos cómo escribir las funciones Booleanas en su forma canónica, mediante un procedimiento algebraico y otro mediante tabla de verdad."
>
> 📖 **Textual del material:** "Toda función, aunque no esté escrita en la forma canónica, puede ser llevada mediante procedimientos algebraicos o por medio de tablas de verdad, a dicha forma. Debe quedar claro que toda función tiene su forma canónica."

**🗣️ En palabras simples:**
*(Nota: El material enuncia este método en las páginas 2 y 3 y lo pide en los Desempeños 12, 13 y 16, por lo que incluimos aquí la explicación paso a paso del procedimiento algebraico basado estrictamente en los axiomas de la Unidad 1).*
Llevar una función a su forma canónica **algebraicamente** (sin hacer la tabla de verdad) consiste en "completar" en cada término las variables que le faltan, usando los axiomas de elemento neutro (`Axioma 3`), complemento (`Axioma 4`) y propiedad distributiva (`Axioma 2`), para que no cambie el valor de la función:
- Si queremos llegar a una **Suma de Minitérminos (`SP`)**, a cada producto al que le falte una variable `X` lo **multiplicamos por `1`** (neutro del producto, Axioma 3) y reemplazamos ese `1` por **`(X + X̄)`** (complemento, Axioma 4); luego distribuimos (Axioma 2).
- Si queremos llegar a un **Producto de Maxitérminos (`PS`)**, a cada suma a la que le falte una variable `X` le **sumamos `0`** (neutro de la suma, Axioma 3) y reemplazamos ese `0` por **`(X • X̄)`** (complemento, Axioma 4); luego aplicamos la propiedad distributiva de la suma respecto del producto (Axioma 2: `A + (X • X̄) = (A + X) • (A + X̄)`).
- Finalmente, si quedan minitérminos o Maxitérminos repetidos, se eliminan los duplicados por la propiedad de **idempotencia** (`T + T = T` o `T • T = T`).

**🔍 Desglose de los pasos del procedimiento algebraico (Contexto adicional fiel a los axiomas de la Unidad 1):**

### A) Procedimiento algebraico para llevar a Suma de Minitérminos (`SP`)
1. Si hay paréntesis o negaciones sobre expresiones compuestas, primero se aplican leyes de De Morgan y distributiva hasta obtener una suma de productos.
2. Se inspecciona cada término: si a un producto le falta una variable `X`:
   - **Paso 1 (Axioma 3 — Elemento neutro del producto):** se multiplica el término por `1` (`T = T • 1`).
   - **Paso 2 (Axioma 4 — Complemento):** se sustituye `1` por la suma de la variable faltante y su complemento: `1 = X + X̄`, quedando `T • (X + X̄)`.
   - **Paso 3 (Axioma 2 — Distributiva del producto respecto de la suma):** se distribuye `T • (X + X̄) = T • X + T • X̄`.
3. Se repite para todas las variables que falten hasta que cada término tenga todas las variables de la función.
4. **Paso 4 (Teorema de Idempotencia):** si algún minitérmino aparece más de una vez (`m_i + m_i = m_i`), se deja una sola vez.

### B) Procedimiento algebraico para llevar a Producto de Maxitérminos (`PS`)
1. Se lleva la expresión a un producto de sumas (aplicando distributiva de la suma respecto del producto si fuera necesario).
2. Se inspecciona cada factor (paréntesis de suma): si a un factor `S` le falta una variable `X`:
   - **Paso 1 (Axioma 3 — Elemento neutro de la suma):** se le suma `0` al factor (`S = S + 0`).
   - **Paso 2 (Axioma 4 — Complemento):** se sustituye `0` por el producto de la variable faltante y su complemento: `0 = X • X̄`, quedando `S + (X • X̄)`.
   - **Paso 3 (Axioma 2 — Distributiva de la suma respecto del producto):** se distribuye la suma sobre el producto: `S + (X • X̄) = (S + X) • (S + X̄)`.
3. Se repite hasta que todos los factores contengan a todas las variables de la función.
4. **Paso 4 (Teorema de Idempotencia):** si algún Maxitérmino quedó repetido (`M_i • M_i = M_i`), se deja una sola vez.

**💡 Ejemplo (aplicado al Desempeño 12.a de la Pág. 6 del material):**
- **Caso i (a Suma de Minitérminos):** `F(A,B,C) = A • B • C + Ā • B • C + B̄ • C̄`
  - Los dos primeros términos ya son minitérminos (tienen `A, B, C`). Al tercer término (`B̄ • C̄`) le falta `A`:
  - Por Axioma 3 (neutro del producto): `B̄ • C̄ = 1 • B̄ • C̄`
  - Por Axioma 4 (complemento): `1 • B̄ • C̄ = (A + Ā) • B̄ • C̄`
  - Por Axioma 2 (distributiva): `(A + Ā) • B̄ • C̄ = A • B̄ • C̄ + Ā • B̄ • C̄`
  - Resultado en forma canónica (suma de minitérminos):
    `F(A,B,C) = A • B • C + Ā • B • C + A • B̄ • C̄ + Ā • B̄ • C̄`
- **Caso ii (a Producto de Maxitérminos):** `G(A,B,C) = (A + B) • (Ā + C) • (B̄ + C)`
  - Al primer factor le falta `C`, al segundo le falta `B` y al tercero le falta `A`.
  - Por Axioma 3 (`+ 0`) y Axioma 4 (`0 = X • X̄`):
    `G(A,B,C) = (A + B + C • C̄) • (Ā + B • B̄ + C) • (A • Ā + B̄ + C)`
  - Por Axioma 2 (distributiva de `+` respecto de `•`):
    - `(A + B + C • C̄) = (A + B + C) • (A + B + C̄)`
    - `(Ā + B • B̄ + C) = (Ā + B + C) • (Ā + B̄ + C)`
    - `(A • Ā + B̄ + C) = (A + B̄ + C) • (Ā + B̄ + C)`
  - Uniendo todos los factores y aplicando idempotencia en `(Ā + B̄ + C)` que aparece dos veces:
    `G(A,B,C) = (A + B + C) • (A + B + C̄) • (Ā + B + C) • (Ā + B̄ + C) • (A + B̄ + C)`

**🔗 Conexiones:**
- Es el proceso **exactamente inverso** a la **Simplificación de funciones** (Sección 4.10): mientras que para simplificar sacamos factor común `(A + Ā)` y lo convertimos en `1` para eliminar una variable, para llevar a la forma canónica introducimos un `1` y lo reemplazamos por `(A + Ā)` para agregar la variable que falta.

**⚠️ Precisiones / errores comunes:**
- **No olvidarse de eliminar términos repetidos al final (idempotencia):** al expandir varios términos incompletos, es muy frecuente que dos términos distintos generen el mismo minitérmino (o el mismo Maxitérmino). Si no se aplica `X + X = X` (o `X • X = X`), el resultado algebraico tendrá más términos que los que aparecen en la tabla de verdad.

**🎤 Cómo decirlo en el oral:**
> "Para llevar una función a su forma canónica mediante procedimiento algebraico, completamos en cada término las variables que faltan aplicando los axiomas del Álgebra de Boole en sentido inverso a la simplificación:
> - Si buscamos la **suma de minitérminos**, multiplicamos cada término incompleto por `1` (Axioma 3), reemplazamos `1` por `(X + X̄)` siendo `X` la variable que falta (Axioma 4), y aplicamos propiedad distributiva (Axioma 2).
> - Si buscamos el **producto de Maxitérminos**, sumamos `0` a cada factor incompleto (Axioma 3), reemplazamos `0` por `(X • X̄)` (Axioma 4), y aplicamos la distributiva de la suma respecto del producto (Axioma 2).
> Por último, si quedan términos o factores repetidos, los reducimos por idempotencia."

---

## 4.9 Síntesis de una función Booleana a partir de los resultados deseados (Aplicación principal)

> 📖 **Textual del material:** "Esta forma de escribir la función utilizando la tabla de verdad, nos permitirá realizar una de las principales aplicaciones, que consiste en encontrar una función que logre llegar a los resultados que queremos. Es decir si nosotros sabemos qué resultados deseamos a la salida para cada combinación de entrada podremos determinar la función que lo provoca."
>
> 📖 **Textual del material:** "Ahora bien, por lo que vimos más arriba en la forma canónica a partir de la tabla, podemos escribir entonces la forma canónica de la función que deseamos encontrar, tomando los 1, o los 0 del resultado. Si usamos los 1 tendríamos la suma de productos, y si usamos los 0 tendríamos el producto de las sumas. Ambas serían formas canónicas de la misma función."
>
> 📖 **Textual del material:** "Si recordamos que una función tiene un circuito lógico, que podría ser además un circuito eléctrico, mientras menos elementos haya en el circuito, más económico será y más rápido llegaremos al resultado, es decir que mientras menos elementos haya, sería más eficiente el circuito. ¿Pero cuáles eran los elementos del circuito? Las compuertas lógicas, y esas compuertas representan las operaciones entre las variables, por lo que si queremos que hayan menos compuertas en el circuito, deberán haber menos operaciones en la función. En conclusión, el paso que daremos ahora es el de simplificar la función."

**🗣️ En palabras simples:**
Hasta la Clase 3 el problema era: *"te doy la fórmula de la función y vos armás la tabla y el circuito"*. Ahora en la Clase 4 podemos resolver el problema de ingeniería real (el camino inverso): **no tenemos la fórmula**, solo sabemos cómo queremos que se comporte el sistema (para qué entradas debe encenderse dando `1` y para cuáles debe apagarse dando `0`).
¿Cómo encontramos la fórmula? Escribimos la tabla con los resultados deseados y leemos directamente su **forma canónica** (usando los `1` para suma de minitérminos o los `0` para producto de Maxitérminos). Y una vez que tenemos esa función canónica, la **simplificamos** para que el circuito tenga menos compuertas lógicas, sea más barato y más rápido (más eficiente).

**🔍 Desglose de la jerga y cadena causal hacia la eficiencia:**
- **"Encontrar una función que logre llegar a los resultados que queremos":** diseño o síntesis lógica a partir de una especificación por tabla de verdad.
- **"Tomando los 1, o los 0 del resultado":** cualquiera de los dos caminos (Suma de Productos con los `1`, o Producto de Sumas con los `0`) resuelve el problema porque ambas son formas canónicas de la misma función.
- **Cadena causal de eficiencia del circuito (muy preguntada en el oral):**
  1. Toda función Booleana tiene asociado un **circuito lógico** (que físicamente puede ser un **circuito eléctrico**).
  2. Los elementos del circuito son las **compuertas lógicas**.
  3. Las compuertas lógicas representan las **operaciones entre las variables** de la función (`+`, `.`, `¯`).
  4. Por lo tanto: **menos operaciones en la función** ⇒ **menos compuertas lógicas (menos elementos en el circuito)** ⇒ un circuito **más económico** y **más rápido** para llegar al resultado ⇒ un circuito **más eficiente**.

**💡 Ejemplo del material (Pág. 5):**
Supongamos que para dos variables `A` y `B` deseamos obtener a la salida los siguientes resultados:

| A | B | F (A,B) | Minitérmino (tomando los `1`) |
| :---: | :---: | :---: | :--- |
| 0 | 0 | **1** | `0 0 1` → minitérmino `Ā . B̄` |
| 0 | 1 | **0** | *(fila con `0`: daría el único Maxitérmino `A + B̄`)* |
| 1 | 0 | **1** | `1 0 1` → minitérmino `A . B̄` |
| 1 | 1 | **1** | `1 1 1` → minitérmino `A . B` |

- Tomando los `1` (primera, tercera y cuarta combinación de entradas), la forma canónica de la función buscada es:
  > 📖 **Textual del material:** "Por lo que la forma canónica de la función sería:
  > F(A,B) = Ā . B̄ + A . B̄ + A . B"

**🔗 Conexiones:**
- Conecta la **forma canónica a partir de la tabla de verdad** (4.7) con los **circuitos lógicos y compuertas** vistos en la Clase 3 y justifica por qué existe la **simplificación de funciones** (4.10).

**⚠️ Precisiones / errores comunes:**
- Si el profesor pregunta *"¿Para qué sirve la forma canónica en la práctica?"*, la respuesta exacta del material es: permite encontrar una función Booleana cuando no conocemos la fórmula pero sí sabemos qué resultados deseamos a la salida para cada combinación de entrada.
- Si pregunta *"¿Por qué no implementamos directamente el circuito de la forma canónica si ya arroja los resultados que queríamos?"*, la respuesta es: porque las formas canónicas son más extensas (tienen más operaciones), lo que implica más compuertas lógicas, haciendo al circuito más caro y más lento (menos eficiente).

**🎤 Cómo decirlo en el oral:**
> "Una de las principales aplicaciones de la forma canónica a partir de la tabla de verdad es poder determinar una función Booleana cuando no la conocemos pero sí sabemos qué resultados deseamos a la salida para cada combinación de entrada: tomamos los `1` de la tabla para armar la suma de productos (o los `0` para el producto de sumas). Luego, como cada operación entre variables representa una compuerta lógica en el circuito, buscamos simplificar esa función: mientras menos operaciones tenga la expresión, menos compuertas tendrá el circuito, por lo que será más económico, más rápido y, en conclusión, más eficiente."

---

## 4.10 Simplificación de funciones Booleanas

> 📖 **Textual del material:** "Si ustedes recuerdan, cuando vimos la forma canónica mediante la tabla, al llegar a las formas canónicas observamos que esas expresiones son más extensas que la función original, entonces simplificar las funciones significa buscar escribir las mismas de una manera más reducida, mediante la utilización de los axiomas y teoremas enunciados como propiedades.
> Debe tener presente que siempre que cambie el formato de una expresión, ese cambio debe estar justificado por alguna de las propiedades enunciadas, ¡NO Vale Inventar Nuevas!"
>
> 📖 **Textual del material (Recuadro de la Pág. 6):**
> "F (A,B) = Ā . B̄ + A . B̄ + A . B
>
> Por Axioma 2
> F (A,B) = B̄ . ( Ā + A) + A . B
> Por axioma 4
> F (A,B) = B̄ . 1 + A . B
> Por Axioma 3
> F (A,B) = B̄ + A . B
>
> Por Axioma 2
> F (A,B) = B̄ . A + B̄ . B
> Por Axioma 4
> F (A,B) = B̄ . A + 0
> Por Axioma 3
> F (A,B) = B̄ . A"

**🗣️ En palabras simples:**
**Simplificar una función Booleana** es achicar su expresión algebraica (lograr que tenga menos términos y menos operaciones) pero manteniendo exactamente la misma tabla de verdad. La regla innegociable del curso es que **cada paso algebraico debe estar respaldado por un axioma o teorema del Álgebra de Boole**.

**🔍 Desglose de la jerga:**
- **"Escribir las mismas de una manera más reducida":** obtener una expresión lógica equivalente (es decir, que arroje idéntica tabla de verdad que la función original) pero con menor cantidad de literales y operaciones.
- **"Mediante la utilización de los axiomas y teoremas enunciados como propiedades":**
  - **Axioma 2:** Propiedad conmutativa y propiedad distributiva (tanto del producto respecto de la suma `X . (Y + Z) = X . Y + X . Z`, como de la suma respecto del producto `X + (Y . Z) = (X + Y) . (X + Z)`).
  - **Axioma 3:** Existencia de elementos neutros (`X . 1 = X` para el producto y `X + 0 = X` para la suma).
  - **Axioma 4:** Existencia del complemento (`X + X̄ = 1` y `X . X̄ = 0`).
  - **Teoremas / propiedades de la Unidad 1:** idempotencia, involución (doble negación), absorción, leyes de De Morgan, elementos absorbentes/dominación (`X + 1 = 1`, `X . 0 = 0`), asociatividad.

**🧩 Idea de la demostración / Resolución paso a paso del ejemplo del material:**
Partimos de la función hallada en la Sección 4.9:
`F(A,B) = Ā . B̄ + A . B̄ + A . B`
1. **Primer tramo (columna izquierda del recuadro de Pág. 6 — Correcto):**
   - Entre los dos primeros términos (`Ā . B̄ + A . B̄`), por **Axioma 2** (conmutativa y distributiva / factor común `B̄`), se extrae `B̄`:
     `F(A,B) = B̄ . (Ā + A) + A . B`
   - Por **Axioma 4** (complemento en la suma: `Ā + A = 1`):
     `F(A,B) = B̄ . 1 + A . B`
   - Por **Axioma 3** (elemento neutro del producto: `B̄ . 1 = B̄`):
     `F(A,B) = B̄ + A . B`

2. **Segundo tramo (continuación desde `F(A,B) = B̄ + A . B`):**
   - *(Ver advertencia crítica abajo sobre la errata de imprenta en la columna derecha de la página 6 del PDF).*
   - **Desarrollo algebraico correcto desde `F(A,B) = B̄ + A . B`:**
     - **Por Axioma 2** (distributiva de la suma `+` respecto del producto `.`):
       `F(A,B) = (B̄ + A) . (B̄ + B)`
     - **Por Axioma 4** (complemento en la suma: `B̄ + B = 1`):
       `F(A,B) = (B̄ + A) . 1`
     - **Por Axioma 3** (elemento neutro del producto):
       `F(A,B) = B̄ + A` (o `A + B̄`)

**⚠️ Precisiones / errores comunes (¡ATENCIÓN ESPECIAL A LA ERRATA DE LA PÁGINA 6 DEL PDF!):**
- **Errata en la segunda columna del recuadro de la Pág. 6 del material:**
  En la página 6 del PDF oficial, luego de llegar correctamente a `F(A,B) = B̄ + A . B` al final de la columna izquierda, en la columna derecha el autor intentó distribuir `B̄` sobre `A . B`, pero escribió por error `F(A,B) = B̄ . A + B̄ . B = B̄ . A + 0 = B̄ . A` (como si la expresión anterior hubiera sido un producto `B̄ . (A + B)` en lugar de la suma `B̄ + (A . B)`).
  - **¿Cómo comprobar que `B̄ . A` es una errata de tipeo del apunte y que el resultado correcto es `B̄ + A`?**
    Comparando las tablas de verdad (que es justamente el control que el propio apunte enseña en los Desempeños 13.d y 16.b: *"Hacer las dos tablas (función original y función simplificada) y compararlas"*):
    - En la tabla original de la página 5, para `A = 0, B = 0` la función vale **`1`**, y para `A = 1, B = 1` la función también vale **`1`**.
    - Con `F(A,B) = B̄ + A . B` (y con su simplificación correcta `F(A,B) = B̄ + A`), para `(0,0)` da `1 + 0 = 1` y para `(1,1)` da `0 + 1 = 1` (**coincide exactamente con la tabla de la Pág. 5**, y además coincide con el único Maxitérmino de la fila `0 1`, que es `A + B̄`).
    - En cambio, `B̄ . A` para `(0,0)` da `1 . 0 = 0` y para `(1,1)` da `0 . 1 = 0`, por lo que cambia la tabla de verdad.
  - **Consejo para el oral:** si el profesor menciona este ejemplo de la página 6, vos conocés tanto los tres pasos exactos que se aplican (**Axioma 2 → Axioma 4 → Axioma 3**) como el detalle de que al distribuir en `B̄ + A . B` por Axioma 2 se distribuye la suma respecto del producto `(B̄ + A) . (B̄ + B) = (B̄ + A) . 1 = B̄ + A`.
- **Verificación de una simplificación:** la función original y la función simplificada **deben tener idéntica tabla de verdad**. Si al construir ambas tablas difieren aunque sea en una fila, algún paso algebraico fue inválido.

**🎤 Cómo decirlo en el oral:**
> "Simplificar una función Booleana significa escribirla de una manera más reducida (con menos operaciones) utilizando exclusivamente los axiomas y teoremas enunciados como propiedades, de modo que cada cambio de formato esté justificado por una propiedad y la función simplificada conserve exactamente la misma tabla de verdad que la función original, logrando así un circuito lógico más eficiente."

---

## 🧠 Resumen esquemático de la clase

- **Forma canónica (definición general):** una función Booleana está en forma canónica cuando es una **suma o un producto de términos canónicos**.
- **Término canónico:** expresión que relaciona a **todas las variables** de la función (ya sea directa o complementada) **una sola vez** mediante **una sola operación** (todas sumadas o todas multiplicadas).
- **Maxitérmino (Suma canónica):** término canónico donde todas las variables se relacionan con la operación **suma (`+`)**. En la tabla de verdad corresponde a las filas donde `F = 0`; las variables que valen `'1'` se leen **negadas** y las que valen `'0'`, **directas**.
- **Minitérmino (Producto canónico):** término canónico donde todas las variables se relacionan con la operación **producto (`.`)**. En la tabla de verdad corresponde a las filas donde `F = 1`; las variables que valen `'1'` se leen **directas** y las que valen `'0'`, **negadas**.
- **Forma canónica (definición específica):** una función está en forma canónica cuando es una **suma de minitérminos** (`SP` / `∑m`) o es un **producto de Maxitérminos** (`PS` / `IIM`).
- **Existencia de la forma canónica:** **toda función Booleana tiene su forma canónica** y puede ser llevada a ella mediante **procedimientos algebraicos** o por medio de **tablas de verdad**.
- **Número de secuencia decimal (`Sec. Dec.`):** columna a la izquierda de la tabla de verdad que numera las filas en decimal (`0` a `2^n - 1`) coincidiendo con las combinaciones binarias de las variables, usada para indexar `IIM_(...)` y `∑m_(...)`.
- **Equivalencia de las formas canónicas:** la función original, su productoria de maxitérminos (`IIM`) y su sumatoria de minitérminos (`∑m`) **tienen la misma tabla de verdad** (aunque las formas canónicas suelen ser mucho más extensas).
- **Aplicación principal (síntesis desde tabla):** si conocemos qué resultados deseamos a la salida para cada combinación de entrada, podemos hallar la función que los provoca escribiendo su forma canónica a partir de los `1` (suma de productos) o de los `0` (producto de sumas).
- **Eficiencia del circuito lógico:** menos operaciones en la función ⇒ menos compuertas lógicas (menos elementos en el circuito) ⇒ circuito **más económico y más rápido** (más eficiente).
- **Simplificación de funciones:** buscar escribir las funciones de una manera más reducida mediante la utilización de los axiomas y teoremas enunciados como propiedades (justificando cada paso, sin inventar propiedades nuevas).

---

## ❓ Preguntas probables del oral

1. **¿Cuándo una función Booleana está escrita en forma canónica?**
   - **Respuesta:** Una función Booleana está escrita en forma canónica cuando es una suma o un producto de términos canónicos; es decir, cuando es una suma de minitérminos o es un producto de Maxitérminos.

2. **¿Qué es un término canónico?**
   - **Respuesta:** Un término canónico es una expresión que relaciona a todas las variables de la función (ya sea directa o complementada) una sola vez mediante una sola operación.

3. **¿Qué es un Maxitérmino y cómo se leen sus variables en la tabla de verdad?**
   - **Respuesta:** Cuando en un término canónico todas las variables se relacionan con la operación suma, a ese término canónico se lo llama Maxitérmino (o suma canónica). En la tabla de verdad, las sumas canónicas son aquellas combinaciones para las cuales la función vale `0` y conforman la productoria de maxitérminos (`IIM`), leyendo las variables que valen `'1'` negadas y las que valen `'0'`, directas.

4. **¿Qué es un minitérmino y cómo se leen sus variables en la tabla de verdad?**
   - **Respuesta:** Cuando en un término canónico todas las variables se relacionan con la operación producto, a ese término canónico se lo llama minitérmino (o producto canónico). En la tabla de verdad, los productos canónicos son aquellas combinaciones para las cuales la función vale `1` y conforman la sumatoria de minitérminos (`∑m`), leyendo las variables que valen `'1'` directas y las que valen `'0'`, negadas.

5. **¿Por qué la función `F(A,B) = Ā . B + A` no está en forma canónica?**
   - **Respuesta:** No está en forma canónica porque el segundo término (`A`) no es un minitérmino, ya que no están las dos variables (`A` y `B`) multiplicadas.

6. **¿Por qué la función `F(A,B) = (A + B) . (A + Ā)` no está en forma canónica?**
   - **Respuesta:** No está en forma canónica porque el segundo factor (`A + Ā`) no es un Maxitérmino, ya que una variable (`A`) se repite y falta la otra (`B`).

7. **Una función que tiene un único término como `F(A,B) = A . B`, ¿está en forma canónica?**
   - **Respuesta:** Sí está en forma canónica, ya que consta de un minitérmino solo (relaciona a todas las variables de la función una sola vez mediante el producto).

8. **¿Toda función Booleana tiene forma canónica? ¿De qué maneras se puede obtener?**
   - **Respuesta:** Sí, toda función Booleana, aunque no esté escrita en la forma canónica, tiene su forma canónica y puede ser llevada a dicha forma mediante dos procedimientos: mediante procedimientos algebraicos o por medio de tablas de verdad.

9. **¿Qué es y para qué se utiliza el número de secuencia decimal en la tabla de verdad?**
   - **Respuesta:** Es un número ubicado en el extremo izquierdo de la tabla de verdad que coincide con el valor decimal de las combinaciones binarias de las variables (`0, 1, 2, ...`). Se utiliza para ubicarnos mejor en la tabla e indicar qué filas conforman la productoria de maxitérminos `IIM(...)` y cuáles la sumatoria de minitérminos `∑m(...)`.

10. **¿Cómo son las tablas de verdad de una función original y de sus dos formas canónicas (`IIM` y `∑m`)?**
    - **Respuesta:** Las tres expresiones tienen exactamente la misma tabla de verdad, aunque las formas canónicas por lo general son mucho más extensas que la función original.

11. **¿Cómo se lleva algebraicamente un término incompleto a la forma canónica suma de minitérminos o producto de Maxitérminos?**
    - **Respuesta:**
      - Para la **suma de minitérminos**: se multiplica el término al que le falta una variable `X` por `1` (Axioma 3, neutro del producto), se reemplaza `1` por `(X + X̄)` (Axioma 4, complemento), se aplica propiedad distributiva (Axioma 2) y se eliminan minitérminos repetidos por idempotencia.
      - Para el **producto de Maxitérminos**: se le suma `0` al factor al que le falta una variable `X` (Axioma 3, neutro de la suma), se reemplaza `0` por `(X • X̄)` (Axioma 4, complemento), se aplica propiedad distributiva de la suma respecto del producto (Axioma 2) y se eliminan Maxitérminos repetidos por idempotencia.

12. **¿Cuál es una de las principales aplicaciones de escribir una función en forma canónica utilizando la tabla de verdad?**
    - **Respuesta:** Permite encontrar una función Booleana que logre llegar a los resultados que queremos cuando no conocemos la función pero sí sabemos qué resultados deseamos a la salida para cada combinación de entrada (tomando los `1` para armar la suma de productos o los `0` para armar el producto de sumas).

13. **¿Qué significa simplificar una función Booleana y por qué se realiza en relación con los circuitos lógicos?**
    - **Respuesta:** Simplificar las funciones significa buscar escribirlas de una manera más reducida mediante la utilización de los axiomas y teoremas enunciados como propiedades (justificando cada paso). Se realiza porque las compuertas lógicas del circuito representan las operaciones entre las variables: si hay menos operaciones en la función, habrá menos compuertas (menos elementos) en el circuito, haciéndolo más económico, más rápido y, por lo tanto, más eficiente.

---

## 📚 Glosario de la clase

| Término | Definición breve fiel al material |
| :--- | :--- |
| **Forma canónica de una función Booleana** | Escritura de una función Booleana como una suma o un producto de términos canónicos (es decir, como una suma de minitérminos o un producto de Maxitérminos). |
| **Término canónico** | Expresión que relaciona a todas las variables de la función (ya sea directa o complementada) una sola vez mediante una sola operación. |
| **Maxitérmino (o Suma canónica)** | Término canónico en el que todas las variables se relacionan con la operación suma (`+`). En la tabla de verdad corresponde a una combinación donde la función vale `0` (variables en `'1'` se leen negadas y en `'0'`, directas). |
| **minitérmino (o Producto canónico)** | Término canónico en el que todas las variables se relacionan con la operación producto (`.`). En la tabla de verdad corresponde a una combinación donde la función vale `1` (variables en `'1'` se leen directas y en `'0'`, negadas). |
| **Producto de Sumas (`PS` / `IIM`)** | Forma canónica conformada por la productoria de maxitérminos (correspondientes a las filas donde la función da `'0'`). |
| **Suma de Productos (`SP` / `∑m`)** | Forma canónica conformada por la sumatoria de minitérminos (correspondientes a las filas donde la función toma valor `'1'`). |
| **Número de secuencia decimal (`Sec. Dec.`)** | Número ubicado en el extremo izquierdo de la tabla de verdad que coincide con el valor decimal de las combinaciones binarias de las variables (`0, 1, 2, ...`). |
| **Variable directa** | Variable escrita sin complementar (sin barra de negación, p. ej., `A`). |
| **Variable complementada (o negada)** | Variable afectada por el complemento o negación (con barra superior, p. ej., `Ā`). |
| **Simplificación de funciones** | Procedimiento que busca escribir las funciones Booleanas de una manera más reducida mediante la utilización exclusiva de los axiomas y teoremas enunciados como propiedades, para lograr un circuito lógico más eficiente (con menos compuertas lógicas, más económico y más rápido). |
