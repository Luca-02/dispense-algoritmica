- ### Delete $k$
Dato uno stack $S$ e una chiave $k$, eliminare da $S$ tutte le occorrenze di $k$, usando come appoggio solo altri stack.
``` Pseudocodice TI:"Push" "FOLD"
void Stack_kDel(S, k)
	while not(Stackempty(S)):
		x = Pop(S)
		if x != k:
			Push(S_app, x)
	while not(Stackempty(S_app)):
		Push(S, Pop(S_app))
```

>$T(n)=3c·n + c·true_{if}+2c·true_{while}$
>- $T_{migliore}(n) = 3c·n \Rightarrow Ω(n) \rightarrow$ $S$ con tutti i valori $=k$
>- $T_{peggiore}(n) = 6c·n \Rightarrow O(n) \rightarrow$ $S$ non contiene valori $=k$
>- $T(n) \Rightarrow θ(n)$

- ### Due Stack in un Array
Realizzare due stack utilizzando solo un array. Non devo avere overflow. Non devo dire che è pieno se non ho più di N elementi in tutto.

>Diamo un'idea della soluzione:
>- uno stack punta all'inizio, una alla fine dell'array. Avrò un overflow quando i due indici si accavallano;
>- chiaramente sono da sistemare le operazioni per la pila che punta in fondo (e che deve quindi "crescere" al contrario);

- ### Trova $k$
Dato uno stack, stabilire se $k$ è presente nello stack.
``` Pseudocodice TI:"Push" "FOLD"
void Stack_kTrova(S, k)
	trovato = false:
	while not(Stackempty(S)) and not(trovato):
		x = Pop(S)
		if x == k:
			trovato = true
	return trovato
```

>- $T_{migliore}(1) \Rightarrow Ω(1) \rightarrow$ $k$ è in testa allo stack
>- $T_{peggiore}(n) \Rightarrow O(n) \rightarrow$ $S$ non contiene $k$

- ### Inverti Stringa
Dato uno stack $S$ contente una stringa, ribaltarla nello stesso stack $S$.

``` Pseudocodice TI:"Stack_Inverti_Stringa" "FOLD"
void Stack_Inverti_Stringa(S)
	while not(Stackempty(S)):
		x = Pop(S)
		Push(S1, x)
	while not(Stackempty(S1)):
		x = Pop(S1)
		Push(S2, x)
	while not(Stackempty(S2)):
		x = Pop(S2)
		Push(S, x)
```

>$T(n)=9c·n \Rightarrow θ(n)$ 

- ### Parentesi
Data una stringa contenuta in un array $A$ di caratteri, verificare che le parentesi siano annidate correttamente.

``` Pseudocodice TI:"checkParentesi" "FOLD"
boolean checkParentesi(A)
	i = 1
	errore = false
	while i <= len(A) && not(errore):
		if A[i] == '(' or A[i] == '[':
			Push(S, A[i])
		if A[i] == ')':
			if Stackempty(S):
				errore = true
			else:
				if Pop(S) != '(':
					errore = true
		if A[i] == ']':
			if Stackempty(S):
				errore = true
			else:
				if Pop(S) != '[':
					errore = true
```