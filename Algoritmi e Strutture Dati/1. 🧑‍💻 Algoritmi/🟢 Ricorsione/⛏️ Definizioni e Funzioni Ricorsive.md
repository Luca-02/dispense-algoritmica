# Esercizio ⛏️
- Qual è la funzione di questa definizione? 
>$$F(n) = 
\begin {cases} 
f(0) = 2 \\
f(n+1) = f(n) + 3 \\
\end {cases}
$$

>$f(n+1) = f(n)+3 = (f(n-1)+3)+3 = ((f(n-2)+3)+3)+3 = ..... =$
>$= f(n-k) + 3·(k+1)$ -> $k = n$ $\rightarrow$ $f(0) + 3·(n+1) = 2 + 3·(n+1)$ 
>
>quindi:
>- $f(n+1) = 2 + 3·(n+1) \rightarrow f(n) = 2 + 3n$


# Esercizio ⛏️
- Se ho:
>$$f(n)=n^2+2n$$

cos'è ricorsivamente?

>$\rightarrow$ $f(0) = 0$
>$\rightarrow$ $f(n-1) = (n-1)^2 + 2·(n-1)$
>$\rightarrow$ $f(n+1) = (n+1)^2 + 2·(n+1)$ = $n^2+2n+1+2n+2$  -> ($n^2+2n = f(n)$) $=$
>$= f(n)+2n+3$
