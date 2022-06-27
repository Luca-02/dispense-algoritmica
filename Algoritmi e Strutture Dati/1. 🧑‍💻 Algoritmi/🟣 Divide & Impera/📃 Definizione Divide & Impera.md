# Definizione 📃
Un algoritmo di tipo **Divide & Impera** è di tipo #ricorsivo ma particolare:
```mermaid 
graph TD; 
id1([A B C D E F G H])
id2([A B C D])
id3([E F G H])
id4([A B])
id5([C D])
id6([E F])
id7([G H])
id8((A))
id9((B))
id10((C))
id11((D))
id12((E))
id13((F))
id14((G))
id15((H))

id1 --> id2
id1 --> id3

id2 --> id4
id2 --> id5
id3 --> id6
id3 --> id7

id4 --> id8
id4 --> id9
id5 --> id10
id5 --> id11
id6 --> id12
id6 --> id13
id7 --> id14
id7 --> id15
```
- #Divide: divide in sottoproblemi
- #Impera $\rightarrow$ `ricorsiva`: risolve i sottoproblemi
- #Combina: combina i sottoproblemi per ottenere la soluzione finale

>[!Important] Regola Fondamentale
>Risolvere **SEMPRE** prima la parte sinistra e poi quella destra, **MAI** in parallelo 

>[!Note]
>Un algoritmo di **D&I** lo si riconosce dal tempo del passo ricorsivo;
>es. 
>- $T(n) = T(\dfrac{2n}{3})$ è D&I? **Sì**, l'importanza della parte che tolgo non è collegata ad $n$
> - $T(n) = T(n-1000)$ **NON è** D&I

