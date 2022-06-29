 # Implementazione 🧪
Lo Stack può essere implementato tramite **array** o tramite **liste concatenate**.
***
- # Implementazione con array
	Possiamo implementare una Coda di **massimo** $n-1$ elementi con un array $Q[1...n]$.
	- L'attributo $Q.head$ indica l'inizio della coda;
	- L'attributo $Q.tail$ indica la prossima posizione in cui l'ultimo elemento che arriva sarà inserito nella coda 
	- Gli elementi della coda occupano le posizioni $[Q.head, Q.head+1...Q.tail-1]$ 

