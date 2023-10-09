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

---

## Algoritmo ricorsivo

``` Pseudocodice TI:"Distanza di Edit" "FOLD"
int EDricorsiva(i, j)
	if i = 0 ⋁ j = 0 then
		return caso base
	else
		d[i - 1, j - 1] = EDricorsiva(i - 1, j - 1)
		if xi = yj then
			return d[i-1, j-1]
		else
			d[i - 1, j] = EDricorsiva(i - 1, j)
			d[i, j - 1] = EDricorsiva(i, j - 1)
			a = D[i - 1, j - 1] + 1 
			b = D[i - 1, j] + 1 
			c = D[i, j - 1] + 1
			return min(a, b, c)
```

---

## Algoritmo DP

1. Costruzione di una matrice D[0…m, 0…n]
2. Riempimento di D in modo tale che D[i, j] = di,j per 0 ≤ i ≤ m e 0 ≤ j ≤ n
3. Soluzione di PR à D[m, n]

``` Pseudocodice TI:"Edit" "FOLD"
int distanza_edit(X, Y) 
	for i from 0 to m do 
		D[i,0] = i 
	for j from 0 to n do
		D[0,j] = j 
	for i from 1 to m do
		for j from 1 to n do 
			if xi = yj then
				D[i,j] = D[i-1,j-1] 
			else 
				a = D[i - 1, j - 1] + 1
				b = D[i - 1, j] + 1
				c = D[i, j - 1] + 1
				D[i,j] = min(a, b, c) 
	return D[m,n]
```

---

## Ricostruzione delle operazioni

- Si inizializza una lista minOP vuota 
- Si parte dalla cella D[m,n] seguendo a ritroso un “percorso di calcolo” 
- Cella di terminazione: cella D[0,0] 
- Per ogni D[i,j] visitata si aggiunge (eventualmente) un operazione a minOP 
- Da D[i,j] si passa alla cella che ne ha determinato il calcolo (in base al passo ricorsivo) 
- Al termine del percorso, minOP = minOP(X,Y)

di,j = di-1,j-1 -> “null operation”
di,j = di-1,j-1 + 1 -> substitution(xi -> yj)
di,j = di-1,j + 1 -> deletion(xi)
di,j = di,j-1 + 1 -> insertion(yj) after xi
di,0 = i = (i-1) + 1 = di-1,0 + 1 -> deletion(xi)
d0,j = j = (j-1) + 1 = d0,j-1 + 1 -> insertion(yj) before x1

##### Versione iterativa

``` Pseudocodice TI:"Distanza di Edit" "FOLD"
List ricostruisci_minOP(X, Y) 
	minOp = empty list
	i = m
	j = n 
	while i >= 0 or j >= 0 then 
		if from diagonal then 
			if xi ≠ yj then 
				append substitution(xiàyj) to minOP 
			i = i-1 
			j = j-1 
		else 
			if from left then 
				append deletion(x[i]) to minOP 
				i = i - 1 
			else 
				append insertion(y[j]) to minOP 
				j = j - 1
```

##### Versione ricorsiva

``` Pseudocodice TI:"Distanza di Edit" "FOLD"
void Ricostruisci_minOP_ricorsiva(D, i, j)
	if i >= 0 or j >= 0 then 
		if from diagonal then 
			if x[i] != y[j] then 
				append substitution(x[i] -> y[j]) to minOP 
			RicostruisciLCSricorsiva(D, i - 1, j - 1) 
		else 
			if from left then 
				append insertion(yj) to minOP 
				RicostruisciLCSricorsiva(D, i - 1, j) 
			else 
				append deletion(xi) to minOP 
				RicostruisciLCSricorsiva(D, i, j - 1)
```