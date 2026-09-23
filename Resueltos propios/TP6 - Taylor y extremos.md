# TP6 — Polinomio de Taylor y extremos

Resoluciones propias, contrastadas contra `Guia de ejercicios-20260923/Respuestas/RESPUESTAS TP VI.pdf`. Enunciados tomados de `Guia de ejercicios-20260923/Guia - v digital.pdf`.

## Ejercicio 1

**Enunciado.** Sea $P_3(x,y) = x^2 - xy + y^3 - 3$ el polinomio de Taylor de 3° orden del campo escalar $f$ en un entorno del punto $(1,2)$.

a) Exprésalo en potencias de $(x-1)$ e $(y-2)$.
b) ¿Cuál es el valor de $f$ en $(1,2)$? ¿Se puede calcular con el polinomio dado sin obtener la forma pedida en "a"?

### a) Reescritura en potencias de $(x-1)$, $(y-2)$

Cambio de variable $u = x-1$, $v = y-2$, es decir $x = u+1$, $y = v+2$.

$$
x^2 = (u+1)^2 = u^2 + 2u + 1
$$

$$
xy = (u+1)(v+2) = uv + 2u + v + 2
$$

$$
y^3 = (v+2)^3 = v^3 + 6v^2 + 12v + 8
$$

Sustituyendo en $P_3 = x^2 - xy + y^3 - 3$:

$$
P_3 = (u^2 + 2u + 1) - (uv + 2u + v + 2) + (v^3 + 6v^2 + 12v + 8) - 3
$$

Agrupando por potencia:

- $u^2$: queda $u^2$
- $uv$: queda $-uv$
- $u$: $2u - 2u = 0$ (se cancela)
- $v$: $-v + 12v = 11v$
- $v^2$: $6v^2$
- $v^3$: $v^3$
- constantes: $1 - 2 + 8 - 3 = 4$

$$
P_3(x,y) = 4 + 11(y-2) + (x-1)^2 - (x-1)(y-2) + 6(y-2)^2 + (y-2)^3
$$

Coincide con la respuesta oficial de la guía.

### b) Valor de $f(1,2)$

Por definición del polinomio de Taylor, $f$ y $P_3$ (y todas sus derivadas hasta el orden $n$) coinciden **exactamente en el punto de desarrollo** $(x_0,y_0) = (1,2)$ — eso es lo que garantiza la construcción del polinomio, aunque fuera de ese punto $P_3$ solo aproxima a $f$.

Por lo tanto:

$$
f(1,2) = P_3(1,2)
$$

**No hace falta** pasar por la forma en potencias de $(x-1),(y-2)$ del punto a): alcanza con evaluar directamente la expresión original dada,

$$
P_3(1,2) = 1^2 - 1\cdot 2 + 2^3 - 3 = 1 - 2 + 8 - 3 = 4
$$

(y, como control, evaluando la forma de a) en $(1,2)$ todos los términos con $(x-1)$ o $(y-2)$ se anulan y solo queda la constante $4$ — mismo resultado).

$$
\boxed{f(1,2) = 4}
$$
