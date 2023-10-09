date due sequenze $X$ e $Y$ , rispettivamente di $m$ ed $n$ numeri interi, si determini **UNA** tra le più lunghe sottosequenze comuni a $X$ e $Y$.

---
## Sottoproblemi

date due #sequenze $X$ e $Y$ , rispettivamente di $m$ ed $n$ numeri interi, si determini la lunghezza di una tra le più lunghe sottosequenze comuni al prefisso $X_i$ e al prefisso $Y_j$

- Considerato il sottoproblema di dimensione $(i, j)$, la `variabile` ad esso associata è $c_{i,j}$ ed è così definita:
	- $c_{i,j}$ = $|LCS(X_i, Y_j)|$
	- $c_{i,j}$ = lunghezza di una tra le più lunghe sottosequenze comuni a $X_i$ e $Y_j$

- Numero di sottoproblemi: $(m+1)(n+1)$

##### Soluzione del problema: $c_{m, n}$

---

## Equazioni di ricorrenza
- **Caso base**: $(i, j)$ con $i = 0 ∨ j = 0$
$$ c_{i,j} = 0 \quad\text{se } i = 0 \lor j = 0 $$
- **Passo ricorsivo**: $(i, j)$ con $i$ > 0 e $j$ > 0
$$c_{i, j} = 
\begin {cases} 
1 + c_{i-1,j-1} & \text{se } x_i = y_j \\
\max{c_{i,j-1}, c_{i-1,j}} & \text{se } x_i \neq y_j
\end {cases}
$$