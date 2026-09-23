# TP6 — Polinomio de Taylor y extremos

Resoluciones propias. Enunciados tomados de `Guia - v digital.pdf` (TP VI. Polinomio de Taylor — Extremos). No hay resueltos ni respuestas oficiales en el repo (ver `.claude/memoria/02-como-trabajamos.md`); la verificación es por consistencia interna del desarrollo.

## Ejercicio 1

**Enunciado.** Sea $P_3(x,y) = x^2 - xy + y^3 - 3$ el polinomio de Taylor de 3° orden del campo escalar $f$ en un entorno del punto $(1,2)$.

a) Exprésalo en potencias de $(x-1)$ e $(y-2)$.
b) ¿Cuál es el valor de $f$ en $(1,2)$?, ¿se puede calcular con el polinomio dado sin obtener la forma pedida en "a"?

### a) Exprésalo en potencias de $(x-1)$ e $(y-2)$.

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

### b) ¿Cuál es el valor de $f$ en $(1,2)$?, ¿se puede calcular con el polinomio dado sin obtener la forma pedida en "a"?

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

## Ejercicio 2

**Enunciado.** Dadas las superficies de ecuación $z=f(x,y)$ y $z=P(x,y)$, donde $P$ es la función polinómica que resulta de desarrollar $f$ en un disco de centro en $(x_0,y_0)$ hasta el orden $n$, verifique que ambas superficies tienen el mismo plano tangente en el punto $(x_0,y_0,f(x_0,y_0))$.

### Resolución

El plano tangente a $z=f(x,y)$ en $(x_0,y_0)$ es

$$
z = f(x_0,y_0) + f_x(x_0,y_0)(x-x_0) + f_y(x_0,y_0)(y-y_0)
$$

Por construcción, el polinomio de Taylor de orden $n\ge 1$ de $f$ centrado en $(x_0,y_0)$ tiene la forma

$$
P(x,y) = f(x_0,y_0) + f_x(x_0,y_0)(x-x_0) + f_y(x_0,y_0)(y-y_0) + \underbrace{\left[\text{términos de grado} \ge 2 \text{ en } (x-x_0),(y-y_0)\right]}_{R(x,y)}
$$

Cada término de $R(x,y)$ es de la forma $c_{ab}(x-x_0)^a(y-y_0)^b$ con $a+b\ge 2$. Al derivar una sola vez respecto de $x$ o de $y$ y evaluar en $(x_0,y_0)$, todo término con $a+b\ge 2$ se anula (porque siempre queda al menos un factor $(x-x_0)$ o $(y-y_0)$ sin derivar, que vale $0$ en el centro). Entonces:

$$
P(x_0,y_0) = f(x_0,y_0), \qquad P_x(x_0,y_0) = f_x(x_0,y_0), \qquad P_y(x_0,y_0) = f_y(x_0,y_0)
$$

Por lo tanto, el plano tangente a $z=P(x,y)$ en $(x_0,y_0)$ es

$$
z = P(x_0,y_0) + P_x(x_0,y_0)(x-x_0) + P_y(x_0,y_0)(y-y_0) = f(x_0,y_0) + f_x(x_0,y_0)(x-x_0) + f_y(x_0,y_0)(y-y_0)
$$

que es exactamente el mismo plano que el de $f$. $\blacksquare$

**Propiedad usada:** el polinomio de Taylor de orden $n$ coincide con $f$ y con todas sus derivadas hasta el orden $n$ inclusive, únicamente en el punto de centro $(x_0,y_0)$ (esto es lo que se usó también en el ejercicio 1b).

## Ejercicio 3

**Enunciado.** Desarrolle los siguientes campos por Taylor hasta 2° orden en un entorno de $\bar A$.

a) $f(x,y) = x - y\sqrt{6-x}$, $\bar A=(2,3)$.
b) $f(x,y) = y\ln(x)$, $\bar A=(1,2)$.

### a) $f(x,y) = x - y\sqrt{6-x}$, $\bar A=(2,3)$.

Escribo $f(x,y) = x - y(6-x)^{1/2}$ y calculo las derivadas necesarias.

**Primeras derivadas:**

$$
f_x = 1 + \frac{y}{2\sqrt{6-x}}, \qquad f_y = -\sqrt{6-x}
$$

**Segundas derivadas:**

$$
f_{xx} = \frac{y}{4(6-x)^{3/2}}, \qquad f_{xy} = \frac{1}{2\sqrt{6-x}}, \qquad f_{yy} = 0
$$

**Evaluando en $\bar A=(2,3)$** (con $\sqrt{6-2}=2$):

$$
f(2,3) = 2 - 3\cdot 2 = -4
$$

$$
f_x(2,3) = 1 + \frac{3}{4} = \frac74, \qquad f_y(2,3) = -2
$$

$$
f_{xx}(2,3) = \frac{3}{4\cdot 8} = \frac{3}{32}, \qquad f_{xy}(2,3) = \frac14, \qquad f_{yy}(2,3)=0
$$

**Polinomio de Taylor de 2° orden** ($h=x-2$, $k=y-3$):

$$
P_2(x,y) = f(\bar A) + f_x(\bar A)\,h + f_y(\bar A)\,k + \tfrac12 f_{xx}(\bar A)\,h^2 + f_{xy}(\bar A)\,hk + \tfrac12 f_{yy}(\bar A)\,k^2
$$

$$
\boxed{f(x,y) \cong -4 + \frac74(x-2) - 2(y-3) + \frac{3}{64}(x-2)^2 + \frac14(x-2)(y-3)}
$$

(el término en $(y-3)^2$ desaparece porque $f_{yy}=0$).

### b) $f(x,y) = y\ln(x)$, $\bar A=(1,2)$.

**Primeras derivadas:**

$$
f_x = \frac{y}{x}, \qquad f_y = \ln(x)
$$

**Segundas derivadas:**

$$
f_{xx} = -\frac{y}{x^2}, \qquad f_{xy} = \frac{1}{x}, \qquad f_{yy} = 0
$$

**Evaluando en $\bar A=(1,2)$:**

$$
f(1,2) = 2\ln(1) = 0
$$

$$
f_x(1,2) = 2, \qquad f_y(1,2) = \ln(1) = 0
$$

$$
f_{xx}(1,2) = -2, \qquad f_{xy}(1,2) = 1, \qquad f_{yy}(1,2) = 0
$$

**Polinomio de Taylor de 2° orden** ($h=x-1$, $k=y-2$):

$$
\boxed{f(x,y) \cong 2(x-1) - (x-1)^2 + (x-1)(y-2)}
$$

## Ejercicio 4

**Enunciado.** Calcule en forma aproximada, aplicando en un punto conveniente, el polinomio de Taylor hasta segundo orden:

a) $0.98^{2.01}$
b) $\sqrt{3.99} + \sqrt[3]{8.06}$
c) $8.79/3.02$

### a) $0.98^{2.01}$

Punto conveniente: $f(x,y)=x^y$ centrado en $\bar A=(1,2)$ (porque $0.98\approx 1$ y $2.01\approx 2$, con derivadas simples ahí). $h=x-1=-0.02$, $k=y-2=0.01$.

$$
f(1,2)=1, \quad f_x = y\,x^{y-1} \Rightarrow f_x(1,2)=2, \quad f_y = x^y\ln x \Rightarrow f_y(1,2)=0
$$

$$
f_{xx} = y(y-1)x^{y-2} \Rightarrow f_{xx}(1,2)=2, \quad f_{xy} = x^{y-1}(1+y\ln x) \Rightarrow f_{xy}(1,2)=1, \quad f_{yy} = x^y(\ln x)^2 \Rightarrow f_{yy}(1,2)=0
$$

$$
f \cong 1 + 2(-0.02) + 0(0.01) + \tfrac12(2)(-0.02)^2 + 1\cdot(-0.02)(0.01) + 0 = 1 - 0.04 + 0.0004 - 0.0002
$$

$$
\boxed{0.98^{2.01} \cong 0.96}
$$

### b) $\sqrt{3.99} + \sqrt[3]{8.06}$

Punto conveniente: $f(x,y)=\sqrt{x}+\sqrt[3]{y}$ centrado en $\bar A=(4,8)$ (porque $\sqrt4=2$ y $\sqrt[3]8=2$ son exactos). $h=x-4=-0.01$, $k=y-8=0.06$.

Como $f$ es suma de una función solo de $x$ más una solo de $y$, $f_{xy}=0$.

$$
f(4,8)=2+2=4
$$

$$
f_x=\frac{1}{2\sqrt x}\Rightarrow f_x(4,8)=\frac14, \qquad f_y=\frac{1}{3y^{2/3}}\Rightarrow f_y(4,8)=\frac{1}{12}
$$

$$
f_{xx}=-\frac{1}{4x^{3/2}}\Rightarrow f_{xx}(4,8)=-\frac{1}{32}, \qquad f_{yy}=-\frac{2}{9y^{5/3}}\Rightarrow f_{yy}(4,8)=-\frac{1}{144}
$$

$$
f \cong 4 + \tfrac14(-0.01) + \tfrac1{12}(0.06) + \tfrac12\left(-\tfrac1{32}\right)(-0.01)^2 + \tfrac12\left(-\tfrac1{144}\right)(0.06)^2
$$

$$
f \cong 4 - 0.0025 + 0.005 - 0.0000016 - 0.0000125 \cong 4.0025
$$

$$
\boxed{\sqrt{3.99} + \sqrt[3]{8.06} \cong 4.0025}
$$

### c) $8.79/3.02$

Punto conveniente: $f(x,y)=x/y$ centrado en $\bar A=(9,3)$ (porque $9/3=3$ es exacto). $h=x-9=-0.21$, $k=y-3=0.02$.

$$
f(9,3)=3, \qquad f_x=\frac1y\Rightarrow f_x(9,3)=\frac13, \qquad f_y=-\frac{x}{y^2}\Rightarrow f_y(9,3)=-1
$$

$$
f_{xx}=0, \qquad f_{xy}=-\frac{1}{y^2}\Rightarrow f_{xy}(9,3)=-\frac19, \qquad f_{yy}=\frac{2x}{y^3}\Rightarrow f_{yy}(9,3)=\frac23
$$

$$
f \cong 3 + \tfrac13(-0.21) + (-1)(0.02) + 0 + \left(-\tfrac19\right)(-0.21)(0.02) + \tfrac12\left(\tfrac23\right)(0.02)^2
$$

$$
f \cong 3 - 0.07 - 0.02 + 0.000467 + 0.000133 \cong 2.9106
$$

$$
\boxed{8.79/3.02 \cong 2.91}
$$

## Ejercicio 5

**Enunciado.** Sea $f:\mathbb{R}^2\to\mathbb{R}$, $f\in C^2$, si el polinomio de Taylor de 2° grado, asociado a la función $f$ en un disco de centro en punto $(1;1)$ es $P_2(x,y) = 2 - x - 3y + 3x^2 + \frac12 y^2$. Encuentre los valores reales de $a$ y $b$ de la función: $g(x;y) = f(x;y) - 3ax + by$, para que el plano tangente a la gráfica de $g(x;y)$ en el punto $A=(1,1,g(1,1))$ sea: $20x-10y+2z=D$.

### Resolución

**Derivadas de $f$ en $(1,1)$** (coinciden con las de $P_2$ por ser su polinomio de Taylor):

$$
P_x = -1+6x \Rightarrow f_x(1,1)=P_x(1,1)=5, \qquad P_y=-3+y \Rightarrow f_y(1,1)=P_y(1,1)=-2
$$

**Derivadas de $g=f-3ax+by$:**

$$
g_x = f_x - 3a \;\Rightarrow\; g_x(1,1) = 5-3a, \qquad g_y = f_y + b \;\Rightarrow\; g_y(1,1) = -2+b
$$

**Plano tangente a $g$ en $A$:**

$$
z = g(1,1) + g_x(1,1)(x-1) + g_y(1,1)(y-1)
$$

que reordenado queda $g_x(1,1)\,x + g_y(1,1)\,y - z = \text{cte}$. El plano pedido, $20x-10y+2z=D$, reordenado como $20x-10y-(-2z)=D$ tiene la forma $z = \tfrac{D}{2} -10x+5y$, es decir coeficiente de $x$ igual a $-10$ y de $y$ igual a $5$. Igualando con los coeficientes del plano tangente a $g$:

$$
g_x(1,1) = -10 \;\Rightarrow\; 5-3a=-10 \;\Rightarrow\; 3a=15 \;\Rightarrow\; \boxed{a=5}
$$

$$
g_y(1,1) = 5 \;\Rightarrow\; -2+b=5 \;\Rightarrow\; \boxed{b=7}
$$

## Ejercicio 6

**Enunciado.** Sea $f:\mathbb{R}^2\to\mathbb{R}$, $f\in C^3$, cuyo polinomio de Taylor de 2º grado, asociado a la función $f$ en un disco de centro en punto $(2;2)$ es $P_2(u,v) = 14 + v^2 - 2uv - u^2$. Si $h(x,y)=f(x^2-2y,\, y^2+xy-1)$, estime el valor aproximado de $h(1.98,1.02)$ empleando una aproximación lineal.

### Resolución

**Punto de trabajo:** busco $(x_0,y_0)$ tal que $\varphi(x,y)=(x^2-2y,\,y^2+xy-1)$ caiga en el centro $(2,2)$ del polinomio de $f$, y que sea cercano a $(1.98,1.02)$. Probando $(x_0,y_0)=(2,1)$:

$$
u(2,1)=2^2-2\cdot1=2, \qquad v(2,1)=1^2+2\cdot1-1=2 \quad\checkmark
$$

**Valor de $h$ en el centro**, usando que $f(2,2)=P_2(2,2)$ (Taylor coincide con $f$ en el centro):

$$
h(2,1) = f(2,2) = P_2(2,2) = 14 + 2^2 - 2\cdot2\cdot2 - 2^2 = 14+4-8-4 = 6
$$

**Derivadas parciales de $f$ en $(2,2)$**, usando que coinciden con las de $P_2$:

$$
P_u = -2v-2u \Rightarrow f_u(2,2)=-8, \qquad P_v = 2v-2u \Rightarrow f_v(2,2)=0
$$

**Regla de la cadena** para $h(x,y)=f(u(x,y),v(x,y))$ con $u=x^2-2y$, $v=y^2+xy-1$:

$$
u_x=2x,\quad u_y=-2, \qquad v_x=y,\quad v_y=2y+x
$$

En $(x_0,y_0)=(2,1)$: $u_x=4$, $u_y=-2$, $v_x=1$, $v_y=4$.

$$
h_x(2,1) = f_u\,u_x + f_v\,v_x = (-8)(4)+(0)(1) = -32
$$

$$
h_y(2,1) = f_u\,u_y + f_v\,v_y = (-8)(-2)+(0)(4) = 16
$$

**Aproximación lineal** ($h=x-2$, $k=y-1$, sin términos de 2° orden por pedir "aproximación lineal"):

$$
h(x,y) \cong h(2,1) + h_x(2,1)(x-2) + h_y(2,1)(y-1) = 6 - 32(x-2) + 16(y-1)
$$

Evaluando en $(1.98,1.02)$, con $x-2=-0.02$ e $y-1=0.02$:

$$
h(1.98,1.02) \cong 6 - 32(-0.02) + 16(0.02) = 6 + 0.64 + 0.32
$$

$$
\boxed{h(1.98,1.02) \cong 6.96}
$$
