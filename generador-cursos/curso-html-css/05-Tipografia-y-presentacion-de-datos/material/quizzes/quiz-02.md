# 📝 Quiz 02 — Tipografía y presentación de datos (sesión 2)

8 ítems. Sin respuestas (ver `material/soluciones/soluciones-quiz.md` para la clave, material
exclusivamente docente).

---

**1. [selección múltiple]** 🔘
¿Qué dibuja la declaración `border: 4px red;`?

A. Un borde rojo de `4px`, continuo.
B. Nada: falta el estilo del borde.
C. Un borde negro de `4px`.
D. Un borde rojo punteado.

_RA: RA-6_

---

**2. [selección múltiple]** 🔘
¿Cuál de estas declaraciones dibuja **solo** el borde de abajo de una caja?

A. `border-bottom: 3px solid #f59e0b;`
B. `border: bottom 3px solid #f59e0b;`
C. `border-width: 0 0 3px;`
D. `border-style: bottom;`

_RA: RA-6_

---

**3. [selección múltiple]** 🔘
Con `border-radius: 10px 0 10px 0;`, ¿qué esquinas quedan redondeadas?

A. Arriba a la izquierda y abajo a la derecha.
B. Arriba a la derecha y abajo a la izquierda.
C. Las cuatro.
D. Solo las dos de arriba.

_RA: RA-6_

---

**4. [identificación de resultado]** 🔍
Con el cálculo por defecto, ¿cuántos píxeles mide **de borde a borde** (sin contar el margen) esta caja?

```css
.caja {
  width: 300px;
  padding: 20px;
  border: 5px solid #111827;
  margin: 10px;
}
```

A. 300
B. 340
C. 350
D. 370

_RA: RA-7_

---

**5. [selección múltiple]** 🔘
Una caja tiene un contenido que no entra. ¿Qué valor de `overflow` recorta el contenido y muestra barras de desplazamiento **solo si hacen falta**?

A. `hidden`
B. `scroll`
C. `auto`
D. `visible`

_RA: RA-7_

---

**6. [identificación de resultado]** 🔍
Con `margin: 5px 10px 15px;`, ¿cuántos píxeles de margen tiene el lado **izquierdo**?

A. 5
B. 10
C. 15
D. 0

_RA: RA-8_

---

**7. [corrección de errores]** ✏️
Esta regla tiene **dos errores**: el navegador ignora dos de sus declaraciones. Encontralos y escribí la regla corregida con el mismo propósito (un relleno de `10px` y márgenes de `10px` arriba, `20px` a la derecha, `30px` abajo y `40px` a la izquierda).

```css
.tarjeta {
  padding: -10px;
  margin: 10px 20px 30px 40px 50px;
}
```

_RA: RA-8_

---

**8. [problema breve]** 🧩
Una caja tiene que medir **400px de borde a borde**, con relleno de `30px` y borde de `2px`. Escribí el `width` que necesitás con el cálculo por defecto y con `box-sizing: border-box`, y explicá en una frase por qué se prefiere `border-box`.

_RA: RA-7_
