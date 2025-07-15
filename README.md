# Analisi sui Disordini e Conflitti in Europa

> Progetto del corso di Data Mining – Università del Salento  
> Studentesse: Fasiello Luana, Pascali Sofia  
> A.A. 2024/2025

## Dataset

Abbiamo utilizzato i dati forniti da **ACLED - Armed Conflict Location & Event Data**, un’organizzazione che monitora con cadenza bisettimanale la violenza nel mondo.  
Il dataset raccoglie eventi disaggregati in Europa, classificati per tipologia di disordine (proteste, violenze, repressioni, ecc.) e arricchiti con variabili geografiche, temporali e demografiche (ad es. Stato, città, popolazione, tipo di evento, numero di attori coinvolti, etc.).

## Obiettivi
I nostri obiettivi sono stati la: 

1. **Valutazione della qualità del dato**  
   Analizzare eventuali bias nei dati: omissioni, distorsioni sistematiche o reporting irregolare.

2. **Analisi esplorativa e descrittiva**  
   Visualizzazione e sintesi delle principali tendenze nei dati: distribuzioni per nazione, tipologie di disordini.

3. **Costruzione di un modello predittivo**  
   Utilizzare algoritmi di classificazione per prevedere:
   - Il **tipo di disordine** (ad esempio: protesta pacifica vs evento violento)
   - Il **livello di interazione umana** (numero di attori coinvolti)

## Analisi Effettuate

### Analisi descrittiva

Ha consentito di individuare la frequenza degli eventi per stato, fare dei confronti temporali (heatmap) e visualizzare una mappa geografica dei conflitti

### Analisi esplorativa

- Analisi delle variabili categoriche e numeriche
- Matrice di correlazione
- PCA (Analisi delle Componenti Principali) per la riduzione dimensionale

---

## Classificazione: Decision Tree & Random Forest

### Decision Tree

Il Decision Tree costruisce una struttura gerarchica che divide lo spazio dei dati in modo ricorsivo. Ogni nodo interno rappresenta una decisione basata su una variabile, mentre i "nodi foglia" indicano la classe predetta.

Quali sono i vantaggi e gli svantaggi?
- **Vantaggi**: interpretabilità, semplicità
- **Svantaggi**: suscettibile a overfitting

### Random Forest

Il Random Forest è un **ensemble** di alberi di decisione. Ogni albero viene addestrato su un sottoinsieme casuale dei dati, e la classificazione finale è data dalla maggioranza delle predizioni.

Quali sono i vantaggi e gli svantaggi?
- **Vantaggi**: maggiore accuratezza, robustezza al rumore
- **Svantaggi**: meno interpretabile rispetto a un singolo albero

Abbiamo addestrato entrambi i modelli su un sottoinsieme di dati puliti, valutando l’accuratezza tramite **cross-validation**.

---

## Risultati

- Il modello **Random Forest** ha raggiunto una precisione superiore rispetto al singolo albero.
Le variabili più influenti nella classificazione risultano essere:
  - Tipo di interazione
  - Popolazione
  - Stato
  - Numero di attori coinvolti

---

## Conclusioni

L’analisi dei disordini e conflitti in Europa, basata sui dati forniti da ACLED, è stata interessante sia dal punto di vista esplorativo che predittivo. Fin dall’inizio, ci siamo poste l’obiettivo di valutare la qualità dell’informazione disponibile e di estrarre pattern utili per anticipare comportamenti sociali e dinamiche conflittuali in aree geografiche differenti.

Durante la fase iniziale, abbiamo rilevato alcune problematiche legate alla natura del dato. La ripetizione degli eventi su base giornaliera, ad esempio, ha sollevato interrogativi su come quantificare correttamente un singolo evento. Abbiamo, dunque, cercato di considerare aspetti come la durata, la cadenza e la portata dell’evento, con l’intento di distinguere manifestazioni isolate da fenomeni più strutturati e continuativi nel tempo.

La parte centrale dell’analisi si è concentrata sulla costruzione di un modello di classificazione. Dopo una fase di pre-processing e bilanciamento dei dati, abbiamo applicato due algoritmi: Decision Tree e Random Forest. I risultati sono stati molto incoraggianti, in particolare per il secondo modello. Random Forest ha infatti raggiunto un’accuratezza complessiva del 96%, mostrando una notevole capacità di generalizzazione.

Le performance del modello, tuttavia, sono risultate disomogenee tra le diverse classi. Gli eventi classificati come “Demonstrations” sono stati riconosciuti con precisione e recall perfetti, senza alcun errore. Anche la classe “Political Violence” ha ottenuto risultati molto solidi, con minime confusioni. La maggiore difficoltà è emersa nella classificazione degli eventi etichettati come “Strategic Developments”. In questo caso, il modello ha mostrato incertezza, probabilmente dovuta alla scarsità di esempi disponibili e alla vicinanza semantica con la classe della violenza politica.

Questo limite non inficia la validità del modello, ma suggerisce la necessità di una valutazione su come raccogliere e rappresentare eventi rari o ambigui nei dataset. La distribuzione sbilanciata delle classi e la mancanza di chiarezza nella definizione di alcune categorie possono infatti ridurre l’efficacia di qualsiasi approccio predittivo.

In definitiva, il nostro progetto ha dimostrato come, anche in un contesto complesso e ad alta variabilità come quello dei disordini sociali, sia possibile costruire modelli affidabili che supportano l’analisi e, potenzialmente, la prevenzione di fenomeni ad alto impatto sociale.


