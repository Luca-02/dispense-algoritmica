# Esercizio ⛏️
- Costruire l'algoritmo della seguente funzione:
>$$F(n) = 
\begin {cases} 
f(0) = 2 \\
f(1) = 4 \\
f(n-1)+7 && \text {n pari} \\ 
3·f(n-1)+5 && \text {n dispari} \\ 
\end {cases}
>$$

``` Pseudocodice TI:"Funzione" "FOLD"
int f(n)
	if n == 0:
		return 2
	if n == 1:
		return 4
	else:
		if n % 2 == 0:
			return f(n-1) + 7
		else:
			return 3 * f(n-1) + 5
```