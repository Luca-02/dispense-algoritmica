date due sequenze X e Y, trovare il minimo insieme di operazioni di cancellazione, inserimento e sostituzione (distanza di edit) che trasformano X in Y

---

## Sottoproble

Trovare la distanza di edit dei prefissi Xi e Y

- Considerato il sottoproblema di dimensione $(i, j)$, la `variabile` ad esso associata è $d_{i,j}$ ed è così definita:
	- $d_{i,j}$ = $|ED(X_i, Y_j)|$
	- $d_{i,j}$ = distanza di edit dei prefissi $X_i$ e $Y_j$

- Numero di sottoproblemi: $(m+1)(n+1)$
##### Soluzione del problema: $d_{m, n}$

---

## Equazioni di ricorrenza

- **Caso base**: $(i, j)$ con $i = 0 ∨ j = 0$
$$ d_{i,j} = 0 \quad\text{se } i = 0 \land j = 0 $$
$$ d_{i,j} = i \quad\text{se } i > 0 \land j = 0 $$
$$ d_{i,j} = j \quad\text{se } i = 0 \land j > 0 $$
- **Passo ricorsivo**: $(i, j)$ con $i$ > 0 e $j$ > 0
i > 0 ⋀ j > 0 ⋀ xi = y
minOP(i, j) = minOP(i-1, j-1) -> di,j = di-1,j-1

i > 0 ⋀ j > 0 ⋀ xi ≠ yj
tre possibilità per minOP(i, j)
1. sostituzione(xi -> yj) + minOP(i-1, j-1) -> 1 + di-1,j-1
2. cancellazione(xi) + minOP(i-1, j) -> 1 + di-1,j
3. inserimento(yj) + minOP(i, j-1) -> 1 + di,j-1

di,j = min(di-1,j-1 + 1, di-1,j + 1, di,j-1 + 1)
