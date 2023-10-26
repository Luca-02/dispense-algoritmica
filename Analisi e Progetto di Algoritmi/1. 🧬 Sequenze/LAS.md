
>[!Premise]
>Sia C un insieme di colori. Gli elementi della sequenza considerata in questo esercizio sono numeri naturali colorati. La funzione di colorazione è definita nel seguente modo: 
>$$φ : N → C$$
>Per esempio, data la funzione:
>$$φ(x) = \begin {cases} rosso & \text{se } x < 5 \\blu & \text{se } 5 \leq x \leq 10 \\ verde & \text{se } x > 10 \\ \end {cases}$$
>la sequenza  
>$$X = ⟨2, 4, 7, 6, 11, 3, 21, 14, 1⟩$$
>sarà colorata nel seguente modo: 
>$$⟨r, r, b, b, g, r, g, g, r⟩$$
>

*Data una sequenza $X$ di m numeri interi, si determini la lunghezza di una tra le più lunghe sottosequenze di $X$ che non abbia elementi consecutivi dello stesso colore.*

---
## Sottoproblemi

*Data una sequenza $X$ di $m$ numeri interi, si determini la lunghezza di una tra le più lunghe sottosequenze di $X_i$ che non abbia elementi consecutivi dello stesso colore.*

- Considerato il sottoproblema di dimensione $(i)$, la `variabile` ad esso associata è $c_i$ ed è così definita:
	- $c_{i}$ = $|LAS(X_i)|$
	- $c_{i}$ = lunghezza di una tra le più lunghe sottosequenze di $X_i$ che non ha elementi consecutivi dello stesso colore

**Numero di sottoproblemi**: $m+1$

Purtroppo, però, il problema così definito **non è risolvibile**! `Ci manca informazioni`.
Non c’è alcun modo per poter comprendere se l’elemento $x_i$ possa essere accodato alle sottosequenze senza elementi consecutivi dello stesso colore relative ai sottoproblemi di dimensione minore a $i$.

Risulta necessario **introdurre un problema ausiliario**, nel quale introdurre l’informazione mancante necessaria.

---
## Problema ausiliario (sottoproblema vincolato)

*Data una sequenza $X$ di $m$ numeri interi, si determini la lunghezza di una tra le più lunghe sottosequenze di $X_i$ che non abbia elementi consecutivi dello stesso colore e che termina con $x_m$.*

- Considerato il sottoproblema di dimensione $(i)$, la `variabile` ad esso associata è $c_i$ ed è così definita:
	- $c_{i}$ = $|LAS_V(X_i)|$
	- $c_{i}$ = lunghezza di una tra le più lunghe sottosequenze di $X_i$ che non ha elementi consecutivi dello stesso colore e che termina con $x_i$

**Numero di sottoproblemi**: $m+1$
**Soluzione del problema**: $max({c_i | 1 \leq i \leq m})$

---
## Sottostruttura ottima

Date $X=⟨x_1, x_2, …, x_{m-1}, x_m⟩$:

- $LAS_V(X_m) = max({LAS_V(X_h) | 1 \leq h < m \land φ(x_h) \neq φ(x_m)}) + ⟨x_m⟩$, con $max(∅) = 0$

---
## Equazioni di ricorrenza
#### <u>**Caso base**</u>: $(i)$ con $i \leq 1$
- Il caso base si ha per un qualunque sottoproblema di dimensione $(i)$ con $i = 0 \lor i =1$, ossia quando il prefisso considerato è la `sequenza vuota oppure` è una sequenza composta da un `singolo elemento`.
	Il caso base $i = 0$, comunque, risulta non necessario in quanto è possibile utilizzare, come caso base, solamente il caso $i = 1$:
$$ c_{i} = 1 \quad\text{se } i = 1$$

#### <u>**Passo ricorsivo**</u>: $(i)$ con $i > 1$
- Il passo ricorsivo si ha per un qualunque sottoproblema di dimensione $(i)$ con $i > 1$, ossia quando si considera un prefisso della sequenza $X$ in input di almeno due elementi.

	Se prendiamo la più lunga sottosequenza alla quale possiamo attaccare $x_i$ e accodiamo ad essa $x_i$, otteniamo la `più lunga sottosequenza` di $X_i$ che **non contiene elementi consecutivi dello stesso colore** e che termina con $x_i$ . La lunghezza di tale sottosequenza, pertanto, sarà uguale alla lunghezza della sottosequenza alla quale abbiamo accodato $x_i$ **aumentata** di $1$:
	$$c_i = max(c_h | 1 ≤ h < i ∧ φ(x_h) \neq φ(x_i)) + 1$$
	assumiamo per definizione che $max(∅) = 0$.

---
## Algoritmo ricorsivo

``` Pseudocodice TI:"LAS_ricorsiva" "FOLD"
int LAS_ricorsiva(i)
	if i = 1 then
		return 1
	else
		max = 0
		for h from 1 to i-1 do
			if φ(x[h]) != φ(x[i]) then
				S = LAS_ricorsiva(h)
				if S > max then
					max = S
		return max + 1
```

---
## Algoritmo DP

- uso un **array** $c[1...m]$ per salvare tutti i `sottoproblemi` $c_i$
- `[facoltativa]` uso un **array** $b[1...m]$ per salvare gli indici $(h)$ della $LIS_V$ che precede l'indice $i-esimo$ per il **backtracking**

``` Pseudocodice TI:"LIS" "FOLD"
int LIS(X) 
	c[1] = 1
	max = c[1]
	for i from 2 to m do
		temp = 0
		for h from 1 to i-1 do
			if φ(x[h]) != φ(x[i]) and c[h] > temp then
				temp = c[h]
		c[i] = temp + 1
		if c[i] > max then
			max = c[i]
	return max
```

> [!Summary]
> - ***Complessità***: $O(m^2)$
> - ***Memoria***: $O(m)$


![[Pasted image 20231026175003.png]]
