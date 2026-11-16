# Clase 7 — Matrices y Determinantes: Matriz Canónica por Filas y Operaciones Elementales

## 🗺️ Mapa de la clase

- **1. Introducción y propósito del tema**
  - Conexión con las matrices especiales vistas en la Clase 5.
  - Diferencia entre operaciones entre matrices y operaciones particulares o elementales entre las líneas (filas) de una misma matriz.
- **2. Matriz canónica por filas**
  - Definición y las **4 características** obligatorias (7.1).
  - **Elemento conductor** y disposición **en escalera** (7.2).
  - **Rango de una matriz** `ρ(matriz)` (7.3).
  - Casos particulares e interpretaciones teóricas: la **matriz nula** y la **matriz identidad** como formas canónicas (7.4).
- **3. Operaciones elementales en una matriz**
  - Las **tres operaciones elementales por filas**: permutar filas (`Hij`), multiplicar una fila por una constante no nula (`Hi(k)`) y sumar a una fila otra previamente multiplicada por una constante no nula (`Hij(k)`) (7.5).
  - **Matrices equivalentes** (`A ~ B`): definición, notación y diferencia con la igualdad de matrices (7.6).
- **4. Búsqueda algorítmica de la matriz canónica y control de errores**
  - **Procedimiento paso a paso** para transformar cualquier matriz en su matriz canónica equivalente (obtención del elemento conductor, anulación de su columna, elección de caminos sin fracciones y operaciones simultáneas) (7.7).
  - **Columna de control**: cómo nace, cómo se opera y cómo permite verificar la exactitud de cada paso (7.8).

### Prerrequisitos
- **Clase 5 (Matrices — Conceptos básicos y matrices especiales):** definición de matriz, orden `m × n`, líneas de una matriz (filas y columnas), fila nula, matriz rectangular, matriz cuadrada, **matriz nula** y **matriz identidad**.
- **Clase 6 (Operaciones con matrices):** suma de matrices y multiplicación de una matriz por un escalar (para no confundir las operaciones *entre matrices* con las operaciones elementales *entre filas de una misma matriz*).

---

## 7.1 Matriz canónica por filas

> 📖 **Textual del material:** "Cuando vimos matrices especiales hace dos clases atrás, nombramos un tipo de matriz que no la terminamos de definir. Podríamos haber colocado ahí a las matrices canónicas, pero como cualquier matriz puede llevarse a esa forma, es que preferí nombrarlas ahora. La canónica no es más que una matriz que cumple con algunas condiciones específicas."
>
> 📖 **Textual del material:** "La matriz canónica es una matriz rectangular que tiene las siguientes características:
> 1| El primer elemento no nulo de las filas, si lo hubiera, debe ser el 1, denominado elemento conductor.
> 2| En la columna a la que pertenece dicho 1, los elementos restantes son cero.
> 3| Los elementos conductores están dispuestos en escalera, o sea que cada fila tiene mayor número de ceros que la anterior adelante del elemento conductor; y las filas nulas, si las hubiera, están últimas.
> 4| El número de filas no nulas se denomina rango de la matriz (ρ(matriz))."

**🗣️ En palabras simples:**
Una matriz está en su **forma canónica por filas** (en otros textos llamada *forma escalonada reducida por filas*, aunque en la cátedra debés llamarla **matriz canónica** o **matriz canónica por filas**) cuando está totalmente "limpia y ordenada" siguiendo cuatro reglas:
1. Si mirás cualquier fila de izquierda a derecha, el primer número distinto de 0 que aparece tiene que ser sí o sí un **1** (llamado **elemento conductor**).
2. En toda la columna vertical donde vive ese **1**, todos los demás números (tanto arriba como abajo de él) tienen que ser **0**.
3. Al bajar de una fila a la siguiente, los elementos conductores van corriendo hacia la derecha formando una **escalera** (cada fila tiene más ceros iniciales que la fila de arriba), y si hay filas compuestas íntegramente por ceros (filas nulas), están todas agrupadas al final (abajo del todo).
4. La cantidad de filas que no son completamente de ceros te dice directamente el **rango** de la matriz.

**🔍 Desglose de la jerga:**
- **"es una matriz rectangular"**: En la jerga de la materia (vista desde la Clase 5), decir que es una matriz rectangular significa que puede tener cualquier orden `m × n` (incluyendo como caso particular a las cuadradas cuando `m = n`, pero sin exigir que sea cuadrada).
- **"El primer elemento no nulo de las filas, si lo hubiera, debe ser el 1"**:
  - *"Primer"*: leyendo la fila de izquierda a derecha.
  - *"No nulo"*: distinto de cero (`≠ 0`).
  - *"Si lo hubiera"*: esta aclaración es clave porque una fila puede ser completamente nula (todos ceros) y no tener ningún elemento no nulo. Gracias a este *"si lo hubiera"*, una fila de ceros (o incluso la matriz nula entera) no viola la condición 1.
- **"denominado elemento conductor"**: Es el nombre oficial en la cátedra para ese primer `1` de cada fila no nula.
- **"En la columna a la que pertenece dicho 1, los elementos restantes son cero"**: Exige ceros **arriba y abajo** del elemento conductor. No alcanza con que haya ceros debajo; toda la columna del elemento conductor debe tener ceros salvo en la posición del propio conductor. (En las columnas donde *no* hay elemento conductor pueden aparecer cualesquiera números reales).
- **"dispuestos en escalera, o sea que cada fila tiene mayor número de ceros que la anterior adelante del elemento conductor"**: Si el elemento conductor de la fila 1 está en la columna `c_1` y el de la fila 2 está en la columna `c_2`, necesariamente `c_1 < c_2`. No puede haber dos elementos conductores en la misma columna ni puede aparecer un elemento conductor más a la izquierda que el de una fila superior.
- **"las filas nulas, si las hubiera, están últimas"**: Ninguna fila de todos ceros puede quedar intercalada arriba o en el medio de filas no nulas; deben ubicarse en las últimas filas de la matriz. Si no hay filas nulas, la condición se cumple automáticamente (por eso dice *"si las hubiera"*).
- **"rango de la matriz (ρ(matriz))"**: Cantidad de filas no nulas una vez que la matriz está en su forma canónica. Se simboliza con la letra griega **ro** minúscula: `ρ`.

**💡 Ejemplo:**
Del **Ejemplo Nº 1** del material (Pág. 3), las siguientes tres matrices están en forma canónica:

```text
     [ 1  0  0  0 -5 ]          [ 1  0  0 ]          [ 1  0  0  5 ]
A =  [ 0  0  1  0  0 ]     B =  [ 0  1  0 ]     C =  [ 0  0  1  2 ]
     [ 0  0  0  1  8 ]          [ 0  0  1 ]
     [ 0  0  0  0  0 ]
```

> 📖 **Textual del material:** "Analicemos:
> • Las tres matrices tienen como primer elemento no nulo de cada fila, el 1 (llamado elemento conductor).
> • Los elementos de la columna a la cual pertenece cada elemento conductor son ceros.
> • Los elementos están dispuestos en escalera.
> • Y la fila nula de la matriz A, está colocada al final de la matriz, respondiendo a la condición 3).
> Además podemos afirmar que:
> ρ (A) = 3 (rango de A)                ρ (B) = 3                            ρ (C) = 2"

Observá en `A` que las columnas 2 y 5 **no** contienen elementos conductores, por lo que en la columna 5 pueden aparecer `-5`, `0`, `8`, `0` sin violar la condición 2. En cambio, las columnas 1, 3 y 4 sí contienen elementos conductores, y por eso todos los demás elementos de las columnas 1, 3 y 4 son ceros.

### Tabla comparativa de diagnóstico (basada en el Desempeño 41, Págs. 3 y 10)

| Matriz del material | ¿Es canónica? | Justificación exacta según las condiciones del material |
| :--- | :--- | :--- |
| `A = [[1, 0, 0, 2], [0, 1, 0, -2], [0, 0, 1, 1]]` | **Sí** | Cumple las condiciones 1, 2 y 3 (conductores en columnas 1, 2 y 3; la columna 4 no tiene conductor). |
| `B = [[1, 2], [0, 1]]` | **No** | Viola la **condición 2**: *"B no es canónica, (por el 2) Tendría que ser 0 porque en esa columna hay un elemento conductor."* |
| `C = [[0, 0], [0, 0]]` | **Sí** | *"C es un caso particular, en realidad es la matriz nula. Pero no contradice ninguna condición."* |
| `D = [[1, 2, 0, 5], [0, 0, 0, 0], [0, 0, 1, 2]]` | **No** | Viola la **condición 3**: *"En la matriz D, la segunda fila tendría que estar en tercer lugar"* (la fila nula no está última). |
| `E = [[1, 0, 0, 5], [0, 1, 0, 23], [0, 0, 1, 3]]` | **Sí** | Cumple todas las condiciones (conductores en columnas 1, 2 y 3). |
| `F = [[1, 0, 0, 0, 5], [0, 0, 4, 0, 1], [0, 0, 0, 1, 3]]` | **No** | Viola la **condición 1**: *"La matriz F no es canónica por el elemento 4. Como es el primer elemento no nulo de la fila, tendría que haber sido 1."* |
| `G = [[1, 3], [0, 0], [0, 0]]` | **Sí** | Tiene un único elemento conductor en la fila 1 columna 1 (resto de su columna es 0) y las dos filas nulas están al final. |

**🔗 Conexiones:**
- Con **Clase 5 (Matrices especiales)**: completa el catálogo de matrices especiales, pero con la particularidad de que **cualquier matriz** puede transformarse en una matriz canónica mediante operaciones elementales por filas.
- Con **Sistemas de Ecuaciones Lineales** (clases siguientes): llevar la matriz de un sistema a su forma canónica permite leer las soluciones y clasificar el sistema a través del rango.

**⚠️ Precisiones / errores comunes:**
- **No confundir matriz triangular con matriz canónica:** En la matriz `B = [[1, 2], [0, 1]]` del Desempeño 41 hay ceros debajo de la diagonal y unos en la diagonal, pero **no es canónica** porque arriba del elemento conductor de la fila 2 hay un `2` en vez de un `0`. La condición 2 exige que **todos** los elementos restantes de la columna del conductor sean cero (arriba y abajo).
- **No olvidar las palabras "si lo hubiera" / "si las hubiera":** Al enunciar las condiciones 1 y 3 en el oral, incluí siempre *"si lo hubiera"* (para el primer elemento no nulo) y *"si las hubiera"* (para las filas nulas), ya que una matriz puede no tener elementos no nulos (matriz nula) o puede no tener filas nulas.

**🎤 Cómo decirlo en el oral:**
> *"La matriz canónica es una matriz rectangular que tiene cuatro características: primero, el primer elemento no nulo de las filas, si lo hubiera, debe ser el 1, denominado elemento conductor; segundo, en la columna a la que pertenece dicho 1, los elementos restantes son cero; tercero, los elementos conductores están dispuestos en escalera, o sea que cada fila tiene mayor número de ceros que la anterior adelante del elemento conductor, y las filas nulas, si las hubiera, están últimas; y cuarto, el número de filas no nulas se denomina rango de la matriz, simbolizado ρ(matriz)."*

---

## 7.2 Elemento conductor y disposición en escalera

> 📖 **Textual del material:** "1| El primer elemento no nulo de las filas, si lo hubiera, debe ser el 1, denominado elemento conductor.
> 2| En la columna a la que pertenece dicho 1, los elementos restantes son cero.
> 3| Los elementos conductores están dispuestos en escalera, o sea que cada fila tiene mayor número de ceros que la anterior adelante del elemento conductor; y las filas nulas, si las hubiera, están últimas."

**🗣️ En palabras simples:**
El **elemento conductor** es el número `1` que inaugura los valores distintos de cero en cada fila no nula de una matriz canónica. Tiene dos propiedades geométricas en la matriz:
- **Verticalmente (en su columna):** está completamente "aislado", porque todos los demás lugares de su columna valen `0`.
- **Horizontal y diagonalmente (entre filas):** a medida que bajamos de fila, cada elemento conductor aparece más a la derecha que el de la fila anterior (formando los peldaños de una escalera que baja hacia la derecha). Los peldaños pueden avanzar de a una columna o saltar varias columnas, pero siempre hacia la derecha.

**🔍 Desglose de la jerga:**
- **"Elemento conductor"**: Nombre técnico específico que usa la cátedra (en otros libros se lo llama *pivote* o *1 principal*; en el examen oral usá siempre **elemento conductor**).
- **"adelante del elemento conductor"**: Se refiere a las posiciones situadas a la **izquierda** del elemento conductor dentro de esa misma fila (que por definición son todas ceros, ya que el conductor es el *primer* elemento no nulo de la fila).
- **"mayor número de ceros que la anterior adelante del elemento conductor"**:
  - Si la fila 1 empieza directamente con `1` en la columna 1, tiene `0` ceros adelante.
  - La fila 2 (si no es nula) debe tener al menos `1` cero adelante de su elemento conductor (puede tener 1, 2, 3... ceros adelante).
  - La fila 3 (si no es nula) debe tener estrictamente más ceros adelante que la fila 2, y así sucesivamente.

**💡 Ejemplo:**
En la matriz `A` del Ejemplo Nº 1 (Pág. 3):
```text
Fila 1:  [ 1   0   0   0  -5 ]  → Elemento conductor en col. 1 (0 ceros adelante)
Fila 2:  [ 0   0   1   0   0 ]  → Elemento conductor en col. 3 (2 ceros adelante)
Fila 3:  [ 0   0   0   1   8 ]  → Elemento conductor en col. 4 (3 ceros adelante)
Fila 4:  [ 0   0   0   0   0 ]  → Fila nula (ubicada al final)
```
Fijate cómo la cantidad de ceros adelante del elemento conductor crece estrictamente de fila en fila (`0 < 2 < 3`), formando la escalera aunque en la columna 2 no haya elemento conductor.

**🔗 Conexiones:**
- Con el **Procedimiento de reducción a la forma canónica (7.7)**: cada paso del algoritmo consiste en fabricar un elemento conductor en una fila y usar ese `1` para anular toda su columna.
- Con el **Rango de una matriz (7.3)**: como cada fila no nula de la matriz canónica tiene exactamente un elemento conductor, la cantidad total de elementos conductores coincide con el número de filas no nulas, es decir, con el rango `ρ`.

**⚠️ Precisiones / errores comunes:**
- **No todo `1` de la matriz es un elemento conductor:** Si una fila es `[0, 1, 0, 1]`, solo el **primer** `1` (el de la columna 2) es el elemento conductor de esa fila. El segundo `1` (en la columna 4) es simplemente un elemento más en una columna sin conductor, y por lo tanto no obliga a que el resto de la columna 4 sea cero.
- **La escalera no necesita bajar de a un casillero por vez:** En el Ejemplo Nº 1 (`A` y `C`), el primer conductor está en la columna 1 y el segundo salta directamente a la columna 3. Eso es perfectamente válido porque `2 ceros adelante > 0 ceros adelante`.

**🎤 Cómo decirlo en el oral:**
> *"Se denomina elemento conductor al primer elemento no nulo de cada fila de una matriz canónica, el cual debe ser igual a 1. En la columna a la que pertenece cada elemento conductor, todos los elementos restantes deben ser cero, y los elementos conductores de las distintas filas deben estar dispuestos en escalera, es decir, que cada fila tenga mayor número de ceros que la anterior adelante del elemento conductor."*

---

## 7.3 Rango de una matriz — ρ(matriz)

> 📖 **Textual del material:** "4| El número de filas no nulas se denomina rango de la matriz (ρ(matriz))."
>
> 📖 **Textual del material:** "Además podemos afirmar que:
> ρ (A) = 3 (rango de A)                ρ (B) = 3                            ρ (C) = 2"

**🗣️ En palabras simples:**
El **rango** de una matriz (simbolizado con `ρ(A)`) es un número entero no negativo que cuenta **cuántas filas no nulas quedan cuando la matriz está en su forma canónica por filas**. Mide cuántas filas aportan información "propia" (que no se anula al combinar filas mediante operaciones elementales).

**🔍 Desglose de la jerga:**
- **"Número de filas no nulas"**: Cantidad de filas que tienen al menos un elemento distinto de cero (o equivalentemente, que tienen su elemento conductor `1`) **en la matriz canónica**.
- **"ρ(matriz)"**: Se lee *"rango de la matriz"* (la letra griega es *ro*, `ρ`). Por ejemplo, `ρ(A) = 3` se lee *"el rango de A es igual a 3"*.

**💡 Ejemplo:**
1. **Cuando la matriz ya es canónica (Ejemplo Nº 1, Pág. 3):**
   - En `A` (orden `4 × 5`), las primeras 3 filas tienen elementos conductores y la 4ª fila es nula `[0, 0, 0, 0, 0]`. Por lo tanto, `ρ(A) = 3`.
   - En `B` (orden `3 × 3`, identidad), las 3 filas son no nulas: `ρ(B) = 3`.
   - En `C` (orden `2 × 4`), las 2 filas son no nulas: `ρ(C) = 2`.
2. **Cuando la matriz NO está en forma canónica (Desempeño 45, Pág. 9 y respuesta en Pág. 11):**
   Sea `B = [[1, 3, 2], [5, 15, 10]]`. A simple vista tiene 2 filas sin ceros, ¡pero cuidado! Aún no es canónica. Si aplicamos la operación elemental `H_2,1(-5)` (sumar a la fila 2 la fila 1 multiplicada por `-5`), obtenemos la matriz canónica equivalente:
   ```text
   [ 1   3   2 ]  ~  [ 1   3   2 ]
   [ 5  15  10 ]     [ 0   0   0 ]
   ```
   Como en la forma canónica quedó **1 sola fila no nula**, el rango es `ρ(B) = 1` (tal como figura en las respuestas de la Pág. 11).

**🔗 Conexiones:**
- Con el **Teorema de Rouché-Frobenius / Sistemas de ecuaciones lineales** (clases siguientes): el rango de la matriz de coeficientes y el de la matriz ampliada determinan si un sistema tiene solución única, infinitas soluciones o ninguna.
- Con las **Operaciones elementales (7.5)**: para hallar el rango de una matriz cualquiera hay que llevarla primero a su forma canónica mediante operaciones elementales por filas y recién ahí contar las filas no nulas.

**⚠️ Precisiones / errores comunes:**
- **¡Error grave de examen!** Contar las filas no nulas en la matriz *original* sin haberla llevado antes a la forma canónica.La definición de rango está dada dentro de las características de la **matriz canónica**: una fila que originalmente no tiene ceros (como `[5, 15, 10]` en el ejemplo anterior) puede anularse por completo al reducir la matriz.
- **Cota del rango (contexto adicional útil para verificar):** Como el rango cuenta filas no nulas y cada fila no nula tiene un elemento conductor en una columna distinta, para una matriz de orden `m × n` siempre se cumple que `0 ≤ ρ(A) ≤ mín(m, n)`. Por ejemplo, en el Desempeño 41 b se pide *"una matriz canónica de orden 4 × 5 y rango 2"*: tendrá 4 filas y 5 columnas, con exactamente 2 filas no nulas (con elementos conductores en escalera) y 2 filas nulas al final.

**🎤 Cómo decirlo en el oral:**
> *"En una matriz llevada a su forma canónica por filas, el número de filas no nulas se denomina rango de la matriz y se simboliza con la letra griega ro, ρ(matriz)."*

---

## 7.4 Casos particulares y propiedades de la forma canónica: Matriz Nula y Matriz Identidad

> 📖 **Textual del material:** "c- C es un caso particular, en realidad es la matriz nula. Pero no contradice ninguna condición." *(Pág. 10, Respuestas del Desempeño n° 41 sobre `C = [[0, 0], [0, 0]]`)*
>
> 📖 **Textual del material:** "y... Si! La matriz obtenida es la matriz canónica, que en este caso es la identidad, pero cuidado, no en todos los casos pasa esto." *(Pág. 7, cierre del Ejemplo n° 3)*
>
> 📖 **Textual del material:** "b- La matriz canónica de una matriz de orden 3x4 ¿Puede ser la matriz identidad? Explica porque.
> c- La matriz canónica de una matriz cuadrada, ¿Es siempre una matriz identidad? Explica." *(Pág. 10, Desempeño 46)*

**🗣️ En palabras simples:**
El material destaca tres verdades teóricas fundamentales que relacionan la **matriz canónica** con las matrices especiales de la Clase 5 (**matriz nula** y **matriz identidad**):
1. **La matriz nula SIEMPRE es una matriz canónica:** Aunque no tenga ningún `1`, no rompe ninguna de las 4 reglas porque la regla 1 dice *"el primer elemento no nulo de las filas, **si lo hubiera**, debe ser el 1"* y la regla 3 dice *"las filas nulas, **si las hubiera**, están últimas"*. Su rango es `0`.
2. **La matriz identidad SIEMPRE es una matriz canónica:** Sus unos en la diagonal principal son elementos conductores en escalera y el resto de cada columna son ceros (como la matriz `B` del Ejemplo Nº 1).
3. **Pero NO toda matriz tiene como canónica a la identidad:**
   - Si la matriz original **no es cuadrada** (por ejemplo, orden `3 × 4`), su matriz canónica sigue siendo de orden `3 × 4`, por lo que **jamás** puede ser la matriz identidad (ya que la matriz identidad es por definición una matriz cuadrada).
   - Si la matriz original **es cuadrada** (orden `n × n`), su matriz canónica **tampoco es siempre la identidad**: solo será la identidad si ninguna fila se anula en el proceso (es decir, si su rango es `n`). Si una o más filas se anulan, quedarán filas de ceros al final y la canónica no será la identidad.

**🔍 Desglose de la jerga:**
- **"no contradice ninguna condición"**: En matemática, cuando una condición es condicional (*"si hubiera un elemento no nulo, debe ser 1"*), y el antecedente no ocurre (no hay elementos no nulos), la condición se cumple (verdad por vacuidad).
- **"en este caso es la identidad, pero cuidado, no en todos los casos pasa esto"**: Advierte contra la generalización falsa de creer que "llevar a la canónica" significa "convertir en la matriz identidad".

**💡 Ejemplo:**
- **Matriz cuadrada cuya canónica SÍ es la identidad:** En el Ejemplo Nº 3 (Págs. 6 y 7), `A = [[1, 2, 3], [4, 5, 6], [5, 7, 8]]` (de orden `3 × 3`) se reduce por operaciones elementales a `I_3 = [[1, 0, 0], [0, 1, 0], [0, 0, 1]]`.
- **Matriz cuadrada cuya canónica NO es la identidad:** Una matriz cuadrada de orden `2 × 2` como `[[1, 3], [2, 6]]` tiene como matriz canónica a `[[1, 3], [0, 0]]`, que es canónica y cuadrada, pero no es la identidad porque tiene una fila nula.
- **Matriz rectangular no cuadrada (`3 × 4`):** En el Ejemplo Nº 1, matrices como `C` (de `2 × 4`) o `A` (de `4 × 5`) son canónicas y rectangulares no cuadradas; no pueden ser la identidad porque la identidad exige el mismo número de filas que de columnas.

**🔗 Conexiones:**
- Con **Clase 5 (Matriz nula y Matriz identidad)**: allá se definieron la matriz nula (`N`) y la matriz identidad (`I` o unidad, que es escalar con `k = 1` y por ende cuadrada). Acá vemos que ambas cumplen la definición de matriz canónica.
- Con **Clase 8 / Determinantes e Inversa**: una matriz cuadrada de orden `n` tiene por matriz canónica a la identidad `I_n` si y solo si su rango es `n` (y su determinante es distinto de cero).

**⚠️ Precisiones / errores comunes:**
- Si en el oral te preguntan *"¿La matriz nula está en forma canónica?"*, nunca respondas "no, porque no tiene unos". La respuesta exacta de la cátedra es: **"Sí, es un caso particular; es la matriz nula, pero no contradice ninguna condición"**.
- Si te preguntan *"¿Por qué la canónica de una matriz de 3×4 no puede ser la identidad?"*, tenés que mencionar dos cosas: que las operaciones elementales no cambian el orden de la matriz (sigue siendo `3 × 4`) y que la matriz identidad es, por definición, una **matriz cuadrada**.

**🎤 Cómo decirlo en el oral:**
> - **Sobre la matriz nula:** *"La matriz nula es un caso particular de matriz canónica porque no contradice ninguna de las condiciones de la definición, dado que la primera condición exige que el primer elemento no nulo de cada fila sea 1 'si lo hubiera'."*
> - **Sobre la matriz identidad:** *"Toda matriz identidad está en forma canónica, pero la matriz canónica equivalente a una matriz dada no siempre es la identidad: primero, porque si la matriz original no es cuadrada (por ejemplo de orden 3×4), su canónica tampoco será cuadrada y la identidad solo existe para matrices cuadradas; y segundo, porque aun siendo cuadrada, si durante las operaciones elementales se anula alguna fila, la matriz canónica tendrá filas nulas al final y no será la matriz identidad."*

---

## 7.5 Operaciones elementales en una matriz (Operaciones elementales por filas)

> 📖 **Textual del material:** "Además de poder realizar operaciones entre matrices, veremos hoy unas operaciones particulares o elementales que se realizan entre las líneas de una matriz. Si bien se pueden realizar las operaciones elementales entre líneas, nosotros solo utilizaremos aquellas aplicadas solo a las filas, es decir operaremos entre filas." *(Pág. 2)*
>
> 📖 **Textual del material:** "Las operaciones elementales son tres, y se aplican tanto en las filas como a columnas, pero debido al interés que presenta este tema para nosotros, se aplicarán las operaciones elementales solamente a las filas de la matriz. Las operaciones son:
> 1º Operación: Permutar filas entre sí. Se simboliza con Hij, lo que indica intercambiar la fila i con la fila j.
> 2º Operación: Multiplicar una fila por una constante distinta de cero. Se simboliza con Hi(k), lo que indica multiplicar la fila i por la constante k.
> 3º Operación: Sumar a una fila otra fila previamente multiplicada por una constante distinta de cero.
> Se simboliza con Hij(k), lo que indica sumar a la fila i, la fila j multiplicada por k . ( i + k . j)." *(Pág. 3)*

**🗣️ En palabras simples:**
A diferencia de la suma o multiplicación de matrices (que combinan dos matrices para dar otra), las **operaciones elementales** son tres maniobras válidas que se hacen **adentro de una misma matriz** trabajando con sus filas para transformarla en otra matriz equivalente más simple (idealmente, su matriz canónica):
1. **Cambiar de lugar dos filas** (`H_i,j`): la fila `i` pasa a donde estaba la `j`, y la `j` pasa a donde estaba la `i`.
2. **Multiplicar todos los números de una fila por un mismo número distinto de cero** (`H_i(k)` con `k ≠ 0`): sirve para convertir el primer elemento no nulo de una fila en el elemento conductor `1`.
3. **Sumarle a una fila un múltiplo de otra fila** (`H_i,j(k)` con `k ≠ 0`): la fila `i` se reemplaza por `fila i + k · fila j` (mientras que la fila `j` usada como auxiliar permanece intacta). Sirve para fabricar ceros en la columna del elemento conductor.

**🔍 Desglose de la jerga:**
- **"se aplican tanto en las filas como a columnas ("entre las líneas"), pero... se aplicarán las operaciones elementales solamente a las filas"**: Recordá de la Clase 5 que *"líneas"* es el término que engloba a filas y columnas. El profesor puede preguntar dónde se pueden aplicar en teoría (en filas o columnas) y dónde las aplicamos nosotros (solamente en las filas).
- **Letra `H` en la simbología (`Hij`, `Hi(k)`, `Hij(k)` o `H_i,j`, `H_i(k)`, `H_i,j(k)`)**: Es el símbolo que usa la cátedra para denotar cada operación elemental por filas (en los desarrollos prácticos del PDF se separan los subíndices con coma cuando son números, por ejemplo `H_1,2`, `H_1(-4)`, `H_3,1(5)`).
- **"Permutar filas entre sí"**: Intercambiar íntegramente todos los elementos de la fila `i` con los correspondientes de la fila `j`.
- **"por una constante distinta de cero" (`k ≠ 0`)**: Esta restricción aparece tanto en la **2º Operación** como en la **3º Operación** y es **obligatoria en el oral**.
  - En la 2º Operación, si multiplicáramos una fila por `k = 0`, destruiríamos toda la información de esa fila convirtiéndola artificialmente en una fila nula (cambiaría el rango y la matriz resultante NO sería equivalente).
  - En la 3º Operación, si `k = 0`, le sumaríamos cero a la fila `i` y no estaríamos realizando ninguna transformación.
- **"Se simboliza con Hij(k), lo que indica sumar a la fila i, la fila j multiplicada por k . ( i + k . j)"**:
  - ¡Atención al orden de los subíndices! El **primer subíndice (`i`)** indica siempre **la fila que se modifica** (donde se guarda el resultado).
  - El **segundo subíndice (`j`)** indica **la fila auxiliar** que se multiplica previamente por `k` para sumársela a la fila `i` (la fila `j` en sí misma no cambia en la matriz).

### Tabla resumen de las 3 Operaciones Elementales por Filas

| Operación | Símbolo en el texto / en ejercicios | Qué hace exactamente | Condición clave | Para qué se usa al buscar la canónica |
| :--- | :--- | :--- | :--- | :--- |
| **1º Operación** | `Hij` / `H_i,j` | Permutar (intercambiar) la fila `i` con la fila `j`. | `i ≠ j` | Llevar filas nulas al final, acomodar la escalera o subir un `1` para lograr el elemento conductor sin usar fracciones. |
| **2º Operación** | `Hi(k)` / `H_i(k)` | Multiplicar toda la fila `i` por la constante `k`. | `k ≠ 0` | Convertir un número `a ≠ 0` en el **elemento conductor `1`**, multiplicando su fila por `k = 1/a`. |
| **3º Operación** | `Hij(k)` / `H_i,j(k)` | Sumar a la fila `i` la fila `j` previamente multiplicada por `k`: `fila_i ← fila_i + k · fila_j`. | `k ≠ 0` (y `i ≠ j`) | **Anular (hacer `0`)** los restantes elementos de la columna del elemento conductor (tomando `j` = fila del conductor y `k` = opuesto del número a anular). |

**💡 Ejemplo:**
Del **Ejemplo Nº 2** del material (Pág. 4), partiendo de:
```text
     [ 3   1   5   0 ]
A =  [ 1   4  -2   2 ]
     [ 0   2  -1   3 ]
```
Se aplican sucesivamente las tres operaciones elementales:
1. **`H_1(-4)`** (*"Esto quiere decir que a la fila 1 la vamos a multiplicar por -4"* — 2º Operación):
   ```text
   [ -12  -4  -20   0 ]
   [   1   4   -2   2 ]
   [   0   2   -1   3 ]
   ```
2. **`H_1,2`** (*"Esto significa que vamos a intercambiar la fila 1 por la fila 2"* — 1º Operación):
   ```text
   [   1   4   -2   2 ]
   [ -12  -4  -20   0 ]
   [   0   2   -1   3 ]
   ```
3. **`H_3,1(5)`** (*"Esto significa que a la fila 3, le vamos a sumar la fila 1, pero antes de sumarla, tenemos que multiplicar dicha fila por 5"* — 3º Operación):
   - El `5` surge de: `1 × 5 + 0 = 5`
   - El `22` surge de: `4 × 5 + 2 = 22`
   - El `-11` surge de: `-2 × 5 + (-1) = -11`
   - El `9` surge de: `2 × 5 + 3 = 9`
   Obteniendo la matriz `B`:
   ```text
        [   1    4   -2   2 ]
   B =  [ -12   -4  -20   0 ]
        [   5   22  -11   9 ]
   ```

**🔗 Conexiones:**
- Con **Matrices equivalentes (7.6)**: el resultado de aplicar cualquiera de estas tres operaciones elementales es una matriz equivalente (`A ~ B`).
- Con **Procedimiento para hallar la matriz canónica (7.7)**: son las únicas herramientas permitidas para llevar una matriz a su forma canónica.

**⚠️ Precisiones / errores comunes:**
- **Omitir "distinta de cero":** Si en el oral decís *"multiplicar una fila por una constante"* sin aclarar **"distinta de cero"**, el profesor te lo va a marcar como incompleto o incorrecto.
- **Invertir los subíndices en `H_i,j(k)`:** En `H_3,1(5)`, la fila que cambia es la **3** (primer subíndice), y la que se multiplica por `5` es la **1** (segundo subíndice). Además, recordá que la fila 1 se multiplica por `5` *mentalmente o en un cálculo auxiliar* solo para sumársela a la fila 3, pero en la matriz la fila 1 **queda como estaba**.

**🎤 Cómo decirlo en el oral:**
> *"Las operaciones elementales son tres, y aunque pueden aplicarse tanto a filas como a columnas, nosotros las aplicamos solamente a las filas de la matriz:*
> *— Primera operación: Permutar filas entre sí. Se simboliza con Hij, lo que indica intercambiar la fila i con la fila j.*
> *— Segunda operación: Multiplicar una fila por una constante distinta de cero. Se simboliza con Hi(k), lo que indica multiplicar la fila i por la constante k.*
> *— Tercera operación: Sumar a una fila otra fila previamente multiplicada por una constante distinta de cero. Se simboliza con Hij(k), lo que indica sumar a la fila i la fila j multiplicada por k, es decir, i + k · j."*

---

## 7.6 Matrices equivalentes (Equivalencia de matrices, símbolo ~)

> 📖 **Textual del material:** "La matriz que se obtiene luego de aplicar las operaciones se dice que es equivalente a la primera (la equivalencia se simboliza con ~)." *(Págs. 3-4)*
>
> 📖 **Textual del material:** "Resulta A ~ B (A equivalente a B)" *(Pág. 4)*
>
> 📖 **Textual del material:** "Podemos afirmar que la matriz A es equivalente a la matriz B.
> Este procedimiento (el de obtener una canónica) será muy utilizado en lo sucesivo. Si bien no son iguales, son equivalentes y nos servirá para trabajar con sistemas de ecuaciones." *(Pág. 7)*

**🗣️ En palabras simples:**
Cuando a una matriz `A` le aplicamos una o varias operaciones elementales por filas y obtenemos otra matriz `B`, no podemos decir que `A` y `B` sean *iguales* (porque sus números cambiaron de valor o de lugar), pero sí decimos que son **equivalentes** y lo escribimos `A ~ B`. Que sean equivalentes significa que guardan la misma información estructural (tienen el mismo orden, el mismo rango y, si representan un sistema de ecuaciones, exactamente las mismas soluciones).

**🔍 Desglose de la jerga:**
- **"es equivalente a la primera"**: Relación que vincula a la matriz original con cualquier matriz obtenida a partir de ella mediante una sucesión finita de operaciones elementales.
- **Símbolo `~` (virgulilla)**: Se lee *"es equivalente a"*. Se escribe entre matriz y matriz a lo largo de la cadena de operaciones elementales: `A ~ ... ~ B`.
- **"Si bien no son iguales, son equivalentes"**: Recalca la distinción con la **igualdad de matrices** (`A = B`, vista en Clase 5, que exige que sean del mismo orden y que cada elemento `a_ij` sea idéntico a `b_ij`).

**💡 Ejemplo:**
En el Desempeño 42 a (Pág. 5 y resolución en Pág. 10):
```text
     [  1  4 -3 ]              [ 1  4 -3 ]              [ 1  4 -3 ]               [ 1  0 -3 ]
A =  [ -1  2  3 ]  ~ H_2,1(1)  [ 0  6  0 ]  ~ H_2(1/6)  [ 0  1  0 ]  ~ H_1,2(-4)  [ 0  1  0 ] = B
```
Aquí `A ≠ B` (por ejemplo, en la posición `(1,2)` la matriz `A` tiene un `4` y `B` tiene un `0`), pero **`A ~ B`** (*A es equivalente a B*) porque `B` se obtuvo aplicando operaciones elementales por filas a `A`.

**🔗 Conexiones:**
- Con **Clase 5 (Igualdad de matrices)**: dos matrices iguales son equivalentes, pero dos matrices equivalentes en general **no son iguales**.
- Con **Desempeño 46 a (Pág. 10)**: responde directamente a la pregunta *"¿Qué operación le podemos aplicar a una matriz, para obtener una matriz equivalente?"* → **Las operaciones elementales (por filas)**.

**⚠️ Precisiones / errores comunes:**
- **No poner el signo `=` entre paso y paso al aplicar operaciones elementales:** Cuando transformás una matriz en otra mediante `H_i,j`, `H_i(k)` o `H_i,j(k)`, el símbolo que conecta una matriz con la siguiente es **`~`** (equivalente), no `=`.

**🎤 Cómo decirlo en el oral:**
> *"La matriz que se obtiene luego de aplicar las operaciones elementales a una matriz dada se dice que es equivalente a la primera, y la equivalencia se simboliza con el signo ~. Si bien ambas matrices no son iguales elemento a elemento, son equivalentes y conservan propiedades fundamentales para trabajar con sistemas de ecuaciones."*

---

## 7.7 Procedimiento (Método) para la búsqueda de la matriz canónica por filas

> 📖 **Textual del material:** "Para que no te compliques en la búsqueda de la matriz canónica, te sugiero que siempre sigas estos pasos: Primero busca el elemento Conductor de la fila (1) e inmediatamente después anula su columna, segundo pasa al elemento conductor de otra fila y anula su columna, y así sucesivamente." *(Pág. 2, Claves de estudio)*
>
> 📖 **Textual del material:** "Las operaciones se pueden aplicar tantas veces como sea necesario y la elección de las mismas se hace con el fin de obtener una matriz canónica" *(Pág. 5)*
>
> 📖 **Textual del material:** "NO necesariamente hay una única manera posible de resolver, sino que podemos ir cambiando de acuerdo a la necesidad que muestre la matriz planteada." *(Pág. 5)*
>
> 📖 **Textual del material:** "En limpio, a la fila 2, le vamos a sumar la fila 1 (no es casualidad que es la fila donde está el elemento conductor) previamente multiplicada por (-4) (no es casualidad que sea el opuesto del número que se quiere convertir en 0)." *(Pág. 6)*
>
> 📖 **Textual del material:** "Para ello te invito a que te animes a trabajar con dos operaciones simultáneas, en el mismo paso, siempre y cuando dichas operaciones no afecten a la misma fila." *(Pág. 7)*
>
> 📖 **Textual del material:** "Ayuda: En este caso, para obtener el elemento conductor de la primera fila tienes dos alternativas:
> • Hacer un cambio de fila (1 por 3), y no complicarte con otras operaciones.
> • O multiplicar la primera fila por (1/2).
> Atención! En este caso, no sería demasiado problema, porque todos los elementos al multiplicarlos por 1/2, van a dar por resultado un número entero; pero puede presentarse alguna situación que queden fracciones. No es que esté mal, pero si hay una alternativa sin fracciones, es más sencillo trabajar." *(Pág. 9, Desempeño 43)*

**🗣️ En palabras simples:**
¿Qué problema resuelve este método? Dada **cualquier matriz**, permite encontrar su **matriz canónica equivalente** aplicando una secuencia ordenada de operaciones elementales por filas.
El secreto para no deshacer los unos y ceros que ya conseguiste es **trabajar columna por columna (de izquierda a derecha) y fila por fila (de arriba hacia abajo)**:
1. **Paso A — Conseguir el elemento conductor (`1`):** En la fila y columna que te toca trabajar, buscás tener un `1`.
   - Si ya hay un `1`, no hacés nada.
   - Si en otra fila de más abajo hay un `1` en esa misma columna (o un número más cómodo), podés **permutar las filas** (`1º Operación: H_i,j`) para evitar trabajar con fracciones desde el principio.
   - Si el elemento actual es un número `a ≠ 0` (por ejemplo `-3`), **multiplicás esa fila por su inverso multiplicativo `1/a`** (`2º Operación: H_i(1/a)`, en ese caso `H_i(-1/3)`), porque `a · (1/a) = 1`.
2. **Paso B — Anular el resto de su columna (`0`):** Inmediatamente después de tener el elemento conductor `1` en la fila `j`, hacés cero todos los demás números de esa misma columna. Para anular un número `b` que está en otra fila `i`, aplicás la **`3º Operación: H_i,j(-b)`**: a la fila `i` (la que querés modificar) le sumás la fila `j` (la fila donde está el elemento conductor `1`) multiplicada por **`-b`** (el opuesto del número que querés anular).
   - Podés anular dos o más elementos de esa misma columna en **un mismo paso con operaciones simultáneas**, siempre que las operaciones **no modifiquen la misma fila**.
3. **Paso C — Avanzar en escalera:** Recién cuando toda la columna del primer elemento conductor tiene ceros salvo el `1`, pasás a la siguiente fila y buscás su elemento conductor más a la derecha, repitiendo A y B. Si alguna fila se hace completamente de ceros, la mandás al final con una permutación de filas (`H_i,j`).

**🔍 Desglose de la jerga y por qué funciona el método:**
- **Por qué para obtener el `1` se multiplica por `1/a` (y no por `a` ni por `-a`):** Como explica el Ejemplo Nº 3 en la Pág. 6 para el número `-3`: *"Si dijiste 3, hay error, si dijiste -3, también hay error. La respuesta correcta sería por -1/3 Si! Por esta fracción se simplificará y dará como resultado 1"*.
- **Por qué para hacer `0` un elemento `b` se usa `H_i,j(-b)` con la fila `j` del elemento conductor:**
  1. Como en la columna que estamos limpiando la fila `j` tiene un `1` (el elemento conductor), al multiplicarlo por `-b` y sumarlo a `b` queda `b + (-b) · 1 = 0`.
  2. Además, como a la izquierda de ese elemento conductor la fila `j` ya tiene todos `0`, sumar múltiplos de la fila `j` a otras filas **no arruina los ceros ni los elementos conductores de las columnas anteriores** (porque `0 · (-b) = 0`). ¡Por eso es fundamental seguir el orden de las Claves de Estudio!
- **Operaciones simultáneas:** En el Ejemplo Nº 3 (Pág. 7), una vez obtenido el elemento conductor de la fila 3 columna 3, hay que anular el `-1` de la fila 1 y el `2` de la fila 2. Se aplican juntas `H_1,3(1)` y `H_2,3(-2)` porque una modifica la fila 1, la otra modifica la fila 2, y ambas usan como auxiliar la fila 3 sin alterarla.
- **Unicidad del resultado vs. libertad del camino (Desempeño 46 d):** No hay una única secuencia de operaciones elementales (por ejemplo, se puede permutar filas o multiplicar por fracción), pero **la matriz canónica final a la que se llega es única** y no depende de qué operaciones válidas se hayan elegido en cada paso.

**💡 Ejemplo (Síntesis del Ejemplo Nº 3 del material, Págs. 6 y 7):**
Para llevar `A = [[1, 2, 3], [4, 5, 6], [5, 7, 8]]` a su forma canónica:
1. **Columna 1:**
   - Ya tenemos el elemento conductor `1` en la posición `(1,1)`.
   - Anulamos el `4` de la fila 2 con `1* H_2,1(-4)` y el `5` de la fila 3 con `2* H_3,1(-5)` → queda `[[1, 2, 3], [0, -3, -6], [0, -3, -7]]`.
2. **Columna 2:**
   - Convertimos el `-3` de la posición `(2,2)` en elemento conductor `1` aplicando `3* H_2(-1/3)` → queda `[[1, 2, 3], [0, 1, 2], [0, -3, -7]]`.
   - Anulamos el `2` de la fila 1 con `4* H_1,2(-2)` y el `-3` de la fila 3 con `5* H_3,2(3)` → queda `[[1, 0, -1], [0, 1, 2], [0, 0, -1]]`.
3. **Columna 3:**
   - Convertimos el `-1` de la posición `(3,3)` en elemento conductor `1` aplicando `6* H_3(-1)` → queda `[[1, 0, -1], [0, 1, 2], [0, 0, 1]]`.
   - Anulamos simultáneamente el `-1` de la fila 1 y el `2` de la fila 2 con `7* H_1,3(1)` y `8* H_2,3(-2)` → llegamos a la matriz canónica `B = [[1, 0, 0], [0, 1, 0], [0, 0, 1]]`.

**🔗 Conexiones:**
- Con **Columna de control (7.8)**: este algoritmo se complementa agregando la columna de control a la derecha para verificar que en ninguno de los pasos `1*` a `8*` se haya cometido un error de cuentas.

**⚠️ Precisiones / errores comunes:**
- **No anular usando una fila que no sea la del elemento conductor:** Si estás en la columna 2 o 3 y usás para anular una fila que todavía tiene números distintos de cero a la izquierda, vas a "ensuciar" las columnas que ya habías hecho cero. Siempre usá como fila auxiliar (`j` en `H_i,j(k)`) la fila del elemento conductor de esa columna.
- **No hacer operaciones simultáneas que se pisen entre sí:** Por ejemplo, no podés hacer en el mismo paso `H_1,2` y `H_2,1(-4)`, ni dos operaciones que modifiquen la misma fila o que usen como auxiliar una fila que se está modificando en ese mismo paso.

**🎤 Cómo decirlo en el oral:**
> *"Para hallar la matriz canónica equivalente a una matriz dada, primero se busca el elemento conductor (el 1) de la primera fila —ya sea multiplicando la fila por el inverso de su primer elemento no nulo mediante Hi(k) o permutando filas con Hij para evitar fracciones— e inmediatamente después se anulan todos los restantes elementos de su columna aplicando la tercera operación elemental Hij(k), sumándole a cada fila la fila del elemento conductor multiplicada por el opuesto del número que se desea anular. Luego se pasa al elemento conductor de la segunda fila y se anula su columna, y así sucesivamente en escalera. Se pueden realizar dos operaciones simultáneas en un mismo paso siempre y cuando no afecten a la misma fila. Aunque el camino de operaciones elegidas puede variar, la matriz canónica obtenida al final es única."*

---

## 7.8 Columna de control (Método de verificación de cálculos)

> 📖 **Textual del material:** "El aplicar este tipo de operaciones sobre las matrices puede llevarnos a cometer errores de cálculo que cambiarán el resultado final. Para evitar esto, se puede agregar una columna más a la matriz dada, denominada columna de control, cuyos elementos se obtienen sumando los elementos de cada fila de la matriz original. A esta columna también se le aplican las operaciones elementales, y se debe controlar que los elementos de dicha columna sigan siendo la suma de los elementos de la fila, ahora transformada." *(Pág. 8)*
>
> 📖 **Textual del material:** "La columna de control SE OBTIENE sumando los elementos de cada fila de la matriz." *(Pág. 8)*
>
> 📖 **Textual del material:** "A partir de este paso, la columna de control se trabaja de la misma manera que el resto de la matriz, como si fuese una columna más, aplicando las operaciones propias de cada fila." *(Pág. 8)*
>
> 📖 **Textual del material:** "Para corroborar si se aplicó bien la operación por fila, la suma de los elementos de cada fila, debe seguir dando igual, al elemento de la columna de control correspondiente. En este caso 0 + (-3) + (-6) = -9. Al dar el mismo resultado, quiere decir que la operación se ha resuelto correctamente. En el caso que no diera el mismo resultado, hay que revisar solo ese paso, ya que se supone que el resto está bien resuelto. Es un proceso que lleva más cálculos, pero garantiza que la matriz a la que se llega, sea la correcta." *(Pág. 8)*

**🗣️ En palabras simples:**
La **columna de control** es una columna extra que le agregamos al costado derecho de la matriz para detectar al instante cualquier error de cuentas cuando hacemos operaciones elementales:
1. **¿Cómo "nace" la columna de control?** Antes de empezar a operar, sumamos horizontalmente todos los números de la fila 1 y anotamos el resultado al lado; hacemos lo mismo con la fila 2, con la fila 3, etc. Esos resultados forman la columna de control inicial.
2. **¿Cómo se trabaja?** Cada vez que le aplicamos una operación elemental a una fila (`H_i,j`, `H_i(k)` o `H_i,j(k)`), **también se la aplicamos al número de la columna de control de esa fila**, exactamente igual que si fuera un elemento más de la matriz.
3. **¿Cómo se controla en cada paso?** Terminado el paso, sumamos los nuevos números de la fila transformada: esa suma **tiene que coincidir** con el nuevo número que nos dio en la columna de control. Si coinciden, el paso está bien hecho; si no coinciden, nos equivocamos en una cuenta de *ese* paso y lo corregimos en el momento sin arrastrar el error hasta el final.

**🔍 Desglose de la jerga:**
- **"cuyos elementos se obtienen sumando los elementos de cada fila de la matriz original"**: Responde textualmente a la pregunta del Desempeño 46 e (*"¿Cómo 'nace' la columna de control?"*).
- **"A esta columna también se le aplican las operaciones elementales"**: El valor de la columna de control en el paso siguiente **no** se escribe sumando la fila nueva (porque si te equivocaste en la fila nueva no te darías cuenta), sino **aplicándole la operación elemental al valor anterior de la columna de control**, y *después* comparándolo contra la suma de la fila transformada.
- **"se debe controlar que los elementos de dicha columna sigan siendo la suma de los elementos de la fila, ahora transformada"**: Responde textualmente a la pregunta del Desempeño 46 f (*"¿Cómo se puede controlar si las operaciones aplicadas en cada paso son correctas?"*).

**🤔 Intuición (¿por qué funciona siempre?):**
La suma de los elementos de una fila cumple la propiedad distributiva y asociativa respecto de las tres operaciones elementales:
- Si permutás dos filas (`H_i,j`), sus sumas también se permutan.
- Si multiplicás todos los elementos de una fila por `k` (`H_i(k)`), por propiedad distributiva `k · a_i1 + k · a_i2 + ... + k · a_in = k · (a_i1 + a_i2 + ... + a_in)`, es decir, la nueva suma de la fila es igual a `k` por la suma anterior.
- Si a la fila `i` le sumás `k` veces la fila `j` (`H_i,j(k)`), la suma de los nuevos elementos de la fila `i` es `(suma de fila i) + k · (suma de fila j)`.

**💡 Ejemplo (Pág. 8 del material):**
Para la matriz `A = [[1, 2, 3], [4, 5, 6], [5, 7, 8]]`:
1. **Nacimiento de la columna de control:**
   - Fila 1: `1 + 2 + 3 = 6`
   - Fila 2: `4 + 5 + 6 = 15`
   - Fila 3: `5 + 7 + 8 = 20`
   Armamos la matriz con su columna de control al lado:
   ```text
        [ 1   2   3 ] [  6 ]
   A =  [ 4   5   6 ] [ 15 ]
        [ 5   7   8 ] [ 20 ]
   ```
2. **Paso `1* H_2,1(-4)`:**
   - Aplicamos la operación a la fila 2: `[4 + (-4)·1,  5 + (-4)·2,  6 + (-4)·3] = [0, -3, -6]`.
   - Aplicamos la **misma operación** a la columna de control: `15 + (-4) · 6 = 15 - 24 = -9`.
   - **Control:** Sumamos los elementos de la fila 2 transformada: `0 + (-3) + (-6) = -9`. ¡Coincide con el `-9` de la columna de control!
3. **Paso `2* H_3,1(-5)`:**
   - Aplicamos la operación a la fila 3: `[5 + (-5)·1,  7 + (-5)·2,  8 + (-5)·3] = [0, -3, -7]`.
   - Aplicamos la **misma operación** a la columna de control: `20 + (-5) · 6 = 20 - 30 = -10`.
   - **Control:** Sumamos los elementos de la fila 3 transformada: `0 + (-3) + (-7) = -10`. ¡Coincide con el `-10` de la columna de control!

**🔗 Conexiones:**
- Con **Operaciones elementales (7.5)** y **Búsqueda de la matriz canónica (7.7)**: es la herramienta de verificación estándar de la cátedra durante la reducción por filas.

**⚠️ Precisiones / errores comunes:**
- **Trampa típica al usar la columna de control:** Calcular el nuevo casillero de la columna de control sumando directamente la fila recién calculada. Si hacés eso, nunca vas a detectar ningún error. Tenés que calcular el nuevo casillero de la columna de control **aplicándole la operación elemental `H`** al casillero anterior de la columna de control, y recién después verificar que coincida con la suma de los elementos de la fila transformada.
- **Nota sobre la numeración de respuestas en las Págs. 10 y 11 del PDF:** Por si revisás las respuestas de los desempeños al final del PDF original, tené en cuenta que en las páginas 10 y 11 del apunte los títulos de las respuestas están corridos un lugar (debajo de "Desempeño n° 41" están tanto las respuestas del 41 como las del 42; debajo de "42" están las del 43; debajo de "43" están las del 44; debajo de "44" están los rangos del 45; y debajo de "45" hace referencia al cuestionario teórico del Desempeño 46).

**🎤 Cómo decirlo en el oral:**
> *"Para evitar arrastrar errores de cálculo al aplicar operaciones elementales, se puede agregar una columna más a la matriz dada denominada columna de control. Esta columna nace sumando los elementos de cada fila de la matriz original. Luego, en cada paso se le aplican a la columna de control las mismas operaciones elementales que al resto de la fila, como si fuese una columna más, y se controla que cada elemento de la columna de control siga siendo igual a la suma de los elementos de la fila ahora transformada. Si en algún paso no coinciden, solo hay que revisar ese paso."*

---

## 🧠 Resumen esquemático de la clase

- **Matriz canónica (por filas):** Matriz rectangular que cumple 4 condiciones: (1) el primer elemento no nulo de cada fila, si lo hubiera, es el `1` (**elemento conductor**); (2) en la columna de dicho `1`, los elementos restantes son `0`; (3) los elementos conductores están dispuestos **en escalera** (cada fila tiene más ceros iniciales que la anterior) y las **filas nulas**, si las hubiera, están **últimas**; (4) el número de filas no nulas es el **rango** `ρ(matriz)`.
- **Elemento conductor:** El primer elemento no nulo (igual a `1`) de cada fila no nula en una matriz canónica.
- **Rango `ρ(matriz)`:** Número de filas no nulas de la matriz en su forma canónica.
- **Casos particulares de canónica:** La **matriz nula** es canónica (no contradice ninguna condición y su rango es `0`); toda **matriz identidad** es canónica, pero no toda matriz tiene como canónica a la identidad (una no cuadrada nunca puede dar la identidad, y una cuadrada con filas que se anulan tampoco).
- **Operaciones elementales (aplicadas a filas):** Son tres: **1º `Hij`** (permutar la fila `i` con la fila `j`), **2º `Hi(k)`** (multiplicar la fila `i` por una constante `k ≠ 0`), **3º `Hij(k)`** (sumar a la fila `i` la fila `j` previamente multiplicada por una constante `k ≠ 0`, es decir `i + k · j`).
- **Matrices equivalentes (`A ~ B`):** Dos matrices son equivalentes si una se obtiene de la otra aplicando operaciones elementales; no son iguales (`A ≠ B`), pero sí equivalentes (`A ~ B`).
- **Método para llevar a la canónica:** Buscar el elemento conductor de la fila 1 (`Hi(1/a)` o `Hij`) e inmediatamente anular su columna (`Hij(-b)`), luego pasar al elemento conductor de la siguiente fila y anular su columna, y así sucesivamente; se pueden hacer operaciones simultáneas si no afectan a la misma fila. El camino de operaciones no es único, pero la matriz canónica final sí es única.
- **Columna de control:** Columna adicional cuyos elementos nacen sumando los elementos de cada fila de la matriz original; se le aplican las mismas operaciones elementales por fila y se verifica en cada paso que su valor coincida con la suma de los elementos de la fila transformada.

---

## ❓ Preguntas probables del oral

1. **¿Qué es una matriz canónica por filas y cuáles son sus características?**
   > **Respuesta:** *"La matriz canónica es una matriz rectangular que tiene las siguientes características: 1) El primer elemento no nulo de las filas, si lo hubiera, debe ser el 1, denominado elemento conductor. 2) En la columna a la que pertenece dicho 1, los elementos restantes son cero. 3) Los elementos conductores están dispuestos en escalera, o sea que cada fila tiene mayor número de ceros que la anterior adelante del elemento conductor; y las filas nulas, si las hubiera, están últimas. 4) El número de filas no nulas se denomina rango de la matriz, ρ(matriz)."*

2. **¿A qué se llama elemento conductor de una fila y qué condiciones debe cumplir tanto en su fila como en su columna?**
   > **Respuesta:** *"Se denomina elemento conductor al primer elemento no nulo de cada fila de una matriz canónica, que debe ser el 1. En su fila debe ser el primer elemento distinto de cero (y tener más ceros adelante que el elemento conductor de la fila anterior, formando una escalera), y en la columna a la que pertenece dicho 1 todos los elementos restantes deben ser cero."*

3. **¿Qué es el rango de una matriz y cómo se simboliza?**
   > **Respuesta:** *"Llevada la matriz a su forma canónica por filas, el número de filas no nulas se denomina rango de la matriz y se simboliza con ρ(matriz)."*

4. **¿La matriz nula está en forma canónica? Justifique.**
   > **Respuesta:** *"Sí, la matriz nula es un caso particular de matriz canónica porque no contradice ninguna de las condiciones: la condición 1 pide que el primer elemento no nulo de las filas, si lo hubiera, sea 1 (y en la matriz nula no hay elementos no nulos), y todas sus filas nulas están al final. Su rango es 0."*

5. **¿Cuáles son las operaciones elementales en una matriz, cómo se simbolizan y sobre qué líneas las aplicamos nosotros?**
   > **Respuesta:** *"Las operaciones elementales son tres, y aunque se aplican tanto a filas como a columnas, nosotros las aplicamos solamente a las filas de la matriz:*
   > *1º Operación: Permutar filas entre sí. Se simboliza con Hij, lo que indica intercambiar la fila i con la fila j.*
   > *2º Operación: Multiplicar una fila por una constante distinta de cero. Se simboliza con Hi(k), lo que indica multiplicar la fila i por la constante k.*
   > *3º Operación: Sumar a una fila otra fila previamente multiplicada por una constante distinta de cero. Se simboliza con Hij(k), lo que indica sumar a la fila i, la fila j multiplicada por k (i + k · j)."*

6. **En la segunda y tercera operación elemental, ¿por qué se exige que la constante `k` sea distinta de cero?**
   > **Respuesta:** *"Porque en la segunda operación Hi(k), si k fuera cero anularíamos toda la fila perdiendo información de la matriz (y dejando de ser equivalente); y en la tercera operación Hij(k), si k fuera cero estaríamos sumando cero a la fila i y no realizaríamos ninguna operación."*

7. **En la notación `Hij(k)` (por ejemplo `H_3,1(-5)`), ¿cuál es la fila que se modifica en la matriz y cuál permanece igual?**
   > **Respuesta:** *"Se modifica la fila indicada por el primer subíndice (la fila i, en el ejemplo la fila 3), a la cual se le suma la fila j (la fila 1) previamente multiplicada por k (-5). La fila j solo se multiplica previamente como cálculo auxiliar para sumarla, pero en la matriz permanece sin cambios."*

8. **¿Qué operación le podemos aplicar a una matriz para obtener una matriz equivalente, cómo se simboliza la equivalencia y qué diferencia hay con la igualdad?** *(Pregunta del Desempeño 46 a)*
   > **Respuesta:** *"Para obtener una matriz equivalente se le aplican las operaciones elementales por filas. La equivalencia se simboliza con `~` (A ~ B). Dos matrices equivalentes no son iguales elemento a elemento, pero se obtienen una de otra por operaciones elementales y sirven para trabajar con sistemas de ecuaciones conservando el rango."*

9. **La matriz canónica de una matriz de orden `3 × 4`, ¿puede ser la matriz identidad? Explica por qué.** *(Pregunta del Desempeño 46 b)*
   > **Respuesta:** *"No, nunca puede ser la matriz identidad, porque la matriz identidad es por definición una matriz cuadrada (de orden n × n), mientras que una matriz de orden 3 × 4 es rectangular no cuadrada y las operaciones elementales por filas conservan el orden 3 × 4 de la matriz."*

10. **La matriz canónica de una matriz cuadrada, ¿es siempre una matriz identidad? Explica.** *(Pregunta del Desempeño 46 c)*
    > **Respuesta:** *"No siempre. Aunque en muchos casos la matriz canónica de una matriz cuadrada da la identidad, si al aplicar las operaciones elementales se anula alguna fila (es decir, aparece una o más filas nulas al final y el rango es menor que el orden de la matriz), la matriz obtenida es canónica y cuadrada, pero no es la matriz identidad."*

11. **La matriz canónica obtenida a partir de operaciones elementales, ¿depende de qué operación se aplique en cada paso?** *(Pregunta del Desempeño 46 d)*
    > **Respuesta:** *"No. Si bien no hay una única secuencia posible de operaciones para resolver y podemos elegir distintos caminos según la conveniencia de la matriz (por ejemplo, permutar filas o multiplicar por una fracción), la matriz canónica final a la que se llega es única."*

12. **¿Cómo "nace" la columna de control y cómo se controla si las operaciones aplicadas en cada paso son correctas?** *(Preguntas del Desempeño 46 e y f)*
    > **Respuesta:** *"La columna de control nace agregando una columna más a la matriz dada cuyos elementos se obtienen sumando los elementos de cada fila de la matriz original. En cada paso se le aplican a esta columna las mismas operaciones elementales que a las filas correspondientes, y se controla que los elementos de la columna de control sigan siendo iguales a la suma de los elementos de cada fila ahora transformada. Si en un paso no dan igual, solo hay que revisar ese paso."*

13. **¿Qué pasos ordenados sugiere la cátedra para no complicarse al buscar la matriz canónica, y cuándo se pueden aplicar dos operaciones simultáneas en un mismo paso?**
    > **Respuesta:** *"El orden sugerido es: primero buscar el elemento conductor (el 1) de la fila 1 e inmediatamente después anular todos los demás elementos de su columna; segundo, pasar al elemento conductor de la siguiente fila y anular su columna, y así sucesivamente. Se pueden aplicar dos operaciones simultáneas en el mismo paso siempre y cuando dichas operaciones no afecten a la misma fila."*

---

## 📚 Glosario de la clase

| Término / Símbolo | Definición breve fiel al material |
| :--- | :--- |
| **Matriz canónica (por filas)** | Matriz rectangular que cumple: (1) el primer elemento no nulo de las filas, si lo hubiera, es el `1` (elemento conductor); (2) en la columna de dicho `1`, los elementos restantes son `0`; (3) los elementos conductores están dispuestos en escalera y las filas nulas, si las hubiera, están últimas; (4) el número de filas no nulas es el rango `ρ(matriz)`. |
| **Elemento conductor** | El primer elemento no nulo de cada fila de una matriz canónica, el cual debe ser igual a `1`. |
| **Disposición en escalera** | Condición por la cual cada fila no nula tiene mayor número de ceros que la fila anterior adelante de su elemento conductor. |
| **Rango de la matriz — `ρ(matriz)`** | Número de filas no nulas de la matriz llevada a su forma canónica por filas. |
| **Operaciones elementales** | Tres operaciones que se aplican a las líneas de una matriz (en nuestro curso, solamente a las filas) para obtener una matriz equivalente y llevarla a su forma canónica. |
| **1º Operación elemental (`Hij` / `H_i,j`)** | Permutar filas entre sí: intercambiar la fila `i` con la fila `j`. |
| **2º Operación elemental (`Hi(k)` / `H_i(k)`)** | Multiplicar una fila por una constante distinta de cero: multiplicar la fila `i` por la constante `k ≠ 0`. |
| **3º Operación elemental (`Hij(k)` / `H_i,j(k)`)** | Sumar a una fila otra fila previamente multiplicada por una constante distinta de cero: sumar a la fila `i`, la fila `j` multiplicada por `k` (`i + k · j`, con `k ≠ 0`). |
| **Matrices equivalentes (`A ~ B`)** | Relación entre una matriz y la que se obtiene luego de aplicarle operaciones elementales. Se simboliza con `~`. |
| **Columna de control** | Columna adicional que se agrega a la matriz dada sumando los elementos de cada fila original; se le aplican las mismas operaciones elementales por fila para verificar en cada paso que su valor coincida con la suma de los elementos de la fila transformada. |
