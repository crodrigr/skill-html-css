# 📘 Ejemplo 05 — Lo que no se anima

> 🎓 **Resultados de aprendizaje:** RA-3
>
> 📐 **Cómo se midió.** Con Chrome: se fijó el instante exacto de cada transición o animación y se leyó el valor calculado en ese momento. Cuando el ejemplo habla del cursor, se simuló el estado `:hover`. Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía intenta animar un panel que se despliega y descubre que algunos cambios **no** se animan. En `no-se-anima.html` prueba cinco paneles con el cursor encima, para ver qué se anima y qué no.

## 💻 Código

El contenido de `no-se-anima.html` (dentro de `<main>`):

```html
<h2>Una altura fija</h2>
<div class="panel panel-fijo">Panel de altura fija</div>

<h2>De altura automática a fija</h2>
<div class="panel panel-auto">Panel de altura automática</div>

<h2>El cambio de display</h2>
<div class="panel panel-display">Panel con display</div>

<h2>Sin duración</h2>
<div class="panel panel-sin-duracion">Panel sin duración</div>

<h2>Retardo negativo</h2>
<div class="panel panel-negativo">Panel con retardo negativo</div>
```

La hoja `css/no-se-anima.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

.panel {
  margin-bottom: 0.5rem;
  background-color: #dbeafe;
}

/* Una altura fija: el navegador puede calcular los valores intermedios */
.panel-fijo {
  height: 50px;
  transition: height 1s linear;
}

.panel-fijo:hover {
  height: 100px;
}

/* De auto a una medida no hay valores intermedios: el cambio es instantáneo */
.panel-auto {
  height: auto;
  transition: height 1s linear;
}

.panel-auto:hover {
  height: 100px;
}

/* display tampoco admite valores intermedios: no se inicia ninguna transición */
.panel-display {
  display: block;
  transition: all 1s linear;
}

.panel-display:hover {
  display: inline-block;
}

/* Sin duración (el valor por defecto es 0s) no hay transición */
.panel-sin-duracion {
  height: 50px;
  transition-property: height;
}

.panel-sin-duracion:hover {
  height: 100px;
}

/* Un retardo negativo: la transición empieza ya avanzada, como si hubieran pasado 0.5s */
.panel-negativo {
  height: 50px;
  transition: height 1s linear -0.5s;
}

.panel-negativo:hover {
  height: 100px;
}
```

## 🔍 Análisis paso a paso

1. **Para animar hace falta un valor intermedio.** El navegador calcula los valores entre el inicio y el final. Si no puede calcularlos, el cambio es **instantáneo** y no se crea ninguna transición.
2. **Altura fija a altura fija.** `.panel-fijo` va de `50px` a `100px` en `1s` con función lineal. Hay una transición activa y a los `500 ms` la altura es `75px`; a los `1000 ms`, `100px`.
3. **De `auto` a una medida.** `.panel-auto` va de `height: auto` a `100px`. `auto` no es un número, así que **no hay valores intermedios**: la altura pasa de golpe a `100px` y no se crea ninguna transición. Para animar una altura, partí de una medida fija (o usá otra propiedad).
4. **`display`.** `.panel-display` pasa de `block` a `inline-block` con `transition: all 1s`. `display` es una propiedad **discreta** (los valores no se mezclan): el cambio es instantáneo y no se crea ninguna transición. Para animar la aparición, se anima `opacity` y se cambia `display` aparte.
5. **Mención.** Existe `transition-behavior: allow-discrete`, que permite iniciar transiciones en propiedades discretas como `display`. MDN la marca con **disponibilidad limitada**; en esta clase solo se menciona, no se usa.
6. **Sin duración.** `.panel-sin-duracion` nombra la propiedad pero **no declara duración**: vale `0s` y la altura pasa de golpe a `100px`, sin transición.
7. **Retardo negativo.** `.panel-negativo` tiene un retardo de `-0.5s`: la transición **empieza ya avanzada**, como si hubieran pasado `0.5s`. A los `0 ms` la altura ya es `75px`; a los `250 ms`, `87.5px`; termina en `100px` a los `500 ms` (la mitad de la duración).

## ✅ Resultado esperado

| Panel | Cambio | ¿Se crea una transición? | Valores medidos |
|---|---|---|---|
| `.panel-fijo` | `50px` → `100px`, `1s` lineal | Sí | `0 ms`: `50px` · `500 ms`: `75px` · `1000 ms`: `100px` |
| `.panel-auto` | `auto` → `100px` | **No** | `100px` de golpe |
| `.panel-display` | `block` → `inline-block` | **No** | `display: inline-block` de golpe |
| `.panel-sin-duracion` | duración `0s` | **No** | `100px` de golpe |
| `.panel-negativo` | retardo `-0.5s` | Sí | `0 ms`: `75px` · `250 ms`: `87.5px` · `500 ms`: `100px` |

- Los paneles `.panel-auto`, `.panel-display` y `.panel-sin-duracion` cambian sin ninguna suavidad aunque lleven `transition`.
