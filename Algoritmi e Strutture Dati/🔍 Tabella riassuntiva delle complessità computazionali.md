I seguenti tempi sono calcolati in base al [limite asintotico superiore](obsidian://open?vault=obsidian-git-sync&file=Algoritmi%20e%20Strutture%20Dati%2F1.%20%F0%9F%A7%91%E2%80%8D%F0%9F%92%BB%20Algoritmi%2F%F0%9F%94%B4%20Limiti%20Asintotici%2F%E2%A4%B4%EF%B8%8F%20Limite%20Asintotico%20Superiore):

|             | Ins.     | Serach   | Del.       | Max      | Min      | Succ     | Pred     | Update   |
| ----------- | -------- | -------- | ---------- | -------- | -------- | -------- | -------- | -------- |
| Array       | $1$      | $n$      | $n$        | $n$      | $n$      | $n$      | $n$      | 1        |
| Array ord.  | $n$      | $\log n$ | $n$        | $1$      | $1$      | $1$      | $1$      | $1$      |
| Heap        | $\log n$ | $n$      | $\log n^*$ | $1$      | $n$      | $n$      | $n$      | $\log n$ |
| Liste       | $1$      | $n$      | $1$        | $n$      | $n$      | $n$      | $n$      | $1$      |
| Liste ord.  | $n$      | $n$      | $1$        | $1$      | $1$      | $1$      | $1$      | $n$      |
| Stack       | $1$      | $n$      | $1^*$      | $n$      | $n$      | $n$      | $n$      | /        |
| Coda        | $1$      | $n$      | $1^*$      | $n$      | $n$      | $n$      | $n$      | /        |
| SBR bilanc. | $\log n$ | $\log n$ | $\log n$   | $\log n$ | $\log n$ | $\log n$ | $\log n$ | $\log n$ |


