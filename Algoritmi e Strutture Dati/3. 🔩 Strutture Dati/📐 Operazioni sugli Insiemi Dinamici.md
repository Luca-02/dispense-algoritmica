- ### Serach($S, k$)
Data una struttura dati $S$ e un valore chiave $k$, restituisce un puntatore $x$ a un elemento di $S$ tale che $key[x]=k$, oppure $Null$ se l'elemento non appartiene a $S$.
***
- ### Insert($S, x$)
Un'operazione di modifica che inserisce nella struttura $S$ l'elemento puntato da $x$. Di solito, si presuppone che qualsiasi attributo dell'elemento $x$ sia già stato inizializzato.

- ### Delete($S, x$)
Un'operazione di modifica che, dato un puntatore $x$ a un elemento dell'insieme $S$, rimuove $x$ da $S$.
***
- ### Minimum($S$)
Restituisce un puntatore dell'elemento di $S$ con la chiave minore.

- ### Maximum($S$)
Restituisce un puntatore dell'elemento di $S$ con la chiave maggiore.
***
- ### Successor($S, x$)
Dato un puntatore $x$ che punta ad un elemento appartenente a $S$, restituisce un puntatore all'elemento successivo ad $x$, oppure $Null$ se $x$ non ha successori.

- ### Predecessor($S, x$)
Dato un puntatore $x$ che punta ad un elemento appartenente a $S$, restituisce un puntatore all'elemento precedente ad $x$, oppure $Null$ se $x$ non ha precedente.
***
>[!Important] Convenzione
>- $S$ $\quad\longmapsto\quad$ struttura dati;
>- $k$ $\quad\longmapsto\quad$ chiave (valore);
>- $x$ $\quad\longmapsto\quad$ puntatore di un elemento;

