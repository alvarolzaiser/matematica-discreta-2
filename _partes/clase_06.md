# Clase 6 — Matrices y Determinantes: Operaciones con matrices

## 🗺️ Mapa de la clase

> 📖 **Textual del material (Objetivos de la Clase 6, Pág. 1):**
> "Al finalizar la clase los alumnos:
> • Comprender las condiciones para poder realizar las operaciones.
> • Manejar con destreza los procedimientos para realizar operaciones entre matrices.
> • Aplicar las operaciones entre matrices a la resolución de situaciones problemáticas concretas."

- **Qué temas cubre y en qué orden:**
  - **Introducción al álgebra de matrices:** Presentación de las tres operaciones fundamentales que se definen en la clase (adición/sustracción, producto de una matriz por un número y multiplicación de matrices) y sus respectivas propiedades a partir de situaciones problemáticas.
  - **6.1 Adición de matrices (Suma de matrices):** Condición de posibilidad (igualdad de orden), procedimiento elemento a elemento, orden de la matriz resultante y expresión simbólica general.
  - **6.2 Sustracción de matrices (Resta de matrices):** Definición operativa análoga a la adición y falta de conmutatividad.
  - **6.3 Propiedades de la suma de matrices:** Conmutativa, asociativa, existencia de elemento neutro aditivo (matriz nula) y existencia de elemento inverso aditivo (matriz opuesta), junto con las definiciones generales de elemento neutro y elemento inverso de una operación.
  - **6.4 Producto de una matriz por un número (Multiplicación por un escalar):** Definición, conservación del orden, procedimiento elemento a elemento y expresión simbólica.
  - **6.5 Propiedades de la multiplicación por un número:** Distributiva respecto a la suma de números, distributiva respecto a la suma de matrices, asociativa respecto a los números, existencia del elemento neutro escalar (el número 1) y convención notacional (letras griegas para números, alfabeto latino para matrices).
  - **6.6 Método general para resolver problemas con matrices:** Heurística de cuatro pasos (Entender, Planificar, Resolver, Revisar).
  - **6.7 Producto escalar entre vectores:** Definición del producto escalar entre un vector fila y un vector columna de igual cantidad de elementos, y sus tres observaciones fundamentales (da un número, exige igual cantidad de elementos, orden estricto fila por columna).
  - **6.8 Multiplicación de matrices (Producto entre matrices) y Matrices Conformables:** Definición a partir de todos los productos escalares posibles entre filas de la primera y columnas de la segunda, condición de posibilidad (matrices conformables: columnas de la primera = filas de la segunda), orden de la matriz resultante y obtención del elemento "ij"-ésimo.
  - **6.9 Propiedades asociativa y distributiva de la multiplicación de matrices:** Carácter atípico del producto matricial frente a los números reales; asociatividad y distributividad respecto a la suma (con respeto estricto de los órdenes de conformabilidad).
  - **6.10 No conmutatividad del producto matricial y Matrices Permutables:** Inexistencia o desigualdad general entre A · B y B · A, y definición del caso especial de matrices permutables (A · B = B · A).
  - **6.11 No cumplimiento de la Propiedad Cancelativa y producto nulo de matrices no nulas:** Demostración algebraica de por qué A · B = A · C equivale a A · (B − C) = 0 pero no permite cancelar A, y contraejemplo de dos matrices no nulas cuyo producto es la matriz nula.
  - **6.12 Elemento neutro multiplicativo (Matriz Identidad):** Rol de la matriz identidad I en el producto matricial (I · A = A · I = A).
  - **6.13 Elemento inverso multiplicativo (Matriz Inversa):** Condición necesaria (sólo para matrices cuadradas y no en todos los casos), notación A⁻¹ y propiedad definitoria (A · A⁻¹ = A⁻¹ · A = I).

- **Prerrequisitos (de la Clase 5):**
  - Concepto de **matriz**, **filas** (horizontales) y **columnas** (verticales).
  - Concepto de **orden o dimensión** de una matriz (m × n: m filas por n columnas) y notación de un elemento genérico a_ij (ubicado en la fila i y columna j).
  - Clasificación de matrices vista en la Clase 5: **matriz cuadrada** (m = n), **matriz fila o vector fila** (1 × n), **matriz columna o vector columna** (m × 1), **matriz nula** (0, todos sus elementos son ceros), **matriz opuesta** (−A, cuyos elementos son los opuestos de los de A) y **matriz identidad o unidad** (I, matriz escalar cuya diagonal principal tiene todos 1 y el resto 0).

---

## 6.1 Adición de matrices (Suma de matrices)

> 📖 **Textual del material:** "En el álgebra de matrices, definiremos tres operaciones, que podemos realizar entre ellas y además las propiedades que las mismas cumplen." (Pág. 2)
>
> 📖 **Textual del material:** "Para sumar dos matrices, (no necesariamente cuadradas), éstas deben ser del mismo orden, si esto es así se suman los elementos correspondientes.
> La matriz resultante tiene el mismo orden que las matrices sumadas." (Pág. 2)
>
> 📖 **Textual del material:**
> "A_(mx,n) =
> [ a_11   a_12   a_1n ]
> [ a_21   a_22   a_2n ]
> [ a_m1   a_m2   a_mn ]
> Y
> B_(mx,n) =
> [ b_11   b_12   b_1n ]
> [ b_21   b_22   b_2n ]
> [ b_m1   b_m2   b_mn ]
>
> (A + B)_(mx,n) =
> [ a_11 + b_11   a_12 + b_12   a_1n + b_1n ]
> [ a_21 + b_21   a_22 + b_22   a_2n + b_2n ]
> [ a_m1 + b_m1   a_m2 + b_m2   a_mn + b_mn ]" (Pág. 3)

**🗣️ En palabras simples:**
Sumar dos matrices consiste simplemente en sumar posición por posición: el elemento de la esquina superior izquierda de la primera con el de la esquina superior izquierda de la segunda, y así sucesivamente con cada casillero. Para que cada elemento tenga su "pareja" en la misma ubicación, las dos matrices tienen que tener exactamente el mismo tamaño (igual cantidad de filas e igual cantidad de columnas). El resultado es una nueva matriz de ese mismo tamaño.

**🔍 Desglose de la jerga:**
- **"no necesariamente cuadradas":** Aclara que la suma no está restringida a matrices de igual número de filas que de columnas (n × n); se pueden sumar matrices rectangulares (por ejemplo, de 3 × 2 o de 2 × 3) siempre que coincidan entre sí en su orden.
- **"del mismo orden":** Es la **condición de posibilidad** (requisito obligatorio) para la adición. Que A y B sean del mismo orden m × n significa que A tiene m filas y n columnas, y B también tiene exactamente m filas y n columnas.
- **"elementos correspondientes" (o homólogos):** Son los elementos que ocupan la misma posición (mismo número de fila i y mismo número de columna j) en ambas matrices; es decir, el elemento a_ij de A se suma únicamente con el elemento b_ij de B.
- **"(A + B)_(mx,n)":** Indica que la matriz suma resultante conserva intacto el orden m × n de las matrices sumadas (en el PDF aparece impreso con una coma tipográfica intermedia como `mx,n`, que representa el orden m × n).

**💡 Ejemplo:**
*(Del material, Situación n° 5, Pág. 2 — suma de tres matrices de orden 3 × 2 que representan acreditaciones, depósitos y extracciones de Matías y Florencia en diciembre D, enero E y febrero F):*
```
            [ 50  45 ]   [ 90  100 ]   [ 100  70 ]   [ 240  215 ]
D + E + F = [ 30  10 ] + [ 15   21 ] + [  40  30 ] = [  85   61 ]
            [ 80  25 ]   [ 90   50 ]   [  30  50 ]   [ 200  125 ]
```
Aquí las tres matrices son de orden 3 × 2 (no son cuadradas). Para hallar, por ejemplo, el elemento de la posición (1,2) de la matriz resultado, se suman los elementos correspondientes de la fila 1 y columna 2 de cada matriz: 45 + 100 + 70 = 215. La matriz resultante también es de orden 3 × 2.

**🔗 Conexiones:**
- Se apoya directamente en el concepto de **orden de una matriz** y de **elementos correspondientes** visto en la Clase 5 (donde la igualdad de matrices también exigía igual orden e igualdad de elementos correspondientes).
- Es la base para definir la **sustracción de matrices** (6.2) y se combina con el producto por un escalar y el producto matricial a través de las **propiedades distributivas** (6.5 y 6.9).

**⚠️ Precisiones / errores comunes:**
- **Error grave en el oral:** Decir "dos matrices se pueden sumar cuando son cuadradas" o confundir la condición de suma con la de multiplicación (conformabilidad). Para sumar, los órdenes deben ser **idénticos** (m × n con m × n); si una matriz es de 2 × 3 y otra de 3 × 2, **no se pueden sumar** aunque tengan la misma cantidad total de números (6 elementos).
- En la expresión simbólica general, si queremos nombrar el elemento genérico en el oral, decimos que el elemento (i, j) de A + B es a_ij + b_ij para todo i desde 1 hasta m y para todo j desde 1 hasta n.

**🎤 Cómo decirlo en el oral:**
> "Para sumar dos matrices, que no necesariamente deben ser cuadradas, la condición necesaria es que ambas sean del **mismo orden** (es decir, que tengan igual cantidad de filas e igual cantidad de columnas). Si se cumple esta condición, se suman los **elementos correspondientes** (cada a_ij con su respectivo b_ij), y la matriz resultante tiene el **mismo orden** que las matrices sumadas."

---

## 6.2 Sustracción de matrices (Resta de matrices)

> 📖 **Textual del material:** "En la sustracción de matrices se procede de igual forma que en la adición, la única diferencia es que los elementos se restan." (Pág. 3)
>
> 📖 **Textual del material:** "b- No, no es posible. Si restamos dos matrices en diferente orden, da distinto resultado." (Pág. 15, Respuesta al Desempeño n° 25 b sobre si es posible resolver la resta de matrices en cualquier orden)

**🗣️ En palabras simples:**
Para restar dos matrices A − B, primero verificás que tengan exactamente el mismo orden (igual que en la suma) y después restás cada elemento de la primera matriz menos el elemento que está en la misma posición de la segunda matriz (a_ij − b_ij). A diferencia de la suma, en la resta importa quién va primero: hacer A − B no da lo mismo que hacer B − A.

**🔍 Desglose de la jerga:**
- **"se procede de igual forma que en la adición":** Significa que hereda exactamente la misma condición de posibilidad (ambas matrices deben ser del mismo orden m × n) y que la matriz resultante (A − B)_(m×n) conserva ese mismo orden m × n.
- **"los elementos se restan":** Cada elemento de la matriz diferencia en la posición (i, j) se obtiene haciendo a_ij − b_ij (elemento de la primera matriz menos su correspondiente en la segunda).
- **"Si restamos dos matrices en diferente orden, da distinto resultado":** Expresa que la sustracción de matrices **no cumple la propiedad conmutativa** (en general, A − B ≠ B − A; de hecho, dan matrices opuestas entre sí).

**💡 Ejemplo:**
*(Del material, Desempeño 24, Págs. 3 y 14):*
Dadas las matrices de orden 2 × 3:
```
    [ 1   0  -1 ]          [ -2  -1   0 ]
A = [ 2   3  -4 ]    y B = [  0   0   3 ]
```
La resta A − B se obtiene restando los elementos correspondientes:
```
        [ 1 - (-2)   0 - (-1)   -1 - 0 ]   [ 3   1  -1 ]
A - B = [ 2 - 0      3 - 0      -4 - 3 ] = [ 2   3  -7 ]
```
*(Nota sobre errata del PDF en Pág. 14: en la respuesta del Desempeño 24 ítem c, el PDF rotula por error tipográfico `c- A + B =` cuando corresponde a la resta `A - B`, y en la posición (1,3) escribe `-2` en vez de `-1 - 0 = -1`).*

**🔗 Conexiones:**
- Algebraicamente *(contexto adicional conectado con 6.3 y 6.4)*, restar A − B equivale a sumar a la matriz A la **matriz opuesta** (inverso aditivo) de B: A − B = A + (−B) = A + (−1) · B.

**⚠️ Precisiones / errores comunes:**
- Cuidado con la palabra "orden" en español dentro de esta clase, porque el material la usa con dos sentidos distintos según el contexto:
  1. **Orden de una matriz:** Su dimensión o tamaño m × n ("matrices del mismo orden").
  2. **Orden de los operandos:** En qué secuencia se escriben en la cuenta, A − B versus B − A ("resolver la resta en cualquier orden"). En el oral, aclaralo siempre para mostrar precisión.

**🎤 Cómo decirlo en el oral:**
> "En la sustracción de matrices se procede de igual forma que en la adición: las matrices deben ser del mismo orden, la matriz resultante conserva ese orden, y la única diferencia es que los elementos correspondientes se restan. A diferencia de la adición, la sustracción **no es conmutativa**: si restamos dos matrices cambiando el orden de los términos, se obtiene un resultado distinto (la matriz opuesta)."

---

## 6.3 Propiedades de la suma de matrices (Elemento neutro e inverso aditivo)

> 📖 **Textual del material:** "Propiedades de la suma de matrices
> Veamos ahora un resumen de las propiedades que cumplen en la suma de matrices:
> 1| Propiedad Conmutativa: A + B = B + A
> 2| Propiedad Asociativa: (A + B) + C = A + (B + C)
> 3| Existencia de elemento neutro aditivo: A + 0 = A
> 4| Existencia elemento inverso aditivito: A + (- A) = 0" (Pág. 3)
>
> 📖 **Textual del material (Respuestas del Desempeño n° 25, Pág. 15):**
> - "a- Si es posible. Si sumamos dos matrices en diferente orden, da el mismo resultado."
> - "d- Nula. Se llama elemento neutro para una determinada operación (la suma en este caso) a un elemento que al operar con él no cambia al otro. Por ejemplo para la suma de números, el neutro es el cero; para el producto, es el uno."
> - "e- Se llama elemento inverso, para una determinada operación a un elemento que al operar con él nos da el neutro de la operación."
> - "f- Matriz opuesta (Todos los elementos son opuestos)."

**🗣️ En palabras simples:**
La suma de matrices se comporta igual de bien que la suma de números comunes:
1. **Conmutativa:** Da igual sumar A + B que B + A.
2. **Asociativa:** Si tenés que sumar tres o más matrices (A + B + C), podés agrupar primero las dos primeras y al resultado sumarle la tercera, o agrupar las dos últimas y sumárselas a la primera; da exactamente lo mismo.
3. **Elemento neutro aditivo:** Existe una matriz que al sumarla no altera nada: la **matriz nula** (0), que tiene todos sus elementos iguales a cero (del mismo orden que A).
4. **Elemento inverso aditivo:** Para cada matriz A existe otra matriz del mismo orden, llamada **matriz opuesta** (−A), que tiene todos sus elementos con el signo cambiado y que al sumarse con A da como resultado la matriz nula (0).

**🔍 Desglose de la jerga:**
- **Propiedad Conmutativa (`A + B = B + A`):** El orden de los sumandos no altera la matriz suma.
- **Propiedad Asociativa (`(A + B) + C = A + (B + C)`):** La forma de agrupar tres o más sumandos no altera el resultado.
- **Elemento neutro de una operación:** Definición general que da el material en Pág. 15: es *"un elemento que al operar con él no cambia al otro"*. En la adición de matrices, ese elemento es la **matriz nula** (simbolizada con `0`), ya que `A + 0 = A`.
- **Elemento inverso de una operación:** Definición general que da el material en Pág. 15: es *"un elemento que al operar con él nos da el neutro de la operación"*.
- **Elemento inverso aditivo (`-A`):** *(En la tabla de Pág. 3 figura con la errata tipográfica "aditivito"; el término correcto es **aditivo**, como aparece en las preguntas de Pág. 3 y Pág. 14).* Para la suma de matrices, el inverso aditivo de A es la **matriz opuesta** `−A` (cuyos elementos son los opuestos de los de A, es decir, `−a_ij`), porque al sumarla con A da el neutro de la suma (la matriz nula `0`): `A + (−A) = 0`.

**🧩 Idea de la demostración / justificación:**
*(Contexto adicional para comprender por qué se cumplen):*
Como la suma de matrices se define sumando elemento a elemento (`a_ij + b_ij`) y cada elemento es un número real, las cuatro propiedades se heredan directamente de las propiedades de la suma de números reales en cada posición `(i, j)`:
- En cada posición `(i, j)`, `a_ij + b_ij = b_ij + a_ij` (conmutatividad en ℝ) ⇒ `A + B = B + A`.
- En cada posición `(i, j)`, `(a_ij + b_ij) + c_ij = a_ij + (b_ij + c_ij)` (asociatividad en ℝ) ⇒ `(A + B) + C = A + (B + C)`.
- En cada posición `(i, j)`, `a_ij + 0 = a_ij` ⇒ sumar la matriz nula `0` (todos ceros) deja cada elemento intacto: `A + 0 = A`.
- En cada posición `(i, j)`, `a_ij + (−a_ij) = 0` ⇒ sumar la matriz opuesta `−A` anula todos los elementos y produce la matriz nula `0`: `A + (−A) = 0`.

**🤔 Intuición:**
Dado que las matrices, al sumarse, no mezclan posiciones entre sí (cada casillero `(i, j)` opera de manera totalmente independiente de los demás), la suma matricial no es más que hacer `m × n` sumas numéricas comunes en paralelo. Por eso cumple exactamente las mismas propiedades que la suma de números.

**💡 Ejemplo:**
*(Basado en el Desempeño 24, Pág. 3):*
Si `A = [ 1  0  -1 ; 2  3  -4 ]` (de orden 2 × 3):
- Su **elemento neutro aditivo** es la matriz nula de orden 2 × 3: `0 = [ 0  0  0 ; 0  0  0 ]`, pues `A + 0 = A`.
- Su **elemento inverso aditivo** (matriz opuesta) es `−A = [ -1  0  1 ; -2  -3  4 ]`, pues `A + (−A) = [ 0  0  0 ; 0  0  0 ] = 0`.

**🔗 Conexiones:**
- Conecta con la **Clase 5**, donde se definieron la **matriz nula** y la **matriz opuesta**. Aquí cobran sentido algebraico: la matriz nula es el *neutro aditivo* y la matriz opuesta es el *inverso aditivo*.
- Contrasta fuertemente con la **multiplicación de matrices** (6.9 a 6.13), donde la conmutativa **no** se cumple, el neutro es la **matriz identidad** `I` y el inverso multiplicativo `A⁻¹` sólo existe para ciertas matrices cuadradas.

**⚠️ Precisiones / errores comunes:**
- **¡Ojo en el oral!** Si el profesor pregunta *"¿Cuál es el elemento neutro de la suma de matrices?"*, **no** respondas "el número cero". Respondé: **"La matriz nula (del mismo orden que la matriz dada)"**. El `0` en `A + 0 = A` y en `A + (-A) = 0` representa una **matriz nula**, no un escalar.
- De igual modo, no confundas el **inverso aditivo** (la matriz opuesta `−A`, que existe siempre para cualquier matriz de cualquier orden) con el **inverso multiplicativo** (la matriz inversa `A⁻¹`, que sólo existe para algunas matrices cuadradas).

**🎤 Cómo decirlo en el oral:**
> "La suma de matrices cumple cuatro propiedades:
> 1. **Propiedad conmutativa:** `A + B = B + A`, es decir, si sumamos dos matrices en diferente orden da el mismo resultado.
> 2. **Propiedad asociativa:** `(A + B) + C = A + (B + C)`.
> 3. **Existencia de elemento neutro aditivo:** `A + 0 = A`, donde `0` es la **matriz nula** (aquella que al operar con otra matriz mediante la suma no la cambia).
> 4. **Existencia de elemento inverso aditivo:** `A + (−A) = 0`, donde `−A` es la **matriz opuesta** (todos sus elementos son los opuestos de los de A, y al sumarla con A nos da el neutro de la operación, que es la matriz nula)."

---

## 6.4 Producto de una matriz por un número (Multiplicación por un escalar)

> 📖 **Textual del material:** "Entonces se define que la multiplicación de una matriz por un número, será igual a una nueva matriz del mismo orden que la anterior, cuyos elementos son los de la matriz original multiplicados por el número.
> En símbolos:
> A =
> [ a_11  ...  a_1n ]
> [ ...   ...  ...  ]
> [ a_m1  ...  a_mn ]
>
> kA =
> [ ka_11  ...  ka_1n ]
> [ ...    ...  ...   ]
> [ ka_m1  ...  ka_mn ]" (Pág. 4)

**🗣️ En palabras simples:**
Multiplicar una matriz por un número suelto (también llamado *escalar*, como 3, −2 o 1,2) consiste en multiplicar **todos y cada uno** de los elementos de la matriz por ese número. No requiere ninguna condición especial sobre el tamaño de la matriz, y la matriz que queda tiene el mismo orden que la original.

**🔍 Desglose de la jerga:**
- **"multiplicación de una matriz por un número" (o por un escalar):** En álgebra matricial, a un número suelto (como `k`, `α`, `β`) se lo suele llamar **escalar** (término que el propio material utiliza en el Desempeño 40 d de la Pág. 14: *"Para multiplicar una matriz por un escalar..."*) para distinguirlo de una matriz.
- **"del mismo orden que la anterior":** El producto por un número no altera la cantidad de filas ni de columnas: si `A` es de orden `m × n`, entonces `kA` también es de orden `m × n`.
- **"cuyos elementos son los de la matriz original multiplicados por el número":** Si el elemento genérico de `A` es `a_ij`, el elemento en la posición `(i, j)` de `kA` es `k · a_ij` para todo `i` y todo `j`.

**💡 Ejemplo:**
*(Del material, Pág. 4 — triplicar los valores de la matriz D de diciembre):*
```
        [ 50  45 ]       [ 150  135 ]
D = 3 . [ 30  10 ]  -->  [  90   30 ]
        [ 80  25 ]       [ 240   75 ]
```
*(Otro caso clave del material, Situación n° 6, Págs. 4 y 5):*
Si se eleva la producción de una fábrica `A` en un 20%, se multiplica la matriz `A` por el número `1,2` (pues 100% + 20% = 120% = 1,2). Si se disminuye en un 10%, se multiplica por `0,9` (en el Desempeño 39 d de la Pág. 14 se vuelve a aplicar para un aumento del 10% multiplicando por `1,1`).

**🔗 Conexiones:**
- Permite expresar la **matriz opuesta** `−A` (vista en 6.3) como el producto del escalar `−1` por la matriz `A`: `(−1) · A = −A`.
- Se diferencia radicalmente de la **multiplicación entre dos matrices** (6.8) y del **producto escalar entre dos vectores** (6.7): aquí intervienen **un número y una matriz**, y el resultado es **una matriz**.

**⚠️ Precisiones / errores comunes:**
- **Pregunta trampa del Desempeño 40 d (Pág. 14):** *"Para multiplicar una matriz por un escalar, la matriz ¿Debe cumplir alguna condición en especial? ¿y el escalar?"*
  - **Respuesta:** **No**, ninguna condición en especial: cualquier matriz de cualquier orden `m × n` se puede multiplicar por cualquier número (escalar). No hace falta que la matriz sea cuadrada ni conformable con nada.
- No confundir el nombre **"producto de una matriz por un escalar"** (que da una **matriz** del mismo orden) con el **"producto escalar"** entre un vector fila y un vector columna (que da un **número**, sección 6.7).

**🎤 Cómo decirlo en el oral:**
> "La multiplicación de una matriz por un número (o escalar) se define como una nueva matriz del **mismo orden** que la anterior, cuyos elementos son los de la matriz original multiplicados todos por dicho número. Simbólicamente, si `A` tiene elementos `a_ij`, la matriz `k · A` tiene elementos `k · a_ij`. Ni la matriz ni el escalar deben cumplir ninguna condición especial para poder realizar esta operación."

---

## 6.5 Propiedades de la multiplicación por un número

> 📖 **Textual del material:** "PROPIEDADES DE LA MULTIPLICACIÓN POR UN NÚMERO
> Veamos las propiedades que se cumplen en esta operación:
> 1| Distributiva respecto a la suma de números: (α + β) . A = α . A + β . A
> 2| Distributiva respecto a la suma de matrices: B . (A + b) = β . A + β . B
> 3| Asociativa respecto a los números: (α . β) . A = α . (β . α)
> 4| Existencia del elemento neutro: 1 . A = A
>
> Recordemos que las letras griegas (α, β, δ) representan números y las de nuestro alfabeto representan matrices." (Pág. 4)
>
> 📖 **Textual del material:** "Estas propiedades, al igual a que las de la Adición de matrices, sirven para facilitar algunos cálculos, predecir algunos resultados y sobre todo entender lo que se tiene que realizar en el momento de resolver alguna situación determinada." (Pág. 5)

**🗣️ En palabras simples:**
Cuando combinamos números (escalares) y matrices, podemos operar con total naturalidad:
1. Si sumamos dos números y multiplicamos el resultado por una matriz `A`, da lo mismo que multiplicar cada número por `A` y sumar las dos matrices.
2. Si multiplicamos un número por la suma de dos matrices `A + B`, podemos distribuir el número a cada matriz.
3. Si multiplicamos dos números entre sí y luego por una matriz `A`, da lo mismo que multiplicar primero uno de los números por `A` y al resultado multiplicarlo por el otro número.
4. Multiplicar cualquier matriz `A` por el número `1` deja a la matriz `A` exactamente igual.

**🔍 Desglose de la jerga y Fe de Erratas del PDF:**
- **Convención de notación del material:** Las **letras griegas** (`α`, `β`, `δ`) representan **números** (escalares) y las **letras de nuestro alfabeto** (`A`, `B`, `C`) representan **matrices**.
- **1| Distributiva respecto a la suma de números:** `(α + β) · A = α · A + β · A`. Aquí hay dos números (`α` y `β`) y una sola matriz (`A`).
- **2| Distributiva respecto a la suma de matrices:** En la tabla de la Pág. 4 del PDF se deslizó una errata tipográfica en el miembro izquierdo: dice `B . (A + b) = β . A + β . B`, pero aplicando la propia regla del material (letras griegas = números, letras latinas mayúsculas = matrices), la expresión correcta que indica el miembro derecho es:
  `β · (A + B) = β · A + β · B` (un número `β` distribuido sobre la suma de dos matrices `A` y `B` del mismo orden).
- **3| Asociativa respecto a los números:** En la tabla de la Pág. 4 del PDF se deslizó otra errata tipográfica al final del miembro derecho: dice `(α . β) . A = α . (β . α)`, cuando el último factor debe ser la matriz `A`:
  `(α · β) · A = α · (β · A)` (asociando los números `α` y `β` con la matriz `A`).
- **4| Existencia del elemento neutro:** `1 · A = A`. Aquí el elemento neutro de la multiplicación de una matriz por un número es el **número 1** (el escalar uno), porque al multiplicar cada elemento `a_ij` por `1` queda `1 · a_ij = a_ij`.

**🧩 Idea de la demostración / justificación:**
*(Contexto adicional):*
Al igual que en la adición, cada propiedad se verifica posición por posición en el elemento `(i, j)` usando las propiedades de los números reales:
1. `(α + β) · a_ij = α · a_ij + β · a_ij` (distributiva en ℝ).
2. `β · (a_ij + b_ij) = β · a_ij + β · b_ij` (distributiva en ℝ).
3. `(α · β) · a_ij = α · (β · a_ij)` (asociativa del producto en ℝ).
4. `1 · a_ij = a_ij` (el 1 es el neutro multiplicativo en ℝ).

**🤔 Intuición:**
Multiplicar por un escalar es un "cambio de escala" uniforme sobre todos los casilleros de la matriz. Hacer dos cambios de escala seguidos (por ejemplo, duplicar y luego triplicar) equivale a hacer un único cambio por el producto de las escalas (sextuplicar: `(3 · 2) · A = 3 · (2 · A)`).

**💡 Ejemplo:**
*(Basado en el Desempeño 34 d, Pág. 12):*
En la expresión `3M − 3 · (N − P)`, gracias a la propiedad distributiva respecto a la suma/resta de matrices, sabemos que `3 · (N − P) = 3N − 3P`, o bien podemos factorizar el escalar `3` como `3 · (M − N + P)`, ahorrando multiplicaciones innecesarias tal como destaca el comentario de la Pág. 5 (*"sirven para facilitar algunos cálculos, predecir algunos resultados"*).

**🔗 Conexiones:**
- Permite distinguir claramente los **tres elementos neutros** que aparecen en la Clase 6:
  1. Neutro de la adición de matrices: la **matriz nula `0`** (`A + 0 = A`).
  2. Neutro de la multiplicación de una matriz por un número: el **número `1`** (`1 · A = A`).
  3. Neutro de la multiplicación entre matrices: la **matriz identidad `I`** (`I · A = A · I = A`).

**⚠️ Precisiones / errores comunes:**
- En el oral, recordá mencionar la convención de notación del apunte: *"Las letras griegas (α, β, δ) representan números y las de nuestro alfabeto representan matrices"*. Y tené presentes las dos erratas de imprenta de la tabla de la página 4 por si el profesor mira el cuadro del PDF.

**🎤 Cómo decirlo en el oral:**
> "La multiplicación de una matriz por un número (donde las letras griegas α, β representan números y las letras de nuestro alfabeto A, B representan matrices) cumple cuatro propiedades:
> 1. **Distributiva respecto a la suma de números:** `(α + β) · A = α · A + β · A`.
> 2. **Distributiva respecto a la suma de matrices:** `β · (A + B) = β · A + β · B`.
> 3. **Asociativa respecto a los números:** `(α · β) · A = α · (β · A)`.
> 4. **Existencia del elemento neutro:** `1 · A = A`, siendo el número 1 el neutro para esta operación."

---

## 6.6 Método general para resolver problemas con matrices

> 📖 **Textual del material:**
> "Para resolver un problema, ten en cuenta lo siguente
> 1| ENTENDER: Leer varias veces el problema y tener en claro que se quiere averiguar.
> 2| PLANIFICAR: Analizar como se puede resolver el problema. Que operación es necesario aplicar.
> 3| RESOLVER: Realizar las operaciones necesarias para encontrar los resultados.
> 4| REVISAR: Comprobar el resultado tratar de analizar si es correcto o no, si es acorde al problema planteado." (Pág. 6)

**🗣️ En palabras simples:**
Antes de ponerte a hacer cuentas con matrices en una situación problemática, el material propone seguir cuatro pasos ordenados: entender qué te piden, decidir cómo armar las matrices y qué operación matricial modela el problema (suma, producto por escalar o producto de matrices), hacer el cálculo y finalmente verificar si el orden y los valores obtenidos tienen sentido en el contexto real.

**🔍 Desglose de los pasos del método:**
1. **1| ENTENDER:** Identificar los datos (por ejemplo, ciudades, categorías, costos, gastos) y la incógnita del problema.
2. **2| PLANIFICAR:** Organizar los datos en matrices cuidando que las filas y columnas queden dispuestas de modo que la operación elegida sea **posible** (del mismo orden si hay que sumar/restar, o **conformables** con la misma magnitud puente entre las columnas de la primera y las filas de la segunda si hay que multiplicar).
3. **3| RESOLVER:** Ejecutar el procedimiento aritmético correspondiente (suma término a término, producto por un escalar o productos escalares fila por columna).
4. **4| REVISAR:** Controlar que el resultado sea coherente con el problema planteado (por ejemplo, qué representa cada fila y cada columna de la matriz resultado).

**💡 Ejemplo:**
*(Del material, Págs. 5 y 6 — empresa de turismo):*
Se organizan las ventas de viajes en una matriz `P` de 4 × 3 (4 ciudades en las filas × 3 categorías A, B, C en las columnas) y los valores monetarios en una matriz `C` de 3 × 2 (3 categorías A, B, C en las filas × 2 conceptos: Costo y Gasto adicional en las columnas). Al planificar `P · C`, las 3 columnas de `P` (categorías) coinciden con las 3 filas de `C` (categorías), y la matriz resultado `R` de 4 × 2 entrega directamente para cada una de las 4 ciudades (filas) el dinero recaudado y el gasto generado (columnas).

**🔗 Conexiones:**
- Conecta el tercer objetivo de la clase (*"Aplicar las operaciones entre matrices a la resolución de situaciones problemáticas concretas"*, Pág. 1) con la organización matricial de datos introducida en la Clase 5.

**⚠️ Precisiones / errores comunes:**
- Al modelar un problema de producto matricial, no basta con que las órdenes numéricas coincidan: además, el **significado** de las columnas de la primera matriz debe coincidir con el **significado** de las filas de la segunda matriz (por ejemplo, categorías A, B, C con categorías A, B, C).

**🎤 Cómo decirlo en el oral:**
> "El material estructura la resolución de problemas mediante cuatro pasos: **1. Entender** (leer varias veces y tener claro qué se quiere averiguar), **2. Planificar** (analizar cómo resolverlo y qué operación matricial aplicar), **3. Resolver** (realizar las operaciones necesarias) y **4. Revisar** (comprobar si el resultado es correcto y acorde al problema planteado)."

---

## 6.7 Producto escalar entre un vector fila y un vector columna

> 📖 **Textual del material:** "Cada uno de estos 8 procedimientos se denomina PRODUCTO ESCALAR y se realiza entre un vector fila y un vector columna, con igual cantidad de elementos.
> Ejemplo:
> Si A = [2  -3  2  1]   y   B =
> [  0 ]
> [  3 ]
> [ -1 ]
> [  4 ]
>
> A . B = 2 . 0 + (-3) . 3 + 2 . (-1) + 1 . 4
>       = 0 – 9 – 2 + 4
>       = -7
>
> Observaciones:
> 1| El producto escalar entre dos vectores siempre da por resultado un número, no una matriz.
> 2| El producto escalar sólo puede realizarse entre vectores que tengan la misma cantidad de elementos.
> 3| Siempre se realiza entre un vector fila y otro columna, nunca al revés." (Pág. 7)

**🗣️ En palabras simples:**
El producto escalar es la cuenta básica ("el ladrillo") con la que después se construye la multiplicación de matrices. Tomás una fila (vector fila) y una columna (vector columna) que tengan la misma cantidad de números. Multiplicás el 1.° de la fila por el 1.° de la columna, el 2.° de la fila por el 2.° de la columna, y así hasta el último, y **sumás todos esos productos**. El resultado final no es una matriz ni un vector: es **un único número**.

**🔍 Desglose de la jerga y de las 3 Observaciones:**
- **Vector fila y vector columna:** En la Clase 5 vimos que una matriz de una sola fila (`1 × n`) se llama matriz fila o **vector fila**, y una matriz de una sola columna (`n × 1`) se llama matriz columna o **vector columna**.
- **"con igual cantidad de elementos" (Observación 2):** Si el vector fila tiene `n` elementos (orden `1 × n`), el vector columna debe tener también `n` elementos (orden `n × 1`). Si uno tiene 3 elementos y el otro 4, quedará un elemento sin pareja y no se puede hacer el producto escalar.
- **"siempre da por resultado un número, no una matriz" (Observación 1):** Precisamente por eso se llama producto *escalar*: porque su resultado es un **escalar** (un número), no un arreglo rectangular entre corchetes.
- **"Siempre se realiza entre un vector fila y otro columna, nunca al revés" (Observación 3):** En esta definición, el primer factor debe ser obligatoriamente el vector fila y el segundo factor el vector columna. *(Si se multiplicara una matriz columna `n × 1` por una matriz fila `1 × n` usando el producto matricial general de 6.8, como ocurre en el Desempeño 36 c de las Págs. 13 y 15 con `P · M`, el resultado ya no es un número sino una matriz de `n × n`).*

**💡 Ejemplo:**
*(Del material, Pág. 7):*
Dados el vector fila `A = [ 2  -3  2  1 ]` (4 elementos) y el vector columna `B = [ 0 ; 3 ; -1 ; 4 ]` (4 elementos):
`A · B = 2 · 0 + (−3) · 3 + 2 · (−1) + 1 · 4 = 0 − 9 − 2 + 4 = −7` (que es un número).

*(Segundo ejemplo del material, Desempeño 26, Págs. 7 y 15):*
Dados `A = [ 2  5  -2 ]` y `B = [ 5 ; 2 ; 0 ]`:
`A · B = 2 · 5 + 5 · 2 + (−2) · 0 = 10 + 10 + 0 = 20`.

**🔗 Conexiones:**
- Es el bloque constructor directo del **producto entre matrices** (6.8): cada elemento `c_ij` de la matriz producto `A · B` no es otra cosa que el producto escalar entre el vector fila `i` de `A` y el vector columna `j` de `B`.
- La **Observación 2** (igual cantidad de elementos en el vector fila y el vector columna) es exactamente la razón por la cual, al multiplicar dos matrices `A` y `B`, el **número de columnas de `A`** (que es la cantidad de elementos de cada fila de `A`) debe ser igual al **número de filas de `B`** (que es la cantidad de elementos de cada columna de `B`).

**⚠️ Precisiones / errores comunes:**
- **No encerrar el resultado entre corchetes** cuando te piden el **producto escalar** entre dos vectores: la Observación 1 recalca expresamente que *"siempre da por resultado un número, no una matriz"*.
- **Pregunta del Desempeño 40 f (Pág. 14):** *"¿Es posible multiplicar dos matrices filas?"*
  - **Respuesta:** **No** (salvo el caso trivial `1 × 1`), porque para el producto escalar se necesita un vector fila y un vector columna (nunca dos vectores fila), y desde el punto de vista de órdenes matriciales, dos matrices fila `1 × n` y `1 × m` (con `n > 1`) no son conformables porque el número de columnas de la primera (`n`) no es igual al número de filas de la segunda (`1`).

**🎤 Cómo decirlo en el oral:**
> "El **producto escalar** se realiza entre un vector fila y un vector columna con igual cantidad de elementos, multiplicando cada elemento de la fila por su correspondiente de la columna y sumando esos productos. Tiene tres observaciones fundamentales:
> 1. Siempre da por resultado un **número**, no una matriz.
> 2. Sólo puede realizarse entre vectores que tengan la **misma cantidad de elementos**.
> 3. Siempre se realiza entre un **vector fila y otro columna, nunca al revés**."

---

## 6.8 Multiplicación de matrices (Producto entre matrices) y Matrices Conformables

> 📖 **Textual del material:** "Ahora sí, entonces vamos a definir el producto entre matrices como la matriz que se obtiene al realizar todos los productos escalares posibles entre las filas de la primera matriz y las columnas de la segunda." (Pág. 7)
>
> 📖 **Textual del material:** "Para realizar A . B debemos multiplicar cada una de las filas de A por cada una de las columnas de B. Tendremos un total de 8 productos escalares, que dispondremos en una matriz según el número de fila y de columna que hallamos multiplicado" (Pág. 8, en el ejemplo de una matriz A de 2 × 3 por una matriz B de 3 × 4)
>
> 📖 **Textual del material:** "Conclusión
> "Para que dos matrices puedan multiplicarse es necesario que el número de columnas de la primera sea igual al número de filas de la segunda. A matrices con esta característica se las llama CONFORMABLES. El resultado es la nueva matriz de orden igual al número de filas de la primera por el número de columnas de la segunda y cuyo elemento "ij" ésimo (esto expresa cualquier elemento de la matriz), es el producto escalar del vector fila i de primera matriz por el vector columna j de la segunda matriz"." (Pág. 9)
>
> 📖 **Textual del material (Cuadro "Resumiendo", Pág. 9):**
> "Resumiendo:
> A_(mxn) . B_(nxp) = C_(mxp)
> - A y B son conformables, pues son iguales la cantidad de columnas de A con la cantidad de filas de B
> - m x p será Orden de la matriz resultante
> Solo se podrán multiplicar al ser el número de columnas (n) de la primer matriz igual al número de filas de la segunda. La matriz resultante será de orden mxp."

**🗣️ En palabras simples:**
Para poder multiplicar una matriz `A` por una matriz `B` (`A · B`), mirás sus órdenes: `A` es de `m × n` y `B` es de `n × p`.
1. **¿Se pueden multiplicar?** Sí, únicamente si los dos números "de adentro" coinciden: la cantidad de **columnas de la primera** (`n`) tiene que ser igual a la cantidad de **filas de la segunda** (`n`). Cuando pasa esto, se dice que `A` y `B` son **conformables**.
2. **¿De qué tamaño queda el resultado?** El orden de la matriz resultado `C` lo dan los dos números "de afuera": **filas de la primera por columnas de la segunda** (`m × p`).
3. **¿Cómo se calcula cada casillero de `C`?** Para rellenar el casillero de la fila `i` y columna `j` de `C` (el elemento `c_ij`), hacés el **producto escalar** entre toda la **fila `i` de la primera matriz** y toda la **columna `j` de la segunda matriz**.

**🔍 Desglose de la jerga:**
- **Matrices CONFORMABLES:** Es el término técnico exacto que usa la cátedra para dos matrices que cumplen la condición de posibilidad del producto: **el número de columnas de la primera es igual al número de filas de la segunda**.
- **`A_(m×n) · B_(n×p) = C_(m×p)`:**
  - Los índices internos (`n` y `n`) deben ser iguales e indican que las matrices son **conformables**.
  - Los índices externos (`m` y `p`) determinan el **orden `m × p`** de la matriz resultante `C`.
- **Elemento "ij" ésimo (`c_ij`):** Representa cualquier elemento de la matriz producto ubicado en la fila `i` y la columna `j`. Se calcula como el producto escalar del **vector fila `i` de la primera matriz** por el **vector columna `j` de la segunda matriz**:
  `c_ij = a_i1 · b_1j + a_i2 · b_2j + ... + a_in · b_nj`.
- **Cantidad total de productos escalares:** Si `A` es de `m × n` y `B` es de `n × p`, como la matriz resultado `C` es de orden `m × p`, tiene `m · p` elementos y por lo tanto hay que realizar un total de `m · p` productos escalares.

**💡 Ejemplo:**
*(Del material, Desempeño 27, Págs. 8 y 15):*
Dadas `A` de orden `2 × 3` y `B` de orden `3 × 4`:
```
    [ 1  3  2 ]          [ 5  3  4  2 ]
A = [ 4  2  0 ]    y B = [ 1  0  2  3 ]
                         [ 2  1  1  0 ]
```
- **Conformabilidad:** Como el número de columnas de `A` (`3`) es igual al número de filas de `B` (`3`), `A` y `B` son **conformables**.
- **Orden del resultado:** La matriz `A · B` tendrá orden `2 × 4` (2 filas de `A` por 4 columnas de `B`), por lo que requiere `2 × 4 = 8` productos escalares:
  - Fila 1 por columna 1 → `1·5 + 3·1 + 2·2 = 12` → lugar (1,1)
  - Fila 2 por columna 1 → `4·5 + 2·1 + 0·2 = 22` → lugar (2,1)
  - Fila 1 por columna 2 → `1·3 + 3·0 + 2·1 = 5` → lugar (1,2)
  - Fila 2 por columna 2 → `4·3 + 2·0 + 0·1 = 12` → lugar (2,2)
  - Fila 1 por columna 3 → `1·4 + 3·2 + 2·1 = 12` → lugar (1,3)
  - Fila 2 por columna 3 → `4·4 + 2·2 + 0·1 = 20` → lugar (2,3)
  - Fila 1 por columna 4 → `1·2 + 3·3 + 2·0 = 11` → lugar (1,4)
  - Fila 2 por columna 4 → `4·2 + 2·3 + 0·0 = 14` → lugar (2,4)
- **Matriz resultante (2 × 4):**
```
        [ 12   5  12  11 ]
A . B = [ 22  12  20  14 ]
```

**🔗 Conexiones:**
- Se apoya en el **producto escalar** (6.7).
- Explica inmediatamente por qué el producto de matrices **no es conmutativo** (6.10): en el Desempeño 29 (Pág. 8), si `A` es de `2 × 2` y `B` es de `2 × 3`, el producto `A × B` se puede hacer (porque `2 = 2`, dando una matriz de `2 × 3`), pero al invertir el orden, `B_(2×3) × A_(2×2)` **no se puede realizar** porque el número de columnas de `B` (`3`) es distinto del número de filas de `A` (`2`).

**⚠️ Precisiones / errores comunes:**
- **La palabra clave para el oral es "CONFORMABLES":** El profesor va a esperar que digas exactamente esa palabra tanto si te pregunta *"¿Cuándo se pueden multiplicar dos matrices?"* como si te pregunta *"¿Qué significa que dos matrices sean conformables?"*.
- La conformabilidad **depende del orden en que se multipliquen**: que `A` y `B` sean conformables para hacer `A · B` no implica que lo sean para hacer `B · A`.
- Nunca multipliques matrices elemento a elemento (`a_ij · b_ij`): ¡eso NO es la multiplicación de matrices! Siempre es **fila `i` de la primera por columna `j` de la segunda**.

**🎤 Cómo decirlo en el oral:**
> "Definimos el **producto entre matrices** como la matriz que se obtiene al realizar todos los productos escalares posibles entre las filas de la primera matriz y las columnas de la segunda.
> Para que dos matrices puedan multiplicarse es necesario que el **número de columnas de la primera sea igual al número de filas de la segunda**. A las matrices con esta característica se las llama **conformables**.
> Si `A` es de orden `m × n` y `B` es de orden `n × p`, el resultado es una nueva matriz `C` de orden `m × p` (número de filas de la primera por número de columnas de la segunda), cuyo elemento `'ij' ésimo` es el producto escalar del vector fila `i` de la primera matriz por el vector columna `j` de la segunda matriz."

---

## 6.9 Propiedades asociativa y distributiva de la multiplicación de matrices

> 📖 **Textual del material:** "Vamos a ver algunas propiedades del producto matricial muy importantes, pues son atípicas, o sea no son comunes, a las que ya conocemos en las operaciones de números reales.
>
> Propiedades de la multiplicación de matrices
> 1| Propiedad asociativa: (A_(nxp) . B_(pxm)) . C_(mxk) = A_(nxp) . (B_(pxm) . C_(mxk))
> 3| Propiedad distributiva del producto respecto a la suma (a derecha): A_(nxm) . (B_(mxp) + C_(mxp)) = A_(nxm) . B_(mxp) + A_(nxm) . C_(mxp)" (Pág. 10)

**🗣️ En palabras simples:**
Aunque la multiplicación de matrices tiene comportamientos muy raros comparada con los números reales (como veremos en 6.10 y 6.11), hay dos propiedades clásicas que **sí se cumplen** siempre que los tamaños (órdenes) permitan hacer las cuentas:
1. **Asociativa:** Si tenés tres matrices en fila para multiplicar (`A · B · C`), podés multiplicar primero `A · B` y al resultado multiplicarlo por `C`, o multiplicar primero `B · C` y luego hacer `A` por ese resultado; da exactamente la misma matriz (de orden `n × k`).
2. **Distributiva respecto a la suma:** Si multiplicás una matriz `A` por una suma de matrices `(B + C)`, podés distribuir `A` haciendo `A · B + A · C`, cuidando de mantener a `A` del mismo lado (a la izquierda de ambas).

**🔍 Desglose de la jerga:**
- **"son atípicas, o sea no son comunes, a las que ya conocemos en las operaciones de números reales":** Advierte que en el álgebra de matrices no podemos dar por sentadas las reglas de los números reales (en particular, fallan la conmutativa, la cancelativa y la regla de que un producto nulo exige algún factor nulo).
- **Condición para aplicar la Propiedad Asociativa (`(A_(n×p) · B_(p×m)) · C_(m×k) = A_(n×p) · (B_(p×m) · C_(m×k))`):**
  *(Pregunta d de la Situación 7, Pág. 10: "¿Cuándo se podrá aplicar la propiedad asociativa? ¿Qué significa esta propiedad?")*
  Se podrá aplicar cuando las matrices consecutivas sean **conformables**: el número de columnas de `A` (`p`) debe igualar al número de filas de `B` (`p`), y el número de columnas de `B` (`m`) debe igualar al número de filas de `C` (`m`). En ambos miembros el resultado final es de orden `n × k`, y significa que al multiplicar tres o más matrices (sin cambiar su posición relativa), la forma de agrupar los factores no altera el producto.
- **Propiedad distributiva del producto respecto a la suma:**
  `A_(n×m) · (B_(m×p) + C_(m×p)) = A_(n×m) · B_(m×p) + A_(n×m) · C_(m×p)`.
  Notá cómo los subíndices de orden muestran que `B` y `C` deben tener el **mismo orden** (`m × p`) para poder sumarse, y a la vez `A` (`n × m`) debe ser **conformable** con ellas (sus `m` columnas coinciden con las `m` filas de `B` y `C`).
  *(Nota terminológica: en la tabla de Pág. 10 el apunte la llama "distributiva del producto respecto a la suma (a derecha)" porque la suma `(B + C)` está a la derecha de `A` y se distribuye hacia la derecha; en la Pág. 11 también la aplica sobre una resta: `A · B − A · C = A · (B − C)`. Asimismo, vale cuando la suma está a la izquierda: `(B + C) · A = B · A + C · A`, respetando siempre de qué lado multiplica cada matriz).*

**🤔 Intuición:**
Como cada elemento del producto matricial es una suma de productos de números reales (`∑ a_ir · b_rj`), y en los números reales el producto es asociativo y distributivo respecto de la suma, al desarrollar todas las sumatorias de `(A · B) · C` y de `A · (B · C)` aparecen exactamente los mismos términos `a_ir · b_rs · c_sj` sumados.

**💡 Ejemplo:**
Si `A` es de `3 × 2`, `B` es de `2 × 3` y `C` es de `3 × 2` *(órdenes tomados del Desempeño 30, Pág. 10)*:
- `A · B` es de `3 × 3`, y `(A · B) · C` es de `(3 × 3) · (3 × 2) = 3 × 2`.
- `B · C` es de `2 × 2`, y `A · (B · C)` es de `(3 × 2) · (2 × 2) = 3 × 2`.
Ambos caminos producen exactamente la misma matriz de `3 × 2`.

**🔗 Conexiones:**
- La propiedad distributiva `A · B − A · C = A · (B − C)` es el paso clave que usa el material en la Pág. 11 para analizar por qué **no** se cumple la propiedad cancelativa (6.11).
- La propiedad asociativa es fundamental para trabajar con la **matriz inversa** (6.13): por ejemplo, si `A` tiene inversa `A⁻¹`, entonces `A⁻¹ · (A · B) = (A⁻¹ · A) · B = I · B = B`.

**⚠️ Precisiones / errores comunes:**
- Al distribuir `A · (B + C)`, **jamás cambies el orden de los factores**: es `A · B + A · C`, **no** `B · A + C · A` (porque el producto de matrices no es conmutativo).
- Al aplicar la asociativa `(A · B) · C = A · (B · C)`, se cambian los **paréntesis** (qué par se multiplica primero), pero **nunca se cambia el orden de aparición** `A, B, C` de izquierda a derecha.

**🎤 Cómo decirlo en el oral:**
> "En la multiplicación de matrices se cumplen:
> - La **propiedad asociativa:** `(A_(n×p) · B_(p×m)) · C_(m×k) = A_(n×p) · (B_(p×m) · C_(m×k))`, que se puede aplicar siempre que los factores consecutivos sean conformables, y significa que al multiplicar tres matrices, agrupar las dos primeras o las dos últimas da el mismo resultado (sin alterar el orden en que están ubicadas).
> - La **propiedad distributiva del producto respecto a la suma (a derecha):** `A_(n×m) · (B_(m×p) + C_(m×p)) = A_(n×m) · B_(m×p) + A_(n×m) · C_(m×p)`, siempre que `B` y `C` sean del mismo orden y `A` sea conformable con ellas."

---

## 6.10 No conmutatividad del producto matricial y Matrices Permutables

> 📖 **Textual del material:**
> "2| Propiedad conmutativa? A_(nxp) . B_(pxm) =??? B_(pxm) . A_(nxp)
> Si el producto A.B existe, el producto B.A no necesariamente existe. Además, si existiera no necesariamente sería igual a A.B" (Pág. 10)
>
> 📖 **Textual del material:** "Para tener en cuenta…
> • Si dos matrices A y B tienen la particularidad de que A . B = B . A se dice que son permutables." (Pág. 10)

**🗣️ En palabras simples:**
En la multiplicación de matrices **NO se cumple la propiedad conmutativa**: el orden de los factores **sí** altera el producto. Cuando cambiás `A · B` por `B · A`, pueden pasar tres cosas malas:
1. Que `B · A` ni siquiera exista (no se pueda calcular porque dejan de ser conformables).
2. Que `B · A` sí exista, pero tenga un **orden (tamaño) distinto** al de `A · B`.
3. Que `A · B` y `B · A` existan y tengan el mismo orden (cuando ambas son cuadradas del mismo orden `n × n`), pero den matrices con **números distintos**.
Ahora bien, si en algún caso particular dos matrices `A` y `B` cumplen que `A · B = B · A`, a ese par especial de matrices se las llama **permutables** (o conmutables).

**🔍 Desglose de la jerga:**
- **"Si el producto A.B existe, el producto B.A no necesariamente existe":**
  Si `A` es de `n × p` y `B` es de `p × m`, entonces `A · B` existe (porque `p = p`), pero para hacer `B_(p×m) · A_(n×p)` haría falta que `m = n`. Si `m ≠ n`, el producto `B · A` **no existe** (como ocurre en el Desempeño 29 de la Pág. 8 con `A_(2×2)` y `B_(2×3)`).
- **"Además, si existiera no necesariamente sería igual a A.B":**
  Esto ocurre por dos motivos posibles:
  1. **Por distinto orden:** Si `A` es de `n × p` y `B` es de `p × n` (con `n ≠ p`), entonces `A · B` existe y es de orden `n × n`, y `B · A` también existe pero es de orden `p × p`. Como tienen distinto orden, no pueden ser iguales. *(Es exactamente lo que sucede en el Desempeño 30 a y b de la Pág. 10, que pide analizar la Situación 7 e: `A` es de `3 × 1` y `B` es de `2 × 3`, o con `B_(2×3)` y `C_(3×2)` donde `B · C` da de `2 × 2` y `C · B` da de `3 × 3`, o en el Desempeño 36 a y c con `M_(1×4)` y `P_(4×1)` donde `M · P` es `1 × 1` y `P · M` es `4 × 4`)*.
  2. **Por distintos elementos (aun siendo cuadradas del mismo orden):** Incluso si `A` y `B` son ambas cuadradas de `n × n` (por lo que `A · B` y `B · A` existen y son ambas de `n × n`), los productos escalares fila por columna mezclan números distintos y en general dan resultados diferentes (`A · B ≠ B · A`).
- **Matrices PERMUTABLES:** Se dice que dos matrices `A` y `B` son **permutables** si tienen la particularidad de que `A · B = B . A`. *(Observación: para que `A · B` y `B · A` puedan ser iguales, como dos matrices iguales deben tener el mismo orden, `A` y `B` tienen que ser necesariamente **cuadradas y del mismo orden** `n × n`).*

**💡 Ejemplo:**
1. **Caso general donde existen del mismo orden pero `A · B ≠ B · A`** *(del Desempeño 35, Págs. 12 y 15)*:
   Para `A = [ 2  11 ; 0  2 ]` y `B = [ 1  3 ; 1  2 ]` (ambas de `2 × 2`):
   - `A · B = [ 2·1+11·1   2·3+11·2 ; 0·1+2·1   0·3+2·2 ] = [ 13  28 ; 2  4 ]`
   - `B · A = [ 1·2+3·0   1·11+3·2 ; 1·2+2·0   1·11+2·2 ] = [ 2  17 ; 2  15 ]`
   Vemos que `A · B ≠ B · A`.
2. **Caso particular de matrices permutables** *(del material, Págs. 10 y 11)*:
   - Cualquier matriz cuadrada `A` y la matriz identidad `I` del mismo orden son permutables, pues `I · A = A · I = A`.
   - Cualquier matriz cuadrada inversible `A` y su matriz inversa `A⁻¹` son permutables, pues `A · A⁻¹ = A⁻¹ · A = I`.

**🔗 Conexiones:**
- Compará siempre dos términos clave de esta clase que los alumnos suelen mezclar en el oral:
  - **Conformables:** Se pueden multiplicar en el orden dado (`A_(m×n)` y `B_(n×p)` tienen columnas de `A` = filas de `B`).
  - **Permutables:** Conmutan en el producto (`A · B = B · A`).

**⚠️ Precisiones / errores comunes:**
- **Error clásico en el oral:** Cuando el profesor pregunta *"¿Por qué el producto de matrices no es conmutativo?"*, no te quedes sólo con *"porque da distinto"*. Mencioná las **dos razones** textuales de la tabla de la Pág. 10:
  1. Si el producto `A · B` existe, el producto `B · A` **no necesariamente existe**.
  2. Además, **si existiera, no necesariamente sería igual a `A · B`** (ya sea porque resultan de distinto orden o porque, aun siendo del mismo orden, sus elementos difieren).

**🎤 Cómo decirlo en el oral:**
> "El producto de matrices **no cumple la propiedad conmutativa**: si el producto `A · B` existe, el producto `B · A` no necesariamente existe; y además, si existiera, no necesariamente sería igual a `A · B`. En el caso particular en que dos matrices `A` y `B` tienen la particularidad de que `A · B = B · A`, se dice que son **permutables**."

---

## 6.11 No cumplimiento de la Propiedad Cancelativa y producto nulo de matrices no nulas

> 📖 **Textual del material:**
> "4| Propiedad cancelativa? A . B = A . C , no podemos cancelar A y asegurar que B = C" (Pág. 10)
>
> 📖 **Textual del material:** "• Una aclaración con la Propiedad cancelativa.
> Esta propiedad no se puede aplicar en el álgebra de matrices. El no - cumplimiento de esta propiedad implica que sí: A . B = A . C NO podemos cancelar A y asegurar que B = C" (Pág. 10)
>
> 📖 **Textual del material (Desarrollo y contraejemplo, Pág. 11):**
> "Veamos por qué no. AB = AC
> Supongamos que restando A . C   A.B – A.C = A.C – A.C   a ambos miembros resulta por   A.B – A.C = 0   propiedad distributiva, esto es   A ( B – C) = 0
> Aquí, usando el álgebra “clásica” diríamos que: “si un producto es cero entonces algunos de los factores también lo es” (es decir A = 0 ó b – C = 0)
> Pero con matrices esto no ocurre. o sea que podemos multiplicar dos matrices no nulas y obtener como resultado la matriz nula.
> Esto es extraño a lo que estamos habituados, pues con los números ocurre que si un producto da cero es porque por lo menos uno de los factores es cero. Veamos con el siguiente ejemplo que con las matrices no es así:
> Dos matrices que no son nulas y su producto da la matriz nula.
> A = [ -1  3 ; 0  0 ] ∙ [ 0  6 ; 0  2 ] = [ 0  0 ; 0  0 ]" (Pág. 11)

**🗣️ En palabras simples:**
Con números comunes, si sabés que `a · b = a · c` (con `a ≠ 0`), podés "tachar" (cancelar) la `a` de los dos lados y concluir que `b = c`, porque si pasás restando te queda `a · (b − c) = 0`, y para que una multiplicación de números dé cero, sí o sí alguno de los dos tiene que ser cero.
¡Con matrices eso es **falso**! Se pueden multiplicar dos matrices que **no** son la matriz nula (tienen números distintos de cero) y que sin embargo su producto dé la **matriz nula** (`[ 0  0 ; 0  0 ]`). Por culpa de eso, que `A · (B − C) = 0` no te garantiza que `B − C` sea `0` (o sea, que `B = C`), y por lo tanto **no se puede aplicar la propiedad cancelativa**: de `A · B = A · C` **no** podemos cancelar `A` ni asegurar que `B = C`.

**🔍 Desglose de la jerga:**
- **Propiedad cancelativa:** En álgebra, cancelar un factor `A` consiste en deducir `B = C` a partir de la igualdad `A · B = A · C` (con `A ≠ 0`). En el álgebra de matrices **no se cumple**.
- **`A · B − A · C = 0 ⇒ A · (B − C) = 0`:** Al restar `A · C` en ambos miembros de `A · B = A · C` se obtiene la matriz nula `0` en el miembro derecho, y sacando factor común `A` a izquierda mediante la propiedad distributiva queda el producto de la matriz `A` por la matriz `(B − C)` igualado a la matriz nula `0`.
- **Diferencia con el "álgebra clásica" (de números reales):**
  - En números reales: `x · y = 0 ⇒ x = 0 ∨ y = 0` (*"si un producto es cero entonces alguno de los factores también lo es"*).
  - En matrices: **podemos multiplicar dos matrices no nulas y obtener como resultado la matriz nula** (existen matrices `M ≠ 0` y `N ≠ 0` tales que `M · N = 0`).

**🧩 Idea de la demostración / justificación (paso a paso según Pág. 11):**
1. Partimos de la igualdad matricial `A · B = A · C` (donde `A` no es la matriz nula).
2. Restamos `A · C` a ambos miembros de la igualdad:
   `A · B − A · C = A · C − A · C`
   `A · B − A · C = 0` (siendo `0` la matriz nula).
3. Aplicamos la **propiedad distributiva** del producto respecto a la suma/resta:
   `A · (B − C) = 0`.
4. En el álgebra clásica de números diríamos que si un producto es cero entonces alguno de los factores es cero (`A = 0` ó `B − C = 0`, de donde saldría `B = C`).
5. **Pero con matrices esto no ocurre:** es posible que `A ≠ 0` y que `B − C ≠ 0` (es decir, `B ≠ C`) y aun así su producto `A · (B − C)` dé como resultado la matriz nula `0`.
6. Por lo tanto, de `A · B = A · C` **no podemos cancelar `A` y asegurar que `B = C`**.

**🤔 Intuición:**
¿Por qué dos matrices sin ser nulas pueden dar cero al multiplicarse? Porque cada elemento del producto es un **producto escalar** (una suma de productos). Para que un producto escalar dé `0`, no hace falta que todos los números sean `0`: alcanza con que las multiplicaciones positivas y negativas se compensen entre sí al sumarse (por ejemplo, `(−1)·0 + 3·0 = 0`, o `2·2 + 4·(−1) = 4 − 4 = 0`).

**💡 Ejemplo:**
1. **Contraejemplo del material de dos matrices no nulas cuyo producto es la matriz nula (Pág. 11):**
   ```
   [ -1   3 ]   [ 0   6 ]   [ (-1)·0 + 3·0   (-1)·6 + 3·2 ]   [ 0   0 ]
   [  0   0 ] ∙ [ 0   2 ] = [   0·0 + 0·0      0·6 + 0·2  ] = [ 0   0 ]
   ```
   Ninguna de las dos matrices factores es la matriz nula, pero en el lugar `(1,2)` se compensa `−6 + 6 = 0` y todos los elementos del producto dan `0`.

2. **Segundo ejemplo del material (Desempeño 37, Pág. 13):**
   Compara los dos productos siguientes:
   ```
   a- [ 2  4 ] ∙ [  2  -4 ] = [ 0  0 ]        b- [ 0  0 ] ∙ [  2  -4 ] = [ 0  0 ]
      [ 4  8 ]   [ -1   2 ]   [ 0  0 ]           [ 0  0 ]   [ -1   2 ]   [ 0  0 ]
   ```
   Observá cómo en `a-` y `b-` ambos productos dan `[ 0  0 ; 0  0 ]`: si igualamos `[ 2  4 ; 4  8 ] · [ 2  -4 ; -1  2 ] = [ 0  0 ; 0  0 ] · [ 2  -4 ; -1  2 ]`, vemos que el factor derecho `[ 2  -4 ; -1  2 ]` está en ambos miembros, pero si lo "canceláramos" llegaríamos al absurdo de que `[ 2  4 ; 4  8 ] = [ 0  0 ; 0  0 ]`.

**🔗 Conexiones:**
- Conecta con **6.13 (Matriz Inversa)**: *(Contexto adicional útil)* La única situación en la que sí podríamos "despejar" `B = C` a partir de `A · B = A · C` es cuando `A` es cuadrada y **admite matriz inversa `A⁻¹`**, no "tachando" sino multiplicando ambos miembros a izquierda por `A⁻¹`: `A⁻¹ · (A · B) = A⁻¹ · (A · C) ⇒ I · B = I · C ⇒ B = C`. Justamente en los contraejemplos de las páginas 11 y 13, las matrices no tienen inversa.

**⚠️ Precisiones / errores comunes:**
- Este es **uno de los temas favoritos de examen oral** (está en la Situación 7, en el desarrollo central de la Pág. 11, en el Desempeño 37 y en la pregunta `h-` del Desempeño 40). Aprendete el desarrollo de `A · B = A · C ⇒ A · B − A · C = 0 ⇒ A · (B − C) = 0` y tené a mano un ejemplo numérico chiquito de `2 × 2` como `[ -1  3 ; 0  0 ] · [ 0  6 ; 0  2 ] = [ 0  0 ; 0  0 ]`.

**🎤 Cómo decirlo en el oral:**
> "En el álgebra de matrices **no se puede aplicar la propiedad cancelativa**: si `A · B = A · C`, **no** podemos cancelar `A` y asegurar que `B = C`.
> ¿Por qué? Si en `A · B = A · C` restamos `A · C` a ambos miembros, queda `A · B − A · C = 0`, y aplicando la propiedad distributiva obtenemos `A · (B − C) = 0`. En el álgebra clásica de números diríamos que si un producto es cero, alguno de los factores es cero (`A = 0` o `B − C = 0`). Pero con matrices esto no ocurre: **podemos multiplicar dos matrices no nulas y obtener como resultado la matriz nula** (por ejemplo, `[ -1  3 ; 0  0 ] · [ 0  6 ; 0  2 ] = [ 0  0 ; 0  0 ]`). Por eso, que `A · (B − C) = 0` no implica que `B − C = 0`."

---

## 6.12 Elemento neutro multiplicativo (Matriz Identidad)

> 📖 **Textual del material:**
> "5| Elemento neutro multiplicativo: I . A = A . I = A" (Pág. 10)
>
> 📖 **Textual del material:** "La matriz identidad es el elemento neutro en la multiplicación de matrices.
> I . A = A . I = A" (Pág. 11)

**🗣️ En palabras simples:**
Así como el número `1` es el neutro cuando multiplicamos números (porque `1 · x = x · 1 = x`), en la multiplicación de matrices el elemento neutro es la **matriz identidad `I`** (la matriz cuadrada que tiene todos `1` en su diagonal principal y `0` en todos los demás lugares). Multiplicar cualquier matriz `A` por la identidad `I` (tanto a izquierda como a derecha, con el orden adecuado) devuelve exactamente la misma matriz `A`.

**🔍 Desglose de la jerga:**
- **Elemento neutro multiplicativo:** Aplicando la definición general de elemento neutro dada en la Pág. 15 (*"un elemento que al operar con él no cambia al otro"*), el neutro para la operación producto de matrices es la **matriz identidad `I`**, porque al multiplicarla con `A` no cambia a `A`.
- **`I · A = A · I = A`:**
  - Si `A` es una matriz cuadrada de orden `n × n`, `I` es la matriz identidad del mismo orden `n × n`, y se cumple `I · A = A · I = A` (de hecho, en el Desempeño 38 a de la Pág. 13 se pide elegir una matriz de orden no menor a 3 y verificar esta propiedad).
  - *(Precisión adicional de órdenes)*: Si `A` fuera rectangular de orden `m × n`, a izquierda la identidad debe ser `I_m` (de orden `m × m`) y a derecha `I_n` (de orden `n × n`) para que sean conformables: `I_m · A_(m×n) = A_(m×n) · I_n = A_(m×n)`.

**🤔 Intuición:**
Cuando hacés el producto escalar de la fila `i` de `I` (que tiene un `1` en el lugar `i` y `0` en todos los demás lugares) por la columna `j` de `A`, todos los elementos de la columna `j` de `A` quedan multiplicados por `0` excepto el que está en la fila `i`, que queda multiplicado por `1`. Por eso en el lugar `(i, j)` del resultado sobrevive intacto el elemento `a_ij`.

**💡 Ejemplo:**
*(Verificación con una matriz de orden 3 × 3, como pide el Desempeño 38 a, Pág. 13):*
```
        [ 1  0  0 ]   [  1  -2   1 ]   [  1  -2   1 ]
I . A = [ 0  1  0 ] ∙ [  2   0   1 ] = [  2   0   1 ] = A
        [ 0  0  1 ]   [ -2   5  -2 ]   [ -2   5  -2 ]
```

**🔗 Conexiones:**
- Retoma la definición de **matriz identidad o unidad** de la Clase 5 (caso particular de matriz diagonal y escalar cuya diagonal principal tiene todos `1`).
- Es indispensable para definir el **elemento inverso multiplicativo** (6.13), ya que el inverso de un elemento se define como aquel que al operar con él da el **neutro de la operación** (en este caso, `I`).

**⚠️ Precisiones / errores comunes:**
- **No confundir los tres neutros de la clase:**
  - ¿Elemento neutro de la **suma** de matrices? → **Matriz nula `0`** (`A + 0 = A`).
  - ¿Elemento neutro del **producto de una matriz por un número**? → **El número `1`** (`1 · A = A`).
  - ¿Elemento neutro del **producto de matrices**? → **Matriz identidad `I`** (`I · A = A · I = A`).

**🎤 Cómo decirlo en el oral:**
> "El **elemento neutro multiplicativo** en el producto de matrices es la **matriz identidad (`I`)**, ya que al multiplicar una matriz `A` por la identidad (a izquierda o a derecha) no cambia a la matriz: simbólicamente, `I · A = A · I = A`."

---

## 6.13 Elemento inverso multiplicativo (Matriz Inversa)

> 📖 **Textual del material:**
> "6| Elemento inverso multiplicativo: A . A⁻¹ = A⁻¹. A = I" (Pág. 10)
>
> 📖 **Textual del material:** "El Elemento inverso multiplicativo sólo existe para matrices cuadradas, y no en todos los casos. Más adelante se verá en que caso existe y cómo se calcula. Cuando existe la inversa de una matriz A se indica como A-1 y se verifica que el producto entre ellas da la Identidad.
> Simbólicamente: A . A-1 = A-1 . A = I
> Ejemplo:
> Para A = [ 3  2 ; 4  3 ] la inversa es A⁻¹ = [ 3  -2 ; -4  3 ]
> pues A . A⁻¹ = [ 3  2 ; 4  3 ] ∙ [ 3  -2 ; -4  3 ] = [ 1  0 ; 0  1 ]" (Pág. 11)

**🗣️ En palabras simples:**
En los números reales, el inverso multiplicativo de `5` es `5⁻¹ = 1/5` porque `5 · (1/5) = 1` (da el neutro del producto). En las matrices, el **inverso multiplicativo** de una matriz `A` es otra matriz, que se escribe `A⁻¹` (se lee *"A a la menos uno"* o *"inversa de A"*), tal que al multiplicar `A` por `A⁻¹` (en cualquier orden) el resultado da el neutro del producto matricial, que es la **matriz identidad `I`**.
¡Pero atención con dos restricciones importantísimas!
1. **Sólo existe para matrices cuadradas** (si una matriz no es cuadrada, seguro no tiene inversa).
2. **Y no en todos los casos** (incluso siendo cuadrada, hay matrices cuadradas que no tienen inversa).

**🔍 Desglose de la jerga:**
- **Elemento inverso multiplicativo / Matriz inversa (`A⁻¹`):** Aplicando la definición general de elemento inverso de la Pág. 15 (*"un elemento que al operar con él nos da el neutro de la operación"*), para el producto de matrices la inversa de `A` es la matriz `A⁻¹` que al multiplicarse con `A` (a derecha y a izquierda) da el neutro multiplicativo `I`:
  `A · A⁻¹ = A⁻¹ · A = I`.
- **"sólo existe para matrices cuadradas":** Para que tanto `A · A⁻¹` como `A⁻¹ · A` existan y sean ambos iguales a la misma matriz identidad cuadrada `I`, `A` y `A⁻¹` deben ser necesariamente cuadradas del mismo orden `n × n`.
- **"y no en todos los casos":** Ser cuadrada es una condición **necesaria pero no suficiente**. Hay matrices cuadradas que no poseen inversa *(en las clases siguientes de la unidad, al estudiar determinantes e inversa, se verá bajo qué condición exacta existe —cuando su determinante es distinto de cero— y cómo se calcula)*.
- **Cómo determinar si dos matrices dadas son inversas entre sí (Procedimiento del Desempeño 38 b, Págs. 13 y 16):**
  Para comprobar si dos matrices cuadradas del mismo orden son inversas entre sí, se realiza el **producto entre ellas** y se verifica si da por resultado la **matriz identidad `I`**.

**💡 Ejemplo:**
1. **Ejemplo de orden 2 × 2 del material (Pág. 11):**
   Para `A = [ 3  2 ; 4  3 ]`, su inversa es `A⁻¹ = [ 3  -2 ; -4  3 ]`, pues:
   ```
              [ 3   2 ]   [  3  -2 ]   [ 3·3 + 2·(-4)   3·(-2) + 2·3 ]   [ 9 - 8   -6 + 6 ]   [ 1  0 ]
   A . A⁻¹ = [ 4   3 ] ∙ [ -4   3 ] = [ 4·3 + 3·(-4)   4·(-2) + 3·3 ] = [ 12-12   -8 + 9 ] = [ 0  1 ] = I
   ```
2. **Ejemplo de orden 3 × 3 del material (Desempeño 38 b, Pág. 13 y respuesta en Pág. 16 como Desempeño n° 35 b):**
   Dadas las matrices:
   ```
       [  1  -2   1 ]        [ -5   1   2 ]        [  1   -2   1 ]
   A = [  2   0   1 ]    C = [  2   0   1 ]    D = [ 10  -20   9 ]
       [ -2   5  -2 ]        [ 10  -1   0 ]        [ -2    5  -2 ]
   ```
   Al multiplicar `C · D` se verifica que `C · D = [ 1  0  0 ; 0  1  0 ; 0  0  1 ] = I`, por lo que **`C` y `D` son inversas entre sí**.

**🔗 Conexiones:**
- Se apoya en el concepto de **elemento neutro multiplicativo (`I`)** (6.12) y es un caso particular de **matrices permutables** (6.10), ya que `A` y `A⁻¹` conmutan (`A · A⁻¹ = A⁻¹ · A = I`).
- Deja planteado el puente directo hacia las **Clases 7 y 8** de la Unidad 2 (*"Más adelante se verá en qué caso existe y cómo se calcula"*): el cálculo de determinantes y de la matriz inversa.

**⚠️ Precisiones / errores comunes:**
- **No confundir `A⁻¹` con `1/A` ni elevar cada elemento a la `−1`:** En matrices **no existe la división** entre matrices, y los elementos de `A⁻¹` **no** son los recíprocos `1/a_ij` de los elementos de `A` (fijate en el ejemplo de Pág. 11: `A = [ 3  2 ; 4  3 ]` y `A⁻¹ = [ 3  -2 ; -4  3 ]`).
- **Dos aclaraciones que nunca pueden faltar al enunciarlo en el oral:**
  1. Que **sólo existe para matrices cuadradas**.
  2. Que **no existe en todos los casos** (no toda matriz cuadrada tiene inversa).

**🎤 Cómo decirlo en el oral:**
> "El **elemento inverso multiplicativo** (o **matriz inversa**) **sólo existe para matrices cuadradas, y no en todos los casos**. Cuando existe la inversa de una matriz `A`, se indica como `A⁻¹` y se verifica que el producto entre ellas (a derecha y a izquierda) da por resultado la **matriz identidad**: simbólicamente, `A · A⁻¹ = A⁻¹ · A = I`."

---

### 📊 Tabla comparativa de las operaciones con matrices (Síntesis de la Clase 6)

| Operación | Condición de posibilidad | Orden del resultado | Conmutativa | Asociativa | Elemento Neutro | Elemento Inverso |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Adición (`A + B`)** | Mismo orden (`m × n` y `m × n`) | Mismo orden (`m × n`) | **Sí:** `A + B = B + A` | **Sí:** `(A + B) + C = A + (B + C)` | **Matriz nula `0`** (`A + 0 = A`) | **Matriz opuesta `−A`** (`A + (−A) = 0`, existe siempre) |
| **Sustracción (`A − B`)** | Mismo orden (`m × n` y `m × n`) | Mismo orden (`m × n`) | **No:** `A − B ≠ B − A` (en general) | **No** | No tiene a ambos lados | — |
| **Producto por un número (`k · A`)** | Ninguna (cualquier matriz y cualquier escalar) | Mismo orden (`m × n`) | — (es ley externa) | **Sí** respecto a los números: `(α · β) · A = α · (β · A)` | **El número `1`** (`1 · A = A`) | — |
| **Producto escalar (`A · B` entre vectores)** | Vector fila (`1 × n`) por vector columna (`n × 1`) de igual cantidad de elementos | **No es una matriz: da un número** | **No:** siempre fila por columna, nunca al revés | — | — | — |
| **Multiplicación de matrices (`A · B`)** | **Conformables:** columnas de la 1.ª (`n`) = filas de la 2.ª (`n`), para `A_(m×n) · B_(n×p)` | Filas de la 1.ª por columnas de la 2.ª (`m × p`) | **No** en general (si `A · B = B · A` se llaman **permutables**) | **Sí:** `(A · B) · C = A · (B · C)` (si son conformables) | **Matriz identidad `I`** (`I · A = A · I = A`) | **Matriz inversa `A⁻¹`** (`A · A⁻¹ = A⁻¹ · A = I`, sólo cuadradas y no siempre existe) |

---

## 🧠 Resumen esquemático de la clase

- **Adición de matrices (`A + B`):** Requiere matrices del **mismo orden** (no necesariamente cuadradas); se suman los **elementos correspondientes** (`a_ij + b_ij`) y la matriz resultante conserva el **mismo orden**.
- **Sustracción de matrices (`A − B`):** Procede igual que la adición (requiere el mismo orden y lo conserva), con la única diferencia de que los elementos correspondientes se restan; **no es conmutativa**.
- **Propiedades de la suma de matrices:** Cumple **conmutativa** (`A + B = B + A`), **asociativa** (`(A + B) + C = A + (B + C)`), **existencia de elemento neutro aditivo** (`A + 0 = A`, donde `0` es la **matriz nula**) y **existencia de elemento inverso aditivo** (`A + (−A) = 0`, donde `−A` es la **matriz opuesta**).
- **Elemento neutro (definición general):** Elemento que al operar con otro en una determinada operación no lo cambia.
- **Elemento inverso (definición general):** Elemento que al operar con otro en una determinada operación da por resultado el neutro de la operación.
- **Producto de una matriz por un número (`k · A`):** Da una nueva matriz del **mismo orden** cuyos elementos son los de la matriz original multiplicados por el número (`k · a_ij`); no exige ninguna condición especial.
- **Propiedades del producto por un número:** **Distributiva respecto a la suma de números** (`(α + β) · A = α · A + β · A`), **distributiva respecto a la suma de matrices** (`β · (A + B) = β · A + β · B`), **asociativa respecto a los números** (`(α · β) · A = α · (β · A)`) y **existencia del elemento neutro** (`1 · A = A`).
- **Convención notacional:** Las letras griegas (`α, β, δ`) representan números (escalares) y las letras de nuestro alfabeto representan matrices.
- **Heurística de resolución de problemas:** **1| Entender**, **2| Planificar**, **3| Resolver**, **4| Revisar**.
- **Producto escalar:** Se realiza entre un **vector fila** y un **vector columna** con **igual cantidad de elementos** (se multiplican elementos correspondientes y se suman los productos); siempre da un **número** (no una matriz) y nunca se hace al revés.
- **Multiplicación de matrices (`A_(m×n) · B_(n×p) = C_(m×p)`):** Se obtiene al realizar todos los productos escalares posibles entre las filas de la primera y las columnas de la segunda; el elemento `"ij" ésimo` es el producto escalar del vector fila `i` de la primera por el vector columna `j` de la segunda.
- **Matrices conformables:** Aquellas en las que el **número de columnas de la primera es igual al número de filas de la segunda** (condición necesaria para poder multiplicarlas).
- **Propiedades asociativa y distributiva del producto matricial:** Cumple la **asociativa** `(A_(n×p) · B_(p×m)) · C_(m×k) = A_(n×p) · (B_(p×m) · C_(m×k))` y la **distributiva respecto a la suma** `A_(n×m) · (B_(m×p) + C_(m×p)) = A_(n×m) · B_(m×p) + A_(n×m) · C_(m×p)`.
- **No conmutatividad y matrices permutables:** El producto de matrices **no es conmutativo** (si `A · B` existe, `B · A` no necesariamente existe, y si existe no necesariamente es igual a `A · B`); si `A · B = B · A`, se dice que `A` y `B` son **permutables**.
- **No cumplimiento de la propiedad cancelativa:** Si `A · B = A · C`, **no** podemos cancelar `A` y asegurar que `B = C`, porque `A · (B − C) = 0` no implica que alguno de los factores sea nulo: **se pueden multiplicar dos matrices no nulas y obtener la matriz nula**.
- **Elemento neutro multiplicativo:** Es la **matriz identidad `I`**, que cumple `I · A = A · I = A`.
- **Elemento inverso multiplicativo (Matriz inversa `A⁻¹`):** **Sólo existe para matrices cuadradas y no en todos los casos**; cuando existe, se indica `A⁻¹` y verifica `A · A⁻¹ = A⁻¹ · A = I`.

---

## ❓ Preguntas probables del oral

*(Incluye las 14 preguntas teóricas de autoevaluación del **Desempeño 40** de la Pág. 14 del material más la pregunta clave sobre la propiedad cancelativa).*

1. **¿Qué condición deben cumplir las matrices para poder sumarlas? ¿De qué orden es la matriz resultante?** *(Desempeño 40 a)*
   **Respuesta:** Para sumar dos matrices, éstas deben ser del **mismo orden** (igual número de filas e igual número de columnas). Si esto es así, se suman los elementos correspondientes y la matriz resultante tiene el **mismo orden** que las matrices sumadas.

2. **La suma de matrices, ¿es conmutativa? ¿Qué quiere decir esto? ¿Y la resta?** *(Desempeño 40 b y Desempeño 25 a-b)*
   **Respuesta:** Sí, la suma de matrices cumple la **propiedad conmutativa**: `A + B = B + A`. Quiere decir que si sumamos dos matrices en diferente orden, da el mismo resultado. La sustracción (resta), en cambio, **no** es conmutativa: si restamos dos matrices en diferente orden, da distinto resultado.

3. **¿Es posible sumar matrices que no sean cuadradas?** *(Desempeño 40 c)*
   **Respuesta:** **Sí**, como indica textualmente la definición: *"Para sumar dos matrices, (no necesariamente cuadradas), éstas deben ser del mismo orden"*. Mientras ambas tengan el mismo orden `m × n`, pueden sumarse aunque `m ≠ n`.

4. **Para multiplicar una matriz por un escalar, la matriz ¿debe cumplir alguna condición en especial? ¿Y el escalar?** *(Desempeño 40 d)*
   **Respuesta:** **No**, ni la matriz ni el escalar deben cumplir ninguna condición en especial. La multiplicación de una matriz de cualquier orden por un número da por resultado una nueva matriz del **mismo orden** que la anterior, cuyos elementos son los de la matriz original multiplicados por el número.

5. **¿Qué es el producto escalar entre dos vectores y cuáles son sus tres observaciones fundamentales?**
   **Respuesta:** El **producto escalar** se realiza entre un vector fila y un vector columna con igual cantidad de elementos, multiplicando los elementos correspondientes y sumando esos productos. Sus tres observaciones son: **1)** Siempre da por resultado un **número**, no una matriz; **2)** Sólo puede realizarse entre vectores que tengan la **misma cantidad de elementos**; **3)** Siempre se realiza entre un **vector fila y otro columna, nunca al revés**.

6. **¿Bajo qué condiciones podemos realizar el producto de dos matrices A y B? ¿Cuál es el orden de la matriz producto y cómo se obtiene su elemento "ij"-ésimo?** *(Desempeño 40 e)*
   **Respuesta:** Para que dos matrices puedan multiplicarse es necesario que el **número de columnas de la primera sea igual al número de filas de la segunda**. El resultado es una nueva matriz de orden igual al **número de filas de la primera por el número de columnas de la segunda** (`A_(m×n) · B_(n×p) = C_(m×p)`), y cuyo elemento `"ij" ésimo` es el **producto escalar del vector fila `i` de la primera matriz por el vector columna `j` de la segunda matriz**.

7. **¿Es posible multiplicar dos matrices filas?** *(Desempeño 40 f)*
   **Respuesta:** **No** (para vectores fila de más de un elemento). En primer lugar, el producto escalar siempre se realiza entre un vector fila y otro columna, nunca entre dos vectores fila. En segundo lugar, como matrices de órdenes `1 × n` y `1 × m` (con `n > 1`), no son conformables porque el número de columnas de la primera (`n`) no es igual al número de filas de la segunda (`1`).

8. **¿El producto de matrices es conmutativo? Justifique.** *(Desempeño 40 g)*
   **Respuesta:** **No**, el producto de matrices no cumple la propiedad conmutativa. Si el producto `A · B` existe, el producto `B · A` **no necesariamente existe** (pueden no ser conformables al invertir el orden); y además, **si existiera, no necesariamente sería igual a `A · B`** (puede tener distinto orden o distintos elementos).

9. **Si el producto de dos matrices es la matriz nula, ¿esto significa que alguna de las matrices multiplicadas debe ser la matriz nula?** *(Desempeño 40 h)*
   **Respuesta:** **No**. A diferencia de lo que ocurre en el álgebra clásica de números (donde si un producto es cero, por lo menos uno de los factores es cero), con matrices **podemos multiplicar dos matrices no nulas y obtener como resultado la matriz nula**. Por ejemplo: `[ -1  3 ; 0  0 ] · [ 0  6 ; 0  2 ] = [ 0  0 ; 0  0 ]`.

10. **¿Por qué no se puede aplicar la propiedad cancelativa en el álgebra de matrices?** *(Situación 7 y Pág. 11)*
    **Respuesta:** Porque si `A · B = A · C`, al restar `A · C` a ambos miembros resulta `A · B − A · C = 0` y, por propiedad distributiva, `A · (B − C) = 0`. Como en matrices el producto de dos matrices no nulas puede dar la matriz nula, que `A · (B − C) = 0` con `A ≠ 0` **no garantiza** que `B − C = 0` (es decir, `B = C`). Por lo tanto, de `A · B = A · C` **no podemos cancelar `A` y asegurar que `B = C`**.

11. **¿Cuándo dos matrices son conformables?** *(Desempeño 40 i)*
    **Respuesta:** Dos matrices son **conformables** (para el producto `A · B`) cuando **el número de columnas de la primera es igual al número de filas de la segunda**.

12. **¿Cuándo dos matrices son permutables?** *(Desempeño 40 j)*
    **Respuesta:** Si dos matrices `A` y `B` tienen la particularidad de que **`A · B = B · A`**, se dice que son **permutables**.

13. **¿Qué significa elemento neutro de una operación? ¿Cuál es el elemento neutro de la suma de matrices y cuál es el del producto de matrices?** *(Desempeño 25 d y Desempeño 40 k, l)*
    **Respuesta:** Se llama **elemento neutro** para una determinada operación a un elemento que al operar con él no cambia al otro.
    - En la **suma de matrices**, el elemento neutro aditivo es la **matriz nula (`0`)**, pues `A + 0 = A`.
    - En el **producto de matrices**, el elemento neutro multiplicativo es la **matriz identidad (`I`)**, pues `I · A = A · I = A`.
    *(Y en la multiplicación de una matriz por un número, el elemento neutro es el número `1`, pues `1 · A = A`).*

14. **¿Qué significa elemento inverso de una operación? ¿Cuál es el elemento inverso de la suma de matrices?** *(Desempeño 25 e, f y Desempeño 40 m)*
    **Respuesta:** Se llama **elemento inverso** para una determinada operación a un elemento que al operar con él nos da el neutro de la operación. En la **suma de matrices**, el elemento inverso aditivo de `A` es la **matriz opuesta (`−A`)**, en la cual todos los elementos son los opuestos de los de `A`, y cumple `A + (−A) = 0`.

15. **¿Cuál es el elemento inverso del producto de matrices? ¿Existe siempre?** *(Desempeño 40 n)*
    **Respuesta:** El **elemento inverso multiplicativo** de una matriz `A`, cuando existe, es la **matriz inversa**, que se indica como **`A⁻¹`** y verifica que el producto entre ellas da la Identidad: **`A · A⁻¹ = A⁻¹ · A = I`**. **No existe siempre:** sólo existe para **matrices cuadradas, y no en todos los casos**.

---

## 📚 Glosario de la clase

| Término | Definición breve fiel al material |
| :--- | :--- |
| **Adición de matrices** | Operación entre dos matrices del mismo orden (no necesariamente cuadradas) en la que se suman los elementos correspondientes, resultando una matriz del mismo orden que las matrices sumadas. |
| **Sustracción de matrices** | Operación en la que se procede de igual forma que en la adición (entre matrices del mismo orden), con la única diferencia de que los elementos correspondientes se restan. |
| **Elemento neutro (de una operación)** | Elemento que, para una determinada operación, al operar con él no cambia al otro. |
| **Elemento neutro aditivo (en matrices)** | La **matriz nula (`0`)**, que cumple `A + 0 = A`. |
| **Elemento inverso (de una operación)** | Elemento que, para una determinada operación, al operar con él nos da el neutro de la operación. |
| **Elemento inverso aditivo (en matrices)** | La **matriz opuesta (`−A`)** (aquella cuyos elementos son todos opuestos a los de `A`), que cumple `A + (−A) = 0`. |
| **Multiplicación de una matriz por un número** | Operación que da por resultado una nueva matriz del mismo orden que la anterior, cuyos elementos son los de la matriz original multiplicados por el número (`kA`). |
| **Producto escalar** | Procedimiento que se realiza entre un vector fila y un vector columna con igual cantidad de elementos (nunca al revés), multiplicando los elementos correspondientes y sumando esos productos; siempre da por resultado un número, no una matriz. |
| **Producto entre matrices (Multiplicación de matrices)** | Matriz que se obtiene al realizar todos los productos escalares posibles entre las filas de la primera matriz y las columnas de la segunda; para `A_(m×n) · B_(n×p) = C_(m×p)`, su elemento `"ij" ésimo` es el producto escalar del vector fila `i` de la primera matriz por el vector columna `j` de la segunda. |
| **Matrices conformables** | Matrices que cumplen la condición necesaria para poder multiplicarse: que el número de columnas de la primera sea igual al número de filas de la segunda. |
| **Matrices permutables** | Matrices `A` y `B` que tienen la particularidad de cumplir que `A · B = B · A`. |
| **Propiedad cancelativa (en el producto de matrices)** | Propiedad que **no se puede aplicar** en el álgebra de matrices: si `A · B = A · C`, no podemos cancelar `A` y asegurar que `B = C` (debido a que el producto de dos matrices no nulas puede dar la matriz nula). |
| **Elemento neutro multiplicativo (en matrices)** | La **matriz identidad (`I`)**, que cumple `I · A = A · I = A`. |
| **Elemento inverso multiplicativo (Matriz inversa `A⁻¹`)** | Matriz que sólo existe para matrices cuadradas y no en todos los casos; cuando existe, se indica como `A⁻¹` y verifica que `A · A⁻¹ = A⁻¹ · A = I`. |
