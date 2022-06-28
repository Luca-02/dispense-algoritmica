- ### Delete $k$
Dato uno Stack $S$ e una chiave $k$, eliminare da $S$ tutte le occorrenze di $k$, usando come appoggio solo altri Stack.
``` Pseudocodice TI:"Push" "FOLD"
void Stack_kDel(S, k)
	while not Stackempty(S):
		x = Pop(S)
		if x != k:
			Push(S_app, x)
	while not Stackempty(S_app):
		Push(S, Pop(S_app))
```

>$T(n)=3c·n + c·true_{if}+2c·true_{while}$