Una *struttura dati per Insiemi disgiunti* è una collezione $S=〈S_1,S_2,...,S_k$〉di insiemi disgiunti. Ogni insieme è identificato da un **rappresentante**, che è uno dei membri dell’insieme stesso. 

Le operazioni supportate sono
- $MAKE\_SET(x)$: questa operazione viene utilizzata per creare un insieme disgiunto contenente un singolo elemento $x$, che sarà il rappresentante dell'insieme.
- $FIND\_SET(x)$: Questa operazione restituisce il rappresentante dell'insieme di cui fa parte $x$.
- $UNION(x, y)$: Questa operazione viene utilizzata per unire i due insiemi disgiunti contenenti $x$ e $y$.