<!-- inject de mathjax -->

<script> MathJax = { tex: { inlineMath: [['$', '$'], ['\\(', '\\)']] }, svg: { fontCache: 'global' } }; </script> <script type="text/javascript" id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js"> </script>

$\def\RR{\Bbb{R}}$
$\def\RRn{\RR^n}$
$\def\PP{\Bbb{P}}$ $\def\PPn{\PP^n}$
$\def\powm{^{-1}}$ $\def\powb{^{2}}$ $\def\pow{^}$

# Espacio tangente, campos vectoriales, métrica Riemanniana

## espacio tangente

El espacio tangente de M tiene una proyección natural
$$
TM \to M: v_p \mapsto p
$$

Una sección de esta proyección es un _campo vectorial_.

Así, un campo vectorial  es una asignación
$$
X: M \to TM : p \mapsto X(p) \in T_pM
$$ 

Recuérdese que $TM$ es también una variedad diferenciable.

## Campos vectoriales y operadores diferenciales

Un campo vectorial se puede escribir en coordenadas
$$
X=\sum_i {a_i \partial_i}
$$

Si $X,Y$ son campos vectoriales, existe un único campo vectorial
$Z$ tal que para toda función diferenciable $f:M\to \RR$ se tiene
$$
Z[f] = (XY - YX)[f]
$$

Este Z se llama el bracket de X e Y: $Z=[X,Y]$

## Propiedades del bracket

1. $[X_1,X_2] = -[X_2,X_1]$
2. Es $\RR$-lineal en cada entrada.
3. $\sum_{\sigma\in \text{cicl}}{[[X_{\sigma(1)},X_{\sigma(2)}],X_{\sigma(3)}]} = 0$
4. $[fX,gY] = fg[X,Y] + fX(g)Y - gY(f)X$

## Bracket como derivada

**Prop.** Sea X campo vectorial diferenciable en una variedad diferenciable M, p un punto en M. Entonces existe $U \subset M$, $\delta \in \RR, \delta > 0$ y $\phi:(-\delta,\delta)\times U \to M$ tales que la curva $t\mapsto \phi(t,q), t\in (-\delta,\delta), q \in U$ es la
única curva que satisface
$$
\frac{\partial \phi}{\partial t} = X(\phi(t,q))
$$

De esta forma se puede ver el bracket de otra forma

**Prop** Sean X, Y campos vectoriales diferenciables en una variedad diferenciable,  p un punto de M, y sea $\phi$ el flujo de X en un entorno de p. Entonces
$\def \d {\operatorname{d}}$
$$
[X,Y] (p) = \lim_{t\to 0} {\frac{1}{t} [Y-\d\phi_t(Y)] (\phi_t(p))}
$$

Esto asocia al bracket con una derivación de campos vectoriales.

## Métrica Riemanniana en $TM$

**Def** Una _Métrica Riemanniana_ es una función diferenciable que asigna a cada $p\in M$ una forma bilineal definida positiva en $T_pM$.

Una variedad M con métrica riemanniana $<,>$ se llama **variedad Riemanniana**.

**Ejemplo:** Para la variedad diferenciable
$$
M:xy-z = 0
$$
Con estructura diferenciable heredada de $\RR\pow3$, se hereda también un producto interno.

El espacio $\RR\pow3$ tiene una métrica Riemanniana natural, dada por el producto interior natural en su espacio tangente. Esta métrica se hereda a $M$, de forma que en una carta (la única que necesitamos en este caso) dada por 
$$
x:\RR\pow2 \to M: (u,v) \mapsto (u,v,uv)
$$

$\def\p#1{\partial_#1}$
La métrica $g$ (usando las notaciones $\p{u}$ y $x_u$) está dada explícitamente por:
$$
\begin{align}
g(\p{u},\p{v}) &= x_u \cdot x_v = (1,0,v)\cdot(0,1,u) = uv \\\\
g(\p{u},\p{u}) &= x_u \cdot x_u = 1 + v\pow2 \\\\
g(\p{v},\p{v}) &= x_v \cdot x_v = 1+u\pow2
\end{align}
$$

En otras palabras, la matriz de la forma bilineal en un punto con coordenadas (u,v) está dada por:
<div>
\begin{pmatrix}
1 + v\pow2 & uv \\\\
uv & 1+v\pow2
\end{pmatrix}
=
\begin{pmatrix}
E & F \\\\
F & G
\end{pmatrix}
</div>

Observe que esta matriz es la identidad en (0,0).

**Fin del ejemplo.**

Es natural, para este ejemplo y en general, definir una métrica para tener noción de distancia (y por tanto una métrica) en la variedad que estamos estudiando. Posiblemente la variedad no esté dada en un espacio ambiente $\RR\pow n$ (e.g. existen los toros planos que no tienen equivalente difeomorfo en $\RR\pow3$).

Esta métrica $g$, tiene una estructura respecto a su evaluación en el espacio tangente que le da la denominación de *tensor métrico*. Hablaremos de tensores con más detalle posteriormente.

El tensor métrico, por su definición y significado, permite en principio definir y calcular la longitud de curvas rectificables (no estrictamente de todas las curvas). Tambien da una noción de medida de área.

*Longitud de una curva:* La longitud de una curva $\alpha:I\to M$ en una variedad $M$ con métrica $g$ es
$$
\ell(\alpha) = \int_I{\sqrt{g(\alpha'(s),\alpha'(s))}\d s}
$$

Esto se simplifica, _para una superficie_ y dada una carta, a:
$$
\ell(\alpha) = \int_I{\sqrt{ E (u')\pow2 + F u'v' + G (v')\pow2 } \d s}
$$
Donde $u(t)$ y $v(t)$ son las coordenadas de la curva $\alpha$, y

$$
\begin{align}
E&=g(\p{u},\p{u}) \\\\
F&=g(\p{u},\p{v}) \\\\
G&=g(\p{v},\p{v})
\end{align}
$$

La expresión subradical $E (u')\pow2 + F u'v' + G (v')\pow2$ se llama la primera forma fundamental de la superficie $M$.

Observe que para una variedad de dimensiones más grandes, la expresión es más extensa pero su construcción es natural.

**Ejercicio** Para la superficie $M:x\pow2 + y\pow2 -z\pow2 -1 =0$, y la curva $\alpha:[-1,1]\to M: t\mapsto (1,t,t)$, encuentre la longitud en $I=[-1,1]$. Observe que, curiosamente esta es una recta propiamente. Encuentre una carta, la expresión del tensor métrico ahí, las coordenadas de la curva, la primera forma fundamental, y calcule la longitud en ese intervalo $I$.

Estos son ejemplos donde el tensor métrico está dado naturalmente por la estructura ambiente, pero en general un tensor métrico se puede asignar a una variedad diferenciable sin tener que pensar en un espacio ambiente. De hecho, se puede pensar en el espacio de todas las métricas que se le pueden dar a una variedad, y este espacio en sí mismo es sumamente interesante.

Para calcular el volumen de una variedad M orientable de dimensión n, tenemos que para una base $(\partial_1,\dots,\partial_n)$, el elemento de volumen (que es naturalmente una forma diferencial de volumen) está dado por el valor absoluto de
$$
\det(\partial_1,\dots,\partial_n)
$$
Si escogemos un campo de marcos $E_i$ (es decir, en cada punto asignamos un marco ortonormal), entonces podemos escribir $\partial_i = \sum_{k}{a_{i,k}E_k}$ . Así, se verifica que el tensor métrico
está dado por
$$
g_{ij} = <\partial_i,\partial_j> = \sum_k{a_{ik}a_{jk}}
$$

Por tanto, el volúmen está dado por (al menos en la carta en la que se ha parametrizado):
$$
\int {\sqrt{|\det(g)|}}
$$

Esto tiene sentido en general, pero es detalle sobre integración de formas diferenciables en la variedad.

**Ejercicio:** Expresar el volumen de la variedad
$$
M: z -xy=0 \quad , \quad 0 < x,y < 1
$$


## Derivadas y marcos

El sistema de Frenet permite expresar las derivadas a lo largo de una curva de un sistema de referencia. Esto permite tener el concepto no solo de derivada direccional de funciones escalares, sino que permite derivar funciones vectoriales sobre la curva. En el caso de las ecuaciones de Frenet-Serret, lo que tenemos es la derivación de campos vectoriales (más precisamente, de *marcos*) a lo largo de la curva, es decir, en la dirección de la tangente. Esta derivada la denotamos, siguiendo una notación un poco informal ahora, como $\nabla_T E$, donde E es uno de los campos vectoriales de forman parte del marco (es decir, es T, N o B):
$$
\begin{align}
T' &=\nabla_T T = \kappa N \\\\
N' &=\nabla_T N = -\kappa T + \tau B \\\\ %doble para mathjax o markor
B' &=\nabla_T B = - \tau N
\end{align}
$$

Para una variedad diferenciable M, esto motiva a definir $\nabla_v X$ para un vector $v\in T_p M$, $v = \alpha'(0)$ para una curva $\alpha$, y un campo vectorial en $M$, **cuando M está dada como subvariedad de $\RRn$ para algún n** se tiene

$\def\dd\{\mathrm{d}}$
$$
\nabla_v X = \frac{\dd}{\dd t}X(\alpha(t)) \mid _{t=0}
$$

Esta se conoce como derivada covariante.

**Obs:** Esta notación puede ser confusa, pues este símbolo se usa de forma ligeramente diferente en un contexto más general, como veremos en un momento.

Esta derivada la vamos a usar para estudiar la curvatura de una superficie. Observe que para una curva plana, las ecuaciones de Frenet son esencialmente 2:
$$
\begin{align}
T' &=\nabla_T T = \kappa N \\\\
N' &=\nabla_T N = -\kappa T 
\end{align}
$$

Es decir, un campo normal da información sobre la curvatura tambien. Para ello, vamos a generalizar lo que tenemos en el sistems de Frenet para derivar campos vectoriales.

## Derivada covariante. Derivación de campos vectoriales. Transporte paralelo.

Históricamente, para una variedad M en $\RRn$, la derivada covariante de un campo vectorial X en la dirección $v=\alpha'(0) \in T_pM$ se tomó como la proyección en el espacio tangente de la derivada conocida
$$
\mathrm{proy}_{T_pM}{\frac{\dd}{\dd t}X(\alpha(t)) \mid _{t=0}}
$$

Esto es útil para los cálculos en variedades encajadas en $\RRn$ (recuede brevemente la definición de encajes y embebimientos).

Observe que para los campos unitarios E (como T, N y B) en las curvas en $\RRn$, la derivada de E es ortogonal a E (esto es un ejercicio de sistemas de Frenet).

Para tener notación, llame $\chi(M)$ al espacio de campos vectoriales $C^\infty$ sobre M.

En general, se define una **conexión afín** por lo siguiente:

$\def\cM{\chi(M)}$$\def\DM{\mathcal{D}(M)}$
**Def.** Una *conexión afín* $\nabla$ en una variedad diferenciable M es un operador
$$
\cM \times \cM \to \cM
$$
tal que $\nabla_X Y$ :
1. es lineal en X  
2. es aditivo en Y  
3. y para todos $X, Y \in \cM$ y funciones $f,g\in \DM$:
$\nabla_X(fY) = X[f]Y + f\nabla_X Y$ 

Observe que se define la conexión afín en M, no se necesita información del espacio ambiente.

Esto permite definir la derivada covariante. Siguiendo el libro de Do Carmo la definiremos así:

$\def\Dt#1{\frac{\mathrm{D} #1}{\dd t}}$
$\def\DDt{\frac{\mathrm{D}}{\dd t}}$
$\def\dt#1{\frac{\mathrm{d} #1}{\dd t}}$
**Def** Para una curva c sobre una variedad diferenciable M, existe una única correspondencia que asocia a un campo vectorial V sobre c otro campo $\Dt{V}$ llamado derivada covariante de V a lo largo de c, tal que:
1) $\DDt(V+U) = \Dt{V} + \Dt{U}$  
2) $\DDt(fV) = (\dt{f})V + f\Dt{V}$
3) Si $V = Y\mid _ c$ entonces $\Dt{V} = \nabla_{c'(t)}Y$

Observe que esta definición relaciona la derivada covariante con la conexión afín.

## Transporte paralelo

La conexión afín permite definir naturalmente el transporte paralelo:

**Def.**  un campo vectorial V a lo largo de c es **paralelo** si su derivada covariante es nula en toda la curva.

Dado un vector $V_0 \in T_pM$, y una curva c que empieza en p, existe un único campo V sobre c que extiende a $V_0$ y que es paralelo a lo largo de c. Esto se llama el **transporte paralelo** de $V_0$.

## Operador de forma

Ahora vamos a estudiar una variedad N inmersa (embebida, embedded) en una variedad Riemanniana M.

* El espacio tangente de N es naturalmente un subespacio del tangente de M
* De esta forma, podemos descomponer cualquier campo sobre N en una parte tangente a N y otra parte ortogonal a N.

Dado un campo U normal y unitario sobre N, se puede definir un operador:
$$
S: \cM \to \cM: X \mapsto -\nabla_X(U)
$$

Este operador se llama **operador de forma** asociado a U.

Este operador de forma, da intuitivamente la información de la curvatura así como en una curva plana la variación de N da información sobre la curvatura.

Un operador asociado al operador de forma se llama **segunda forma fundamental**:
$$
\mathrm{II}(X)= <S(X),X>
$$

Esta forma (es una forma diferencial) da información sobre qué tan curva está la variedad.

