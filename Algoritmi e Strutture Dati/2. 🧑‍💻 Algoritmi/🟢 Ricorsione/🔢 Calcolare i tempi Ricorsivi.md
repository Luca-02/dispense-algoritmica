# Come calcolo i tempi Ricorsivi?🤔
1. ***Sostituzione***
2. ***Metodo Iterativo o Albero di Ricorsione***

- **Sostituzione**:
$T(n) =
\begin {cases} 
1 && \text n = 1 \\
2·T(\dfrac{n}{2})+n && \text n > 1\\
\end {cases}
$ 
>Ipotizzo $O(n·\log n)$ e dimostro per induzione:
>$T(n) = O(n·\log n) ≤ c·(n·\log n)$
>$$∃c, n_0 > 0:n ≥ n_0 => T(n) ≤ c·(n·\log n)$$
>dimostro per induzione:
>Ipotesi $\rightarrow$ $T(m)$ vera per $1≤m≤n-1$ $\rightarrow$ $T(n)$
>$T(n)=2·T(\dfrac{n}{2})+n ≤ c·(\dfrac{n}{2}·\log \dfrac{n}{2})+n=$
>$= c·n·\log \dfrac{n}{2}+n = c·n·(\log_2 n - \log_2 2)+n =$
>$= c·n·\log_2 n-c·n+n ≤ c·n·\log n$ $\rightarrow$ se $c≥1$
>Caso base $\rightarrow$ $T(1) = 1$, $1≤c·\log_2 1$? No, mai $1≤c·0$
>$T(2) = 2T(1)+2 = 2+2 = 4$, $4≤c·2\log_2 2$? $4≤2c$, $c≥2$ 
>$T(3) = 2T(1)+3 = 2+3 = 5$, $5≤c·3\log_2 3$?
>2 -> 4 -> 8 -> 16 -> ...
>3 -> 6 -> ... 
>Ho dimostrato tutto (???)

- **Metodo iterativo**: 
$T(n) =
\begin {cases} 
6 && \text n = 1 \\
8+T(n-1) && \text n > 1\\
\end {cases}
$ 
>$T(n) = 8+T(n-1) =$
>$= 8+(8+T(n-2)) = 2·8+T(n-2) =$
>$= 2·8+(8+T(n-3)) = 3·8+T(n-3) =$
>$= ... =$
>$= k·8+T(n-k)$
$\Rightarrow$ se $k = n-1$ (mi riconduco al caso base, faccio diventare T il caso base):
>$T(n) = (n-1)·8+T(1) = (n-1)·8+6 = θ(n)$

- **Metodo iterativo**:
$T(n) =
\begin {cases} 
1 && \text n = 1 \\
3·T(\dfrac{n}{4})+n && \text n > 1\\
\end {cases}
$
>$T(n) = 3·T(\cfrac{n}{4})+n =$
>$= 3·[3·T(\cfrac{n}{4^2})+\cfrac{n}{4}]+n = 3^2·T(\cfrac{n}{4^2})+3·\cfrac{n}{4}+n =$
>$= 3^2·[3·T(\cfrac{n}{4^3})+\cfrac{n}{4^2}]+3·\cfrac{n}{4}+n = 3^3·T(\cfrac{n}{4^3})+3^2·\cfrac{n}{4^2}+3·\cfrac{n}{4}+n =$
>$=...=$
>$= 3^k·T(\cfrac{n}{4^k})+(\cfrac{3}{4})^{k-1}·n+...+(\cfrac{3}{4})^{1}·n+(\cfrac{3}{4})^{0}·n$
$\Rightarrow$ $4^k = n$ $\Rightarrow$ $k = \log_4 n$ (mi riconduco al caso base, faccio diventare T il caso base):
>$T(n) = 3^{\log_4 n}·1+(\cfrac{3}{4})^{{(\log_4 n)}-1}·n+...+(\cfrac{3}{4})^{0}·n =$
>$= 3^{\log_4 n}+\sum\limits_{i = 0}^{(\log_4 n)-1} ({\dfrac{3}{4})^i} ≤ 3^{\log_4 n}+\sum\limits_{i = 0}^{∞} ({\dfrac{3}{4})^i}=$
>$= 3^{\log_4 n}+\dfrac{1}{1-\frac{3}{4}} = 3^{\log_4 n}+4n = θ(n)$

>[!important]
>$$\sum\limits_{i = 0}^{∞} {k^i} = \dfrac{1}{1-k}, k<1$$

- **Metodo albero di ricorsione**:
$T(n) = 2·T(\dfrac{n}{2})+n^2$
![[Albero di Ricorsione.png]]
>come si può vedere, l'albero di ricorsione ha una profondità di $\log_2 n$ con i seguenti costi per ogni livello:
>- $0^o$ livello: $n^2 = \cfrac{n^2}{2^0}$
>- $1^o$ livello: $2·(\cfrac{n}{2})^2 = \cfrac{2n^2}{4} = \cfrac{n^2}{2^1}$
>- $2^o$ livello: $4·(\cfrac{n}{4})^2 = \cfrac{4n^2}{16} = \cfrac{n^2}{4} = \cfrac{n^2}{2^2}$
>- $3^o$ livello: $8·(\cfrac{n}{8})^2 = \cfrac{8n^2}{64} = \cfrac{n^2}{8} = \cfrac{n^2}{2^3}$
>- ...
>- $k^o$ livello: $2^k·(\cfrac{n}{2^k})^2 = \cfrac{2^kn^2}{2^{2k}} = \cfrac{n^2}{2^k}$
>- ...
>- $\log_2 n^o$ livello: $2^{\log_2 n}·(\cfrac{n}{2^{\log_2 n}})^2 = \cfrac{2^{\log_2 n}n^2}{2^{2\log_2 n}} = \cfrac{n^2}{2^{\log_2 n}}$
>sapendo che il $T(n)$ di un algoritmo #ricorsivo è dato dalla somma del costo di ogni suo livello:
>- $T(n) = \sum\limits_{i = 0}^{\log_2 n} {\dfrac{n^2}{2^i}} = n^2·\sum\limits_{i = 0}^{\log_2 n} {(\dfrac{1}{2})^i} ≤ n^2·\sum\limits_{i = 0}^{∞} {(\dfrac{1}{2})^i} = n^2·\dfrac{1}{1-\frac{1}{2}} = 2n^2$ $\Rightarrow$ $θ(n^2)$

