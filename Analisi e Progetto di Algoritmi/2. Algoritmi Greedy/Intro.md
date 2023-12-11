## Algoritmi Greedy

#### Applicazione: 
problemi di ottimizzazione.

#### Tipo di approccio: 
calcolo della soluzione ottima attraverso una sequenza di scelte localmente ottime.

#### Caratteristiche: 
- semplici da scrivere  
- efficienti 

#### Questioni 
- dimostrare la correttezza di un algoritmo greedy 
- capire quali problemi sono affrontabili con una strategia greedy

#### Due ingredienti chiave
- **proprietà della sottostruttura ottima**: tipica anche della Programmazione Dinamica
- **proprietà della scelta greedy**: la scelta, che compio ad ogni passo, appartiene a una soluzione ottima del sottoproblema che sto risolvendo in quel momento

---
## Greedy VS DP

- Soluzione ottima **VS** Valore ottimo + soluzione ottima 
- Top-down **VS** Bottom-up 
- Pochi sottoproblemi da risolvere **VS** Tanti sottoproblemi da risolvere 
- Efficiente e semplice da scrivere **VS** Meno efficiente e più complicato da scrivere 
- Applicabilità inferiore **VS** Applicabilità maggiore

---

## Correttezza di un algoritmo greedy

Si deve **DIMOSTRARE** che la sequenza di scelte <u>localmente</u> ottime conduce a una soluzione globalmente ottima.
Ad ogni passo, l’attività scelta è inclusa in una soluzione ottima del sottoproblema che sto risolvendo.