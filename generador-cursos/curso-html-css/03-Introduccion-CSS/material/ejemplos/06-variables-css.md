# 📘 Ejemplo 06 — Variables CSS

## 🧱 Situación inicial

La hoja de Lucía repite el mismo azul (`#2563eb`) y el azul oscuro (`#1e3a8a`) en varias reglas. Hoy quiere probar un azul más
claro y tiene que buscarlo regla por regla. Descubre las **variables CSS**: valores con nombre que se definen una vez. Reescribe su
hoja para usarlas.

## 💻 Código

Antes, sin variables (de `css/sin-variables.css`), cada color se repite:

```css
/* Estilos generales: se heredan a casi todo el contenido */
body {
  color: #1f2937;
  background-color: #eff6ff;
}

/* Títulos: el h1 lleva un gradiente lineal */
h1 {
  color: #ffffff;
  background-color: #1e3a8a;
  background-image: linear-gradient(90deg, #1e3a8a, #2563eb);
}

h2 {
  color: #1e3a8a;
}

/* Enlaces */
a {
  color: #2563eb;
}
```

Después, con variables (de `css/estilos.css`):

```css
/* Variables: cada color se define una sola vez */
:root {
  --color-principal: #2563eb;
  --color-oscuro: #1e3a8a;
  --color-fondo: #eff6ff;
  --color-texto: #1f2937;
  --color-acento: #f59e0b;
}

/* Estilos generales: se heredan a casi todo el contenido */
body {
  color: var(--color-texto);
  background-color: var(--color-fondo);
}

/* Títulos: el h1 lleva un gradiente lineal */
h1 {
  color: #ffffff;
  background-color: var(--color-oscuro);
  background-image: linear-gradient(90deg, var(--color-oscuro), var(--color-principal));
}

h2 {
  color: var(--color-oscuro);
}

/* Enlaces */
a {
  color: var(--color-principal);
}
```

## 🔍 Análisis paso a paso

1. **Definir las variables.** En una regla `:root` (que representa a toda la página) escribe una declaración por color, con
   nombre que empieza con **dos guiones**: `--color-principal: #2563eb;`.
2. **Elegir buenos nombres.** Los nombres dicen **para qué** sirve el color (`--color-principal`, `--color-oscuro`) y no cómo es
   (`--azul`).
3. **Usar las variables.** En cada regla, reemplaza el color repetido por `var(--color-principal)`.
4. **Cambiar en un solo lugar.** Si Lucía cambia `--color-principal` en `:root`, cambian a la vez los enlaces, las clases, los
   bordes de las tablas y el gradiente de los títulos.
5. **Mayúsculas.** Los nombres distinguen mayúsculas: `--Color-principal` sería otra variable distinta.
6. **Valor de respaldo.** `var(--color-extra, red)` usa `red` si `--color-extra` no existe. Lucía lo agrega para colores que
   quizás no estén definidos.
7. **Comprobar.** Con el Inspector, un elemento muestra tanto la declaración `color: var(--color-principal)` como su valor
   calculado.

## ✅ Resultado esperado

- La página se ve **igual** con la hoja sin variables y con la hoja con variables: los enlaces, `.destacado` y los bordes de las tablas
  se ven en `rgb(37, 99, 235)`, y el texto del `body`, en `rgb(31, 41, 55)`.
- En `estilos.css` cada color aparece escrito **una sola vez**, en `:root`.
- Si Lucía cambia `--color-principal` a `#16a34a`, todos los elementos que lo usan pasan a verde sin tocar sus reglas.
