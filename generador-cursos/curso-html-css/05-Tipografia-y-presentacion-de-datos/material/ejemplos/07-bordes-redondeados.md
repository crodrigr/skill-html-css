# 📘 Ejemplo 07 — Bordes redondeados

> 🕐 **Sesión 2** · 🎓 **Resultados de aprendizaje:** RA-6

## 🧱 Situación inicial

Lucía quiere suavizar las esquinas de sus cajas: redondear las cuatro, solo algunas o una sola, y hacer un círculo. Lo practica en `esquinas.html`.

## 💻 Código

El contenido de `esquinas.html` (dentro de `<main>`):

```html
<h2>Todas las esquinas</h2>
<div class="caja caja--redondeada">Esquinas de 16 píxeles</div>
<div class="caja caja--circulo">Círculo</div>

<h2>Una, dos o cuatro medidas</h2>
<div class="caja caja--dos-valores">Dos valores: 16px 0</div>
<div class="caja caja--cuatro-valores">Cuatro valores: 4px 12px 20px 28px</div>

<h2>Una esquina específica</h2>
<div class="caja caja--una-esquina">Solo arriba a la izquierda</div>
```

La hoja `css/esquinas.css`:

```css
/* Aspecto común: un borde para ver la forma de las esquinas */
.caja {
  padding: 12px;
  margin-bottom: 12px;
  border: 3px solid #2563eb;
  background-color: #dbeafe;
}

/* Un valor: las cuatro esquinas */
.caja--redondeada {
  border-radius: 16px;
}

/* Un círculo: caja cuadrada y radio del 50% */
.caja--circulo {
  width: 100px;
  height: 100px;
  border-radius: 50%;
}

/* Dos valores: arriba a la izquierda y abajo a la derecha / arriba a la derecha y abajo a la izquierda */
.caja--dos-valores {
  border-radius: 16px 0;
}

/* Cuatro valores: en el sentido de las agujas del reloj, desde arriba a la izquierda */
.caja--cuatro-valores {
  border-radius: 4px 12px 20px 28px;
}

/* Una esquina por separado */
.caja--una-esquina {
  border-top-left-radius: 24px;
}
```

## 🔍 Análisis paso a paso

1. **`border-radius`.** Redondea las esquinas del borde (y del fondo). Con **un valor** (`16px`) redondea las **cuatro** esquinas con el mismo radio. El radio es el de la
   circunferencia imaginaria que «muerde» la esquina: cuanto mayor, más redonda.
2. **Dos valores.** `16px 0`: el primero para **arriba a la izquierda y abajo a la derecha**; el segundo, para **arriba a la derecha y abajo a la izquierda**. Con `0`, la esquina queda
   recta.
3. **Cuatro valores.** `4px 12px 20px 28px` va **en el sentido de las agujas del reloj**, empezando por arriba a la izquierda: arriba-izquierda, arriba-derecha, abajo-derecha y
   abajo-izquierda. (Con tres valores: arriba-izquierda; arriba-derecha y abajo-izquierda; abajo-derecha.)
4. **Una esquina específica.** `border-top-left-radius`, `border-top-right-radius`, `border-bottom-right-radius` y `border-bottom-left-radius` cambian una sola esquina. Usalas
   cuando las otras tres tienen que quedar como están.
5. **Un círculo.** Una caja cuadrada con `border-radius: 50%` se convierte en un círculo. El porcentaje se mide contra el tamaño de la caja. En el ejemplo la caja mide
   `100px` de contenido más relleno y borde, es decir, `130px` por lado: sigue siendo cuadrada y, por eso, circular.
6. **Se aplica al fondo también.** El fondo se recorta siguiendo la curva, aunque el elemento no tenga borde.
7. **Cuidado con el contenido.** Un radio muy grande puede «comerse» el texto de las esquinas: agregá relleno (`padding`) para separarlo.

## ✅ Resultado esperado

| Clase | Propiedad | Valor calculado |
|---|---|---|
| `.caja--redondeada` | las cuatro esquinas | `16px` |
| `.caja--circulo` | `border-radius` / `offsetWidth` | `50%` / `130` |
| `.caja--dos-valores` | arriba-izquierda, arriba-derecha, abajo-derecha, abajo-izquierda | `16px`, `0px`, `16px`, `0px` |
| `.caja--cuatro-valores` | arriba-izquierda, arriba-derecha, abajo-derecha, abajo-izquierda | `4px`, `12px`, `20px`, `28px` |
| `.caja--una-esquina` | arriba-izquierda / arriba-derecha | `24px` / `0px` |

- La caja `.caja--circulo` se ve como un **círculo**.
- La caja `.caja--dos-valores` tiene dos esquinas redondeadas (arriba a la izquierda y abajo a la derecha) y dos rectas.
