# 🟡 Intermedio 02 — Bordes por lado y esquinas

> 🟡 **Nivel:** Intermedio · 🕑 **Sesión 2** · 🎓 **Resultados de aprendizaje:** RA-6

## 🧱 Estado inicial

Abrí [`intermedio-02.html`](../recursos/portafolio-inicial/intermedio-02.html) y su hoja [`css/intermedio-02.css`](../recursos/portafolio-inicial/css/intermedio-02.css), de la carpeta
`portafolio-inicial`. La página tiene ocho cajas (`div`) y la hoja ya da a todas un relleno de `8px` y un margen inferior de `12px`. La paleta de Mateo es gris oscuro `#111827`
y verde `#16a34a`.

## 🛠️ Proceso esperado

Agregá a `intermedio-02.css` una regla por caja, con los bordes y las esquinas de la tabla.

| # | Caja | Pedido | Valor calculado esperado |
|---|---|---|---|
| 1 | `.nota` | Borde de `2px`, continuo, gris oscuro, en los cuatro lados | `2px solid rgb(17, 24, 39)` |
| 2 | `.aviso` | Solo una barra verde de `6px` a la izquierda | izquierda `6px` verde; los otros tres lados `0px` |
| 3 | `.recuadro` | Arriba `4px` continuo; abajo `4px` doble; a los costados `1px` continuo; todos grises | `4px solid`, `1px solid`, `4px double`, `1px solid` (arriba, derecha, abajo, izquierda) |
| 4 | `.etiqueta` | Con **dos valores** por propiedad: `1px` arriba y abajo y `4px` a los costados; gris oscuro arriba y abajo y verde a los costados; todos continuos | anchos `1px`, `4px`, `1px`, `4px`; colores gris, verde, gris, verde |
| 5 | `.redonda` | Borde de `1px` continuo gris oscuro y las cuatro esquinas redondeadas con `12px` | las cuatro esquinas en `12px` |
| 6 | `.circulo` | Un círculo verde de `2px` de borde: contenido de `80px` por `80px` y radio del `50%` | `border-radius` `50%`; mide `100px` por `100px` de borde a borde |
| 7 | `.pestana` | Borde de `1px` continuo gris oscuro y **solo** las dos esquinas de arriba redondeadas con `16px`, con cuatro valores | arriba-izquierda `16px`, arriba-derecha `16px`, abajo-derecha `0px`, abajo-izquierda `0px` |
| 8 | `.esquina` | Borde de `1px` continuo gris oscuro y **solo** la esquina de abajo a la derecha con `24px`, con la propiedad de esa esquina | abajo-derecha `24px`; las otras tres `0px` |

**Parte B.** Respondé:

1. Si escribieras `border: 3px #16a34a;` (sin estilo), ¿se vería el borde? ¿Qué valor calculado tendría el grosor?
2. ¿Por qué la caja `.circulo` mide `100px` y no `80px`?

## ✅ Resultado esperado

- ☑️ Ocho reglas con los valores calculados de la tabla.
- ☑️ Una respuesta de una o dos frases a cada pregunta de la Parte B.
- ☑️ El HTML sin cambios.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni agregues clases.
- 🚫 No modifiques la regla `div` que ya existe en la hoja.
- 🚫 No uses `!important` ni el atributo `style`.
- 🚫 Cada color de la paleta se escribe como valor hexadecimal.

## 🎓 Resultados de aprendizaje

- RA-6: Crear bordes, incluidos bordes distintos en cada lado, y redondear sus esquinas.
