# 🔑 Soluciones — Quiz 01 de la Clase 08 (material docente)

No compartir este archivo con los estudiantes. Las respuestas con valores se comprobaron en Chrome fijando el instante indicado.

| Ítem | Tipo | Respuesta correcta | RA | Sesión |
|---|---|---|---|---|
| 1 | Selección múltiple | **B** | RA-1 | 1 |
| 2 | Identificación de resultado | **B** | RA-2 | 1 |
| 3 | Selección múltiple | **B** | RA-3 | 1 |
| 4 | Selección múltiple | **B** | RA-4 | 1 |
| 5 | Selección múltiple | **C** | RA-5 | 1 |
| 6 | Identificación de resultado | **B** | RA-6 | 1 |
| 7 | Selección múltiple | **B** | RA-7 | 2 |
| 8 | Identificación de resultado | **B** | RA-7 | 2 |
| 9 | Selección múltiple | **B** | RA-8 | 2 |
| 10 | Problema breve | Ver abajo | RA-8 | 2 |
| 11 | Problema breve | Ver abajo | RA-7 | 2 |
| 12 | Corrección de errores | Ver abajo | RA-9 | 2 |

## Justificaciones

**1. B.** La duración por defecto es `0s`: sin duración no hay transición y el cambio es instantáneo (comprobado: `transition-duration` `0s` y ninguna transición activa).

**2. B.** El **primer** tiempo es la duración (`2s`) y el **segundo** es el retardo (`0.5s`). `0s` sería el valor por defecto si no se escribiera.

**3. B.** La transición está solo en `:hover`, que es el estado de **entrada**; al salir, manda el estado base, que no declara nada. Comprobado: al salir no se crea ninguna transición y el color vuelve de golpe.

**4. B.** `ease-out` arranca rápido y termina despacio: el panel llega pronto y se asienta. `ease-in` arranca despacio y termina rápido (sirve para lo que sale); `linear` es constante.

**5. C.** `x1 = 2` está fuera del rango `0` a `1`, que MDN exige para `x1` y `x2`. Se ignora **toda** la declaración `transition` (comprobado: duración `0s` y ninguna transición). Los valores de `y` sí pueden salirse (B).

**6. B.** Con cuatro intervalos de `500 ms`, a los `750 ms` estamos en el segundo intervalo (`500` a `1000 ms`), donde el valor es `50px` (comprobado: `0`, `50`, `100` y `150px` en el medio de cada intervalo).

**7. B.** Una transición necesita un cambio de valor y tiene un solo tramo; una animación se define con `@keyframes`, puede empezar sola y tener varios pasos. No necesita JavaScript.

**8. B.** El primer tiempo (`3s`) es la duración y el segundo (`1s`) es el retardo.

**9. B.** Si la secuencia no define `from`, el navegador usa los estilos que el elemento ya tiene: parte de `20px` (comprobado en una secuencia equivalente: parte del valor propio del elemento, no de `0`).

**10. Problema breve.** `25%` de `4s` son `1s`: llega a `-40px` al **primer segundo**. A los `3s` (`75%`), entre el `50%` y el `100%`, los dos pasos valen `0`: vale **`0px`**. Se acepta también explicar que `50%` es el segundo `2` y `100%` el `4`.

**11. Problema breve.** `animation-fill-mode: forwards` (o `both`). Sin relleno, al terminar la animación el elemento vuelve a sus estilos normales (`opacity: 0`). Con `forwards` conserva los valores del último paso (`opacity: 1`). Con `both` también muestra el primer paso durante un retardo.

**12. Corrección de errores.** Hay que quitar la animación cuando la persona pide menos movimiento:

```css
@media (prefers-reduced-motion: reduce) {
  .latido {
    animation: none;
  }
}
```

Comprobado con la preferencia simulada: no queda ninguna animación activa y `animation-name` es `none`. Se acepta reemplazar el latido por un cambio simple (por ejemplo, de opacidad, sin movimiento) mientras no haya animación infinita ni desplazamiento.
