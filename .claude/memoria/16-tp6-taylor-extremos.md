# TP6 — Taylor y extremos

**Parcial:** P1 (último tema del temario de P1: "hasta extremos inclusive")

## Fuentes

- Enunciado: `Guia - v digital.pdf`, "TP VI. Polinomio de Taylor — Extremos" (20 ejercicios).
- Presentación: `Presentaciones/TP6 - Taylor a.pdf` y `Presentaciones/TP6 - Taylor b.pdf`.
- Resolución propia: `Resueltos propios/TP6 - Taylor y extremos.md`.

## Teoría resumida

_(completar a medida que se estudia el tema — no inventar contenido acá sin haberlo visto en la presentación o la guía)_

## Errores frecuentes propios

Detectados en el repaso por preguntas del 24–25/09 (ítems E1, E4 y T2 del P1):

- **Taylor / potencias (E1):**
  - Leer el coeficiente de $(x-a)$ directo del polinomio original (tomó el $-3$ de $-3x$ cuando el coeficiente de $(x+3)$ era $p_x(-3,1)=-9$). Al cambiar de punto, los términos de grado alto aportan a los coeficientes bajos.
  - Invertir el signo de los paréntesis al armar el resultado: calculó bien en $(-3,1)$ pero escribió $(x-3)$ e $(y+1)$. Copiar los paréntesis tal cual del enunciado.
  - Cortar el desarrollo antes del grado del polinomio (faltó el término $(x+3)^2(y-1)$ de grado 3). El método de cambio de variable evita este olvido.
  - Control que no hizo y lo hubiera detectado: evaluar ambas expresiones en un punto fácil, como $(0,0)$.
- **Extremos (E4):**
  - Tomar la unión en lugar del sistema: $\nabla f=0$ exige $f_x=0$ **y** $f_y=0$ a la vez (da puntos, no rectas).
  - Buscar puntos críticos igualando a cero las derivadas **segundas** en vez de las primeras.
  - Contar como candidatos puntos fuera del dominio (los "puntos donde $f$ no es diferenciable" tienen que ser del dominio).
  - Olvidar calcular el valor de $f$ en los extremos cuando el enunciado lo pide.
  - Clasificar con "det < 0" sin mostrar $H$ evaluada ni el número del determinante.
- **Criterio de la hessiana (T2):** creer que $\det H(x_0)>0$ y $f_{xx}(x_0)>0$ alcanzan para un mínimo; falta la hipótesis $\nabla f(x_0)=0$. Confundió la definición de mínimo local con el criterio (condición suficiente).

## Estado

En curso — ejercicios 1 a 6 de 20 resueltos (ver `Resueltos propios/TP6 - Taylor y extremos.md`).
