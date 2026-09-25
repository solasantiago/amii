# P1 — Modelo de Primer Parcial (resolución propia)

Enunciados: `Modelos de parcial/Modelo_Primer_Parcial_AM2 (1).pdf`.

## E1

**Enunciado.** Expresar el polinomio $p(x,y) = -x^3 + 2x^2y + 4x - 5y + 10$ en potencias de $(x-1)$ y $(y+2)$.

**Tipo:** TP6 — Taylor. Mismo método que TP6 ej. 1a.

### Resolución

**Idea:** "en potencias de $(x-1)$ y $(y+2)$" significa desarrollar alrededor del punto $(1,-2)$. Como $p$ es un polinomio de grado 3, su Taylor de orden 3 en $(1,-2)$ **es el mismo** $p$, escrito de otra forma, y no queda resto.

**Cambio de variable:** $u = x-1$, $v = y+2$, o sea $x = u+1$, $y = v-2$.

$$
x^3 = (u+1)^3 = u^3 + 3u^2 + 3u + 1
$$

$$
x^2y = (u^2+2u+1)(v-2) = u^2v - 2u^2 + 2uv - 4u + v - 2
$$

Sustituyendo en cada término:

$$
\begin{aligned}
-x^3 &= -u^3 - 3u^2 - 3u - 1 \\
2x^2y &= 2u^2v - 4u^2 + 4uv - 8u + 2v - 4 \\
4x &= 4u + 4 \\
-5y &= -5v + 10 \\
+10 &= 10
\end{aligned}
$$

**Agrupando por potencia:**

- constante: $-1 - 4 + 4 + 10 + 10 = 19$
- $u$: $-3u - 8u + 4u = -7u$
- $v$: $2v - 5v = -3v$
- $u^2$: $-3u^2 - 4u^2 = -7u^2$
- $uv$: $4uv$
- $u^3$: $-u^3$
- $u^2v$: $2u^2v$

**Resultado:**

$$
\boxed{p(x,y) = 19 - 7(x-1) - 3(y+2) - 7(x-1)^2 + 4(x-1)(y+2) - (x-1)^3 + 2(x-1)^2(y+2)}
$$

### Control (en el parcial lleva 1 minuto)

Los coeficientes de orden 0 y 1 tienen que coincidir con Taylor:

- $p(1,-2) = -1 + 2(1)(-2) + 4 + 10 + 10 = 19$ ✓
- $p_x = -3x^2 + 4xy + 4 \Rightarrow p_x(1,-2) = -3 - 8 + 4 = -7$ ✓
- $p_y = 2x^2 - 5 \Rightarrow p_y(1,-2) = -3$ ✓

Además se verificó numéricamente que las dos expresiones coinciden en puntos al azar.
