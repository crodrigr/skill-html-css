# 🟡 Intermedio 02 — Gradientes, imágenes y opacidad

> 🟡 **Nivel:** Intermedio · 🎓 **Resultados de aprendizaje:** RA-8

## 🧱 Estado inicial

Abrí [`intermedio-02.html`](../recursos/portafolio-inicial/intermedio-02.html) y su hoja
[`intermedio-02.css`](../recursos/portafolio-inicial/css/intermedio-02.css). La página de Mateo tiene seis cajas de 400 × 80 píxeles,
cada una con su clase, y la hoja solo define el aspecto general de `.caja` (texto blanco sobre fondo gris oscuro `#111827`). En la
carpeta `imagenes/` hay dos imágenes de fondo: `patron.png` (un mosaico) y `portada.png` (una imagen ancha).

| Clase | Qué hay que lograr |
|---|---|
| `.lineal` | Un gradiente lineal de izquierda a derecha, de `#111827` a `#16a34a` |
| `.radial` | Un gradiente radial circular, del centro `#fef3c7` al borde `#16a34a` |
| `.mosaico` | El patrón `patron.png` repetido; texto `#111827` |
| `.portada` | La imagen `portada.png` una sola vez, centrada y cubriendo toda la caja; texto `#111827` |
| `.tenue` | Toda la caja, con su texto, al 60% de opacidad |
| `.vidrio` | Solo el fondo, en verde `#16a34a` al 50% de transparencia; el texto sigue blanco y nítido |

## 🛠️ Proceso esperado

1. Escribí en `intermedio-02.css` una regla para cada clase de la tabla.
2. Revisá en las herramientas del navegador que las imágenes cargan y que los valores calculados son los pedidos.
3. Respondé: ¿por qué `.tenue` atenúa el texto y `.vidrio` no? ¿Desde qué carpeta se cuenta la ruta de `url()`?

## ✅ Resultado esperado

- ☑️ Seis reglas, una por clase.
- ☑️ Los gradientes escritos en `background-image`, no en `background-color`.
- ☑️ Las rutas de las imágenes correctas (`../imagenes/…`) y las dos cajas con imagen se ven.
- ☑️ Dos respuestas de una o dos frases.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni las imágenes.
- 🚫 Para `.vidrio`, no uses `opacity`: usá un color con canal alfa.
- 🚫 No uses `!important`.
- 🚫 Solo gradientes lineales y radiales.

## 🎓 Resultados de aprendizaje

- RA-8: Crear gradientes, usar imágenes como fondo y controlar la opacidad.
