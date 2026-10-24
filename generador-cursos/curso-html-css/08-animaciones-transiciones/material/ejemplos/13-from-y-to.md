# 📘 Ejemplo 13 — `from` y `to`

> 🎓 **Resultados de aprendizaje:** RA-8
>
> 📐 **Cómo se midió.** Con Chrome: se fijó el instante exacto de cada transición o animación y se leyó el valor calculado en ese momento. Cuando el ejemplo habla del cursor, se simuló el estado `:hover`. Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía descubre que no siempre hay que escribir los dos pasos: a veces alcanza con el final. En `from-to.html` prueba una secuencia sin `from`, un nombre con error de escritura y una función de tiempo dentro de un paso.

## 💻 Código

El contenido de `from-to.html` (dentro de `<main>`):

```html
<h2>Una secuencia sin from</h2>
<div class="pista"><div class="caja sin-from"></div></div>

<h2>Un nombre que no coincide</h2>
<div class="pista"><div class="caja nombre-mal"></div></div>

<h2>Una función de tiempo dentro de un paso</h2>
<div class="pista"><div class="caja en-paso"></div></div>
```

La hoja `css/from-to.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

.pista {
  width: 400px;
  margin-bottom: 0.75rem;
  background-color: #e5e7eb;
}

.caja {
  width: 100px;
  height: 40px;
  background-color: #2563eb;
}

/* Solo define el final: el principio es el valor que la caja ya tiene (40px) */
@keyframes solo-to {
  to {
    transform: translateX(200px);
  }
}

.sin-from {
  transform: translateX(40px);
  animation-name: solo-to;
  animation-duration: 2s;
  animation-timing-function: linear;
}

/* El nombre de la animación tiene un error de escritura: no hay secuencia con ese nombre y no se anima */
@keyframes recorrer {
  from {
    transform: translateX(0);
  }

  to {
    transform: translateX(200px);
  }
}

.nombre-mal {
  animation-name: recorer;
  animation-duration: 2s;
}

/* La función de tiempo se puede cambiar en cada paso: este paso avanza en 2 saltos y el resto lineal */
@keyframes por-pasos {
  from {
    transform: translateX(0);
    animation-timing-function: steps(2, end);
  }

  to {
    transform: translateX(200px);
  }
}

.en-paso {
  animation-name: por-pasos;
  animation-duration: 2s;
  animation-timing-function: linear;
}
```

## 🔍 Análisis paso a paso

1. **`from` y `to`.** `from` equivale a `0%` (el principio) y `to` a `100%` (el final), según MDN. Son los dos pasos mínimos de una secuencia.
2. **Si falta uno, se usa el valor del elemento.** `@keyframes solo-to` no tiene `from`. MDN dice que, si no se especifica el principio o el final, el navegador usa **los estilos que el elemento ya tiene** en ese extremo. La caja tiene `translateX(40px)` de base: la animación **parte de `40px`** (a los `0 ms`, `40px`), pasa por `80px` a los `500 ms` y por `160px` a los `1500 ms` y llega a `200px`.
3. **Al terminar vuelve a lo suyo.** Sin relleno, a los `2000 ms` la caja ya no está animada y vuelve a su `translateX(40px)` de base.
4. **Un nombre con error.** `.nombre-mal` usa `animation-name: recorer` (le falta una «r») pero la secuencia se llama `recorrer`. El nombre **no coincide con ninguna secuencia**: no se anima (`transform: none` en cualquier instante). No da ningún error: revisá siempre que los nombres coincidan.
5. **La función de tiempo dentro de un paso.** `animation-timing-function` también se puede escribir **dentro de un paso**, y entonces vale para el tramo que **empieza** en ese paso. `por-pasos` la escribe en `from` con `steps(2, end)`: pisa la función `linear` de la caja para ese tramo.
6. **Qué se ve.** En `.en-paso` la caja avanza en **dos saltos**: `0px` hasta los `1000 ms`, `100px` desde los `1000 ms` hasta el final (a los `500 ms`, `0px`; a los `1500 ms`, `100px`). Si lo hubieras dejado `linear`, avanzaría de forma continua.
7. **Resumen.** Si solo cambia el final, alcanza con `to`; si solo cambia el principio, con `from`; la función de tiempo por paso permite mezclar ritmos dentro de una misma secuencia.

## ✅ Resultado esperado

| Caja | Qué ocurre | Valores medidos (`translateX`) |
|---|---|---|
| `.sin-from` | Solo `to`; base `40px` | `0 ms`: `40px` · `500 ms`: `80px` · `1000 ms`: `120px` · `1500 ms`: `160px` · `2000 ms`: `40px` (vuelve a la base) |
| `.nombre-mal` | El nombre no coincide | `none` siempre; `animation-name` calculado: `recorer` |
| `.en-paso` | `steps(2, end)` en `from` | `0 ms` a `999 ms`: `0px` · `1000 ms` y `1500 ms`: `100px` · `2000 ms`: terminó (`none`) |

- `.sin-from` sale de su posición base, no de `0`.
