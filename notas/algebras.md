# Anillos y Álgebras

**Definición.** Sea $\mathcal A$ una colección de subconjuntos de un conjunto $X$. Decimos que $\mathcal A$ es una **álgebra** si:
1. Si $E, F \in \mathcal A$, entonces $E \setminus F \in \mathcal A$.  
2. Si $E, F \in \mathcal A$, entonces $E \cup F \in \mathcal A$.
Si además tenemos que $X \in \mathcal A$, entonces decimos que $\mathcal A$ es una **álgebra.**

Notemos que si $\mathcal A$ no es vacío, entonces si $F \in \mathcal A$, se tiene que $\emptyset = F \setminus F \in \mathcal A$; es decir, el vacío siempre es elemento de una álgebra. 

**Definición.** Una **sigma-álgebra** (anillo) $S$ es una álgebra que satisface lo siguiente:
- **sigma-aditividad**: si $\{E_n\}$ es una sucesión de elementos en $S$, entonces
$$\bigcup_n E_n \in S.$$
> **Nota** : Toda sigma-álgebra es una álgebra, pues podemos hacer $E \cup F \cup \emptyset \cup \emptyset \cup \ldots$
>No obstante, no toda álgebra es una sigma-álgebra ❗

>**Nota:** En el caso de las álgebras (o sigma-álgebras), podemos sustituir la condición 1 de la definición por: $E \in S \Rightarrow E^c \in S$. Si $E \in S$, entonces $E \setminus X = E^c$. Sean $E, F \in S$. Entonces $E^c \in S$ y $(E^c \cup F)^c \in S$. Note que $(E^c \cup F)^c = E \cap F^c = E \setminus F$ .

**Ejemplo.** La colección $P(X)$ (la colección de todos los subconjuntos de $X$) es una sigma-álgebra de $X$. A su vez, la colección $\{\emptyset, X\}$ es una sigma-álgebra (y también álgebra) en $X$.

**Ejemplo.** Sea $X$ un conjunto infinito. Definamos la colección $S = \{A: A \text{ o } A^c \text{ es numerable.} \}$. Note que $X$ es un elemento de $A$. Si $A, B$ son elementos de $A$, entonces 

**Teorema.** Sea $\{A_\alpha \}$ una colección de sigma-álgebras en $X$. Entonces 
$$\mathcal A = \bigcap_\alpha A_\alpha$$
es una álgebra en $X$.

*Demostración:*
1. Dado que cada $A_\alpha$ es una sigma-álgebra, entonces $X\in A_\alpha$ para toda $\alpha$. Por lo que $X \in \mathcal A$. 
2. Sean $E, F \in \mathcal A$. Entonces tanto $E$ como $F$  pertenecen a $A_\alpha$ para toda $\alpha$. Como cada $A_\alpha$ es una sigma-álgebra, entonces $E \setminus F$ es un elementos de $A_\alpha$ para toda $\alpha$. Por tanto, $E\setminus F \in \mathcal A.$
3. Sea $\{E_n\}$ una sucesión en $\mathcal A$. Entonces, $\{E_n\}$ es una sucesión en $A_\alpha$ para toda $\alpha$. Por lo que $E = \bigcup_n E_n$ es un elemento en cada $A_\alpha$. Por tanto $E \in \mathcal A$.
Concluimos que $\mathcal A$ es una sigma-álgebra.

> **Nota:** La colección de sigma-álgebras tiene cardinalidad arbitraria.

El Teorema anterior puede parecer a primera vista insípido. No obstante, nos permitirá definir sigma-álgebras importantes.

**Teorema**. Sea $\mathcal E$ una colección de subconjuntos de $X$. Entonces existe una sigma-álgebra $S(\mathcal E)$ tal que:
1. $\mathcal E \subset S(\mathcal E)$.
2. Si $\mathcal A$ es una sigma-álgebra que contiene a $\mathcal E$, entonces $S(\mathcal E) \subset \mathcal A$.
Debido a estas dos propiedades, decimos que $S(\mathcal E)$ es la **sigma-álgebra más pequeña que contiene a $\mathcal E$.** 

*Demostración:* Considere la colección 
$$S = \bigcap\{\mathcal A: \mathcal E \subset \mathcal A, \text{ y } \mathcal A \text{ es una sigma-álgebra.}  \}$$
Demostraremos que $S$ satisface las dos propiedades establecidas en el Teorema. En primer lugar, observe que $S$ es no vacío, pues $P(X)$ es una sigma-álgebra que contiene a $\mathcal E$. Por el Teorema anterior, $S$ es una sigma-álgebra. Por construcción, $\mathcal E \subset S$. Por otra parte, si $\mathcal A$ es una sigma-álgebra que contiene a $\mathcal E$, entonces $\mathcal A$ aparece en la intersección que define a $S$. Por tanto $S \subset \mathcal A$. Podemos concluir que $S = S(\mathcal E)$.

> **Nota:** También decimos que $S(\mathcal E)$ es **la sigma-álgebra generada por** $\mathcal E$. Note también que decimos **la** y no **una** pues $S(\mathcal E)$ es única: si $\mathcal A$ es otra sigma-álgebra que satisface las propiedades 1 y 2 del Teorema, entonces $\mathcal S(\mathcal E)$ y $S(\mathcal E) \subset \mathcal A$, por lo que $S(\mathcal E) = \mathcal A$.

De nuevo parece que el resultado obtenido es bastante trivial. No obstante, con esto ya podemos definir la sigma-álgebra más importante en este curso.

**Definición.** Sea $\tau$ la topología usual en los reales. A la sigma-álgebra generada por $\tau$,  $\mathcal B = S(\tau)$, se le conoce como **sigma-álgebra de Borel.**  Si $B$ es un elemento en $\mathcal B$, entonces decimos $B$ que es un conjunto boreliano. 💡

> **Nota**: Esta construcción la podemos realizar con cualquier topología.

**Teorema.**
1. Si $f: X \rightarrow Y$ y $S$ es una sigma-álgebra en $Y$, entonces 
$$ \{ f^{-1}(A): A \in S \}$$es una sigma-álgebra en $X$.	