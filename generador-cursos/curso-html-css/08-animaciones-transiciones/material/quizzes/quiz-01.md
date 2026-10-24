# 📝 Quiz 01 — Animaciones y transiciones

12 ítems: los **6 primeros** son de la **sesión 1** (transiciones y funciones de tiempo) y los **6 últimos**, de la **sesión 2** (animaciones y keyframes). Sin respuestas (ver `material/soluciones/soluciones-quiz.md` para la clave, material exclusivamente docente).

---

**1. [selección múltiple]** 🔘
Una regla cambia el color de un botón en `:hover` pero **no declara `transition-duration`**. ¿Qué pasa al pasar el cursor?

A. Dura `0.3s` por defecto
B. No hay transición: el cambio es instantáneo
C. Dura `1s` por defecto
D. El navegador muestra un error

*RA: RA-1* · *Sesión: 1*

---

**2. [identificación de resultado]** 🔍
En `transition: opacity 2s ease-in 0.5s;`, ¿cuánto vale el retardo?

A. `2s`
B. `0.5s`
C. `0s`
D. `ease-in`

*RA: RA-2* · *Sesión: 1*

---

**3. [selección múltiple]** 🔘
Una hoja escribe `transition: color 1s;` **solo** en `.boton:hover`. ¿Qué pasa cuando el cursor sale del botón?

A. El color vuelve gradualmente en `1s`
B. El color vuelve de golpe, sin transición
C. El color tarda el doble en volver
D. El color no vuelve

*RA: RA-3* · *Sesión: 1*

---

**4. [selección múltiple]** 🔘
Un panel **entra** a la pantalla y debe llegar rápido y asentarse despacio. ¿Qué función de tiempo conviene?

A. `ease-in`
B. `ease-out`
C. `linear`
D. `steps(1)`

*RA: RA-4* · *Sesión: 1*

---

**5. [selección múltiple]** 🔘
¿Cuál de estas funciones es **inválida** y hace que se ignore toda la declaración?

A. `cubic-bezier(0.25, 0.1, 0.25, 1)`
B. `cubic-bezier(0.68, -0.55, 0.27, 1.55)`
C. `cubic-bezier(2, 0, 0.5, 1)`
D. `cubic-bezier(0.42, 0, 1, 1)`

*RA: RA-5* · *Sesión: 1*

---

**6. [identificación de resultado]** 🔍
Una caja se desplaza de `0` a `200px` en `2s` con `steps(4, end)`. ¿Cuánto vale el desplazamiento a los `750 ms`?

A. `0px`
B. `50px`
C. `75px`
D. `100px`

*RA: RA-6* · *Sesión: 1*

---

**7. [selección múltiple]** 🔘
¿Cuál es la diferencia principal entre una transición y una animación?

A. La animación necesita siempre JavaScript
B. La transición va de un estado a otro cuando cambia un valor; la animación puede empezar sola y tener varios pasos
C. La transición solo funciona con colores
D. No hay ninguna diferencia

*RA: RA-7* · *Sesión: 2*

---

**8. [identificación de resultado]** 🔍
En `animation: 3s ease-in 1s 2 alternate backwards pulso;`, ¿cuánto espera la animación antes de empezar?

A. `3s`
B. `1s`
C. `2s`
D. `0s`

*RA: RA-7* · *Sesión: 2*

---

**9. [selección múltiple]** 🔘
Un elemento tiene `transform: translateX(20px)` y la secuencia solo define `to { transform: translateX(100px); }`. ¿Desde dónde parte la animación?

A. Desde `0px`
B. Desde `20px`
C. Desde `100px`
D. No se anima

*RA: RA-8* · *Sesión: 2*

---

**10. [problema breve]** ✍️
Esta secuencia dura `4s`. ¿En qué instante llega a `-40px` y cuánto vale a los `3s`?

```css
@keyframes salto {
  0%   { transform: translateY(0); }
  25%  { transform: translateY(-40px); }
  50%  { transform: translateY(0); }
  100% { transform: translateY(0); }
}
```

*RA: RA-8* · *Sesión: 2*

---

**11. [problema breve]** ✍️
Una tarjeta tiene `opacity: 0` en su estilo normal y la animación `aparecer 1s` (de `opacity: 0` a `opacity: 1`). Al terminar la animación, la tarjeta **vuelve a ser invisible**. ¿Qué propiedad agregás y con qué valor para que quede visible?

*RA: RA-7* · *Sesión: 2*

---

**12. [corrección de errores]** 🛠️
Una hoja tiene un indicador que late sin parar. Una persona con sensibilidad al movimiento no puede usar la página. Escribí la regla que lo soluciona.

```css
.latido {
  animation: latir 1s ease-in-out infinite alternate;
}
```

*RA: RA-9* · *Sesión: 2*
