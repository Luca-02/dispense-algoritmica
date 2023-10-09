date due #sequenze $X$ e $Y$ , rispettivamente di $m$ ed $n$ numeri interi, si determini <b>UNA</b> tra le più lunghe sottosequenze comuni a $X$ e $Y$.

---
## Sottoproblemi

date due #sequenze $X$ e $Y$ , rispettivamente di $m$ ed $n$ numeri interi, si determini la lunghezza di una tra le più lunghe sottosequenze comuni al prefisso $X_i$ e al prefisso $Y_j$

- Considerato il sottoproblema di dimensione (i, j), la `variabile` ad esso associata è $c_{i,j}$ ed è così definita:
	- $c_{i,j}$ = $|LCS(X_i, )|$
	- $c_{i,j}$ = lunghezza di una tra le più lunghe sottosequenze comuni a $X_i$ e $Y_j$