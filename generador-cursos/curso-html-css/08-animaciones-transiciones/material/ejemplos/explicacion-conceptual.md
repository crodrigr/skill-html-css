# 📚 Explicación conceptual — Animaciones y transiciones

Hasta ahora, cuando algo cambiaba en tu página (el color de un botón al pasar el cursor, por ejemplo), el cambio era **instantáneo**. En esta clase aprendés a **hacer que los cambios sean graduales** con las transiciones, a **elegir su ritmo** con las funciones de tiempo y a crear **secuencias de movimiento** con animaciones y `@keyframes`, cuidando siempre a quienes prefieren menos movimiento. Seguimos con el sitio de **Lucía Fernández**, con una página de práctica por tema. Se recomienda haber hecho las Clases 01 a 07.

La clase se dicta en **dos sesiones**: la **sesión 1** cubre las transiciones y las funciones de tiempo (bloques 1 y 2) y la **sesión 2**, las animaciones y los keyframes (bloques 3 a 5).

Resultados de aprendizaje de la clase:

- **RA-1**: explicar qué es una transición y usar sus cuatro propiedades.
- **RA-2**: escribir transiciones con el atajo `transition`.
- **RA-3**: diseñar transiciones de entrada y de salida.
- **RA-4**: elegir una función de tiempo predefinida.
- **RA-5**: crear una curva con `cubic-bezier()`.
- **RA-6**: crear una función de salto con `steps()`.
- **RA-7**: explicar qué es una animación y usar sus propiedades y el atajo `animation`.
- **RA-8**: definir secuencias con `@keyframes`, con `from`/`to` y con porcentajes.
- **RA-9**: respetar la preferencia de movimiento reducido.

## 🗒️ Glosario

| Término | Equivalente |
|---|---|
| *transition* | transición (cambio gradual de un valor) |
| *animation* | animación (secuencia de estilos que se reproduce) |
| *keyframe* | fotograma clave (un paso de la secuencia) |
| *timing function* / *easing* | función de tiempo (cómo avanza el cambio) |
| *delay* | retardo |
| *duration* | duración |
| *iteration* | repetición (una vuelta de la secuencia) |
| *fill mode* | modo de relleno |
| *control point* | punto de control |
| *reduced motion* | movimiento reducido |

> 📌 **Origen de la información.** Los valores de todos los ejemplos se comprobaron en un navegador **fijando el instante exacto** de cada transición o animación y leyendo el valor calculado en ese momento (por ejemplo, a los `0`, `500`, `1000`, `1500` y `2000 ms`). Las descripciones siguen la terminología de MDN Web Docs. Lo medido son **valores**, no la impresión visual del movimiento: cada ejemplo lo describe también con palabras. `transform` aparece solo como medio para animar (`translate`, `scale` y `rotate`), sin estudiarlo como tema.

---

## ⏱️ Transiciones

### 🧭 1.1 Transiciones — Propiedades de transición

*Resultados de aprendizaje: RA-1*

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 01 — Qué es una transición](01-que-es-una-transicion.md): un botón con y sin transición, medido en cinco instantes.
> - [Ejemplo 02 — Retardo y varias propiedades](02-retardo-y-varias-propiedades.md): retardo, listas de propiedades, `all` y lo que no se nombra.

![Una transición con un retardo de 1 segundo y una duración de 0.5 segundos. Entre 0 y 1000 milisegundos el botón sigue azul (retardo); entre 1000 y 1500 milisegundos el color cambia gradualmente; desde 1500 milisegundos queda en gris oscuro. Se muestran los colores medidos en 0, 1000, 1250 y 1500 milisegundos.](../imagenes/linea-de-tiempo-de-una-transicion.svg)

#### 🌍 Contexto

Cuando pasás el cursor sobre un botón y cambia de color, el cambio es de golpe. Eso se siente brusco: no se ve que «algo pasó».

#### 💡 Concepto

Una **transición** es un cambio **gradual** del valor de una propiedad entre dos estados. Ocurre cuando **cambia el valor** de la propiedad (por un estado como `:hover`, por una clase). Tiene cuatro propiedades: qué propiedad se anima, cuánto dura, con qué función de tiempo y con qué retardo.

#### 📖 Explicación

| Propiedad | Qué define | Valor por defecto | Ejemplo |
|---|---|---|---|
| `transition-property` | Qué propiedad(es) se animan | `all` | `background-color` |
| `transition-duration` | Cuánto dura el cambio | `0s` (sin transición) | `0.3s` |
| `transition-timing-function` | Cómo avanza el cambio | `ease` | `ease-in-out` |
| `transition-delay` | Cuánto espera antes de empezar | `0s` | `1s` |

- **La duración es obligatoria**: sin ella (`0s`) no hay transición.
- Se pueden poner **varias propiedades** separadas por comas; las demás listas se leen **en el mismo orden**.
- `all` anima cualquier propiedad que cambie; lo que no se nombra cambia **al instante**.
- Un retardo negativo hace que la transición empiece **ya avanzada**.
- La transición se define en el elemento, y se dispara cuando cambia el valor en otro estado.

---

### ✂️ 1.2 Transiciones — Atajo: Transiciones

*Resultados de aprendizaje: RA-2*

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 03 — El atajo `transition`](03-el-atajo-transition.md): la forma larga frente al atajo y dos transiciones en una declaración.

#### 🌍 Contexto

Escribir cuatro propiedades por cada transición es largo y repetitivo.

#### 💡 Concepto

La propiedad **abreviada** `transition` reúne las cuatro en una sola declaración: `transition: propiedad duración función retardo;`.

#### 📖 Explicación

```css
.boton {
  transition: background-color 0.4s ease-in 0.2s;
}
```

- El **primer** tiempo es la **duración** y el **segundo**, el **retardo** (según MDN).
- Se pueden omitir la función (vale `ease`) y el retardo (`0s`); si se omite la duración, no hay transición.
- Varias transiciones se separan por coma: `transition: background-color 0.3s, opacity 1s ease-out 0.2s;`.
- Cada transición de la lista tiene **sus propios valores**.

---

### ↔️ 1.3 Transiciones — Transiciones de entrada y salida

*Resultados de aprendizaje: RA-3*

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 04 — Transiciones de entrada y de salida](04-entrada-y-salida.md): entrada rápida y salida lenta, y la transición escrita solo en `:hover`.
> - [Ejemplo 05 — Lo que no se anima](05-lo-que-no-se-anima.md): `auto`, `display`, la duración `0s` y el retardo negativo.

![Dos tiras de color a la misma escala de tiempo. Al entrar con el cursor, la regla de hover manda: 0.2 segundos con ease-out, y el botón pasa de azul a gris oscuro rápido. Al salir, manda la regla del estado base: 1 segundo con ease-in, y vuelve de gris oscuro a azul lentamente.](../imagenes/entrada-y-salida.svg)

#### 🌍 Contexto

Al pasar el cursor el cambio debería ser rápido; al sacarlo, más calmado. Y algunos cambios, por más que se declare una transición, no se animan.

#### 💡 Concepto

Una transición de **entrada** es la que ocurre al pasar al estado que cambia (`:hover`, `:focus`); la de **salida**, al volver al estado base. El navegador usa la transición del **estado de destino**.

#### 📖 Explicación

- La transición escrita en el **estado base** vale para la **salida** y, si el estado `:hover` no declara otra, también para la entrada.
- La transición escrita en `:hover` manda en la **entrada**: sirve para darle otro tiempo o ritmo.
- Si la transición está **solo en `:hover`**, la entrada se anima pero la **salida no**: vuelve de golpe.
- Una salida un poco más lenta que la entrada suele sentirse natural.

**Lo que no se anima.** Para animar, el navegador debe poder calcular valores intermedios:

| Cambio | ¿Se anima? | Por qué |
|---|---|---|
| `50px` → `100px` | Sí | Hay valores intermedios |
| `auto` → `100px` | No | `auto` no es un número |
| `display: block` → `inline-block` | No | Valor discreto: no se mezcla |
| Duración `0s` o ausente | No | No hay tiempo para animar |

- Existe `transition-behavior: allow-discrete`, que permite transicionar propiedades discretas como `display`; MDN la marca con **disponibilidad limitada** y en esta clase solo se menciona.
- Mejor animar `opacity` y `transform`, que son baratas de dibujar.

---

## 📈 Funciones de tiempo

### 🎚️ 2.1 Funciones de tiempo — Función predefinida

*Resultados de aprendizaje: RA-4*

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 06 — Funciones de tiempo predefinidas](06-funciones-predefinidas.md): cinco cajas con las cinco funciones, medidas en cinco instantes.

![Cinco gráficas del progreso del cambio a lo largo del tiempo: linear es una recta; ease arranca con rapidez y termina despacio; ease-in arranca despacio y termina rápido; ease-out arranca rápido y termina despacio; ease-in-out arranca y termina despacio. Debajo de cada gráfica, los cuatro valores de su cubic-bezier.](../imagenes/funciones-de-tiempo-predefinidas.svg)

#### 🌍 Contexto

Dos transiciones de la misma duración pueden sentirse muy distintas según **cómo avanzan** dentro de ese tiempo.

#### 💡 Concepto

Una **función de tiempo** (*easing function*) define cómo cambia el progreso a lo largo de la duración. Las palabras clave son atajos de curvas ya definidas.

#### 📖 Explicación

| Palabra clave | Cómo avanza | Equivale a |
|---|---|---|
| `linear` | Velocidad constante | `cubic-bezier(0, 0, 1, 1)` |
| `ease` (por defecto) | Arranca rápido, termina despacio | `cubic-bezier(0.25, 0.1, 0.25, 1)` |
| `ease-in` | Arranca despacio, termina rápido | `cubic-bezier(0.42, 0, 1, 1)` |
| `ease-out` | Arranca rápido, termina despacio | `cubic-bezier(0, 0, 0.58, 1)` |
| `ease-in-out` | Arranca y termina despacio | `cubic-bezier(0.42, 0, 0.58, 1)` |

- `ease-out` suele quedar bien para lo que **entra**; `ease-in`, para lo que **sale**; `ease-in-out`, para movimientos que van y vuelven; `linear`, para giros y barras de progreso.
- A la mitad del tiempo, `ease` ya hizo el `80%` del cambio y `ease-in`, solo el `32%`.

---

### 🧮 2.2 Funciones de tiempo — Función Cubic Bezier

*Resultados de aprendizaje: RA-5*

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 07 — La función `cubic-bezier()`](07-cubic-bezier.md): curvas propias, una que se pasa del destino y una inválida.

![Una curva cubic-bezier(0.68, -0.55, 0.27, 1.55) dibujada sobre un eje de tiempo de 0 a 1 y de progreso de menos 0.6 a 1.6. Los dos puntos de control, P1 con x 0.68 e y menos 0.55 y P2 con x 0.27 e y 1.55, tiran de la curva desde los extremos. La curva baja por debajo de 0 al principio y se pasa de 1 antes de asentarse.](../imagenes/curva-cubic-bezier.svg)

#### 🌍 Contexto

Las cinco palabras clave no alcanzan para un movimiento con carácter propio, como un rebote elástico.

#### 💡 Concepto

`cubic-bezier(x1, y1, x2, y2)` crea una curva con **cuatro números**: las coordenadas de **dos puntos de control** (P1 y P2). La curva siempre une `(0, 0)` con `(1, 1)`.

#### 📖 Explicación

- El eje horizontal es el **tiempo** (de `0` a `1`) y el vertical, el **progreso del cambio**.
- `x1` y `x2` **deben estar entre `0` y `1`** (según MDN). Si no, se ignora **toda la declaración** y no hay transición.
- `y1` e `y2` **pueden salirse** de `0` a `1`: la curva retrocede al principio o se pasa del destino y vuelve.
- Las palabras clave son curvas: `ease-in-out` es `cubic-bezier(0.42, 0, 0.58, 1)`.
- Podés dibujar y probar curvas en las herramientas para desarrolladores del navegador.

---

### 🪜 2.3 Funciones de tiempo — Función de salto

*Resultados de aprendizaje: RA-6*

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 08 — La función `steps()`](08-steps.md): `steps()` con distintas posiciones del salto.

![Tres gráficas escalonadas de steps(4) con cuatro intervalos. Con end, el salto ocurre al final de cada intervalo y los valores en el medio de cada intervalo son 0, 50, 100 y 150 píxeles. Con start, el salto ocurre al principio y los valores son 50, 100, 150 y 200. Con jump-none no hay salto en los extremos y los valores son 0, 66.7, 133.3 y 200.](../imagenes/funcion-steps.svg)

#### 🌍 Contexto

A veces no querés un movimiento continuo sino por **pasos**, como las agujas de un reloj.

#### 💡 Concepto

`steps(n, posición)` divide la duración en `n` intervalos iguales y mantiene el valor **constante dentro de cada uno**: el cambio ocurre en saltos.

#### 📖 Explicación

| Posición | Dónde ocurre el salto |
|---|---|
| `end` (por defecto, igual que `jump-end`) | Al **final** de cada intervalo |
| `start` (igual que `jump-start`) | Al **principio** de cada intervalo |
| `jump-none` | No hay salto en los extremos |
| `jump-both` | Hay salto al principio y al final |

- `step-start` equivale a `steps(1, jump-start)` y `step-end`, a `steps(1, jump-end)` (según MDN).
- Sirven para relojes, contadores, efectos de «máquina de escribir» y animaciones cuadro a cuadro (*sprites*).
- Al medir, el valor justo en el borde de un salto ya cambió: se mide en el **medio** de cada intervalo.

---

## 🎬 Animaciones

### 🎭 3.1 Animaciones — Qué es una animación

*Resultados de aprendizaje: RA-7, RA-8*

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 09 — Qué es una animación](09-que-es-una-animacion.md): una tarjeta que aparece sola y la comparación con una transición.

![Comparación en dos columnas. La transición va de un estado a otro cuando cambia un valor, por ejemplo al pasar el cursor, con un solo tramo y se define con la propiedad transition. La animación se reproduce sola o cuando se la asocia a un elemento, puede tener muchos pasos, repetirse y alternar, y se define con la regla keyframes y la propiedad animation.](../imagenes/transicion-frente-a-animacion.svg)

#### 🌍 Contexto

Una transición necesita que algo cambie. Pero a veces querés que algo se mueva **solo**, pase por varios estados o se repita.

#### 💡 Concepto

Una **animación** es una secuencia de estilos que se reproduce sobre un elemento. Se compone de dos partes: la secuencia, descrita con `@keyframes`, y su asociación a un elemento con las propiedades `animation-*`.

#### 📖 Explicación

- La secuencia lleva un **nombre**: `@keyframes aparecer { from {…} to {…} }`.
- Se asocia con `animation-name: aparecer` y se le da `animation-duration` (sin duración, no se anima).
- Puede empezar **sola**, al cargar la página, sin interacción.
- Una transición va de **un estado a otro**; una animación puede tener **varios pasos**, repetirse y alternar.

---

### 🎛️ 3.2 Animaciones — Propiedades de animación

*Resultados de aprendizaje: RA-7*

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 10 — Repeticiones y dirección](10-repeticiones-y-direccion.md): tres repeticiones, `infinite` con `alternate`, retardo y media repetición.
> - [Ejemplo 11 — Relleno y estado de reproducción](11-relleno-y-reproduccion.md): los cuatro modos de relleno y el estado de reproducción.

![Una animación con un retardo de 1 segundo, una duración de 1 segundo, 2 repeticiones alternadas y relleno both. De 0 a 1000 milisegundos es el retardo y, por el relleno hacia atrás, la caja ya muestra el primer paso. De 1000 a 2000 milisegundos va de 0 a 100 píxeles. De 2000 a 3000 vuelve de 100 a 0 porque la dirección alterna. Después de 3000 milisegundos termina y, por el relleno hacia adelante, conserva el último paso.](../imagenes/fases-de-una-animacion.svg)

#### 🌍 Contexto

Una vez que existe la secuencia, hay que decidir cuántas veces se repite, en qué sentido, cuándo empieza y qué queda al terminar.

#### 💡 Concepto

Las propiedades `animation-*` controlan **cómo se reproduce** la secuencia.

#### 📖 Explicación

| Propiedad | Qué controla | Valores |
|---|---|---|
| `animation-name` | La secuencia (`@keyframes`) | un nombre |
| `animation-duration` | Cuánto dura una vuelta | `1s` |
| `animation-timing-function` | Cómo avanza | `ease`, `linear`, `cubic-bezier()`… |
| `animation-delay` | Espera antes de empezar | `1s` |
| `animation-iteration-count` | Cuántas vueltas | número o `infinite` |
| `animation-direction` | Sentido de cada vuelta | `normal`, `reverse`, `alternate`, `alternate-reverse` |
| `animation-fill-mode` | Qué estilos aplica antes y después | `none`, `forwards`, `backwards`, `both` |
| `animation-play-state` | Si se reproduce | `running`, `paused` |

- `alternate`: la primera vuelta va hacia adelante y la segunda, hacia atrás.
- `backwards`: durante el retardo muestra el primer paso; `forwards`: al terminar conserva el último.
- Con `paused`, al volver a `running` continúa desde donde quedó.
- Los valores no enteros de `animation-iteration-count` reproducen parte de la secuencia (`0.5` es la mitad); los negativos no son válidos.

---

### ✂️ 3.3 Animaciones — El atajo animation

*Resultados de aprendizaje: RA-7*

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 12 — El atajo `animation`](12-el-atajo-animation.md): siete propiedades frente al atajo y dos animaciones.

#### 🌍 Contexto

Con ocho propiedades por animación, la hoja se llena de líneas.

#### 💡 Concepto

La propiedad abreviada `animation` reúne todas en una declaración.

#### 📖 Explicación

```css
.tarjeta {
  animation: 2s ease-out 0.5s 2 alternate both aparecer;
}
```

- El **primer** tiempo es la duración y el **segundo**, el retardo.
- **MDN recomienda escribir el nombre al final**, para que no se confunda con otra palabra clave.
- Los valores que no escribís toman su valor por defecto.
- Varias animaciones se separan por coma: cada una con sus valores.
- Cuidado con el relleno: si la última vuelta termina en `from`, con `forwards` el elemento puede quedar en su primer paso.

---

## 🔑 Keyframes

### 🔤 4.1 Keyframes — Selectores from y to

*Resultados de aprendizaje: RA-8*

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 09 — Qué es una animación](09-que-es-una-animacion.md): una tarjeta que aparece sola y la comparación con una transición.
> - [Ejemplo 13 — `from` y `to`](13-from-y-to.md): una secuencia sin `from`, un nombre con error y la función de tiempo dentro de un paso.

![Arriba, una secuencia con dos pasos: from, que equivale a 0 por ciento, con opacidad 0 y desplazada 20 píxeles hacia abajo, y to, que equivale a 100 por ciento, con opacidad 1 y sin desplazamiento. Abajo, un rebote con cinco pasos en 2 segundos: 0 por ciento en 0 píxeles, 25 por ciento en menos 60, 50 por ciento en 0, 75 por ciento en menos 30 y 100 por ciento en 0; los pasos caen a 0, 0.5, 1, 1.5 y 2 segundos.](../imagenes/keyframes-from-to-y-porcentajes.svg)

#### 🌍 Contexto

La secuencia más simple tiene un principio y un final.

#### 💡 Concepto

En `@keyframes`, **`from`** equivale a `0%` (el principio) y **`to`** a `100%` (el final).

#### 📖 Explicación

```css
@keyframes aparecer {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0); }
}
```

- Si falta `from` o `to`, el navegador usa **los estilos que el elemento ya tiene** en ese extremo (según MDN): una secuencia con solo `to` parte del valor propio del elemento.
- Si el **nombre** de `animation-name` no coincide con ninguna secuencia, **no se anima** y no hay ningún error.
- Dentro de un paso se puede escribir `animation-timing-function`, que vale para el tramo que **empieza** en ese paso.
- Para mover o girar, usamos `transform` solo como medio: `translate()` desplaza, `scale()` agranda o achica y `rotate()` gira.

---

## 🧮 Keyframes - Selectores porcentuales

### 📊 5.1 Keyframes - Selectores porcentuales

*Resultados de aprendizaje: RA-8*

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 14 — Selectores porcentuales](14-selectores-porcentuales.md): un rebote de cinco pasos con tres funciones de tiempo.

#### 🌍 Contexto

Un rebote, un parpadeo o un latido necesitan más de dos pasos.

#### 💡 Concepto

Los **selectores porcentuales** ubican cada paso en un **porcentaje de la duración**: `0%` es el principio y `100%`, el final.

#### 📖 Explicación

```css
@keyframes rebote {
  0%   { transform: translateY(0); }
  25%  { transform: translateY(-60px); }
  50%  { transform: translateY(0); }
  75%  { transform: translateY(-30px); }
  100% { transform: translateY(0); }
}
```

- Con una duración de `2s`, `25%` ocurre a los `0.5s`, `50%` a `1s` y `75%` a `1.5s`.
- Entre dos pasos, el navegador calcula los valores intermedios; la **función de tiempo se aplica entre cada par de pasos**, no a toda la animación.
- Los pasos con el mismo estilo se pueden agrupar con comas: `0%, 50%, 100% { … }`.
- Los porcentajes pueden escribirse en cualquier orden, pero conviene de menor a mayor.
- Si se repite un porcentaje, se usan los dos bloques (según MDN).

---

### ♿ 5.2 Movimiento reducido

*Resultados de aprendizaje: RA-9*

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 15 — Movimiento reducido](15-movimiento-reducido.md): una regla que quita las animaciones cuando la persona lo pide.

#### 🌍 Contexto

Algunas personas tienen trastornos vestibulares o son sensibles al movimiento: una animación que se repite sin parar, o que escala y desplaza objetos grandes, puede causarles malestar.

#### 💡 Concepto

`prefers-reduced-motion` es una condición de consulta de medios (Clase 07) que detecta si la persona pidió **menos movimiento** en su dispositivo. Sus valores son `no-preference` y `reduce`.

#### 📖 Explicación

```css
@media (prefers-reduced-motion: reduce) {
  .latido,
  .entrada {
    animation: none;
  }

  .boton-suave {
    transition: none;
  }
}
```

- Dentro de la consulta se **quitan o se reducen** las animaciones y transiciones.
- Conviene reducir lo que **se repite sin fin**, lo que **se mueve o escala mucho** y los efectos parpadeantes.
- Reducir no siempre es quitar: a veces se reemplaza el movimiento por un cambio simple.
- **La información no debe depender del movimiento.**
- Probá con la opción de reducir el movimiento del sistema operativo.
