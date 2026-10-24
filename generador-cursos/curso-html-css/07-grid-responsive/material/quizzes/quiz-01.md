# 📝 Quiz 01 — Grid y diseño adaptable

10 ítems: los **5 primeros** son de la **sesión 1** (Grid) y los **5 últimos**, de la **sesión 2** (diseño adaptable y consultas de medios). Sin respuestas (ver `material/soluciones/soluciones-quiz.md` para la clave, material exclusivamente docente).

---

**1. [selección múltiple]** 🔘
En una cuadrícula, ¿cómo se llama el cruce de una fila y una columna?

A. Línea
B. Pista
C. Celda
D. Contenedor

*RA: RA-1* · *Sesión: 1*

---

**2. [identificación de resultado]** 🔍
Con una ventana de `1200px` y sin huecos, ¿cuánto mide la columna `1fr` más ancha en `grid-template-columns: 200px 1fr 1fr`?

A. `200px`
B. `400px`
C. `500px`
D. `600px`

*RA: RA-2* · *Sesión: 1*

---

**3. [selección múltiple]** 🔘
Una galería usa `grid-template-columns: repeat(3, minmax(200px, 1fr))`. Con la ventana en `500px`, ¿qué ocurre?

A. Las tres columnas miden `166.66px` cada una
B. Las tres columnas miden `200px` y la cuadrícula se sale de la ventana
C. Se muestra una sola columna de `500px`
D. La regla no se aplica porque `minmax()` solo funciona con `px`

*RA: RA-2* · *Sesión: 1*

---

**4. [identificación de resultado]** 🔍
Una cuadrícula con `repeat(3, 1fr)` y `gap: 16px` está en una ventana de `1200px`. ¿Cuánto mide cada columna?

A. `400px`
B. `389.33px`
C. `384px`
D. `368px`

*RA: RA-3* · *Sesión: 1*

---

**5. [selección múltiple]** 🔘
¿Qué regla hace que un elemento ocupe **dos columnas** a partir de la celda donde le toca?

A. `grid-column: 2`
B. `grid-column: span 2`
C. `grid-columns: 2`
D. `column-span: 2`

*RA: RA-3* · *Sesión: 1*

---

**6. [selección múltiple]** 🔘
¿Para qué sirve `<meta name="viewport" content="width=device-width, initial-scale=1">`?

A. Para que la página se vea idéntica en todos los navegadores de escritorio
B. Para que un navegador de teléfono dibuje la página con el ancho real del dispositivo
C. Para cambiar la cantidad de columnas de una cuadrícula
D. Para obligar a que todas las imágenes sean flexibles

*RA: RA-4* · *Sesión: 2*

---

**7. [corrección de errores]** 🛠️
Esta hoja hace que la página se desborde en una ventana de `500px`. Encontrá **dos** errores y escribí la hoja corregida.

```css
.caja {
  width: 100%;
  padding: 20px;
  border: 5px solid #111827;
}

img {
  width: 1200px;
}
```

*RA: RA-5* · *Sesión: 2*

---

**8. [selección múltiple]** 🔘
¿En cuál de estos casos **basta** `repeat(auto-fit, minmax(200px, 1fr))`, sin consulta de medios?

A. Mover el menú de la izquierda a la derecha en pantallas anchas
B. Cambiar el orden de los bloques de la página según el dispositivo
C. Una galería de tarjetas iguales que pase de 2 a 5 columnas según el ancho
D. Ocultar el lateral en el teléfono

*RA: RA-6* · *Sesión: 2*

---

**9. [identificación de resultado]** 🔍
Con esta hoja, ¿qué tamaño de letra tiene `.t` en una ventana de `600px` de ancho?

```css
.t { font-size: 1rem; }

@media (min-width: 600px) {
  .t { font-size: 2rem; }
}
```

(Tamaño base: `16px`.)

A. `16px`
B. `32px`
C. `24px`
D. `2px`

*RA: RA-7* · *Sesión: 2*

---

**10. [problema breve]** ✍️
Esta hoja debería mostrar **tres** columnas desde `900px`, pero en una ventana de `1200px` muestra dos. Explicá por qué y escribí la corrección.

```css
.g { display: grid; grid-template-columns: 1fr; }

@media (min-width: 900px) {
  .g { grid-template-columns: repeat(3, 1fr); }
}

@media (min-width: 600px) {
  .g { grid-template-columns: repeat(2, 1fr); }
}
```

*RA: RA-7* · *Sesión: 2*
