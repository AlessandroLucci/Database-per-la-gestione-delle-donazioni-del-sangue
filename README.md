# Sistema di Donazione del Sangue

Questo repository raccoglie il progetto universitario per la gestione e l’analisi delle donazioni di sangue, sviluppato come parte dell'esame di basi di dati e data mining.

## Descrizione del Progetto

Il progetto prevede la realizzazione di:

- **Database Relazionale**  
  Progettazione di un database con 7 entità principali: Medico, Donatore, Donazione, Centro di Raccolta, Magazzino, Test e Mail, e definizione delle relazioni (ad es. Medico-Donatore 0–N, Donatore-Donazione 1–N).

- **Data Warehouse**  
  Creazione di un Data Warehouse con 16 tabelle per l’analisi geografica e temporale delle donazioni, con operazioni OLAP (slice, drill-down) per un’analisi granulare.

- **Data Mining**  
  Applicazione di tecniche di clustering (K-means con k=4, scarto quadratico = 58, seed=10) e classificazione (albero decisionale con precisione 0,814 e recall 0,800, confronto con Naive Bayes con accuratezza 84,28%) per la segmentazione e la previsione delle fasce d’età dei donatori.

- **Info Visualization**  
  Sviluppo di visualizzazioni interattive con Tableau per evidenziare la distribuzione delle nazionalità e dei gruppi sanguigni.

## Tecnologie Utilizzate

- **SQL** per la gestione del database.
- **OLAP** per l’analisi dei dati.
- **Data Mining**: K-means, Albero Decisionale (J48) e Naive Bayes.
- **Tableau** per la visualizzazione interattiva dei dati.
