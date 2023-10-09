>[!Premise]
>Sia C un insieme di colori. Gli elementi della sequenza considerata in questo esercizio sono numeri naturali colorati. La funzione di colorazione è definita nel seguente modo: 
>$$φ : N → C$$
>Per esempio, data la funzione:
>$$φ(x) = \begin {cases} rosso & \text{se } x < 5 \\blu & \text{se } 5 <= x <= 10 \\ verde & \text{se } x > 10 \\ \end {cases}$$
>la sequenza  
>$$X = <2, 4, 7, 6, 11, 3, 21, 14, 1>$$
>sarà colorata nel seguente modo: 
>$$<r, r, b, b, g, r, g, g, r>$$
>

date due sequenze X e Y , rispettivamente di m e n numeri interi, e un naturale R, stabilire se tutte le più lunghe sottosequenze comuni a X e Y contengono al più R elementi colorati di rosso.

--- 
## Sottoproblemi

date due sequenze X e Y, rispettivamente di m ed n numeri interi, e un naturale r, stabilire se tutte le più lunghe sottosequenze comuni a Xi e Yj contengono al più r elementi colorati di rosso

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
