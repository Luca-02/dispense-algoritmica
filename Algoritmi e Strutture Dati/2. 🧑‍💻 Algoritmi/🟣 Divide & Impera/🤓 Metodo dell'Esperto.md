# Definizione 📃
Il **Metodo dell'Esperto** (o `Teorema Principale`) è un teorema per il calcolo dei tempi di algoritmi **solamente** di tipo [Divide & Impera](obsidian://open?vault=obsidian-git-sync&file=Algoritmi%20e%20Strutture%20Dati%2F1.%20%F0%9F%A7%91%E2%80%8D%F0%9F%92%BB%20Algoritmi%2F%F0%9F%9F%A3%20Divide%20%26%20Impera%2F%F0%9F%93%83%20Definizione%20Divide%20%26%20Impera): 

# Enunciato ✒️
Sia data una **relazione di ricorrenza** $T(n)$ nella forma: 
$$T(n) = a·T(\dfrac{n}{b})+f(n)$$
dove $a≥1$ e $b>1$;

- Allora la funzione $T(n)$ è limitata asintoticamente secondo uno dei tre seguenti casi:
	1. se ∃ $ε>0$ | $f(n) = O(n^{\log_b {a}-ε})$ $\quad\Longrightarrow\quad$ $T(n) = θ(n^{\log_b a})$ 
	2. se $f(n) = θ(n^{\log_b a})$ $\quad\Longrightarrow\quad$ $T(n) = θ(f(n)·\log n)$
	3. se ∃ $ε>0$, $0<c<1$ | $f(n) = Ω(n^{\log_b {a}+ε})$ e $a·f(\dfrac{n}{b})≤c·f(n)$ $\quad\Longrightarrow\quad$ $T(n) = θ(f(n))$

# Esempi 🔍
- $T(n) = 9·T(\dfrac{n}{3})+n$
>$a = 9, b = 3$
$f(n) = n = θ(n)$ $\longleftarrow$ minore
$n^{\log_b a} = n^{\log_3 9} = n^2 = θ(n^2)$ $\longleftarrow$ maggiore
$n = O(n^{2-ε})$, $ε>0$ ???
Sì, se $ε = \cfrac{1}{2}$ $\longmapsto$ $n = O(n^{\dfrac{3}{2}})$
$\Rightarrow$ `caso 1` $\longmapsto$ $T(n) = θ(n^{\log_b a}) = θ(n^{2})$

- $T(n) = T(\dfrac{2n}{3})+1$
>$a = 1, b = \cfrac{3}{2}$
$f(n) = 1 = θ(1)$ $\longleftarrow$ uguali
$n^{\log_b a} = n^{\log_{\frac{3}{2}} 1} = n^{0} = 1 = θ(1)$ $\longleftarrow$ uguali
$1 = θ(1)$ ???
Sì, 
$\Rightarrow$ `caso 2` $\longmapsto$ $T(n) = θ(1·\log n) = θ(\log n)$

-  $T(n) = 3·T(\dfrac{n}{4})+n·\log n$
>$a = 3, b = 4$
$f(n) = n·\log n = θ(n·\log n)$  $\longleftarrow$ maggiore
$n^{\log_b a} = n^{\log_4 3(<1)} = θ(n^{\log_4 3})$ $\longleftarrow$ minore
$n·\log n = Ω(n^{\log_4 3+ε})$, $ε>0$ ???
Sì, $ε=1-\log_3 4$ -> $n·\log n = Ω(n)$
$\lim_{x \to +∞} \dfrac{n\log n}{n} = +∞$
$\cfrac{3}{4}n·\log\cfrac{n}{4}≤c·n·\log n$, $0<c<1$ ???
Sì, se $c = \cfrac{3}{4}$ $\longmapsto$ $\cfrac{3}{4}n·\log\cfrac{n}{4}≤\cfrac{3}{4}n·\log n$
$\Rightarrow$ `caso 3` $\longmapsto$ $T(n) = θ(n·\log n)$

- $T(n) = 2·T(\dfrac{n}{2})+n·\log n$
>$a = 2, b = 2$
$f(n) = n·\log n$ $\longleftarrow$ maggiore
$n^{\log_b a} = n^{\log_2 2} = n$ $\longleftarrow$ minore
$n·\log n = Ω(n^{1+ε})$, $ε>0$ ???
$\lim_{x \to +∞} \dfrac{n\log n}{n^{1+ε}} = 0$, $∀ε>0$

- $T(n) = 2·T(\dfrac{n}{2})+4$
>$a = 2, b = 2$
$f(n) = 4 = θ(1)$ $\longleftarrow$ minore
$n^{\log_b a} = n^{\log_2 2} = n = θ(n)$ $\longleftarrow$ maggiore
$1 = O(n^{1-ε})$, $ε>0$ ???
Sì, se $ε = 1$ $\longmapsto$ $4 = O(1)$
$\Rightarrow$ `caso 1` $\longmapsto$ $T(n) = θ(n^{\log_b a}) = θ(n)$
