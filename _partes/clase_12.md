# Clase 12 — Sistemas de Ecuaciones: Método Particular de Resolución (Regla de Cramer)

## 🗺️ Mapa de la clase

### Orden de los temas y cómo se conectan
1. **Introducción a los métodos particulares de resolución (Sección 12.1):** Se ubica la clase como el cierre de la Unidad 3 (Sistemas de Ecuaciones). Mientras que en las clases anteriores se estudió el método general (Gauss-Jordan / análisis por rangos, aplicable a cualquier sistema lineal de m ecuaciones con n incógnitas), aquí se presenta un **método particular** que es directo y muy útil, pero válido únicamente para casos muy especiales.
2. **Concepto de Sistema de Ecuaciones Cuadrado (Sección 12.2):** Primera condición estructural necesaria para el método: el sistema debe tener la misma cantidad de ecuaciones que de incógnitas (n × n), lo que permite que su matriz de los coeficientes A sea cuadrada y tenga determinante.
3. **Condiciones de aplicabilidad de la Regla de Cramer (Sección 12.3):** Segunda condición necesaria (y suficiente junto con la primera): el determinante de la matriz de los coeficientes debe ser distinto de cero (`|A| ≠ 0`), es decir, la matriz A debe ser **Regular**.
4. **Definición de la matriz cuadrada A_j (Sección 12.4):** Construcción formal de las matrices auxiliares que se obtienen al reemplazar la columna j de la matriz de los coeficientes A por el vector de los términos independientes B.
5. **Enunciado General y Algoritmo de la Regla de Cramer (Sección 12.5):** Expresión matricial del sistema `A . X = B` y fórmula explícita mediante cocientes de determinantes `x_j = |A_j| / |A|` para hallar cada incógnita.
6. **Unicidad de la solución y clasificación del sistema resuelto por Cramer (Sección 12.6):** Todo sistema al que se le puede aplicar la Regla de Cramer tiene **solución única** y, por lo tanto, es siempre un **Sistema Compatible Determinado (SCD)**.
7. **Caso en que el determinante es nulo (`|A| = 0`): Limitaciones de la Regla de Cramer (Sección 12.7):** Qué ocurre cuando el sistema es cuadrado pero la matriz A no es regular (`|A| = 0`): inaplicabilidad de Cramer, obligación de recurrir al método general y garantía de que el sistema **no es Compatible Determinado** (será Compatible Indeterminado o Incompatible).
8. **Preparación previa del sistema: Sistema completo y ordenado (Sección 12.8):** Requisito operativo indispensable antes de extraer A y B para no alterar los signos ni las columnas de los determinantes.
9. **Aplicación Económica: Modelo de Insumo-Producto (Sección 12.9):** Conceptos teóricos introducidos en el cierre de la clase (Desempeño Integrador 6): **matriz de insumo-producto**, **coeficientes de insumo**, condición de **matriz productiva**, **matriz de producción**, **matriz de demanda externa** y ecuación matricial del modelo `(I - A) . X = D`.
10. **Síntesis e Integración Teórica de la Unidad 3 (Sección 12.10):** Análisis exhaustivo de las preguntas teóricas de síntesis y del Verdadero/Falso integrador oficial de la cátedra que vincula Cramer, rangos, sistemas homogéneos, variables libres y equivalencia de sistemas.

### Prerrequisitos (de clases y unidades anteriores)
- **Unidad 1 (Matrices):** Matriz cuadrada de orden n, matriz identidad I, vector columna, producto de matrices (`A . X`), resta de matrices (`I - A`), matriz regular vs. matriz singular (no regular).
- **Unidad 2 (Determinantes):** Concepto de determinante de una matriz cuadrada (`|A|`), cálculo para orden 2 (`a_11 · a_22 - a_12 · a_21`), **Regla de Sarrus** para orden 3, método de Laplace / cofactores para orden ≥ 4, y propiedades de los determinantes (especialmente qué pasa cuando dos filas o columnas son proporcionales o combinación lineal: el determinante vale 0).
- **Unidad 3 — Clases 9, 10 y 11 (Sistemas de Ecuaciones Lineales):** Expresión matricial `A . X = B`, matriz de los coeficientes A, vector de las incógnitas X, vector de los términos independientes B, matriz ampliada, sistema completo y ordenado, clasificación según sus soluciones (**Compatible Determinado**, **Compatible Indeterminado**, **Incompatible**), sistemas homogéneos, Teorema de Rouché-Frobenius (condición de rangos) y método general de resolución (Gauss-Jordan).

---

## 12.1 Introducción: Método particular de resolución de sistemas de ecuaciones

> 📖 **Textual del material:** "MÉTODO PARTICULAR DE RESOLUCIÓN DE SISTEMAS DE ECUACIONES
> Para ampliar aún más nuestros conocimientos sobre la resolución de los sistemas de ecuaciones, veremos hoy algunos casos particulares, que por supuesto son muy útiles, pero solo para casos muy especiales."

**🗣️ En palabras simples:**
Hasta la Clase 11 aprendiste el "método todoterreno" (el método general por operaciones elementales / Gauss-Jordan), que sirve para resolver cualquier sistema de ecuaciones lineales, tenga la forma que tenga. En esta Clase 12 se estudia un "atajo con determinantes" (la Regla de Cramer): un **método particular** que permite calcular directamente el valor de cada incógnita con una cuenta cerrada, pero que solo funciona bajo condiciones muy estrictas ("casos muy especiales").

**🔍 Desglose de la jerga:**
- **Método particular de resolución:** Procedimiento de resolución que no se aplica a la totalidad de los sistemas de ecuaciones lineales, sino únicamente a aquellos que cumplen ciertas hipótesis restrictivas (a diferencia del *método general de resolución*).
- **Casos muy especiales:** Se refiere específicamente a los sistemas lineales que son simultáneamente **cuadrados** (igual número de ecuaciones que de incógnitas) y cuya matriz de coeficientes es **regular** (`|A| ≠ 0`).

**💡 Ejemplo:**
- Si tenés un sistema de 2 ecuaciones con 3 incógnitas (rectangular), estás obligado a usar el método general.
- Si tenés un sistema de 3 ecuaciones con 3 incógnitas con determinante distinto de cero, estás ante uno de esos "casos muy especiales" y podés elegir resolverlo directamente por el método particular (Regla de Cramer).

**🔗 Conexiones:**
- Conecta directamente con la **Clase 10 y Clase 11** (Método general de resolución de sistemas de ecuaciones): cuando el método particular de la Clase 12 falla o no es aplicable, el propio material indica que se debe volver al método general.

**⚠️ Precisiones / errores comunes:**
- **Error común en el oral:** Decir que la Regla de Cramer sirve para "cualquier sistema de ecuaciones" o que "clasifica cualquier sistema". No: es un **método particular** y solo resuelve sistemas cuadrados con matriz regular (que son siempre Compatibles Determinados).

**🎤 Cómo decirlo en el oral:**
> "En la Unidad 3 estudiamos dos tipos de métodos: el método general de resolución, que se aplica a cualquier sistema de ecuaciones lineales, y el método particular de resolución —la Regla de Cramer—, que es muy útil para hallar directamente las incógnitas mediante determinantes, pero solo puede aplicarse en casos muy especiales: cuando el sistema es cuadrado y la matriz de los coeficientes es regular."

---

## 12.2 Sistema de ecuaciones cuadrado (Sistema cuadrado)

> 📖 **Textual del material:** "Antes de comenzar a resolver analizaremos el sistema:
> • ¿Cuántas ecuaciones tiene el sistema? (3)
> • ¿Cuántas incógnitas tiene el sistema? (3)
> Por lo tanto, estamos trabajando con un sistema cuadrado, es decir que tiene la misma cantidad de ecuaciones que de incógnitas. Este es el primer punto para decir que se puede aplicar la Regla de Cramer."

**🗣️ En palabras simples:**
Un sistema de ecuaciones se llama **cuadrado** cuando el número de ecuaciones coincide exactamente con el número de incógnitas (por ejemplo: 2 ecuaciones con 2 incógnitas, 3 ecuaciones con 3 incógnitas, n ecuaciones con n incógnitas). Se lo llama "cuadrado" porque, al armar la matriz de los coeficientes A, esta tiene igual cantidad de filas (ecuaciones) que de columnas (incógnitas), formando una matriz cuadrada de orden n × n.

**🔍 Desglose de la jerga:**
- **Cantidad de ecuaciones:** Número de igualdades lineales que componen el sistema; representa la cantidad de **filas** de la matriz de los coeficientes A.
- **Cantidad de incógnitas:** Número de variables desconocidas (como `x, y, z` o `x_1, x_2, ..., x_n`) presentes en el sistema; representa la cantidad de **columnas** de la matriz de los coeficientes A.
- **Sistema cuadrado:** Sistema de ecuaciones lineales que tiene la misma cantidad de ecuaciones que de incógnitas.
- **Primer punto para aplicar la Regla de Cramer:** Es la primera condición necesaria (condición de forma o dimensión). ¿Por qué? Porque la Regla de Cramer usa **determinantes**, y el determinante solo está definido para matrices cuadradas.

**💡 Ejemplo:**
Del **Ejemplo Nº 10** del material (pág. 2):
```
3x +  y -  z =  2
 x - 2y +  z = -9
4x + 3y + 2z =  1
```
- Cantidad de ecuaciones: 3.
- Cantidad de incógnitas: 3 (`x`, `y`, `z`).
- Como tiene 3 ecuaciones y 3 incógnitas, es un **sistema cuadrado** (de orden 3).
- Su matriz de los coeficientes es cuadrada de 3 × 3:
```
    [ 3   1  -1 ]
A = [ 1  -2   1 ]
    [ 4   3   2 ]
```

**🔗 Conexiones:**
- **Unidad 1 (Matrices):** Una matriz es cuadrada cuando tiene orden n × n (igual número de filas que de columnas).
- **Unidad 2 (Determinantes):** Solo las matrices cuadradas poseen determinante. Si el sistema no fuera cuadrado (por ejemplo, 3 ecuaciones con 4 incógnitas, como el Desempeño Integrador 3 de la pág. 7), la matriz A sería de 3 × 4 y ni siquiera existiría `|A|`.

**⚠️ Precisiones / errores comunes:**
- **Cuidado con las incógnitas "ocultas" (coeficiente cero):** Si un sistema de 3 ecuaciones tiene las ecuaciones `2x_2 + 4x_3 + 5x_1 = 2`, `x_1 + 3x_2 + 2x_3 = 3` y `2x_3 + x_1 - 1 = 0` (Desempeño Integrador 4, pág. 7), aunque en la tercera ecuación no aparezca escrita `x_2`, el sistema **sí tiene 3 incógnitas** (`x_1, x_2, x_3`) porque se cuenta el total de incógnitas del sistema completo (`0x_2`).
- **Ser cuadrado NO alcanza para aplicar Cramer:** Que el sistema sea cuadrado es recién "el primer punto". Falta verificar que `|A| ≠ 0`.

**🎤 Cómo decirlo en el oral:**
> "Un sistema de ecuaciones es un sistema cuadrado cuando tiene la misma cantidad de ecuaciones que de incógnitas. Esta es la primera condición necesaria para poder aplicar la Regla de Cramer, ya que garantiza que la matriz de los coeficientes A sea una matriz cuadrada y, por ende, que se pueda calcular su determinante."

---

## 12.3 Condiciones de aplicabilidad de la Regla de Cramer y regularidad de la matriz de los coeficientes

> 📖 **Textual del material:** "Al ser una matriz cuadrada, podemos calcular el determinante (en este caso como es una matriz de orden 3, se puede aplicar la Regla de Sarrus).
> El determinante de A es = -30 Al ser el determinante un número distinto de 0, nos indica que la matriz es Regular, por lo tanto va a ser posible aplicar la Regla de Cramer.
> Concluyendo:
> La Regla de Cramer es posible aplicarla cuando:
> • Se tiene un sistema de ecuaciones que tienen la misma cantidad de ecuaciones que de incógnitas, y
> • el determinante de la matriz de los coeficientes es distinto de cero."

**🗣️ En palabras simples:**
Para poder usar la Regla de Cramer tenés que hacer un "doble chequeo" obligatorio antes de empezar a calcular incógnitas:
1. **Chequeo de tamaño:** ¿Hay igual cantidad de ecuaciones que de incógnitas? (Sistema cuadrado).
2. **Chequeo de regularidad:** Calculás el determinante de la matriz de coeficientes `|A|`. ¿Da distinto de cero (`|A| ≠ 0`)? Si da distinto de cero, la matriz se llama **Regular** y tenés luz verde para aplicar Cramer. Si falla cualquiera de las dos condiciones, **no se puede** aplicar Cramer.

**🔍 Desglose de la jerga:**
- **Matriz de los coeficientes (A):** Matriz formada exclusivamente por los números (coeficientes) que multiplican a cada incógnita en el sistema ordenado (sin incluir los términos independientes).
- **Determinante de A (`|A|`):** Número real asociado a la matriz cuadrada A. Si A es de orden 2 se calcula como `a_11·a_22 - a_12·a_21`; si es de orden 3 se puede aplicar la **Regla de Sarrus**; si es de orden mayor, por Laplace/cofactores.
- **Matriz Regular:** Es toda matriz cuadrada cuyo determinante es un número distinto de cero (`|A| ≠ 0`). En la jerga de la materia, decir "la matriz de los coeficientes es regular" es exactamente equivalente a decir "el determinante de la matriz de los coeficientes es distinto de cero".
- **Conjunción "y" en las condiciones:** Ambas condiciones deben cumplirse simultáneamente (`m = n` ∧ `|A| ≠ 0`).

**💡 Ejemplo:**
En el **Ejemplo Nº 10** (pág. 2):
1. El sistema tiene 3 ecuaciones y 3 incógnitas → cumple la primera condición (es cuadrado).
2. La matriz de los coeficientes es:
```
    [ 3   1  -1 ]
A = [ 1  -2   1 ]
    [ 4   3   2 ]
```
Calculando por Regla de Sarrus:
`|A| = [3·(-2)·2 + 1·3·(-1) + 4·1·1] - [(-1)·(-2)·4 + 1·1·3 + 2·1·3] = (-12 - 3 + 4) - (8 + 3 + 6) = -11 - 17 = -30` *(Nota: aplicando Sarrus: `3(-2)(2) + 1(1)(4) + (-1)(1)(3) - [(-1)(-2)(4) + 3(1)(3) + 1(1)(2)] = (-12 + 4 - 3) - (8 + 9 + 2) = -11 - 19 = -30`)*.
Como `|A| = -30 ≠ 0`, la matriz A es **Regular** → cumple la segunda condición y es posible aplicar la Regla de Cramer.

**🔗 Conexiones:**
- **Unidad 1 y 2 (Matriz Regular e Inversa):** Una matriz cuadrada A es regular (`|A| ≠ 0`) si y solo si admite matriz inversa `A⁻¹`. De hecho (contexto adicional para entender el trasfondo), en `A . X = B`, si A es regular existe `A⁻¹` y la solución única es `X = A⁻¹ . B = (1/|A|) · Adj(A) . B`, de donde sale exactamente la fórmula de Cramer.
- **Unidad 3 (Rango y Rouché-Frobenius):** Que A sea cuadrada de orden n y `|A| ≠ 0` implica que el rango de A es máximo (`r(A) = n`), por lo que el rango de la matriz ampliada también es `n` (`r(A) = r(A') = n`), cumpliendo la condición matricial de Sistema Compatible Determinado.

**⚠️ Precisiones / errores comunes:**
- **No olvidarse la palabra "Regular":** En el Desempeño de Síntesis 1c (pág. 5) preguntan textualmente: *"Si la matriz de los coeficientes no es regular ¿Qué significa?"*. Significa que su determinante es igual a cero (`|A| = 0`), por lo que no se puede aplicar la Regla de Cramer (y el sistema no es Compatible Determinado).
- **No confundir matriz de los coeficientes con matriz ampliada:** El determinante que exige la Regla de Cramer es el de la **matriz de los coeficientes A**, nunca el de la matriz ampliada (que ni siquiera es cuadrada).

**🎤 Cómo decirlo en el oral:**
> "La Regla de Cramer es posible aplicarla cuando se cumplen dos condiciones: primero, que se tenga un sistema de ecuaciones cuadrado, es decir, que tenga la misma cantidad de ecuaciones que de incógnitas; y segundo, que el determinante de la matriz de los coeficientes sea distinto de cero, lo cual nos indica que la matriz A es Regular."

---

## 12.4 Definición de la matriz cuadrada A_j (Matriz con columna reemplazada)

> 📖 **Textual del material:** "Además, definimos a la matriz cuadrada A_j como la matriz que resulta de reemplazar en la matriz A a la columna j por el vector de los términos independientes. (es lo mismo que explicamos en el ejemplo anterior, nada más que un poco más formalmente.)"

**🗣️ En palabras simples:**
Para averiguar cuánto vale la incógnita número `j` (por ejemplo, la primera incógnita `x_1`, la segunda `x_2`, etc.), armás una matriz nueva llamada `A_j`. ¿Cómo se fabrica `A_j`? Copiás la matriz original de coeficientes `A` tal cual está, pero borrás la columna `j` (la columna donde estaban los coeficientes de esa incógnita que querés calcular) y en ese lugar enchufás la columna `B` de los términos independientes (los resultados del otro lado del igual). Todas las demás columnas de `A` quedan intactas.

**🔍 Desglose de la jerga:**
- **Matriz cuadrada A_j:** Matriz de igual orden (n × n) que la matriz de los coeficientes A, asociada específicamente a la j-ésima incógnita `x_j`.
- **Subíndice j (`j = 1, 2, ..., n`):** Indica el número de posición de la columna (y de la incógnita correspondiente). Por ejemplo:
  - `A_1` es la matriz que resulta de reemplazar la **columna 1** de A por el vector B (sirve para calcular la primera incógnita, `x_1` o `x`).
  - `A_2` es la matriz que resulta de reemplazar la **columna 2** de A por el vector B (sirve para calcular la segunda incógnita, `x_2` o `y`).
  - `A_3` es la matriz que resulta de reemplazar la **columna 3** de A por el vector B (sirve para calcular la tercera incógnita, `x_3` o `z`).
- **Columna j de A:** Es la columna formada por todos los coeficientes que multiplican a la incógnita j-ésima en las distintas ecuaciones del sistema.
- **Vector de los términos independientes (B):** Matriz columna de orden n × 1 formada por las constantes que no están multiplicadas por ninguna incógnita (ubicadas a la derecha del signo igual cuando el sistema está escrito como `A . X = B`).

**💡 Ejemplo:**
Del **Ejemplo Nº 11** del material (págs. 3 y 4), donde el sistema es:
```
 2x_1 +  x_2 + 2x_3 = 3
  x_1 + 5x_2 -  x_3 = 6
 -x_1 - 2x_2 +  x_3 = 0
```
La matriz de coeficientes verdadera es `A = [ 2  1  2 ; 1  5 -1 ; -1 -2  1 ]` y el vector de términos independientes es `B = [ 3 ; 6 ; 0 ]`. Entonces las matrices `A_j` son:
- **Para j = 1 (`A_1`):** *"Reemplazamos la columna 1, pues es la primer incógnita, por el vector de los términos independientes"*:
```
      [ 3   1   2 ]
A_1 = [ 6   5  -1 ]
      [ 0  -2   1 ]
```
- **Para j = 2 (`A_2`):** *"Reemplazamos la columna 2, pues es la segunda incógnita, por el vector de los términos independientes"*:
```
      [  2   3   2 ]
A_2 = [  1   6  -1 ]
      [ -1   0   1 ]
```
- **Para j = 3 (`A_3`):** *"Reemplazamos la columna 3, pues es la tercer incógnita, por el vector de los términos independientes"*:
```
      [  2   1   3 ]
A_3 = [  1   5   6 ]
      [ -1  -2   0 ]
```

**🔗 Conexiones:**
- Se conecta con el concepto de **determinante (`|A_j|`)**: una vez construida cada matriz cuadrada `A_j`, se calcula su determinante `|A_j|`, el cual irá en el **numerador** de la fórmula de la Regla de Cramer.

**⚠️ Precisiones / errores comunes:**
- **¿Qué pasa si `|A_j| = 0` para algún j?** ¡Mucho cuidado con esta trampa clásica de examen! El determinante que **no puede ser cero** es `|A|` (porque va en el denominador). En cambio, el determinante `|A_j|` (que va en el numerador) **sí puede dar cero**: si `|A_j| = 0` y `|A| ≠ 0`, simplemente significa que esa incógnita vale cero (`x_j = 0 / |A| = 0`), lo cual es perfectamente válido.
- **No cambiar de lugar las otras columnas:** Al armar `A_j`, el vector `B` debe colocarse exactamente en la posición de la columna `j`, sin desplazar ni permutar las demás columnas (porque permutar columnas en un determinante le cambia el signo).

**🎤 Cómo decirlo en el oral:**
> "Definimos a la matriz cuadrada A sub j como la matriz que resulta de reemplazar en la matriz de los coeficientes A a la columna j —que es la columna correspondiente a la incógnita x sub j— por el vector de los términos independientes B, manteniendo todas las demás columnas en su posición original."

---

## 12.5 Enunciado general y algoritmo de la Regla de Cramer

> 📖 **Textual del material (Procedimiento en Ejemplo Nº 10, págs. 2 y 3):**
> "Escribimos entonces la matriz de los coeficientes y el vector de los términos independientes:
> A = [ 3  1 -1 ; 1 -2  1 ; 4  3  2 ]    B = [ 2 ; -9 ; 1 ]
> Para calcular la incógnita x, hacemos lo siguiente: Reemplazamos la columna correspondiente a la incógnita x, por el vector de los términos independientes, le calculamos el determinante de esta nueva matriz y lo dividimos por el determinante de A:
> x = | 2  1 -1 ; -9 -2  1 ; 1  3  2 | / -30 = 30 / -30 = -1, es decir que el valor de la incógnita x = -1
> Lo mismo hacemos para y: Reemplazamos la columna correspondiente a la incógnita y, por el vector de los términos independientes, le calculamos el determinante de esta nueva matriz y lo dividimos por el determinante de A:
> y = | 3  2 -1 ; 1 -9  1 ; 4  1  2 | / -30 = -90 / -30 = 3, es decir que el valor de la incógnita y = 3
> Y por último lo hacemos para z: Reemplazamos la columna correspondiente a la incógnita z, por el vector de los términos independientes, le calculamos el determinante de esta nueva matriz y lo dividimos por el determinante de A:
> z = | 3  1  2 ; 1 -2 -9 ; 4  3  1 | / -30 = 60 / -30 = -2, es decir que el valor de la incógnita z = -2"

> 📖 **Textual del material (Generalización formal, págs. 3 y 4):**
> "Generalizando:
> Sea el sistema A . X = B
> Donde A es la matriz de los coeficientes, cuadrada y regular; X es el vector de las incógnitas y B el vector de los términos independientes.
> Además, definimos a la matriz cuadrada A_j como la matriz que resulta de reemplazar en la matriz A a la columna j por el vector de los términos independientes. (es lo mismo que explicamos en el ejemplo anterior, nada más que un poco más formalmente.)
> Entonces el sistema de ecuaciones A . X = B tiene por solución el vector:
> X = [ X_1 ; X_2 ; X_n ] donde: x_1 = |A_1| / |A| , x_2 = |A_2|, ... x_n = |A_n| / |A|"
> *(Y en pág. 4 completa explícitamente:)*
> "Como A es una matriz regular (el determinante es distinto de 0) … Entonces ahora calculamos el valor de cada incógnita a través de:
> x_1 = |A_1| / |A| , x_2 = |A_2| / |A| , x_3 = |A_3| / |A|"

**🗣️ En palabras simples:**
La Regla de Cramer nos da una receta directa para resolver cualquier sistema cuadrado `A . X = B` cuando `|A| ≠ 0`: el valor de cada incógnita `x_j` es una simple división entre dos números:
- **Arriba (numerador):** el determinante de la matriz `A_j` (`|A_j|`), que es la matriz con la columna `j` reemplazada por los términos independientes.
- **Abajo (denominador):** siempre el mismo número para todas las incógnitas, que es el determinante de la matriz de los coeficientes original (`|A|`).

**🔍 Desglose de la jerga y la notación:**
- **`A . X = B`:** Expresión matricial del sistema de ecuaciones lineales.
  - **`A`:** Matriz de los coeficientes, de orden n × n, **cuadrada y regular** (`|A| ≠ 0`).
  - **`X`:** Vector (matriz columna de orden n × 1) de las incógnitas: `X = [ x_1 ; x_2 ; ... ; x_n ]`. (En el Ejemplo Nº 10 también denota al vector solución particular con un asterisco: `X*`).
  - **`B`:** Vector (matriz columna de orden n × 1) de los términos independientes.
- **`|A|`:** Determinante de la matriz de los coeficientes A (va siempre en el denominador).
- **`|A_j|`:** Determinante de la matriz cuadrada `A_j` obtenida al sustituir la j-ésima columna de A por B (va en el numerador de la incógnita `x_j`).
- **`x_j = |A_j| / |A|` (para `j = 1, 2, ..., n`):** Fórmula de la Regla de Cramer para la incógnita j-ésima.

### ⚙️ Pasos del Algoritmo (Método particular de la Regla de Cramer)
Tal como lo presenta y aplica el material en los Ejemplos Nº 10 y Nº 11:
1. **Verificar que el sistema esté completo y ordenado**, y analizar la cantidad de ecuaciones y de incógnitas para confirmar que sea un **sistema cuadrado** (n ecuaciones con n incógnitas).
2. **Armar la matriz de los coeficientes A y el vector de los términos independientes B** a partir del sistema `A . X = B`.
3. **Calcular el determinante de la matriz de los coeficientes `|A|`** (por ejemplo, con Regla de Sarrus si es de orden 3) para saber si la matriz A es **Regular** (`|A| ≠ 0`).
   - Si `|A| = 0`, detener el algoritmo: no se puede aplicar la Regla de Cramer (pasar al método general).
   - Si `|A| ≠ 0`, continuar al paso 4.
4. **Calcular cada incógnita `x_j` (`j = 1, 2, ..., n`):** Para cada incógnita, formar la matriz `A_j` reemplazando la columna `j` de `A` por el vector `B`, calcular su determinante `|A_j|` y dividirlo por `|A|`:
   `x_1 = |A_1| / |A|`, `x_2 = |A_2| / |A|`, ..., `x_n = |A_n| / |A|`.
5. **Escribir el vector solución única `X` (o `X*`)** con los valores obtenidos para cada incógnita.

**🧩 Idea de la demostración / Por qué funciona el método (Contexto adicional para comprender a fondo):**
*(Nota: El PDF enuncia la generalización sin demostración algebraica formal, pero comprender por qué funciona te da seguridad total si el profesor pregunta "¿de dónde sale que se divide por |A|?")*.
1. Partimos del sistema matricial `A . X = B`.
2. Como por hipótesis A es cuadrada y regular (`|A| ≠ 0`), sabemos por la Unidad 2 que existe su matriz inversa `A⁻¹`, y que esta se calcula como:
   `A⁻¹ = (1 / |A|) · Adj(A)` (donde `Adj(A)` es la matriz adjunta, es decir, la transpuesta de la matriz de cofactores `C^T`).
3. Multiplicando a izquierda por `A⁻¹` en `A . X = B`, obtenemos la única solución:
   `X = A⁻¹ . B = (1 / |A|) · (Adj(A) . B)`.
4. Al hacer el producto de la fila `j` de `Adj(A)` (que contiene los cofactores `C_1j, C_2j, ..., C_nj` de la columna `j` de A) por la columna `B` (`b_1, b_2, ..., b_n`), queda la suma:
   `b_1 · C_1j + b_2 · C_2j + ... + b_n · C_nj`.
5. ¡Pero por el desarrollo de Laplace (Unidad 2), esa suma es exactamente el determinante de la matriz `A_j` desarrollado por su columna `j` (donde ahora están `b_1, ..., b_n`)! Es decir, esa suma vale `|A_j|`.
6. Por lo tanto, la componente j-ésima de `X` es `x_j = |A_j| / |A|`.

**🤔 Intuición:**
El determinante mide cómo una matriz "escala" volúmenes o áreas. Como `|A| ≠ 0`, la transformación lineal asociada a A no aplasta el espacio y es biyectiva (invertible). Reemplazar la columna `j` por `B` y comparar el nuevo determinante `|A_j|` contra el original `|A|` mide exactamente en qué proporción (`x_j`) tuvo que participar la columna `j` para generar el vector resultado `B`.

**💡 Ejemplo:**
En el **Ejemplo Nº 11** (págs. 3 y 4):
Sistema ya completo y ordenado:
```
 2x_1 +  x_2 + 2x_3 = 3
  x_1 + 5x_2 -  x_3 = 6
 -x_1 - 2x_2 +  x_3 = 0
```
- Determinante de la matriz de coeficientes: `|A| = 12 ≠ 0` (matriz regular).
- Cálculo de las incógnitas:
  - `x_1 = |A_1| / |A| = -21 / 12 = -7/4`
  - `x_2 = |A_2| / |A| =  24 / 12 =  2`
  - `x_3 = |A_3| / |A| =  27 / 12 =  9/4`
- Única solución (vector solución):
  `X = [ x_1 ; x_2 ; x_3 ] = [ -7/4 ; 2 ; 9/4 ]`.

**🔗 Conexiones:**
- Integra **Sistemas de Ecuaciones (Unidad 3)** con **Determinantes y Regla de Sarrus (Unidad 2)** y **Matrices Regulares (Unidad 1)**.
- En un **Sistema Homogéneo** cuadrado (`A . X = 0`, donde `B = [0; 0; ...; 0]`): si `|A| ≠ 0`, al reemplazar cualquier columna `j` por el vector nulo `B = 0`, la matriz `A_j` tiene una columna entera de ceros, por lo que `|A_j| = 0` para todo `j`. Entonces Cramer da inmediatamente `x_1 = 0/|A| = 0, ..., x_n = 0/|A| = 0`, confirmando que si `|A| ≠ 0` un sistema homogéneo tiene **únicamente la solución trivial**.

**⚠️ Precisiones / errores comunes (¡ATENCIÓN A LAS ERRATAS DEL PDF EN PÁG. 3!):**
1. **Errata tipográfica 1 en la pág. 3 del PDF:** En la fórmula general de la página 3 escribieron `x_2 = |A_2|` omitiendo sin querer el denominador `/ |A|`. En la página 4 (arriba del todo) está bien escrito: `x_1 = |A_1| / |A| , x_2 = |A_2| / |A| , x_3 = |A_3| / |A|`. En el oral, por supuesto, **todas** las incógnitas van divididas por `|A|`.
2. **Errata tipográfica 2 en la pág. 3 del PDF (Ejemplo Nº 11):** Al final de la página 3, al escribir `|A|` para el Ejemplo Nº 11, el PDF imprimió por error `| 3  1 -1 ; 1  5 -1 ; 1 -2  1 | = 12`, pero mirando el sistema original y las matrices `A_1, A_2, A_3` en la página 4 se ve que la matriz `A` verdadera usada para obtener `|A| = 12` es `| 2  1  2 ; 1  5 -1 ; -1 -2  1 | = 12`.
3. **Notación de barras vs. corchetes:** En la página 2 (Ejemplo Nº 10), el diseño gráfico del PDF dibujó corchetes en el numerador de `x`, `y`, `z`, pero el texto dice literalmente *"le calculamos el determinante de esta nueva matriz"*. En la Generalización (pág. 3) y el Ejemplo Nº 11 (pág. 4) usa correctamente las barras verticales de determinante `|A_j|`. Nunca olvides decir en el oral que se dividen **determinantes** (números), porque no existe la división entre matrices.

**🎤 Cómo decirlo en el oral:**
> "Generalizando: dado el sistema A por X igual a B, donde A es la matriz de los coeficientes, cuadrada y regular, X es el vector de las incógnitas y B es el vector de los términos independientes, definimos a la matriz cuadrada A sub j como la que resulta de reemplazar en la matriz A la columna j por el vector de los términos independientes B. Entonces el sistema tiene por única solución el vector X cuyas componentes se obtienen mediante x sub 1 igual al determinante de A sub 1 sobre el determinante de A, x sub 2 igual al determinante de A sub 2 sobre el determinante de A, y así sucesivamente hasta x sub n igual al determinante de A sub n sobre el determinante de A."

---

## 12.6 Unicidad de la solución y clasificación del sistema resuelto por la Regla de Cramer

> 📖 **Textual del material (Pág. 3):** "Como podrás observar, la solución es única, y la podemos escribir como:
> X* = [ x ; y ; z ] → X* = [ -1 ; 3 ; -2 ]
> Por lo tanto el sistema es un Sistema Compatible Determinado."
>
> 📖 **Textual del material (Pág. 4):** "Luego la única solución es el vector:
> X = [ x_1 ; x_2 ; x_3 ] = [ -7/4 ; 2 ; 9/4 ]"

**🗣️ En palabras simples:**
Cada vez que podés aplicar la Regla de Cramer (porque el sistema es cuadrado y `|A| ≠ 0`), el resultado está cantado desde antes de terminar las cuentas: como cada determinante `|A_j|` da un único número real y lo dividís por otro único número real distinto de cero (`|A|`), cada incógnita toma **un único valor**. Por lo tanto, cualquier sistema que se pueda resolver por la Regla de Cramer tiene **solución única** y se clasifica siempre como **Sistema Compatible Determinado (SCD)**.

**🔍 Desglose de la jerga:**
- **Solución única:** Existe un único vector columna `X*` (una única n-upla de valores para las incógnitas `x_1, x_2, ..., x_n`) que verifica simultáneamente todas las ecuaciones del sistema.
- **Sistema Compatible Determinado (SCD):** Clasificación (vista en Clases 9-11) que corresponde a los sistemas de ecuaciones que admiten solución (son *compatibles*) y dicha solución es única (son *determinados*).

**💡 Ejemplo:**
- En el **Desempeño de Síntesis 1b y 1d** (pág. 5), el material pregunta:
  - *"b- ¿Qué tipo de soluciones va a tener un sistema de ecuaciones resuelto por este método?"* → Va a tener **solución única** (el sistema será siempre un **Sistema Compatible Determinado**).
  - *"d- ¿Cuántas soluciones se pueden obtener utilizando este método particular en un sistema de cuatro ecuaciones con cuatro incógnitas?"* → **Una única solución** (un único vector solución `X` de 4 componentes: `x_1, x_2, x_3, x_4`). ¡Cuidado con no responder "cuatro soluciones" confundiéndolo con las 4 incógnitas que forman el único vector solución!

**🔗 Conexiones:**
- **Desempeño Integrador 2i (pág. 6 y respuesta en pág. 8):** *"Si el determinante de la matriz de los coeficientes de un sistema es distinto de cero, podemos asegurar que el sistema tiene solución."* → **Verdadero (V)**. No solo tiene solución, sino que es única (SCD).

**⚠️ Precisiones / errores comunes:**
- **¡Trampa mortal en el oral! No confundir "cantidad de soluciones" con "cantidad de incógnitas":** Un sistema de 4 ecuaciones con 4 incógnitas resuelto por Cramer tiene **1 sola solución** (un único vector solución `X = [x_1, x_2, x_3, x_4]^T`), la cual está compuesta por 4 valores (uno para cada incógnita).

**🎤 Cómo decirlo en el oral:**
> "Todo sistema de ecuaciones que pueda resolverse mediante la Regla de Cramer admite solución única, expresada a través del vector solución X*, y por lo tanto se clasifica siempre como un Sistema Compatible Determinado."

---

## 12.7 ¿Qué ocurre cuando `|A| = 0`? Inaplicabilidad de la Regla de Cramer y consecuencias sobre la clasificación

> 📖 **Textual del material (Pág. 4 — Ejemplo Nº 12):** "Ejemplo Nº12: Para resolver el sistema
> 2x1 + x2 = 3
> 4x1 + 2x2 = 6
> Calculamos |A|:
> |A| = | 2  1 ; 4  2 | = 0
> Luego el sistema no se puede resolver por la regla de Cramer. En este caso habría que aplicar el método general de resolución.
> Se puede asegurar que el sistema no es Compatible Determinado, ya que no es posible calcular el determinante y resolverlo por este método."

**🗣️ En palabras simples:**
Si tenés un sistema cuadrado, calculás el determinante de la matriz de los coeficientes y te da **cero** (`|A| = 0`), la matriz A **no es regular**. En ese momento se frena la Regla de Cramer:
1. **No podés resolver el sistema por la Regla de Cramer** (porque en la fórmula `x_j = |A_j| / |A|` tendrías que dividir por cero, lo cual no existe en matemática).
2. **Ya podés asegurar algo muy importante sobre la clasificación:** el sistema **NO es Compatible Determinado** (es decir, seguro que no tiene solución única; o tiene infinitas soluciones —Compatible Indeterminado— o no tiene ninguna —Incompatible—).
3. **¿Cómo sabés cuál de esos dos es y cómo lo resolvés?** Tenés que recurrir obligatoriamente al **método general de resolución** (Gauss-Jordan / análisis de los rangos de la matriz de coeficientes y de la matriz ampliada).

**🔍 Desglose de la jerga:**
- **`|A| = 0` (Matriz no regular / singular):** El determinante de la matriz de los coeficientes es nulo.
- **"No se puede resolver por la regla de Cramer":** Falla la segunda condición de aplicabilidad del método particular.
- **"Aplicar el método general de resolución":** Se refiere al método visto en las Clases 10 y 11 (escalonamiento / Gauss-Jordan sobre la matriz ampliada) que sirve para cualquier sistema y permite distinguir si es Compatible Indeterminado o Incompatible.
- **"Se puede asegurar que el sistema no es Compatible Determinado":** En un sistema cuadrado de orden n, el sistema es Compatible Determinado si y solo si `|A| ≠ 0` (es decir, `r(A) = n`). Por contrarrecíproco, si `|A| = 0` (entonces `r(A) < n`), es imposible que sea Compatible Determinado.

**💡 Ejemplo:**
Analicemos el **Ejemplo Nº 12** (pág. 4) y compáremoslo con el **Desempeño de Síntesis 2b** (pág. 5):
- En el **Ejemplo Nº 12**:
  ```
  2x_1 +  x_2 = 3
  4x_1 + 2x_2 = 6
  ```
  `|A| = 2·2 - 1·4 = 4 - 4 = 0`. No se puede aplicar Cramer. Si le aplicamos el método general, vemos que la segunda ecuación es exactamente el doble de la primera (`r(A) = r(A') = 1 < 2`), por lo que resulta ser **Compatible Indeterminado** (infinitas soluciones).
- En el **Desempeño de Síntesis 2b** (pág. 5):
  ```
   3x - 2y = 6
  -4y + 6x = 6   (que ordenado es: 6x - 4y = 6)
  ```
  `|A| = 3·(-4) - (-2)·6 = -12 + 12 = 0`. Respuesta oficial (pág. 5): **No** es posible aplicar Regla de Cramer. Acá el lado izquierdo se duplicó pero el término independiente quedó en 6 (`r(A) = 1 ≠ r(A') = 2`), por lo que es **Incompatible** (no tiene solución).
- En ambos casos se cumple la regla general del material: cuando `|A| = 0`, **el sistema no es Compatible Determinado**.

**🔗 Conexiones:**
- Conecta la **Regla de Cramer (Clase 12)** con el **Teorema de Rouché-Frobenius y el Método General (Clases 10 y 11)**:
  - Si el sistema es cuadrado (n × n) y `|A| ≠ 0` ⇒ `r(A) = r(A') = n` ⇒ **Sistema Compatible Determinado** (se resuelve por Cramer).
  - Si el sistema es cuadrado (n × n) y `|A| = 0` ⇒ `r(A) < n` ⇒ **No es Compatible Determinado**. Hay que usar el método general para ver si `r(A) = r(A') < n` (**Compatible Indeterminado**) o si `r(A) ≠ r(A')` (**Incompatible**).

**⚠️ Precisiones / errores comunes:**
- **Aclaración conceptual sobre la redacción del PDF:** Al final de la página 4, el PDF dice *"ya que no es posible calcular el determinante y resolverlo por este método"*. En rigor, el determinante `|A|` **sí se pudo calcular** (de hecho se calculó arriba y dio `0`); lo que quiso decir el autor del módulo es que al dar `0` no es posible usar ese determinante para dividir en la fórmula `|A_j| / |A|` y resolverlo por este método. En el oral, decí: *"Se puede asegurar que el sistema no es Compatible Determinado, ya que el determinante de la matriz de los coeficientes es igual a cero (la matriz no es regular) y no es posible resolverlo por la Regla de Cramer"*.
- **No decir que si `|A| = 0` el sistema "no tiene solución":** ¡Falso! Si `|A| = 0`, el sistema puede no tener solución (Incompatible) **o puede tener infinitas soluciones** (Compatible Indeterminado, como pasa justamente en el Ejemplo Nº 12 o en cualquier sistema homogéneo con `|A| = 0`). Lo único que se asegura con certeza absoluta es que **no es Compatible Determinado**.

**🎤 Cómo decirlo en el oral:**
> "Si en un sistema cuadrado el determinante de la matriz de los coeficientes es igual a cero, significa que la matriz A no es regular. En ese caso, el sistema no se puede resolver por la Regla de Cramer y se puede asegurar que el sistema no es Compatible Determinado. Para saber si es Compatible Indeterminado o Incompatible, y hallar su conjunto solución si existe, debemos aplicar el método general de resolución."

---

## 12.8 Requisito operativo previo: Sistema completo y ordenado

> 📖 **Textual del material (Pág. 3 — Ejemplo Nº 11):** "Ejemplo Nº11: Para resolver el sistema ya completo y ordenado:
> 2x1 + x2 + 2x3 = 3
> x1 + 5x2 - x3 = 6
> -x1 - 2x2 + x3 = 0"

**🗣️ En palabras simples:**
Antes de armar la matriz `A` y el vector `B` para aplicar Cramer, tenés que mirar bien las ecuaciones y asegurarte de que el sistema esté **completo y ordenado**:
1. **Ordenado:** En todas las ecuaciones, las incógnitas deben aparecer en el mismo orden de columnas (por ejemplo, primero `x`, segundo `y`, tercero `z` del lado izquierdo del igual) y los términos independientes (los números sueltos) deben estar todos del lado derecho del signo igual (`A . X = B`).
2. **Completo:** Si en alguna ecuación falta una incógnita, su lugar debe completarse con un **`0`** en la matriz de los coeficientes.

**🔍 Desglose de la jerga:**
- **Sistema ordenado:** Sistema en el cual cada columna vertical de términos con incógnitas corresponde a la misma variable (`x_1, x_2, ..., x_n`) en todas las ecuaciones, y los términos independientes están despejados en el segundo miembro de cada igualdad.
- **Sistema completo:** Sistema en el que se explicitan (con coeficiente `0`) las incógnitas que no figuran en alguna de las ecuaciones.

**💡 Ejemplo (tomado de los Desempeños de la Clase 12):**
1. **Desempeño de Síntesis 2c (pág. 5):**
   ```
   2y + 5x = 3
   -x + 2  = 3y
   ```
   Si armaras la matriz sin ordenar, pondrías `[2, 5 ; -1, 2]`, ¡lo cual está todo mal! Primero hay que **ordenarlo** (pasando `3y` restando a la izquierda y el `2` restando a la derecha, y encolumnando primero `x` y luego `y`):
   ```
    5x + 2y =  3
   -1x - 3y = -2
   ```
   Ahora sí: `A = [ 5  2 ; -1 -3 ]`, `B = [ 3 ; -2 ]`, y `|A| = 5·(-3) - 2·(-1) = -15 + 2 = -13 ≠ 0` (por eso la respuesta oficial en pág. 5 es **Sí**).
2. **Desempeño Integrador 4 (pág. 7):** *"Resuelve el sistema dado, sin aplicar el método general:"*
   ```
   2x_2 + 4x_3 + 5x_1 = 2
   x_1 + 3x_2 + 2x_3 = 3
   2x_3 + x_1 - 1 = 0
   ```
   Antes de aplicar Cramer, se lo **completa y ordena** (`x_1, x_2, x_3` a la izquierda, término independiente a la derecha):
   ```
   5x_1 + 2x_2 + 4x_3 = 2
   1x_1 + 3x_2 + 2x_3 = 3
   1x_1 + 0x_2 + 2x_3 = 1
   ```

**🔗 Conexiones:**
- Se conecta con la **Propiedad de los Determinantes (Unidad 2)**: intercambiar dos columnas de una matriz cambia el signo de su determinante (`|B| = -|A|`). Si un sistema está desordenado y no encolumnás bien las incógnitas, los determinantes `|A|` y `|A_j|` quedan alterados y la Regla de Cramer da valores erróneos.

**⚠️ Precisiones / errores comunes:**
- **Cuidado con los términos independientes del lado izquierdo:** En ecuaciones como `2x_3 + x_1 - 1 = 0` o `-x + 2 = 3y`, el término independiente debe pasar al otro lado del igual cambiando su signo antes de armar el vector `B` (porque la forma matricial de Cramer parte de `A . X = B`, no de `A . X - B = 0`).

**🎤 Cómo decirlo en el oral:**
> "Antes de construir la matriz de los coeficientes A y el vector de los términos independientes B para aplicar la Regla de Cramer, el sistema debe estar completo y ordenado bajo la forma A por X igual a B: las incógnitas deben estar encolumnadas en el mismo orden en todas las ecuaciones, completando con coeficiente cero las que falten, y los términos independientes deben estar en el segundo miembro de la igualdad."

---

## 12.9 Aplicación económica: La Matriz de Insumo-Producto y el Modelo de Producción

> 📖 **Textual del material (Pág. 8 — Desempeño Integrador 6: LA MATRIZ DE INSUMO-PRODUCTO):**
> "Los datos se observan en la matriz A, llamada matriz de insumo-producto, donde sus elementos son los coeficientes de insumo. Se considera que esta matriz es productiva, si las sumas de los elementos de cada columna son menores que 1."
> "Los niveles de producción se calculan siguiendo un modelo económico dado por (I-A) . X = D, donde X es la matriz de producción, D es la matriz de demanda externa e I es la matriz Identidad."

**🗣️ En palabras simples:**
En la página 8, como cierre integrador, el material presenta una aplicación económica clásica del álgebra matricial y de los sistemas de ecuaciones (el modelo de Leontief o de insumo-producto):
- Imaginá un grupo de empresas (por ejemplo: informática, estadística y computadoras) que se compran insumos entre sí para poder producir.
- La tabla que dice cuántos centavos de cada empresa se necesitan para producir 1 peso de una empresa dada es una matriz cuadrada `A` llamada **matriz de insumo-producto**, y cada numerito adentro se llama **coeficiente de insumo**.
- Para que el sistema económico sea rentable y no consuma más de lo que produce, la suma de cada columna de `A` tiene que dar menos que 1 (1 peso); cuando pasa eso, se dice que la matriz `A` es **productiva**.
- La relación entre lo que producen en total las empresas (`X`, **matriz de producción**) y lo que queda disponible para vender afuera del grupo (`D`, **matriz de demanda externa**) está dada por la ecuación matricial **`(I - A) . X = D`**.

**🔍 Desglose de la jerga:**
- **Matriz de insumo-producto (A):** Matriz cuadrada de orden n × n que registra los requerimientos internos entre n sectores o empresas de un grupo económico.
- **Coeficientes de insumo (`a_ij`):** Son los elementos de la matriz de insumo-producto A. Cada elemento `a_ij` de la columna `j` y fila `i` representa cuánto insumo del sector `i` se requiere invertir por cada peso (1 unidad monetaria) que produce el sector `j`.
- **Matriz productiva:** Se considera que la matriz de insumo-producto A es **productiva** si **las sumas de los elementos de cada columna son menores que 1**. (Económicamente significa que producir 1 peso en cualquier sector requiere menos de 1 peso en insumos totales).
- **Matriz de producción (X):** Vector columna (matriz de n × 1) que indica los niveles totales de producción de cada empresa o sector.
- **Matriz de demanda externa (D):** Vector columna (matriz de n × 1) que indica la cantidad producida que se destina a satisfacer la demanda externa (fuera del consumo interno entre las empresas del grupo).
- **Matriz Identidad (I):** Matriz cuadrada diagonal de orden n con 1 en la diagonal principal y 0 fuera de ella.
- **Modelo económico `(I - A) . X = D`:** Ecuación matricial que vincula la producción con la demanda externa. Si se distribuye el producto matricial: `I . X - A . X = D` ⇒ `X - A . X = D`, lo que significa que: *(Producción Total `X`) menos (Consumo Interno de Insumos `A . X`) = (Demanda Externa `D`)*.

**💡 Ejemplo (del Desempeño 6, pág. 8):**
Tres empresas: 1) Asesoría informática, 2) Servicios estadísticos, 3) Fábrica de computadoras.
- **Matriz de insumo-producto A:**
```
    [ 0,30   0,20   0,30 ]
A = [ 0,10   0,40   0,10 ]
    [ 0,30   0,20   0,20 ]
```
- **¿Es productiva la matriz A?** Sumamos los elementos de cada columna:
  - Columna 1: `0,30 + 0,10 + 0,30 = 0,70 < 1`
  - Columna 2: `0,20 + 0,40 + 0,20 = 0,80 < 1`
  - Columna 3: `0,30 + 0,10 + 0,20 = 0,60 < 1` (o `0,70 < 1` con el `0,30` del texto).
  Como las sumas de los elementos de cada columna son menores que 1, **sí, la matriz A es productiva** (respuesta oficial en pág. 8: *"b- Si"*).
- **Cálculo de la demanda externa D dado `X = [ 53000 ; 44000 ; 61000 ]`:**
  Aplicando `(I - A) . X = D`:
  ```
          [  0,70  -0,20  -0,30 ]
  I - A = [ -0,10   0,60  -0,10 ]
          [ -0,30  -0,20   0,80 ]
  ```
  *(Nota sobre errata del PDF en pág. 8: En el texto del problema dice que producir cada peso de computadoras cuesta "30 pesos" —errata por 0,30 pesos— de informática, 0,10 pesos de estadística y "0,30 pesos de computadoras", mientras que en la matriz A impresa pusieron `a_33 = 0,20`. Las respuestas oficiales de la pág. 8 —Informática: 10.000 pesos; Servicios/Computadoras: 15.000 pesos; Estadística: 18.000 pesos— se obtienen exactamente usando `a_33 = 0,30` como dice el texto, es decir `0,70·61000 - 0,30·53000 - 0,20·44000 = 18000` para la tercera fila si fuera `0,20`, o `15000` si `a_33 = 0,25` / según el redondeo del apunte)*.

**🔗 Conexiones:**
- **Si te dan `X` y te piden `D`:** Es una operación directa de resta y multiplicación de matrices (Unidad 1): calculás `I - A` y lo multiplicás por `X`.
- **Si te dan la demanda externa `D` y te piden hallar los niveles de producción `X`:** ¡Queda planteado un **sistema de ecuaciones lineales cuadrado** `(I - A) . X = D`! Donde la matriz de los coeficientes es `M = I - A`, el vector de incógnitas es `X` y el vector de términos independientes es `D`, el cual se puede resolver por la Regla de Cramer o por el método general.

**⚠️ Precisiones / errores comunes:**
- **Sumar columnas, no filas:** La condición del material para que la matriz de insumo-producto sea **productiva** exige que las sumas de los elementos de **cada columna** sean menores que 1.
- **No olvidarse de la matriz Identidad `I`:** En `(I - A) . X = D`, no se puede escribir `(1 - A)` porque `1` es un escalar y `A` es una matriz; se resta `I - A` donde `I` es la matriz Identidad del mismo orden que `A`.

**🎤 Cómo decirlo en el oral:**
> "En el modelo económico de insumo-producto, la matriz A se denomina matriz de insumo-producto y sus elementos son los coeficientes de insumo. Se considera que esta matriz es productiva si las sumas de los elementos de cada columna son menores que 1. Los niveles de producción se calculan mediante el modelo (I menos A) por X igual a D, donde X es la matriz de producción, D es la matriz de demanda externa e I es la matriz Identidad."

---

## 12.10 Síntesis e Integración Teórica de la Unidad 3 (Cuestionarios y Verdadero/Falso Oficial)

Al ser la Clase 12 la última clase de la Unidad 3 y de todo el módulo de Matemática Discreta 2, las páginas 5, 6 y 8 incluyen dos bloques fundamentales de evaluación teórica: el **Desempeño de Síntesis (Desempeño 1)** y los **Desempeños Integradores (Desempeño 1 y Desempeño 2)** junto con las **respuestas y justificaciones oficiales textuales de la cátedra**. Como estas preguntas resumen todo lo que el profesor evalúa en el oral sobre Sistemas de Ecuaciones, las desglosamos completas a continuación.

### A. Preguntas teóricas del Desempeño de Síntesis (Pág. 5) y Desempeño Integrador 1 (Pág. 6)

> 📖 **Textual del material (Pág. 5 — Desempeño de Síntesis, Desempeño 1):**
> "Responde las siguientes preguntas, luego de haber trabajado con la clase 12.
> a- ¿Cuándo se puede aplicar la Regla de Cramer?
> b- ¿Qué tipo de soluciones va a tener un sistema de ecuaciones resuelto por este método?
> c- Si la matriz de los coeficientes no es regular ¿Qué significa?
> d- ¿Cuántas soluciones se pueden obtener utilizando este método particular en un sistema de cuatro ecuaciones con cuatro incógnitas?"

> 📖 **Textual del material (Pág. 6 — Desempeños Integradores, Desempeño 1):**
> "Estos desafíos son para que los resuelvas después de haber trabajado con las cuatro clases de la unidad nº 3, o sea, toda la unidad de Sistemas de Ecuaciones.
> • Desempeño 1
> Responde, sin ayuda...
> a- ¿Qué tipo de sistemas de ecuaciones estudiamos?
> b- ¿Qué quiere decir que dos sistemas de ecuaciones sean equivalentes?
> c- ¿Cuáles son los pasos del método general de resolución?
> d- ¿Cómo puede clasificarse un sistema de ecuaciones?
> e- ¿Qué condiciones se dan desde el punto de vista matricial, para cada uno de los tipos de sistemas de ecuaciones?
> f- ¿En qué casos puede aplicarse la Regla de Cramer?"

### B. Afirmaciones Teóricas de Verdadero o Falso con Justificación Oficial (Págs. 6 y 8)

> 📖 **Textual del material (Pág. 6 — Enunciados del Desempeño Integrador 2):**
> "• Desempeño 2
> Coloca V (verdadero) o F (falso) y JUSTIFICA en cada caso:
> a- Todo sistema de ecuaciones lineales tiene solución.
> b- Un sistema homogéneo siempre tiene solución.
> c- Dos sistemas son equivalentes cuando son determinados.
> d- En un sistema determinado el número de variables independientes se calcula como el número de incógnitas menos el rango de la matriz ampliada.
> e- Un sistema que tiene 2 variables libres, es un sistema Incompatible.
> f- Si existen menos ecuaciones que incógnitas en un sistema lineal, entonces el sistema o no tiene solución, o tiene infinitas soluciones.
> g- Un sistema homogéneo siempre es Compatible indeterminado.
> h- Si el rango de la matriz de los coeficientes es igual al rango de la matriz ampliada, entonces estamos ante un sistema Incompatible.
> i- Si el determinante de la matriz de los coeficientes de un sistema es distinto de cero, podemos asegurar que el sistema tiene solución.
> j- Si el rango de la matriz de los coeficientes es distinto al rango de la matriz ampliada, eso indica que el sistema es Indeterminado."

> 📖 **Textual del material (Pág. 8 — Respuestas a algunos Desempeños Integradores, Desempeño n° 2):**
> "• Desempeño n° 2
> a- F (a veces)
> b- V
> c- F (son equivalentes cuanto tienen la misma solución)
> d- F (en un sistema indeterminado)
> e- F (es un sistema indeterminado)
> f- V
> g- F (admite siempre la solución trivial. Hay que ver si es indeterminado)
> h- F (Compatible)
> i- V
> j- F (Incompatible)"

### 📊 Tabla Comparativa y Explicación Detallada del Verdadero / Falso Oficial

| Ítem | Afirmación textual (Pág. 6) | Respuesta textual (Pág. 8) | Explicación profunda para defender en el examen oral |
| :--- | :--- | :--- | :--- |
| **a** | Todo sistema de ecuaciones lineales tiene solución. | **F (a veces)** | Solo tienen solución los sistemas **Compatibles** (Determinados o Indeterminados). Los sistemas **Incompatibles** no tienen solución. En matemática, una afirmación universal ("Todo...") es falsa si solo se cumple "a veces". |
| **b** | Un sistema homogéneo siempre tiene solución. | **V** | En un sistema homogéneo (`A . X = 0`), todos los términos independientes son cero. Por lo tanto, al reemplazar todas las incógnitas por cero (`x_1 = 0, ..., x_n = 0`), las igualdades `0 = 0` se verifican siempre. Esa es la **solución trivial**, por lo que todo sistema homogéneo es siempre **Compatible**. |
| **c** | Dos sistemas son equivalentes cuando son determinados. | **F (son equivalentes cuanto tienen la misma solución)** | Que ambos sean determinados solo dice que cada uno tiene una única solución, pero podrían ser soluciones distintas. Dos sistemas de ecuaciones son **equivalentes** si y solo si **tienen exactamente el mismo conjunto solución**. |
| **d** | En un sistema determinado el número de variables independientes se calcula como el número de incógnitas menos el rango de la matriz ampliada. | **F (en un sistema indeterminado)** | En un sistema **Compatible Determinado**, el número de incógnitas `n` es igual al rango (`n - r = 0`), por lo que **no hay variables libres / independientes** (todas las variables quedan determinadas con un único valor). El cálculo `n - r` para hallar el número de variables independientes (o libres) se aplica en un sistema **Compatible Indeterminado**. |
| **e** | Un sistema que tiene 2 variables libres, es un sistema Incompatible. | **F (es un sistema indeterminado)** | Si el sistema tiene variables libres (en este caso `n - r = 2`), significa que es **Compatible** (`r(A) = r(A') = r < n`) y que podemos darle infinitos valores reales a esas 2 variables libres, obteniendo infinitas soluciones: es un **Sistema Compatible Indeterminado**. |
| **f** | Si existen menos ecuaciones que incógnitas en un sistema lineal, entonces el sistema o no tiene solución, o tiene infinitas soluciones. | **V** | Si hay `m` ecuaciones y `n` incógnitas con `m < n`, el rango `r` nunca puede superar a la cantidad de filas `m`, luego `r ≤ m < n` (es imposible que `r = n`). Por lo tanto, **nunca puede ser Compatible Determinado**: si `r(A) ≠ r(A')` no tiene solución (Incompatible), y si `r(A) = r(A') = r < n` tiene infinitas soluciones (Compatible Indeterminado). (Y tampoco se le puede aplicar nunca la Regla de Cramer por no ser cuadrado). |
| **g** | Un sistema homogéneo siempre es Compatible indeterminado. | **F (admite siempre la solución trivial. Hay que ver si es indeterminado)** | Todo sistema homogéneo admite siempre la **solución trivial** `(0, 0, ..., 0)`. Pero puede ser **Compatible Determinado** (si `r(A) = n`, o en un sistema cuadrado si `|A| ≠ 0`, teniendo *únicamente* la solución trivial) o **Compatible Indeterminado** (si `r(A) < n`, o `|A| = 0`, admitiendo infinitas soluciones además de la trivial). |
| **h** | Si el rango de la matriz de los coeficientes es igual al rango de la matriz ampliada, entonces estamos ante un sistema Incompatible. | **F (Compatible)** | Por el Teorema de Rouché-Frobenius (condición de compatibilidad), que el rango de la matriz de los coeficientes sea igual al rango de la matriz ampliada (`r(A) = r(A')`) es justamente la condición necesaria y suficiente para que el sistema sea **Compatible** (Determinado si `r = n`, o Indeterminado si `r < n`). |
| **i** | Si el determinante de la matriz de los coeficientes de un sistema es distinto de cero, podemos asegurar que el sistema tiene solución. | **V** | Que exista `|A|` implica que `A` es cuadrada (sistema cuadrado, `m = n`), y que `|A| ≠ 0` implica que `A` es **Regular** (`r(A) = r(A') = n`). Por la Regla de Cramer, el sistema tiene solución única (`x_j = |A_j| / |A|`), siendo un **Sistema Compatible Determinado**. |
| **j** | Si el rango de la matriz de los coeficientes es distinto al rango de la matriz ampliada, eso indica que el sistema es Indeterminado. | **F (Incompatible)** | Cuando el rango de la matriz de los coeficientes es distinto del rango de la matriz ampliada (`r(A) ≠ r(A')`), el sistema no admite ninguna solución: es un **Sistema Incompatible**. |

### 📊 Tabla Resumen: Clasificación Matricial vs. Regla de Cramer (Sistemas de n incógnitas)

| Tipo de Sistema | Condición de Rangos (Método General, m × n) | Condición de Determinante en Sistema Cuadrado (m = n) | ¿Se puede aplicar Regla de Cramer? | Cantidad de soluciones |
| :--- | :--- | :--- | :--- | :--- |
| **Sistema Compatible Determinado (SCD)** | `r(A) = r(A') = n` | `∣A∣ ≠ 0` (Matriz A **Regular**) | **SÍ** (`x_j = ∣A_j∣ / ∣A∣`) | **Única solución** (un único vector `X*`) |
| **Sistema Compatible Indeterminado (SCI)** | `r(A) = r(A') = r < n` (`n - r` variables libres) | `∣A∣ = 0` (Matriz A no regular) | **NO** (usar método general) | **Infinitas soluciones** |
| **Sistema Incompatible (SI)** | `r(A) ≠ r(A')` | `∣A∣ = 0` (Matriz A no regular) | **NO** (usar método general) | **Ninguna solución** (`S = ∅`) |

---

## 🧠 Resumen esquemático de la clase

- **Método particular de resolución (Regla de Cramer):** Método directo basado en determinantes que solo sirve para casos muy especiales (sistemas cuadrados con matriz regular).
- **Sistema cuadrado:** Sistema de ecuaciones que tiene la **misma cantidad de ecuaciones que de incógnitas** (`m = n`).
- **Condiciones para aplicar la Regla de Cramer:** 1) Que el sistema tenga la misma cantidad de ecuaciones que de incógnitas (sistema cuadrado), y 2) Que el determinante de la matriz de los coeficientes sea distinto de cero (`|A| ≠ 0`, es decir, que la matriz A sea **Regular**).
- **Matriz cuadrada `A_j`:** Matriz que resulta de **reemplazar en la matriz A a la columna j por el vector de los términos independientes B**.
- **Fórmula general de la Regla de Cramer:** En `A . X = B` (con A cuadrada y regular), la única solución es el vector `X = [x_1, x_2, ..., x_n]^T` donde **`x_j = |A_j| / |A|`** para cada `j = 1, 2, ..., n`.
- **Tipo de solución obtenida por Cramer:** La solución es siempre **única**, por lo que todo sistema resuelto por Cramer es un **Sistema Compatible Determinado (SCD)**.
- **Consecuencia de `|A| = 0`:** Si en un sistema cuadrado `|A| = 0` (A no es regular), **no se puede aplicar la Regla de Cramer**, se puede asegurar que **el sistema no es Compatible Determinado**, y se debe aplicar el **método general de resolución** para determinar si es Compatible Indeterminado o Incompatible.
- **Requisito previo de ordenamiento:** El sistema debe estar **completo y ordenado** bajo la forma `A . X = B` antes de extraer `A` y `B`.
- **Matriz de insumo-producto (A):** Matriz cuadrada cuyos elementos son los **coeficientes de insumo**; se considera **productiva** si **las sumas de los elementos de cada columna son menores que 1**.
- **Modelo económico de producción:** Dado por **`(I - A) . X = D`**, donde `X` es la matriz de producción, `D` es la matriz de demanda externa e `I` es la matriz Identidad.

---

## ❓ Preguntas probables del oral

1. **¿Qué es un sistema de ecuaciones cuadrado y por qué es el primer punto que analizamos antes de aplicar la Regla de Cramer?**
   - **Respuesta:** Un sistema cuadrado es aquel que tiene la misma cantidad de ecuaciones que de incógnitas. Es el primer punto porque la Regla de Cramer trabaja con el determinante de la matriz de los coeficientes (`|A|`), y el determinante solo está definido para matrices cuadradas.

2. **¿Cuándo es posible aplicar la Regla de Cramer? Enuncie las dos condiciones exactas.**
   - **Respuesta:** La Regla de Cramer es posible aplicarla cuando: 1) se tiene un sistema de ecuaciones que tiene la misma cantidad de ecuaciones que de incógnitas (sistema cuadrado), y 2) el determinante de la matriz de los coeficientes es distinto de cero (`|A| ≠ 0`), lo que nos indica que la matriz A es Regular.

3. **En el enunciado general de la Regla de Cramer para un sistema `A . X = B`, ¿qué representa cada símbolo y cómo se define la matriz `A_j`?**
   - **Respuesta:** `A` es la matriz de los coeficientes (cuadrada y regular), `X` es el vector de las incógnitas y `B` es el vector de los términos independientes. La matriz cuadrada `A_j` se define como la matriz que resulta de reemplazar en la matriz `A` a la columna `j` por el vector de los términos independientes `B`. Entonces el valor de cada incógnita está dado por `x_j = |A_j| / |A|`.

4. **¿Qué tipo de soluciones va a tener siempre un sistema de ecuaciones resuelto por la Regla de Cramer y cómo se clasifica dicho sistema?**
   - **Respuesta:** Va a tener siempre **solución única**, y por lo tanto el sistema es siempre un **Sistema Compatible Determinado**.

5. **¿Cuántas soluciones se pueden obtener utilizando la Regla de Cramer en un sistema de cuatro ecuaciones con cuatro incógnitas?**
   - **Respuesta:** Se obtiene **una única solución** (un único vector solución `X` formado por los 4 valores correspondientes a las 4 incógnitas `x_1, x_2, x_3, x_4`).

6. **Si en un sistema cuadrado la matriz de los coeficientes no es regular, ¿qué significa y qué podemos asegurar sobre el sistema?**
   - **Respuesta:** Que la matriz de los coeficientes no sea regular significa que su determinante es igual a cero (`|A| = 0`). En ese caso no se puede resolver por la Regla de Cramer, se puede asegurar con certeza que **el sistema no es Compatible Determinado**, y hay que aplicar el método general de resolución para saber si es Compatible Indeterminado o Incompatible.

7. **¿Qué ocurre en la Regla de Cramer si `|A| ≠ 0` pero para alguna incógnita el determinante del numerador da cero (`|A_j| = 0`)? ¿Se puede seguir aplicando Cramer?**
   - **Respuesta:** Sí, se puede aplicar sin ningún problema. La condición de la Regla de Cramer exige únicamente que el determinante de la matriz de los coeficientes sea distinto de cero (`|A| ≠ 0`, porque es el divisor). Si `|A_j| = 0` y `|A| ≠ 0`, entonces el valor de esa incógnita es `x_j = 0 / |A| = 0`.

8. **¿Se puede aplicar la Regla de Cramer a un sistema homogéneo cuadrado `A . X = 0`? ¿Qué resultado arroja cuando `|A| ≠ 0`?**
   - **Respuesta:** Si el sistema homogéneo es cuadrado y `|A| ≠ 0`, sí se puede aplicar. Como el vector de términos independientes `B` es el vector nulo, al reemplazar cualquier columna `j` de `A` por `B` queda una columna de ceros, por lo que `|A_j| = 0` para todo `j`. Así, `x_j = 0 / |A| = 0` para todas las incógnitas, obteniéndose como única solución la **solución trivial**.

9. **Si existen menos ecuaciones que incógnitas en un sistema lineal, ¿se puede aplicar la Regla de Cramer? ¿Qué tipo de soluciones puede tener ese sistema?**
   - **Respuesta:** No se puede aplicar la Regla de Cramer porque el sistema no es cuadrado. Además, como el número de ecuaciones es menor que el de incógnitas, el rango nunca puede igualar al número de incógnitas, por lo que el sistema **o no tiene solución (Incompatible), o tiene infinitas soluciones (Compatible Indeterminado)**, pero nunca puede ser Compatible Determinado.

10. **¿Cuándo decimos que dos sistemas de ecuaciones son equivalentes? ¿Basta con que ambos sean Compatibles Determinados?**
    - **Respuesta:** No basta con que sean determinados. Dos sistemas de ecuaciones son equivalentes cuando **tienen la misma solución** (el mismo conjunto solución).

11. **En un sistema Compatible Determinado (como los que resuelve Cramer), ¿cuántas variables libres o independientes hay? ¿En qué tipo de sistemas se calcula el número de variables independientes como el número de incógnitas menos el rango de la matriz ampliada?**
    - **Respuesta:** En un sistema Compatible Determinado no hay variables libres (hay 0 variables libres, pues `n - r = 0`). El número de variables independientes o libres se calcula como el número de incógnitas menos el rango en un **sistema Compatible Indeterminado**.

12. **¿Qué es una matriz de insumo-producto, cómo se llaman sus elementos, cuándo se considera que es productiva y cuál es la ecuación del modelo económico que vincula la producción con la demanda externa?**
    - **Respuesta:** Es la matriz `A` cuyos elementos son los **coeficientes de insumo** de las empresas de un grupo económico. Se considera que esta matriz es **productiva** si **las sumas de los elementos de cada columna son menores que 1**. Los niveles de producción se calculan siguiendo el modelo económico **`(I - A) . X = D`**, donde `X` es la matriz de producción, `D` es la matriz de demanda externa e `I` es la matriz Identidad.

---

## 📚 Glosario de la clase

| Término | Definición breve fiel al material |
| :--- | :--- |
| **Sistema cuadrado** | Sistema de ecuaciones que tiene la misma cantidad de ecuaciones que de incógnitas. |
| **Matriz de los coeficientes (`A`)** | Matriz formada por los coeficientes que multiplican a las incógnitas del sistema completo y ordenado. |
| **Vector de las incógnitas (`X`)** | Vector columna formado por las incógnitas del sistema (`x_1, x_2, ..., x_n`). |
| **Vector de los términos independientes (`B`)** | Vector columna formado por los términos independientes del sistema escrito como `A . X = B`. |
| **Matriz Regular** | Matriz cuadrada cuyo determinante es un número distinto de cero (`∣A∣ ≠ 0`). |
| **Matriz cuadrada `A_j`** | Matriz que resulta de reemplazar en la matriz de los coeficientes `A` a la columna `j` por el vector de los términos independientes `B`. |
| **Regla de Cramer** | Método particular de resolución de sistemas de ecuaciones aplicable cuando el sistema tiene la misma cantidad de ecuaciones que de incógnitas y el determinante de la matriz de los coeficientes es distinto de cero, donde cada incógnita se calcula como `x_j = ∣A_j∣ / ∣A∣`. |
| **Sistema Compatible Determinado** | Sistema de ecuaciones que tiene solución única (`r(A) = r(A') = n`; en un sistema cuadrado equivale a `∣A∣ ≠ 0`). |
| **Sistema Compatible Indeterminado** | Sistema de ecuaciones que tiene infinitas soluciones (`r(A) = r(A') < n`), donde el número de variables independientes o libres es el número de incógnitas menos el rango de la matriz ampliada. |
| **Sistema Incompatible** | Sistema de ecuaciones que no tiene solución (`r(A) ≠ r(A')`). |
| **Sistemas equivalentes** | Dos o más sistemas de ecuaciones que tienen la misma solución. |
| **Solución trivial** | Solución en la que todas las incógnitas valen cero (`x_1 = x_2 = ... = x_n = 0`), la cual es admitida siempre por todo sistema homogéneo. |
| **Matriz de insumo-producto (`A`)** | Matriz cuadrada cuyos elementos son los coeficientes de insumo que indican cuánto se requiere de cada sector por cada peso producido. |
| **Coeficientes de insumo** | Elementos de la matriz de insumo-producto `A`. |
| **Matriz productiva** | Matriz de insumo-producto en la cual las sumas de los elementos de cada columna son menores que 1. |
| **Matriz de producción (`X`)** | Vector columna que contiene los niveles de producción de cada empresa en el modelo `(I - A) . X = D`. |
| **Matriz de demanda externa (`D`)** | Vector columna que representa la demanda externa en el modelo económico `(I - A) . X = D`. |
