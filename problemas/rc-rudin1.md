**Problema 3.** Demuestre que si $f$ es una función real en una espacio medible $X$ tal que $\{x: f(x) \ge r\}$ es medible para todo racional $r$, entonces $f$ es medible.

*Demostración.* Sea $\alpha$ un número real. Dado que el conjunto de racionales $\mathbb Q$ es denso en los reales, existe para cada $n \in \mathbb N$ un racional $q_n$ tal que $\alpha < q_n < \alpha + \frac{1}{n}$. Por definición, la sucesión $\{q_n\}$ tiende a $\alpha$ cuando $n$ tiende a infinito. Luego,
$$f^{-1}((\alpha, \infty]) = \bigcup_n f^{-1}((q_n, \infty]).$$
Esto muestra que $f$ es medible.

---

**Problema 6.** Sea $X$ no numerable, y sea $S$ la familia de todos los conjuntos $E \subset X$ tal que $E$ o $E^c$ es a lo más numerable. Defina $\mu(E) = 0$ si $E$ es numerable y $\mu(E) = 1$ si $E^c$ es numerable. Demuestre que $S$ es una sigma-álgebra, $\mu$ es una medida en $(X, S)$. Describa a las correspondientes funciones medibles y sus integrales.

*Demostración.* 
1. Dado que $\varnothing$ es finito, este pertenece a $S$.
2. Si $A \in S$, entonces $A$ o $A^c$ es a lo más numerable. Por simetría, $A^c$ también es elemento de $S$.
3. Sea $\{A_n\}$ una sucesión de elementos en $S$. Si todos los elementos de la sucesión son a lo más numerables, entonces $A = \bigcup_n A_n$ es numerable, por lo que $A \in S$. Por otro lado, suponga que existe un elemento en la sucesión, digamos $A_k$, tal que $A_k^c$ es numerable. Como $A_k \subset A$, se tiene que $A^c \subset A_k^c$, por lo que $A^c$ es a lo más numerable. Ambos casos muestran que $A \in S$.
Concluimos que $S$ es una sigma-álgebra.

El punto 1 anterior muestra que $\mu(\varnothing) = 0$. Sea ahora una sucesión disjunta $\{A_n\}$ de elementos en $S$. Si todos son los elementos de la sucesión son a lo más numerables, entonces
$$0 = \mu\left(\bigcup_nA_n\right) = \sum_n 0 = \sum_n\mu(A_n).$$
Por otro lado, suponga que existen dos elementos, digamos $A_k$ y $A_m$, en la sucesión cuyos complementos son a lo más numerables. Como la sucesión es disjunta,  $A_k \cap A_m = \varnothing$, lo cual implica que $A_k \subset A_m^c$. Pero entonces $X = A_k \cup A_k^c$ es la unión de dos conjuntos a lo más numerables, lo que contradice la hipótesis de que $X$ es no numerable. Por tanto, si en la sucesión $\{A_n\}$ existe algún elemento cuyo complemento es a lo más numerable, este es único en la sucesión. Luego,
$$1 = \mu\left(\bigcup_n A_n \right) = 1 + 0 = \mu(A_k) + \sum_{n\neq k} \mu(A_n) = \sum_n \mu(A_n)$$
donde $A_k$ es el elemento con complemento a lo más numerable. Por tanto $\mu$ es sigma-aditiva. Concluimos que $\mu$ es una medida. 

Sea $f: X \rightarrow [-\infty, \infty]$ una función medible en $X$ y considere la familia de intervalos $(n, n+1)$ donde $n \in \mathbb . Entonces, para toda $n\in \mathbb N$, el conjunto 
$$A_n = \{x: f(x) >  -n\},$$ es medible en $X$. Note que $A_n \subset A_{n+1}$  y $\bigcup_

---
**Problema 7.** Sean $f_n: X \rightarrow [0, \infty]$ medibles, $f_n \geq f_{n + 1}$ y $f_n \ge 0$ para toda $n \in \mathbb N$. Sea $f = \lim f_n$ para toda $x \in X$ y $f_1 \in L^1(\mu)$.  Demuestre que 
$$\lim_{n \to \infty} \int_X f_n d\mu = \int_X f d\mu.$$
Además, muestre que la condición $f_1 \in L^1(\mu)$ es necesaria.
*Demostración:* Para toda $n \in \mathbb N$ defina $g_n: X \rightarrow \mathbb R$ como 
$$g_n(x) = \begin{cases} f_{1}(x) - f_{n}(x), & \text{si } f_{n}(x) \neq \infty ;\\0, & \text{de otro modo.} \end{cases}$$
Cada $g_n$ es medible y no negativa. Más aún, $g_n(x) = f_1(x) - f_{n}(x) \leq f_{1}(x) - f_{n+1}(x) = g_{n+1}(x)$  para toda $n\in \mathbb N$. Por tanto, el Teorema de Convergencia Monótona establece que 
$$\lim_{n\to \infty} \int_X g_n d\mu = \lim_{n \to \infty} \int_X f_1 - f_n d \mu =  \int_X \lim_{n \to \infty} f_1 - f_{n} d \mu = \int_X f_1 - f d\mu. $$Luego, $\int_X f_1 d\mu - \lim \int_X f_n d \mu = \int_X f_1 d \mu - \int_X f d\mu$. Como $f_1 \in L^1(\mu)$, podemos restar $\int_X f_1 d \mu$ en ambos lados de la igualdad y obtener
$$ \lim_{n\to \infty} \int_X f_n d \mu = \int_X f d\mu.$$

Considere ahora el espacio de medida $(\mathbb N, P(\mathbb N), \mu)$, donde $\mu$ es la medida de contar. Para cada $n \in \mathbb N$, defina $A_n = \{n, n+1, n+2, \ldots \}$. Note que la sucesión $\chi_{A_n}$ es decreciente, es positiva y 
$$ \lim_{n \to \infty} \chi_{A_n} \equiv 0.$$
Pero, $\int_{\mathbb N} \chi_{A_n} d\mu = \mu(A_n) = \infty$ para toda $n \in \mathbb N$. Por lo que 
$$ \lim_{n\to \infty} \int_{\mathbb N} \chi_{A_n} d\mu \neq \int_{\mathbb N} \lim_{n \to \infty} \chi_{A_n} d\mu.$$
En este ejemplo, $\chi_{A_n}$ no pertenece al conjunto $L^1(\mu)$.

---
**Problema 8**. Considere $f_n = \chi_E$ si $n$ es impar y $f_n = 1 - \chi_{E}$ si $n$ es par. ¿Cuál es la importancia del lemma de Fatou en este ejemplo?