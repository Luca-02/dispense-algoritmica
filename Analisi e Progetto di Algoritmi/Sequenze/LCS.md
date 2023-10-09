date due #sequenze $X$ e $Y$ , rispettivamente di $m$ ed $n$ numeri interi, si determini **UNA** tra le più lunghe sottosequenze comuni a $X$ e $Y$.

---
## Sottoproblemi

date due #sequenze $X$ e $Y$ , rispettivamente di $m$ ed $n$ numeri interi, si determini la lunghezza di una tra le più lunghe sottosequenze comuni al prefisso $X_i$ e al prefisso $Y_j$

- Considerato il sottoproblema di dimensione $(i, j)$, la `variabile` ad esso associata è $c_{i,j}$ ed è così definita:
	- $c_{i,j}$ = $|LCS(X_i, Y_j)|$
	- $c_{i,j}$ = lunghezza di una tra le più lunghe sottosequenze comuni a $X_i$ e $Y_j$

---

## Equazioni di ricorrenza
- **Caso base**: $(i, j)$ con $i = 0 ∨ j = 0$
<center> $c_{i,j}$ = 0 se $i = 0 ∨ j = 0$ </center>
- Passo ricorsivo: (i, j) con i > 0 e j > 0