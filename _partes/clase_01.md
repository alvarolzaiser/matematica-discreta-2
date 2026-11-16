# Clase 1 — Álgebra de Boole

## 🗺️ Mapa de la clase

- **1. Ubicación en la materia y motivación (Págs. 2–3)**
  - **1.1** Concepto de Matemática Discreta (conjuntos discretos), continuidad con la Lógica Simbólica Proposicional (MD1) y origen binario del Álgebra de Boole.
  - **1.2** Codificación binaria y Circuitos Lógicos como sistemas de entrada/salida.
- **2. Elementos básicos del Álgebra de Boole (Págs. 3–5)**
  - **1.3** Variables lógicas (definición, valores excluyentes 0 y 1, estados en tuberías y circuitos eléctricos).
  - **1.4** Operaciones lógicas (concepto general, diferencia con el Álgebra clásica y clasificación).
  - **1.5** Suma Lógica (`+`): definición, tabla de valores, circuito en paralelo e interpretación.
  - **1.6** Producto lógico (`.`): definición, tabla de valores, circuito en serie e interpretación.
  - **1.7** Negación o Complemento (`¯`): definición, tabla de valores, circuito inversor e interpretación.
- **3. Propiedades del Álgebra de Boole y Sistema Axiomático (Págs. 5–7)**
  - **1.8** Propiedades del Álgebra de Boole: clasificación en Axiomas y Teoremas.
  - **1.9** Axioma A1: Propiedad Conmutativa (para la suma y para el producto).
  - **1.10** Axioma A2: Propiedad Distributiva (del producto respecto de la suma y de la suma respecto del producto).
  - **1.11** Axioma A3: Elemento Neutro (propiedad de identidad para la suma y para el producto).
  - **1.12** Axioma A4: Complemento (para la suma y para el producto).
  - **1.13** Método de demostración algebraica de igualdades booleanas mediante axiomas.

### Prerrequisitos
- **De Matemática Discreta 1 (Unidad 3 — Lógica Simbólica Proposicional):**
  - Concepto de **proposición** (sentencia que es verdadera o falsa).
  - Conectores lógicos: **disyunción** (`∨`), **conjunción** (`∧`) y **negación** (`¬`), junto con sus tablas de verdad.
- **De Teoría de Conjuntos / Sistemas de Numeración:**
  - Noción de **conjunto finito** e **infinito numerable**.
  - **Sistema de numeración binario** (base 2, dígitos `0` y `1`).

---

## 1.1 Matemática Discreta, Lógica Proposicional e Introducción al Álgebra de Boole

> 📖 **Textual del material:** "Hoy damos comienzo a nuestra Matemática Discreta 2, que como ustedes recordarán recibe ese nombre ya que trabaja con conjuntos discretos, es decir conjuntos finitos o infinitos pero numerables. Y para comenzar con el estudio de esta Matemática, lo haremos continuando o ampliando, los conceptos que vimos en la unidad 3 de nuestra Matemática Discreta 1, es decir la lógica simbólica proposicional, en la que nuestras variables eran las proposiciones, sentencias que son verdaderas o son falsas. Nuestra primer unidad entonces será continuación de aquella tercera, y corresponde a un nuevo Álgebra que al principio podrá parecernos algo compleja, pero solo es porque no estamos tan familiarizados como con la clásica, éste será el Álgebra de Boole. Luego en la unidad 2 estudiaremos álgebra de Matrices, y en la unidad 3 las aplicaremos a la resolución de sistemas de ecuaciones lineales."

> 📖 **Textual del material:** "En las situaciones planteadas [1], podemos observar que según sea el estado de dos elementos, el resultado cambia. Además que el estado de esos elementos solo tiene dos posibilidades (en este caso abierta o cerrada), como así también el resultado. Estos elementos que pueden asociarse a dos estados podemos relacionarlos al sistema de numeración binario, en el que basó Boole su esquema, para formalizar su Álgebra."

**🗣️ En palabras simples:**
Antes de definir fórmulas, el material ubica dónde estamos parados: la materia se llama *Matemática Discreta* porque estudia objetos "separados" que se pueden contar uno por uno (conjuntos finitos o infinitos numerables, a diferencia de los números reales continuos del análisis matemático). El Álgebra de Boole es la continuación directa de la Lógica Proposicional de MD1: en lugar de trabajar con oraciones que son Verdaderas (V) o Falsas (F), ahora trabajamos con elementos que tienen dos estados posibles representados con el sistema binario (`0` y `1`).

**🔍 Desglose de la jerga:**
- **Conjuntos discretos:** Conjuntos cuyos elementos están aislados entre sí; el material los define explícitamente como *"conjuntos finitos o infinitos pero numerables"*.
- **Conjunto finito:** Conjunto con una cantidad limitada de elementos (por ejemplo, `{0, 1}`).
- **Conjunto infinito pero numerable:** Conjunto infinito cuyos elementos se pueden poner en correspondencia uno a uno con los números naturales `ℕ` (se pueden "enumerar": primero, segundo, tercero...).
- **Lógica simbólica proposicional:** Rama vista en la Unidad 3 de MD1 donde las variables son proposiciones.
- **Proposiciones:** *"Sentencias que son verdaderas o son falsas"* (no admiten términos medios).
- **Sistema de numeración binario:** Sistema de base 2 que utiliza únicamente dos símbolos (`0` y `1`), sobre el cual George Boole basó su esquema para formalizar su Álgebra.

**💡 Ejemplo:**
El material plantea en la figura `[1]` dos circuitos de tuberías de agua con dos llaves `A` y `B`, donde cada llave solo tiene dos estados posibles (abierta o cerrada) y el resultado (si llega o no agua al recipiente inferior) también tiene solo dos posibilidades:
- **Circuito de tuberías 1 (llaves A y B en ramas paralelas):** El agua llega al recipiente inferior cuando la llave `A` o la llave `B` está abierta (situaciones A2, A3 y A4).
- **Circuito de tuberías 2 (llaves A y B en la misma tubería en serie):** El agua llega al recipiente inferior únicamente cuando la llave `A` y la llave `B` están abiertas simultáneamente (situación A4).

**🔗 Conexiones:**
- Conecta hacia atrás con **Lógica Simbólica Proposicional (MD1, Unidad 3)**: las proposiciones (V/F) pasan a ser variables lógicas (`1`/`0`), y los conectores `∨`, `∧`, `¬` pasan a ser las operaciones `+`, `.`, `¯`.
- Conecta hacia adelante con el resto de la **Unidad 1 (Clases 1 a 4)**: todo el diseño y simplificación de circuitos digitales y compuertas lógicas se apoya en este modelo de dos estados.

**⚠️ Precisiones / errores comunes:**
- Si el profesor pregunta al inicio del oral *"¿Por qué la materia se llama Matemática Discreta?"*, no responder vagamente "porque ve cosas de computación". La respuesta exacta del apunte es: **porque trabaja con conjuntos discretos, es decir, conjuntos finitos o infinitos pero numerables**.
- No confundir el Álgebra clásica (que opera con números reales o enteros en general) con el Álgebra de Boole (que opera sobre un conjunto de dos estados asociados al sistema binario).

**🎤 Cómo decirlo en el oral:**
> "La Matemática Discreta recibe ese nombre porque trabaja con conjuntos discretos, es decir, conjuntos finitos o infinitos pero numerables. En esta primera unidad ampliamos la lógica simbólica proposicional de Matemática Discreta 1 —donde las variables eran proposiciones, sentencias que son verdaderas o falsas— hacia el Álgebra de Boole. Boole basó su esquema para formalizar su Álgebra en el sistema de numeración binario, modelando elementos y resultados que solo tienen dos estados o posibilidades."

---

## 1.2 Codificación Binaria y Circuitos Lógicos como Sistemas

> 📖 **Textual del material:** "Las computadoras usan codificación binaria, entonces una unidad elemental de información puede tomar solamente dos valores, 0 ó 1, por lo que la base de las computadoras son los circuitos lógicos como el que se muestra en la figura, los cuales son analizados mediante el Álgebra de Boole. En esta figura [2] podemos considerar al circuito como un sistema que transforma las señales de entrada, que serían la posición de los interruptores A B y C, en señales de salida, que sería el estado de la lámpara."

**🗣️ En palabras simples:**
Como adentro de una computadora la unidad mínima de información (el bit) solo vale `0` o `1`, las computadoras están construidas con **circuitos lógicos**. Un circuito lógico funciona como una "caja" (un sistema): recibe **señales de entrada** (por ejemplo, si los interruptores `A`, `B` y `C` están abiertos o cerrados) y devuelve **señales de salida** (por ejemplo, si la lámpara `L` queda encendida o apagada). El Álgebra de Boole es la herramienta matemática para analizar estos circuitos.

**🔍 Desglose de la jerga:**
- **Codificación binaria:** Representación de la información utilizando únicamente dos símbolos (`0` y `1`).
- **Unidad elemental de información:** La mínima porción de información en un sistema digital (conocida en informática como *bit*), que *"puede tomar solamente dos valores, 0 ó 1"*.
- **Circuito lógico:** Dispositivo físico o esquemático que constituye la base de las computadoras y cuyo comportamiento se analiza mediante el Álgebra de Boole.
- **Sistema:** Modelo que transforma señales de entrada en señales de salida.
- **Señales de entrada:** Variables independientes que ingresan al sistema (en la figura `[2]`, la posición de los interruptores `A`, `B` y `C`).
- **Señales de salida:** Resultado producido por el sistema en función de las entradas (en la figura `[2]`, el estado de la lámpara `L`).

**💡 Ejemplo:**
En la figura `[2]` del material se muestra un circuito eléctrico con una **Fuente**, tres **Interruptores** (`A`, en serie con el paralelo entre `B` y `C`) y una **Lámpara** (`L`), junto a su diagrama en bloques:
- **Entradas:** Posición de los interruptores `A`, `B` y `C`.
- **Salida:** Estado de la lámpara `L` (que encenderá si `A` está cerrado y al menos uno entre `B` y `C` está cerrado; en notación booleana de las clases siguientes: `L = A • (B + C)`).

**🔗 Conexiones:**
- Este concepto de circuito como sistema con entradas y salidas es la base directa de las **Funciones Booleanas**, las **Tablas de Verdad** y las **Compuertas Lógicas** que se desarrollan en las Clases 2, 3 y 4.

**⚠️ Precisiones / errores comunes:**
- Distinguir claramente qué es **entrada** y qué es **salida** en el ejemplo del apunte: los interruptores son las *señales de entrada* (lo que uno acciona) y la lámpara es la *señal de salida* (el resultado observable).

**🎤 Cómo decirlo en el oral:**
> "Dado que las computadoras usan codificación binaria, una unidad elemental de información puede tomar solamente dos valores, 0 ó 1. Por eso la base de las computadoras son los circuitos lógicos, que se analizan mediante el Álgebra de Boole. Podemos considerar a un circuito lógico como un sistema que transforma las señales de entrada —como la posición de los interruptores A, B y C— en señales de salida —como el estado de la lámpara L—."

---

## 1.3 Variables Lógicas

> 📖 **Textual del material:** "A continuación definiremos los elementos básicos con los que se define el Álgebra de Boole, es decir las variables y las operaciones.
> · Variables lógicas: solo pueden tomar un valor entre dos opciones excluyentes, 0 ó 1. En una tubería una llave puede estar abierta (1) o cerrada (0), en un circuito eléctrico un interruptor puede estar abierto (0) o cerrado (1), y una lámpara en el mismo puede estar apagada (0) o encendida (1). Por lo tanto el estado de los distintos elementos de un circuito, se describe usando variables lógicas."

**🗣️ En palabras simples:**
Una **variable lógica** (representada con letras como `A`, `B`, `C`) es un símbolo que representa el estado de un elemento, con la restricción de que **solo puede valer `0` o `1`**, nunca los dos a la vez ni ningún otro número. Sirve para describir matemáticamente en qué estado está cada parte de un circuito.

**🔍 Desglose de la jerga:**
- **Elementos básicos con los que se define el Álgebra de Boole:** Son dos: las **variables** y las **operaciones**.
- **Opciones excluyentes (0 ó 1):** Significa que si la variable toma el valor `0`, no puede tomar el valor `1` al mismo tiempo, y viceversa (principio del tercero excluido y no contradicción llevado al sistema binario).
- **Convención de asignación de estados en el material:**

| Sistema físico | Elemento | Estado asociado al valor `0` | Estado asociado al valor `1` | ¿Por qué? (Contexto adicional) |
| :--- | :--- | :--- | :--- | :--- |
| **Tubería** | Llave de paso | Cerrada (`0`) | Abierta (`1`) | Llave abierta (`1`) deja pasar el agua; cerrada (`0`) bloquea el paso. |
| **Circuito eléctrico** | Interruptor | Abierto (`0`) | Cerrado (`1`) | Interruptor cerrado (`1`) cierra el puente metálico y deja pasar la corriente; abierto (`0`) corta el cable y no pasa corriente. |
| **Circuito eléctrico** | Lámpara | Apagada (`0`) | Encendida (`1`) | Lámpara encendida (`1`) indica presencia de corriente/luz; apagada (`0`) ausencia. |

**💡 Ejemplo:**
Si en un circuito eléctrico el interruptor `A` está cerrado (deja pasar corriente) y el interruptor `B` está abierto (no deja pasar corriente), describimos sus estados mediante las variables lógicas `A = 1` y `B = 0`.

**🔗 Conexiones:**
- Equivale a las **variables proposicionales** (`p`, `q`, `r`) de MD1, reemplazando Verdadero por `1` y Falso por `0`.
- Son los operandos sobre los que actúan las **operaciones lógicas** (Sección 1.4).

**⚠️ Precisiones / errores comunes:**
- **¡Trampa clásica de examen oral!** Mirá la diferencia entre una **llave de agua** y un **interruptor eléctrico**:
  - En una **tubería**, **abierta = `1`** y **cerrada = `0`**.
  - En un **circuito eléctrico**, **interruptor abierto = `0`** e **interruptor cerrado = `1`**.
  - *¿Por qué es al revés la palabra "abierto/cerrado"?* (Explicación adicional): Porque cuando "abrís" una canilla el agua pasa (`1`), pero cuando "abrís" un interruptor eléctrico levantás la llave, cortás el contacto del cable y la corriente NO pasa (`0`); en cambio, cuando "cerrás" el interruptor, unís los contactos y la corriente SÍ pasa (`1`). En ambos casos, **`1` significa que el flujo (agua o corriente) pasa**, y **`0` que no pasa**.

**🎤 Cómo decirlo en el oral:**
> "Los elementos básicos con los que se define el Álgebra de Boole son las variables y las operaciones. Las variables lógicas son aquellas que solo pueden tomar un valor entre dos opciones excluyentes, 0 ó 1, y se usan para describir el estado de los distintos elementos de un circuito. Por ejemplo, en una tubería una llave puede estar abierta (1) o cerrada (0); mientras que en un circuito eléctrico un interruptor puede estar abierto (0) o cerrado (1), y una lámpara puede estar apagada (0) o encendida (1)."

---

## 1.4 Operaciones Lógicas (Concepto General)

> 📖 **Textual del material:** "· Operaciones lógicas: las operaciones lógicas permiten combinar variables para poder obtener otras variables. Si bien podrás ver que reciben nombres similares o iguales a algunas operaciones del Álgebra clásica, debes tener en cuenta que no tienen nada que ver con ellas, así que en esta parte deberás hacer un pequeño gran esfuerzo para abrir un poco más la mente y poder formar nuevas estructuras, o también podría decirse desestructurar las que ya tienes. Las operaciones son, suma lógica, producto lógico y negación."

**🗣️ En palabras simples:**
Las **operaciones lógicas** son las reglas que nos permiten juntar una o más variables lógicas (de entrada) para producir una nueva variable lógica (de salida). Aunque se llamen "suma" y "producto", **no son la suma y multiplicación de números comunes** (por ejemplo, acá `1 + 1` no da `2`, sino `1`), sino operaciones lógicas sobre estados binarios.

**🔍 Desglose de la jerga:**
- **Combinar variables para poder obtener otras variables:** Es la propiedad de **ley de composición interna / cerradura** (contexto adicional): al operar variables que valen `0` o `1`, el resultado vuelve a ser otra variable lógica que solo vale `0` o `1`.
- **Diferencia con el Álgebra clásica:** Comparten nombres (*suma*, *producto*) y símbolos (`+`, `.`) porque cumplen axiomas parecidos, pero su significado y sus tablas de valores son puramente lógicos, no aritméticos.
- **Las tres operaciones básicas del Álgebra de Boole:**
  1. **Suma lógica (`+`)**
  2. **Producto lógico (`.`)**
  3. **Negación o Complemento (`¯`)**

**💡 Ejemplo:**
Si combinamos dos variables lógicas `A` y `B` mediante la suma lógica, obtenemos una nueva variable lógica `F = A + B`.

**🔗 Conexiones:**
- Cada una de estas tres operaciones se corresponde con un conector lógico de MD1 (`∨`, `∧`, `¬`) y, como se verá en la Clase 2, con una **compuerta lógica** básica (OR, AND, NOT).

**⚠️ Precisiones / errores comunes:**
- Si el profesor pregunta *"¿Cuáles son las operaciones lógicas del Álgebra de Boole?"*, nombrá las tres exactas: **suma lógica, producto lógico y negación (o complemento)**. No existen "resta lógica" ni "división lógica" en el Álgebra de Boole.

**🎤 Cómo decirlo en el oral:**
> "Las operaciones lógicas permiten combinar variables lógicas para poder obtener otras variables lógicas. Aunque reciben nombres similares o iguales a las operaciones del Álgebra clásica, no tienen nada que ver con la aritmética tradicional. Las tres operaciones básicas del Álgebra de Boole son la suma lógica, el producto lógico y la negación o complemento."

---

## 1.5 Suma Lógica (`+`)

> 📖 **Textual del material:** "- Suma Lógica (+): esta operación la podemos relacionar con el conector lógico “∨” (disyunción) que estudiamos en lógica proposicional de la MD1. En el Álgebra de Boole esta operación se define de la siguiente manera:
>
> | A | B | A + B |
> | :-: | :-: | :-: |
> | 0 | 0 | 0 |
> | 0 | 1 | 1 |
> | 1 | 0 | 1 |
> | 1 | 1 | 1 |
>
> Y lo podemos asociar a una situación de un circuito eléctrico como el siguiente. (F = A + B)
> En este circuito podemos observar que el estado encendido (1) de la lámpara, se dará cuando al menos uno de los interruptores esté cerrado (1).
> La suma lógica tendrá un valor de 1 cuando al menos una de las variables tenga el valor 1, es decir que será 0, solo cuando todas las variables sumadas sean 0."

**🗣️ En palabras simples:**
La **suma lógica** (`A + B`) equivale al **"O" inclusivo (disyunción `∨`)** de MD1. Da como resultado `1` si **al menos una** de las variables vale `1` (alcanza con que una sola valga `1`, o las dos). Solo da `0` cuando **todas** las variables sumadas valen `0`. Físicamente se representa con dos interruptores conectados **en paralelo**: si cerrás cualquiera de los dos (o ambos), la corriente pasa y la lámpara se enciende.

**🔍 Desglose de la jerga:**
- **Símbolo `+`:** Signo de la suma lógica (se lee *"A más B"* o *"A o B"*).
- **Conector lógico `∨` (disyunción):** Conector de la lógica proposicional que es verdadero cuando al menos una proposición es verdadera.
- **Circuito asociado (`F = A + B`):** Circuito eléctrico con dos interruptores en ramas **en paralelo** conectadas a la fuente y a la lámpara `F`.
- **"Cuando al menos una de las variables tenga el valor 1":** Incluye tanto el caso en que una sola vale `1` (`0 + 1 = 1`, `1 + 0 = 1`) como el caso en que ambas valen `1` (`1 + 1 = 1`).
- **"Será 0, solo cuando todas las variables sumadas sean 0":** Condición necesaria y suficiente para que la suma lógica valga `0` (`0 + 0 = 0`).

**💡 Ejemplo:**
En el circuito eléctrico de la página 4 para `F = A + B`:
- Si el interruptor `A` está abierto (`0`) y el interruptor `B` está cerrado (`1`), la corriente pasa por la rama de `B`, por lo que `F = 0 + 1 = 1` (lámpara encendida).
- Si ambos interruptores están cerrados (`A = 1` y `B = 1`), la corriente también llega a la lámpara, por lo que `F = 1 + 1 = 1` (lámpara encendida).

**🔗 Conexiones:**
- **Con MD1:** Disyunción inclusiva (`∨`).
- **Con circuitos eléctricos:** Conexión de interruptores **en paralelo**.
- **Con Clase 2:** Compuerta lógica **OR**.

**⚠️ Precisiones / errores comunes:**
- **¡Cuidado con `1 + 1 = 1`!** En el Álgebra de Boole `1 + 1 = 1` (no `2`, ni `0` con acarreo como en la suma aritmética binaria). Si dos interruptores en paralelo están cerrados, la lámpara simplemente está encendida (`1`), no "doblemente encendida".
- Es una disyunción **inclusiva** ("al menos una"), no exclusiva.

**🎤 Cómo decirlo en el oral:**
> "La suma lógica, simbolizada con el signo más (+), se relaciona con el conector lógico '∨' (disyunción) de la lógica proposicional. La suma lógica tendrá un valor de 1 cuando al menos una de las variables tenga el valor 1; es decir que será 0 solo cuando todas las variables sumadas sean 0. Así: 0+0=0, 0+1=1, 1+0=1 y 1+1=1. En un circuito eléctrico se asocia a interruptores en paralelo (F = A + B), donde la lámpara estará encendida (1) cuando al menos uno de los interruptores esté cerrado (1)."

---

## 1.6 Producto Lógico (`.`)

> 📖 **Textual del material:** "- Producto lógico ( . ): si la relacionamos con lo visto en lógica proposicional de MD1, esta operación sería el conector lógico “∧” (conjunción). En el Álgebra de Boole esta operación producto se define de la siguiente manera:
>
> | A | B | A + B |
> | :-: | :-: | :-: |
> | 0 | 0 | 0 |
> | 0 | 1 | 0 |
> | 1 | 0 | 0 |
> | 1 | 1 | 1 |
>
> Y lo podemos asociar a una situación de un circuito eléctrico como el siguiente. (F = A . B)
> En este circuito podemos observar que el estado encendido (1) de la lámpara, se dará cuando los dos interruptores estén cerrados (1).
> El producto lógico tendrá un valor de 1 sólo cuando todas las variables tengan el valor 1, es decir que siempre que en el producto haya un valor 0, sin importar la cantidad de 1, el resultado será 0."

**🗣️ En palabras simples:**
El **producto lógico** (`A . B` o `A • B`) equivale al **"Y" (conjunción `∧`)** de MD1. Es exigente: solo da `1` cuando **todas** las variables valen `1`. Si aunque sea una sola variable vale `0` (aunque haya cien variables que valgan `1`), todo el producto se hace `0`. Físicamente se representa con dos interruptores conectados **en serie** (uno detrás del otro en el mismo cable): para que pase la corriente y se encienda la lámpara, tienen que estar cerrados **los dos**.

**🔍 Desglose de la jerga:**
- **Símbolo `.` o `•` (o yuxtaposición sin signo):** Signo del producto lógico (se lee *"A por B"* o *"A y B"*).
- **Conector lógico `∧` (conjunción):** Conector de la lógica proposicional que es verdadero únicamente cuando todas las proposiciones son verdaderas.
- **Circuito asociado (`F = A . B`):** Circuito eléctrico con dos interruptores conectados **en serie** junto a la fuente y la lámpara `F`.
- **"Tendrá un valor de 1 sólo cuando todas las variables tengan el valor 1":** Condición necesaria y suficiente para que el producto valga `1` (`1 . 1 = 1`).
- **"Siempre que en el producto haya un valor 0, sin importar la cantidad de 1, el resultado será 0":** Regla práctica fundamental para evaluar productos de cualquier cantidad de variables.

**💡 Ejemplo:**
Si tenemos el producto de cuatro variables `A . B . C . D` y sabemos que `A = 1`, `B = 1`, `C = 0`, `D = 1`, como hay un `0` en el producto, sin importar la cantidad de `1`, el resultado es `1 . 1 . 0 . 1 = 0`.

**🔗 Conexiones:**
- **Con MD1:** Conjunción (`∧`).
- **Con circuitos eléctricos:** Conexión de interruptores **en serie**.
- **Con Clase 2:** Compuerta lógica **AND** y propiedad de **Elemento Nulo o Absorbente** (`A • 0 = 0`).

**⚠️ Precisiones / errores comunes:**
- **¡Errata tipográfica en el PDF oficial (Página 4)!** En la tabla del Producto lógico de la página 4, el encabezado de la tercera columna quedó impreso por error como `A + B` (copiado de la tabla anterior), pero los valores de la columna (`0, 0, 0, 1`) y la fórmula del circuito (`F = A . B`) corresponden a **`A . B`**. Tenelo presente por si el profesor muestra la página del apunte.
- Notación: en la página 6 el material también escribe el producto sin punto entre paréntesis, por ejemplo `(Ā + B) (Ā + B̄)`, igual que en el álgebra común.

**🎤 Cómo decirlo en el oral:**
> "El producto lógico, simbolizado con un punto (.), se relaciona con el conector lógico '∧' (conjunción) de la lógica proposicional. El producto lógico tendrá un valor de 1 sólo cuando todas las variables tengan el valor 1; es decir que siempre que en el producto haya un valor 0, sin importar la cantidad de 1, el resultado será 0. Así: 0.0=0, 0.1=0, 1.0=0 y 1.1=1. En un circuito eléctrico se asocia a interruptores en serie (F = A . B), donde la lámpara se encenderá (1) únicamente cuando los dos interruptores estén cerrados (1)."

---

## 1.7 Negación o Complemento (`¯`)

> 📖 **Textual del material:** "- Negación o Complemento ( _ ): si la relacionamos con lo estudiado en lógica proposicional de MD 1, correspondería al conector “¬” esta operación se aplica sobre una sola variable, y lo que hace es invertir el valor de la misma. En Álgebra de Boole se la define del siguiente modo [3].
>
> | A | Ā |
> | :-: | :-: |
> | 0 | 0 |
> | 1 | 1 |
>
> Y lo podemos asociar a una situación de un circuito eléctrico como el siguiente. (F = Ā)
> En este circuito podemos observar que el estado encendido (1) de la lámpara, se dá cuando el estado del (0)."

*(Nota de corrección sobre la tabla [3] impresa en el material: como se detalla en Precisiones, la tabla impresa en la pág. 5 tiene una errata tipográfica; dado que la operación invierte el valor de la variable, la tabla correcta es para `A = 0 → Ā = 1` y para `A = 1 → Ā = 0`).*

**🗣️ En palabras simples:**
La **negación o complemento** (`Ā`, una barra horizontal arriba de la letra) equivale al **"NO" (`¬`)** de MD1. A diferencia de la suma y el producto (que necesitan al menos dos variables), la negación se aplica sobre **una sola variable** (es una operación unaria) y simplemente **invierte su valor**: si `A` vale `0`, su complemento `Ā` vale `1`; si `A` vale `1`, su complemento `Ā` vale `0`.

**🔍 Desglose de la jerga:**
- **Símbolo `¯` (barra superior o sobrelínea):** Se coloca sobre la variable (`Ā`) y se lee *"A negado"* o *"complemento de A"*.
- **Conector `¬`:** Conector de negación de la lógica proposicional de MD1.
- **"Se aplica sobre una sola variable":** En jerga algebraica (contexto adicional), es una **operación unaria** (o monaria), mientras que la suma y el producto son **operaciones binarias**.
- **"Lo que hace es invertir el valor de la misma":** Transforma el `0` en `1` y el `1` en `0`.

### Tabla comparativa de las tres operaciones lógicas básicas

| Operación | Símbolo en Boole | Conector en MD1 | Cantidad de variables | ¿Cuándo vale `1`? | ¿Cuándo vale `0`? | Circuito asociado |
| :--- | :-: | :-: | :-: | :--- | :--- | :--- |
| **Suma Lógica** | `A + B` | Disyunción (`∨`) | 2 o más (binaria) | Cuando **al menos una** variable vale `1` | **Solo** cuando **todas** valen `0` | Interruptores en **paralelo** |
| **Producto Lógico** | `A . B` o `A • B` | Conjunción (`∧`) | 2 o más (binaria) | **Sólo** cuando **todas** las variables valen `1` | Siempre que haya **al menos un `0`** | Interruptores en **serie** |
| **Negación o Complemento** | `Ā` | Negación (`¬`) | 1 sola (unaria) | Cuando la variable original vale `0` | Cuando la variable original vale `1` | Interruptor inversor (`F = Ā`) |

**💡 Ejemplo:**
- Si `A = 0`, entonces `Ā = 1`.
- Si `A = 1`, entonces `Ā = 0`.
- En el circuito de `F = Ā` (página 5): la lámpara `F` está encendida (`1`) cuando el interruptor `A` está abierto (`0`), y se apaga (`0`) cuando el interruptor `A` se cierra (`1`).

**🔗 Conexiones:**
- **Con MD1:** Negación (`¬`).
- **Con Axioma A4 (Sección 1.12):** Define algebraicamente al complemento mediante `A + Ā = 1` y `A • Ā = 0`.
- **Con Clase 2:** Compuerta lógica **NOT** (inversor), Teorema de **Involución** (doble negación) y Leyes de **De Morgan**.

**⚠️ Precisiones / errores comunes:**
- **¡Doble errata de imprenta en la Página 5 del PDF oficial!**
  1. En la tabla `[3]` de la página 5, las filas quedaron impresas como `0 | 0` y `1 | 1`. Eso contradice la propia definición textual del párrafo anterior (*"lo que hace es invertir el valor de la misma"*) y la explicación del circuito (*"el estado encendido (1) de la lámpara, se dá cuando el estado del [interruptor es] (0)"*). La tabla correcta de la negación es: para `A = 0`, `Ā = 1`; y para `A = 1`, `Ā = 0`.
  2. En la oración debajo del circuito de la página 5 falta la palabra *"interruptor es"*: quedó impreso *"cuando el estado del (0)"*.
- En el circuito eléctrico de `F = Ā` dibujado en el apunte (el interruptor en paralelo con la lámpara), físicamente la idea pedagógica del autor es que al cerrar el interruptor (`A = 1`) la corriente se desvía por el interruptor sin resistencia y la lámpara se apaga (`F = 0`), y al abrir el interruptor (`A = 0`) la corriente pasa por la lámpara y se enciende (`F = 1`).

**🎤 Cómo decirlo en el oral:**
> "La negación o complemento, simbolizada con una barra superior sobre la variable (Ā), se relaciona con el conector '¬' de la lógica proposicional de MD1. Esta operación se aplica sobre una sola variable y lo que hace es invertir el valor de la misma: si A vale 0, Ā vale 1; y si A vale 1, Ā vale 0. En el circuito asociado (F = Ā), el estado encendido (1) de la lámpara se da cuando el estado del interruptor es abierto (0)."

---

## 1.8 Propiedades del Álgebra de Boole: Axiomas y Teoremas

> 📖 **Textual del material:** "· Propiedades del Álgebra de Boole. Dentro de las propiedades del Álgebra de Boole haremos la distinción en dos grandes grupos, aquellas a las que llamamos Axiomas, que son la base de las demás, ya que ellas se toman como válidas o ciertas sin la necesidad de demostrar nada; y el otro grupo serán aquellas a las que llamamos Teoremas, que no se toman como válidas hasta haberlas demostrado lógicamente.
> Veamos entonces cuales son los axiomas que constituyen la base de este Algebra:"

**🗣️ En palabras simples:**
Todas las reglas o propiedades del Álgebra de Boole se dividen en dos categorías:
1. **Axiomas:** Son las reglas "de fábrica", el punto de partida. Se aceptan como verdaderas directamente, **sin demostración**, porque sobre ellas se construye todo lo demás.
2. **Teoremas:** Son propiedades que **no** se aceptan porque sí; para poder darlas por válidas, primero hay que **demostrarlas lógicamente** usando los axiomas (esto se hace en la Clase 2).

**🔍 Desglose de la jerga:**
- **Propiedades del Álgebra de Boole:** Leyes algebraicas (igualdades) que cumplen las variables y operaciones booleanas.
- **Axiomas:** Propiedades que *"son la base de las demás, ya que ellas se toman como válidas o ciertas sin la necesidad de demostrar nada"*.
- **Teoremas:** Propiedades *"que no se toman como válidas hasta haberlas demostrado lógicamente"*.

| Grupo de propiedades | ¿Requieren demostración? | Rol en el Álgebra de Boole | ¿Cuáles son en el material? |
| :--- | :-: | :--- | :--- |
| **Axiomas** | **No** (se toman como válidos o ciertos sin demostrar nada) | Son la **base** de las demás propiedades | **A1** (Conmutativa), **A2** (Distributiva), **A3** (Elemento Neutro), **A4** (Complemento) — *Clase 1* |
| **Teoremas** | **Sí** (no se toman como válidos hasta demostrarlos lógicamente) | Se deducen a partir de los axiomas | Idempotencia, Involución, Elemento Nulo, Absorción, Asociativa, De Morgan, etc. — *Clase 2* |

**🧩 Idea de la demostración:**
Esta sección establece justamente el criterio epistemológico de demostración del curso: los axiomas no se demuestran (son los ladrillos iniciales), mientras que todo teorema se demuestra transformando algebraicamente un miembro de la igualdad en el otro aplicando paso a paso los axiomas (y teoremas ya demostrados).

**🤔 Intuición:**
En cualquier sistema matemático no se puede demostrar absolutamente todo desde la nada, porque caeríamos en un círculo vicioso infinito (para demostrar A necesito B, para B necesito C...). Por eso se elige un conjunto mínimo de verdades evidentes llamadas **Axiomas** (sistema axiomático de Huntington para el Álgebra de Boole, contexto adicional) y de ahí se deducen los **Teoremas**.

**💡 Ejemplo:**
- `A + 0 = A` es un **Axioma** (Elemento Neutro, A3a): se acepta directamente por definición.
- `A + A = A` (Idempotencia, que se verá en la Clase 2) es un **Teorema**: aunque parezca obvio mirando la tabla de verdad, dentro del sistema axiomático hay que demostrarlo usando A3, A4 y A2.

**🔗 Conexiones:**
- Conecta directamente con los cuatro axiomas **A1, A2, A3 y A4** de esta Clase 1 y con todos los **Teoremas del Álgebra de Boole** de la Clase 2.

**⚠️ Precisiones / errores comunes:**
- **¡Pregunta fija de examen oral!** *"¿Cuál es la diferencia entre un axioma y un teorema en el Álgebra de Boole?"* Usá las palabras exactas del material: los **axiomas** son la base de las demás propiedades y se toman como válidos o ciertos sin la necesidad de demostrar nada; los **teoremas** no se toman como válidos hasta haberlos demostrado lógicamente.
- **¡Ojo con la Propiedad Asociativa!** En muchos libros generales o en el álgebra común la asociativa se da junto con la conmutativa, pero **en este apunte los Axiomas son únicamente cuatro: A1 (Conmutativa), A2 (Distributiva), A3 (Elemento Neutro) y A4 (Complemento)**. La propiedad Asociativa aparece recién en la Clase 2 dentro de los Teoremas. No la metas en la lista de axiomas si el profesor pide enumerar los axiomas de la Clase 1.

**🎤 Cómo decirlo en el oral:**
> "Dentro de las propiedades del Álgebra de Boole hacemos la distinción en dos grandes grupos: por un lado los Axiomas, que son la base de las demás propiedades ya que se toman como válidos o ciertos sin la necesidad de demostrar nada; y por otro lado los Teoremas, que no se toman como válidos hasta haberlos demostrado lógicamente. Los axiomas que constituyen la base de este Álgebra son cuatro: A1 Propiedad Conmutativa, A2 Propiedad Distributiva, A3 Elemento Neutro y A4 Complemento."

---

## 1.9 Axioma A1: Propiedad Conmutativa

> 📖 **Textual del material:** "· A1: PROPIEDAD CONMUTATIVA
> Para cualesquiera dos elementos, A y B pertenecientes a M, se cumple:
> a- A + B = B + A
> b- A • B = B • A"

**🗣️ En palabras simples:**
El orden en que escribís las variables al sumarlas lógicamente o al multiplicarlas lógicamente **no altera el resultado**. Da lo mismo hacer `A + B` que `B + A`, y da lo mismo hacer `A • B` que `B • A`.

**🔍 Desglose de la jerga:**
- **"Para cualesquiera dos elementos, A y B pertenecientes a M":** Corresponde al cuantificador universal (`∀ A, B ∈ M`). Indica que la igualdad vale sin importar qué elementos del conjunto soporte `M` del Álgebra de Boole sean `A` y `B` (tanto si son variables simples con valores `0` o `1` como si son expresiones booleanas del conjunto `M`).
- **`M`:** Es el conjunto de elementos sobre el cual está definida el Álgebra de Boole (en nuestro caso binario básico, `M = {0, 1}` o el conjunto de variables/expresiones lógicas).
- **Parte `a- A + B = B + A`:** Conmutatividad de la **suma lógica**.
- **Parte `b- A • B = B • A`:** Conmutatividad del **producto lógico**.

**🧩 Idea de la demostración:**
Por ser el **Axioma A1**, se toma como válido o cierto sin necesidad de demostración algebraica. (Se puede verificar por inspección en las tablas de verdad de la suma y del producto: las filas `A=0, B=1` y `A=1, B=0` arrojan exactamente el mismo resultado en ambas operaciones).

**🤔 Intuición:**
En un circuito en paralelo (`A + B`), no importa cuál de los dos cables dibujes arriba y cuál abajo; y en un circuito en serie (`A • B`), no importa si la corriente pasa primero por el interruptor `A` y después por el `B` o al revés: el estado de la lámpara será idéntico.

**💡 Ejemplo:**
En el **Desempeño 1, ítem c** (página 6 del material):
Para simplificar `J . K̄ + K . J`, en el primer paso se transforma `K . J` en `J . K` aplicando **A1b (Propiedad Conmutativa del producto)**, obteniendo `J . K̄ + J . K`, lo cual permite luego extraer el factor común `J` en el mismo orden.

**🔗 Conexiones:**
- Se utiliza constantemente en combinación con **A2 (Distributiva)** para acomodar el orden de los factores antes de sacar factor común o distribuir.

**⚠️ Precisiones / errores comunes:**
- Al enunciar A1 en el oral, no olvides mencionar el encabezado cuantificado: **"Para cualesquiera dos elementos, A y B pertenecientes a M, se cumple..."** y dar **ambas** igualdades (`a-` para la suma y `b-` para el producto).

**🎤 Cómo decirlo en el oral:**
> "El Axioma A1 es la Propiedad Conmutativa. Enuncia que para cualesquiera dos elementos, A y B pertenecientes a M, se cumple: a) para la suma lógica, A + B = B + A; y b) para el producto lógico, A • B = B • A."

---

## 1.10 Axioma A2: Propiedad Distributiva

> 📖 **Textual del material:** "· A2: PROPIEDAD DISTRIBUTIVA
> Para cualesquiera elementos, A, B y C pertenecientes a M, se cumple:
> a- A • (B + C) = (A • B) + (A • C)
> b- A + (B • C) = (A + B) • (A + C)"

> 📖 **Textual del material:** "Para que podamos aplicar el Algebra de Boole en la resolución de ejercicios es de gran importancia conocer e incorporar los axiomas que se han enunciado hoy. Debe recordarlos y tratar de comprender sus enunciados más allá de las letras que se utilicen. ¿Qué le quiero decir con eso? Con un ejemplo intentaré explicarlo. El axioma de la propiedad distributiva dice A + B . C = (A + B) . (A + C), eso mismo lo podría decir así, 1 + 2 . 3 = (1 + 2) . (1 + 3) , o también podría ser `[símbolo 1]` + `[símbolo 2]` . `[símbolo 3]` = (`[símbolo 1]` + `[símbolo 2]`) . (`[símbolo 1]` + `[símbolo 3]`) Es decir, trate de entender el enunciado más allá de los símbolos empleados."

**🗣️ En palabras simples:**
El Axioma A2 tiene dos partes:
- **Parte a (`A • (B + C) = (A • B) + (A • C)`):** Es la distributiva del producto respecto de la suma, idéntica a la que conocemos de toda la vida en el álgebra común.
- **Parte b (`A + (B • C) = (A + B) • (A + C)`):** Es la distributiva de la **suma respecto del producto**. ¡En el álgebra de números comunes esto sería falso, pero en el Álgebra de Boole es totalmente cierto!
Además, como toda igualdad, se puede usar de izquierda a derecha (**distribuir**) o de derecha a izquierda (**sacar factor común**, tanto factor común producto como "factor común suma").

**🔍 Desglose de la jerga:**
- **"Para cualesquiera elementos, A, B y C pertenecientes a M":** Cuantificador universal (`∀ A, B, C ∈ M`) sobre tres elementos cualesquiera del conjunto `M`.
- **Parte `a- A • (B + C) = (A • B) + (A • C)`:** Distributiva del **producto respecto de la suma**.
  - De izquierda a derecha: se distribuye `A •` sobre cada término de `(B + C)`.
  - De derecha a izquierda: se extrae `A •` como factor común de ambos paréntesis.
- **Parte `b- A + (B • C) = (A + B) • (A + C)`:** Distributiva de la **suma respecto del producto**.
  - De izquierda a derecha: se distribuye `A +` sobre cada factor de `(B • C)`.
  - De derecha a izquierda: si dos paréntesis que se multiplican comparten un mismo término sumado (`A + ...`), se puede extraer `A +` hacia afuera quedando `A + (B • C)`.
- **"Entender el enunciado más allá de los símbolos empleados" (Pág. 7):** Las letras `A`, `B` y `C` son "moldes" o lugares vacíos. En el lugar de `A` puede haber una variable negada (`Ā`), u otra expresión entera.

**🧩 Idea de la demostración:**
Por ser el **Axioma A2**, se toma como válido o cierto sin necesidad de demostración algebraica.

**🤔 Intuición:**
En el Álgebra de Boole existe una simetría perfecta (llamada *Principio de Dualidad*, contexto adicional) entre la suma `+` y el producto `•`: toda propiedad básica que cumple el producto respecto de la suma también la cumple la suma respecto del producto.

**💡 Ejemplo:**
1. **Aplicación de A2a hacia atrás (factor común) en Desempeño 1c (pág. 6):**
   De `J . K̄ + J . K` se pasa a `J . (K̄ + K)` aplicando **A2a**.
2. **Aplicación de A2b con otras letras en Desempeño 2a (pág. 6):**
   En `(Ā + B) (Ā + B̄)`, reconociendo el molde de `A2b` más allá de las letras (donde el primer elemento repetido es `Ā`, el segundo es `B` y el tercero es `B̄`), sabemos que `(Ā + B) • (Ā + B̄) = Ā + (B • B̄)`.
3. **Aplicación de A2b en Desempeño 2b (pág. 6):**
   En `A + Ā • B • C`, tomando `B • C` como un bloque, al aplicar `A2b` queda `(A + Ā) • (A + B • C)`.

**🔗 Conexiones:**
- Es el axioma más potente para demostrar los **Teoremas de la Clase 2** (Idempotencia, Absorción, etc.) y para pasar entre expresiones en suma de productos y producto de sumas (Clases 3 y 4).

**⚠️ Precisiones / errores comunes:**
- **¡El error más frecuente de todos los alumnos!** Olvidarse de que en Boole **la suma distribuye sobre el producto** (`A2b`: `A + B • C = (A + B) • (A + C)`). Como en la escuela secundaria eso no existe para números reales, el cerebro tiende a ignorar `A2b`. El propio autor dedica toda la página 7 a recalcar `A2b` porque es la clave para destrabar las demostraciones (como el Desempeño 2a y 2b).

**🎤 Cómo decirlo en el oral:**
> "El Axioma A2 es la Propiedad Distributiva. Enuncia que para cualesquiera elementos A, B y C pertenecientes a M, se cumple: a) la distributiva del producto respecto de la suma, A • (B + C) = (A • B) + (A • C); y b) la distributiva de la suma respecto del producto, A + (B • C) = (A + B) • (A + C). Además, debemos comprender este axioma más allá de las letras empleadas, reconociendo su estructura tanto para distribuir como para extraer factor común."

---

## 1.11 Axioma A3: Elemento Neutro

> 📖 **Textual del material:** "· A3: ELEMENTO NEUTRO
> Existen para cada una de las operaciones un elemento neutro que cumple con la propiedad de identidad, esto es:
> a- A + 0 = A
> b- A • 1 = A"

**🗣️ En palabras simples:**
Un **elemento neutro** es un valor que, cuando lo operás con cualquier variable `A`, **deja a `A` exactamente igual que como estaba** (por eso dice que *"cumple con la propiedad de identidad"*).
- Para la **suma lógica**, el neutro es el **`0`**: sumar `0` no cambia nada (`A + 0 = A`).
- Para el **producto lógico**, el neutro es el **`1`**: multiplicar por `1` no cambia nada (`A • 1 = A`).

**🔍 Desglose de la jerga:**
- **"Existen para cada una de las operaciones un elemento neutro":** Cuantificador existencial (`∃`). Afirma la existencia de dos constantes distinguidas en el conjunto `M`: el `0` (neutro aditivo) y el `1` (neutro multiplicativo).
- **Propiedad de identidad:** Propiedad según la cual al operar un elemento `A` con el neutro de esa operación, el resultado es idéntico al mismo elemento `A`.
- **Parte `a- A + 0 = A`:** El `0` es el elemento neutro de la suma lógica.
- **Parte `b- A • 1 = A`:** El `1` es el elemento neutro del producto lógico.

**🧩 Idea de la demostración:**
Por ser el **Axioma A3**, se toma como válido o cierto sin necesidad de demostrar nada.

**🤔 Intuición:**
- **Circuito de `A + 0 = A`:** Si ponés en paralelo con el interruptor `A` una rama que está permanentemente abierta (`0`, cable cortado), por esa rama nunca pasa corriente; así que el encendido de la lámpara depende pura y exclusivamente de lo que haga `A`.
- **Circuito de `A • 1 = A`:** Si ponés en serie con el interruptor `A` otro interruptor que está permanentemente cerrado (`1`, cable directo), ese puente siempre deja pasar la corriente; así que todo depende únicamente de lo que haga `A`.

**💡 Ejemplo:**
En el **Desempeño 1, ítem a** (página 6):
En el último paso se pasa de `M + 0` a `M` aplicando **A3a (Elemento Neutro de la suma)**.
En el **Desempeño 1, ítems b y c** (página 6):
En el último paso se pasa de `X . 1` a `X` (y de `J . 1` a `J`) aplicando **A3b (Elemento Neutro del producto)**.

**🔗 Conexiones:**
- Trabaja siempre en dupla con el **Axioma A4 (Complemento)**: primero A4 convierte un par `(B + B̄)` en `1` o `(B • B̄)` en `0`, y enseguida **A3** elimina ese `1` (si está multiplicando) o ese `0` (si está sumando).
- No confundir con el **Elemento Nulo o Absorbente** (`A + 1 = 1` y `A • 0 = 0`), que se verá en la Clase 2 como Teorema.

**⚠️ Precisiones / errores comunes:**
- **¡No confundir Elemento Neutro (Axioma A3, Clase 1) con Elemento Nulo / Absorbente (Teorema, Clase 2)!**
  - En el **Elemento Neutro (A3)**, el resultado es **la variable `A`**: `A + 0 = A` y `A • 1 = A` (cumple la propiedad de identidad).
  - En el **Elemento Nulo** (Clase 2), el resultado es **la constante**: `A + 1 = 1` y `A • 0 = 0`.
- En el oral, incluí la frase exacta del apunte: *"un elemento neutro que cumple con la propiedad de identidad"*.

**🎤 Cómo decirlo en el oral:**
> "El Axioma A3 es el de Elemento Neutro. Establece que existe para cada una de las operaciones un elemento neutro que cumple con la propiedad de identidad, esto es: a) para la suma lógica el neutro es el 0, cumpliéndose A + 0 = A; y b) para el producto lógico el neutro es el 1, cumpliéndose A • 1 = A."

---

## 1.12 Axioma A4: Complemento

> 📖 **Textual del material:** "· A4: COMPLEMENTO
> Para cada elemento A de M existe otro que oficia de negación o complemento del mismo (Ā), es decir, que cumpla lo siguiente:
> a- A + Ā = 1
> b- A • Ā = 0"

**🗣️ En palabras simples:**
Cada elemento `A` tiene su opuesto o inverso llamado **complemento (`Ā`)**. Como `A` y `Ā` tienen siempre valores contrarios (cuando uno vale `1`, el otro vale `0`):
- **Parte a (`A + Ā = 1`):** Si los **sumás** lógicamente, seguro que uno de los dos vale `1`, así que la suma da siempre **`1`**.
- **Parte b (`A • Ā = 0`):** Si los **multiplicás** lógicamente, seguro que uno de los dos vale `0`, así que el producto da siempre **`0`**.

**🔍 Desglose de la jerga:**
- **"Para cada elemento A de M existe otro... (Ā)":** Combinación de cuantificador universal y existencial (`∀ A ∈ M, ∃ Ā ∈ M`). Para todo elemento `A`, existe su correspondiente complemento `Ā`.
- **"Que oficia de negación o complemento del mismo (Ā)":** Caracteriza algebraicamente qué significa ser el complemento: es aquel elemento que al sumarse con `A` da el neutro del producto (`1`), y al multiplicarse con `A` da el neutro de la suma (`0`).
- **Parte `a- A + Ā = 1`:** Suma de un elemento con su complemento (equivale al *Principio del Tercero Excluido* `p ∨ ¬p ≡ V` de MD1, contexto adicional).
- **Parte `b- A • Ā = 0`:** Producto de un elemento por su complemento (equivale al *Principio de No Contradicción* `p ∧ ¬p ≡ F` de MD1, contexto adicional).

### Tabla resumen de los 4 Axiomas del Álgebra de Boole (Pág. 5)

| Código | Nombre exacto | Cuantificación / Enunciado textual | Caso `a-` (Suma) | Caso `b-` (Producto) |
| :-: | :--- | :--- | :-: | :-: |
| **A1** | **PROPIEDAD CONMUTATIVA** | Para cualesquiera dos elementos, `A` y `B` pertenecientes a `M`, se cumple: | `A + B = B + A` | `A • B = B • A` |
| **A2** | **PROPIEDAD DISTRIBUTIVA** | Para cualesquiera elementos, `A`, `B` y `C` pertenecientes a `M`, se cumple: | `A • (B + C) = (A • B) + (A • C)` | `A + (B • C) = (A + B) • (A + C)` |
| **A3** | **ELEMENTO NEUTRO** | Existen para cada una de las operaciones un elemento neutro que cumple con la propiedad de identidad, esto es: | `A + 0 = A` | `A • 1 = A` |
| **A4** | **COMPLEMENTO** | Para cada elemento `A` de `M` existe otro que oficia de negación o complemento del mismo (`Ā`), es decir, que cumpla lo siguiente: | `A + Ā = 1` | `A • Ā = 0` |

**🧩 Idea de la demostración:**
Por ser el **Axioma A4**, se toma como válido o cierto sin necesidad de demostrar nada.

**🤔 Intuición:**
Imaginá dos interruptores acoplados mecánicamente de forma inversa: cuando apretás el botón, `A` se cierra (`1`) y `Ā` se abre (`0`); cuando lo soltás, `A` se abre (`0`) y `Ā` se cierra (`1`).
- Si los ponés **en paralelo** (`A + Ā`), siempre hay uno de los dos cerrado, por lo que la lámpara está **siempre encendida (`1`)**.
- Si los ponés **en serie** (`A • Ā`), siempre hay uno de los dos abierto cortando el paso, por lo que la lámpara está **siempre apagada (`0`)**.

**💡 Ejemplo:**
En el **Desempeño 1** (página 6):
- En `a-`: `M + N . N̄` pasa a `M + 0` porque `N . N̄ = 0` por **A4b**.
- En `b-`: `X . (Y + Ȳ)` pasa a `X . 1` porque `Y + Ȳ = 1` por **A4a**.

**🔗 Conexiones:**
- Conecta con la operación **Negación o Complemento** (Sección 1.7) y con el **Axioma A3 (Elemento Neutro)**.
- En la Clase 2 se usará para demostrar el **Teorema de Involución** y la unicidad del complemento.

**⚠️ Precisiones / errores comunes:**
- No confundir los resultados de A4a y A4b:
  - `A + Ā = 1` (la **suma** con su complemento da `1`, porque al menos uno de los dos es `1`).
  - `A • Ā = 0` (el **producto** con su complemento da `0`, porque uno de los dos es `0`).
- Nota sobre la página 6 del PDF: en las impresiones de `Desempeño 1` (`N . N`, `Y + Y`, `K + K`) y `Desempeño 2a` (`(Ā + B) (Ā + B)`), la tipografía del PDF omitió visualmente la rayita superior sobre la segunda letra (`N̄`, `Ȳ`, `K̄`, `B̄`), pero como el mismo desarrollo impreso reemplaza `N . N̄` por `0` y `Y + Ȳ` por `1`, se deduce inequívocamente que se trata del complemento **A4**.

**🎤 Cómo decirlo en el oral:**
> "El Axioma A4 es el de Complemento. Establece que para cada elemento A de M existe otro que oficia de negación o complemento del mismo (Ā), es decir, que cumpla lo siguiente: a) A + Ā = 1; y b) A • Ā = 0."

---

## 1.13 Método de Demostración de Igualdades mediante Axiomas

> 📖 **Textual del material:** "Las siguientes igualdades están demostradas, es decir está justificada que una expresión es igual a la otra que puede ser mucho más simple. Se le solicita a usted, que en cada paso determine e indique que axiomas se han aplicado, al pasar del renglón superior al inferior:"

> 📖 **Textual del material:** "Le planteamos algunas igualdades simples, y lo que deberá hacer usted es demostrarlas mediante la aplicación de las propiedades. Tenga en cuenta que puede partir del primer miembro de la igualdad y llegar a la segunda o partir de la segunda y llegar a la primera o desarrollar las dos hasta llegar a expresiones idénticas."

**🗣️ En palabras simples:**
¿Qué significa "demostrar una igualdad" en el Álgebra de Boole? Significa justificar paso a paso, renglón por renglón, qué axioma (o propiedad) te permite transformar una expresión en otra equivalente, hasta probar que ambos lados del signo `=` son iguales. El material habilita **tres caminos válidos** para demostrar cualquier igualdad `Expresión 1 = Expresión 2`:
1. Empezar en el **primer miembro** (izquierda) y aplicar axiomas hasta llegar al **segundo miembro** (derecha).
2. Empezar en el **segundo miembro** (derecha) y aplicar axiomas hasta llegar al **primer miembro** (izquierda).
3. Desarrollar **ambos miembros** por separado hasta que los dos lleguen a **expresiones idénticas**.

**🔍 Desglose de la jerga:**
- **Igualdad demostrada:** Igualdad en la que *"está justificada que una expresión es igual a la otra que puede ser mucho más simple"* indicando en cada paso qué axioma se aplicó para pasar del renglón superior al inferior.
- **Primer miembro / Segundo miembro:** La expresión ubicada a la izquierda / derecha del signo `=`.
- **Tres estrategias válidas de demostración:**
  1. `Primer miembro ⇒ ... ⇒ Segundo miembro`
  2. `Segundo miembro ⇒ ... ⇒ Primer miembro`
  3. `Primer miembro ⇒ ... ⇒ Expresión C` y `Segundo miembro ⇒ ... ⇒ Expresión C` (expresiones idénticas).

**💡 Ejemplo:**
Veamos los casos planteados en la página 6 del material (indicando el axioma aplicado en cada renglón):

- **Desempeño 1a:** Demostrar `M + N • N̄ = M`
  1. `M + N • N̄` (Primer miembro)
  2. `= M + 0` — *por Axioma A4b (Complemento: `N • N̄ = 0`)*
  3. `= M` — *por Axioma A3a (Elemento Neutro: `M + 0 = M`)*

- **Desempeño 1c:** Demostrar `J • K̄ + K • J = J`
  1. `J • K̄ + K • J` (Primer miembro)
  2. `= J • K̄ + J • K` — *por Axioma A1b (Conmutativa del producto: `K • J = J • K`)*
  3. `= J • (K̄ + K)` — *por Axioma A2a (Distributiva del producto respecto de la suma)*
  4. `= J • 1` — *por Axioma A1a y A4a (Complemento de la suma: `K̄ + K = 1`)*
  5. `= J` — *por Axioma A3b (Elemento Neutro del producto: `J • 1 = J`)*

- **Desempeño 2b:** Demostrar `A + Ā • B • C = A + B • C`
  1. `A + Ā • (B • C)` (Primer miembro)
  2. `= (A + Ā) • (A + B • C)` — *por Axioma A2b (Distributiva de la suma respecto del producto)*
  3. `= 1 • (A + B • C)` — *por Axioma A4a (Complemento: `A + Ā = 1`)*
  4. `= (A + B • C) • 1` — *por Axioma A1b (Conmutativa del producto)*
  5. `= A + B • C` — *por Axioma A3b (Elemento Neutro del producto)*

**🔗 Conexiones:**
- Este método exacto es el que utiliza el material en la **Clase 2** para demostrar todos los **Teoremas del Álgebra de Boole** a partir de los axiomas A1–A4.

**⚠️ Precisiones / errores comunes:**
- A diferencia del álgebra clásica de ecuaciones, en las demostraciones de identidades booleanas **no se "pasa" un término restando ni dividiendo al otro lado del igual** (porque no existen la resta ni la división en Boole). Siempre se transforma un miembro en el otro (o ambos hacia una misma expresión común) aplicando únicamente axiomas y teoremas.

**🎤 Cómo decirlo en el oral:**
> "Para demostrar una igualdad en el Álgebra de Boole debemos justificar en cada paso qué axioma o propiedad se ha aplicado al pasar del renglón superior al inferior. Existen tres maneras válidas de hacerlo: partir del primer miembro de la igualdad y llegar al segundo, partir del segundo miembro y llegar al primero, o desarrollar los dos miembros hasta llegar a expresiones idénticas."

---

## 🧠 Resumen esquemático de la clase

- **Matemática Discreta:** Trabaja con **conjuntos discretos**, es decir, conjuntos **finitos o infinitos pero numerables**.
- **Álgebra de Boole:** Continuación de la **lógica simbólica proposicional** (MD1), formalizada por Boole basándose en el **sistema de numeración binario** (`0` y `1`).
- **Circuito lógico como sistema:** Transforma **señales de entrada** (posición de interruptores) en **señales de salida** (estado de la lámpara).
- **Variables lógicas:** Solo pueden tomar un valor entre dos **opciones excluyentes, `0` ó `1`**, y describen el estado de los elementos de un circuito (tubería: llave abierta `1` / cerrada `0`; circuito eléctrico: interruptor abierto `0` / cerrado `1`, lámpara apagada `0` / encendida `1`).
- **Operaciones lógicas:** Permiten combinar variables para obtener otras variables; son tres: **suma lógica (`+`), producto lógico (`.`) y negación o complemento (`¯`)**.
- **Suma Lógica (`+`):** Equivale a `∨` (disyunción); vale `1` cuando **al menos una** variable vale `1`, y `0` **solo cuando todas** valen `0` (circuito en **paralelo**, `F = A + B`).
- **Producto Lógico (`.`):** Equivale a `∧` (conjunción); vale `1` **sólo cuando todas** las variables valen `1`, y siempre que haya un `0` el resultado es `0` (circuito en **serie**, `F = A . B`).
- **Negación o Complemento (`Ā`):** Equivale a `¬`; se aplica sobre **una sola variable** e **invierte su valor** (`0 ↔ 1`, circuito `F = Ā`).
- **Axiomas vs. Teoremas:** Los **Axiomas** son la base de las demás propiedades y se toman como válidos o ciertos **sin necesidad de demostrar nada**; los **Teoremas** no se toman como válidos **hasta haberlos demostrado lógicamente**.
- **Axioma A1 (Propiedad Conmutativa):** `∀ A, B ∈ M`: `a) A + B = B + A` y `b) A • B = B • A`.
- **Axioma A2 (Propiedad Distributiva):** `∀ A, B, C ∈ M`: `a) A • (B + C) = (A • B) + (A • C)` y `b) A + (B • C) = (A + B) • (A + C)`.
- **Axioma A3 (Elemento Neutro / Identidad):** `a) A + 0 = A` y `b) A • 1 = A`.
- **Axioma A4 (Complemento):** `∀ A ∈ M, ∃ Ā`: `a) A + Ā = 1` y `b) A • Ā = 0`.
- **Demostración de igualdades:** Justificar cada paso con axiomas partiendo del 1.º miembro hacia el 2.º, del 2.º hacia el 1.º, o desarrollando ambos hasta llegar a expresiones idénticas.

---

## ❓ Preguntas probables del oral

1. **¿Por qué la materia recibe el nombre de Matemática Discreta y cómo se conecta esta primera unidad con Matemática Discreta 1?**
   *Respuesta:* Recibe ese nombre porque trabaja con **conjuntos discretos**, es decir, **conjuntos finitos o infinitos pero numerables**. Esta primera unidad (Álgebra de Boole) es continuación y ampliación de la Unidad 3 de Matemática Discreta 1, la **lógica simbólica proposicional**, en la que las variables eran las proposiciones (sentencias que son verdaderas o son falsas).

2. **¿En qué sistema se basó Boole para formalizar su Álgebra y por qué se aplica a las computadoras?**
   *Respuesta:* Boole basó su esquema en el **sistema de numeración binario**, asociando los elementos y resultados que solo tienen dos posibilidades a dos estados. Como las computadoras usan **codificación binaria** (donde una unidad elemental de información puede tomar solamente dos valores, `0` ó `1`), la base de las computadoras son los **circuitos lógicos**, los cuales son analizados mediante el Álgebra de Boole.

3. **¿Cómo se interpreta un circuito lógico desde el punto de vista de un sistema?**
   *Respuesta:* Se considera al circuito como un **sistema que transforma las señales de entrada** (que en un circuito eléctrico serían la posición de los interruptores `A`, `B` y `C`) **en señales de salida** (que sería el estado de la lámpara `L`).

4. **¿Cuáles son los elementos básicos con los que se define el Álgebra de Boole?**
   *Respuesta:* Los elementos básicos con los que se define el Álgebra de Boole son las **variables lógicas** y las **operaciones lógicas**.

5. **¿Qué es una variable lógica y cómo se asignan los valores `0` y `1` en una tubería y en un circuito eléctrico?**
   *Respuesta:* Las **variables lógicas** son aquellas que solo pueden tomar un valor entre dos opciones excluyentes, `0` ó `1`, y permiten describir el estado de los distintos elementos de un circuito. En una tubería, una llave puede estar abierta (`1`) o cerrada (`0`); en un circuito eléctrico, un interruptor puede estar abierto (`0`) o cerrado (`1`), y una lámpara puede estar apagada (`0`) o encendida (`1`).

6. **¿Qué son las operaciones lógicas y cuáles son?**
   *Respuesta:* Las **operaciones lógicas** permiten combinar variables para poder obtener otras variables. Aunque reciben nombres similares o iguales a algunas operaciones del Álgebra clásica, no tienen nada que ver con ellas. Las operaciones son tres: **suma lógica, producto lógico y negación (o complemento)**.

7. **¿Cómo se define la Suma Lógica (`+`), con qué conector de MD1 se relaciona y a qué circuito eléctrico se asocia?**
   *Respuesta:* Se relaciona con el conector lógico `∨` (**disyunción**) de MD1. La suma lógica tendrá un valor de `1` cuando **al menos una de las variables tenga el valor `1`**, es decir que será `0` **solo cuando todas las variables sumadas sean `0`** (`0+0=0`, `0+1=1`, `1+0=1`, `1+1=1`). Se asocia a un circuito eléctrico con interruptores en **paralelo** (`F = A + B`), donde la lámpara se enciende (`1`) cuando al menos uno de los interruptores está cerrado (`1`).

8. **¿Cómo se define el Producto Lógico (`.`), con qué conector de MD1 se relaciona y a qué circuito eléctrico se asocia?**
   *Respuesta:* Se relaciona con el conector lógico `∧` (**conjunción**) de MD1. El producto lógico tendrá un valor de `1` **sólo cuando todas las variables tengan el valor `1`**, es decir que **siempre que en el producto haya un valor `0`, sin importar la cantidad de `1`, el resultado será `0`** (`0.0=0`, `0.1=0`, `1.0=0`, `1.1=1`). Se asocia a un circuito eléctrico con interruptores en **serie** (`F = A . B`), donde la lámpara se enciende (`1`) cuando los dos interruptores están cerrados (`1`).

9. **¿Cómo se define la Negación o Complemento (`¯`) y con qué conector de MD1 se relaciona?**
   *Respuesta:* Se relaciona con el conector `¬` de la lógica proposicional de MD1. Se aplica sobre **una sola variable**, y lo que hace es **invertir el valor de la misma** (si `A = 0`, `Ā = 1`; si `A = 1`, `Ā = 0`). En el circuito asociado (`F = Ā`), el estado encendido (`1`) de la lámpara se da cuando el estado del interruptor es `0`.

10. **¿Cómo se clasifican las propiedades del Álgebra de Boole y cuál es la diferencia entre ambos grupos?**
    *Respuesta:* Se distinguen en dos grandes grupos: los **Axiomas**, que son la base de las demás propiedades ya que se toman como válidos o ciertos **sin la necesidad de demostrar nada**; y los **Teoremas**, que **no se toman como válidos hasta haberlos demostrado lógicamente**.

11. **Enuncie los cuatro Axiomas del Álgebra de Boole tal como figuran en el material.**
    *Respuesta:*
    - **A1 — Propiedad Conmutativa:** Para cualesquiera dos elementos, `A` y `B` pertenecientes a `M`, se cumple: `a) A + B = B + A` y `b) A • B = B • A`.
    - **A2 — Propiedad Distributiva:** Para cualesquiera elementos, `A`, `B` y `C` pertenecientes a `M`, se cumple: `a) A • (B + C) = (A • B) + (A • C)` y `b) A + (B • C) = (A + B) • (A + C)`.
    - **A3 — Elemento Neutro:** Existen para cada una de las operaciones un elemento neutro que cumple con la propiedad de identidad, esto es: `a) A + 0 = A` y `b) A • 1 = A`.
    - **A4 — Complemento:** Para cada elemento `A` de `M` existe otro que oficia de negación o complemento del mismo (`Ā`), es decir, que cumpla lo siguiente: `a) A + Ā = 1` y `b) A • Ā = 0`.

12. **¿Qué particularidad tiene el Axioma A2 (Propiedad Distributiva) respecto del Álgebra clásica y qué recomienda el material al respecto?**
    *Respuesta:* Además de la distributiva del producto respecto de la suma (`A • (B + C) = (A • B) + (A • C)`), en el Álgebra de Boole se cumple la distributiva de la **suma respecto del producto**: `A + (B • C) = (A + B) • (A + C)`. El material recomienda comprender su enunciado **más allá de las letras o símbolos que se utilicen**, para poder identificar la estructura con cualquier expresión.

13. **¿De qué maneras se puede demostrar una igualdad booleana mediante las propiedades?**
    *Respuesta:* Indicando en cada paso qué axioma se aplica al pasar del renglón superior al inferior, pudiendo elegir entre tres caminos: **partir del primer miembro de la igualdad y llegar al segundo**, **partir del segundo y llegar al primero**, o **desarrollar los dos hasta llegar a expresiones idénticas**.

---

## 📚 Glosario de la clase

| Término | Definición breve fiel al material |
| :--- | :--- |
| **Conjuntos discretos** | Conjuntos finitos o infinitos pero numerables con los que trabaja la Matemática Discreta. |
| **Proposiciones** | Sentencias que son verdaderas o son falsas, utilizadas como variables en la lógica simbólica proposicional de MD1. |
| **Sistema de numeración binario** | Sistema de dos estados (`0` y `1`) en el que basó Boole su esquema para formalizar su Álgebra. |
| **Unidad elemental de información** | Mínima unidad en codificación binaria que puede tomar solamente dos valores, `0` ó `1`. |
| **Circuito lógico** | Base de las computadoras analizada mediante el Álgebra de Boole; sistema que transforma señales de entrada en señales de salida. |
| **Variables lógicas** | Elementos básicos del Álgebra de Boole que solo pueden tomar un valor entre dos opciones excluyentes, `0` ó `1`, para describir el estado de los elementos de un circuito. |
| **Operaciones lógicas** | Operaciones que permiten combinar variables lógicas para obtener otras variables: suma lógica, producto lógico y negación. |
| **Suma Lógica (`+`)** | Operación relacionada con la disyunción (`∨`) que vale `1` cuando al menos una de las variables tiene el valor `1`, y es `0` solo cuando todas las variables sumadas son `0`. |
| **Producto lógico (`.`)** | Operación relacionada con la conjunción (`∧`) que vale `1` sólo cuando todas las variables tienen el valor `1`, y es `0` siempre que haya algún valor `0`. |
| **Negación o Complemento (`¯`)** | Operación relacionada con el conector `¬` que se aplica sobre una sola variable e invierte el valor de la misma. |
| **Axiomas** | Propiedades del Álgebra de Boole que son la base de las demás, ya que se toman como válidas o ciertas sin la necesidad de demostrar nada. |
| **Teoremas** | Propiedades del Álgebra de Boole que no se toman como válidas hasta haberlas demostrado lógicamente. |
| **A1: Propiedad Conmutativa** | Axioma que establece que para cualesquiera dos elementos `A` y `B` pertenecientes a `M`, se cumple `A + B = B + A` y `A • B = B • A`. |
| **A2: Propiedad Distributiva** | Axioma que establece que para cualesquiera elementos `A`, `B` y `C` pertenecientes a `M`, se cumple `A • (B + C) = (A • B) + (A • C)` y `A + (B • C) = (A + B) • (A + C)`. |
| **A3: Elemento Neutro** | Axioma que establece la existencia para cada operación de un elemento neutro que cumple con la propiedad de identidad: `A + 0 = A` y `A • 1 = A`. |
| **A4: Complemento** | Axioma que establece que para cada elemento `A` de `M` existe otro que oficia de negación o complemento del mismo (`Ā`), cumpliendo `A + Ā = 1` y `A • Ā = 0`. |
