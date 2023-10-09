
#### Premessa
Sia C un insieme di colori. Gli elementi della sequenza considerata in questo esercizio sono numeri naturali colorati. La funzione di colorazione è definita nel seguente modo:
$$φ : N → C$$Per esempio, data la funzione:
$$φ(x) = 
\begin {cases} 
rosso x < 5 & \text{se } x_i = y_j \\
\max{c_{i,j-1}, c_{i-1,j}} & \text{se } x_i \neq y_j
\end {cases}
$$

---
## Sottoproble



**Numero di sottoproblemi**:
**Soluzione del problema**:

---

## Equazioni di ricorrenza

- **Caso base**: $(i, j)$ con $i = 0 \lor j = 0$

- **Passo ricorsivo**: $(i, j)$ con $i$ > 0 e $j$ > 0

---

## Algoritmo ricorsivo

``` Pseudocodice TI:"" "FOLD"

```

---

## Algoritmo DP

1. Costruzione di una matrice D[0…m, 0…n]
2. Riempimento di D in modo tale che D[i, j] = di,j per 0 ≤ i ≤ m e 0 ≤ j ≤ n
3. Soluzione di PR à D[m, n]

``` Pseudocodice TI:"" "FOLD"

```
