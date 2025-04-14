## Indice dei Contenuti
- [Contesto del Progetto](#contesto-del-progetto)
- [Sommario Esecutivo](#sommario-esecutivo)
- [Approfondimenti Analitici](#approfondimenti-analitici)
- [Struttura del Database e Cardinalità](#struttura-del-database-e-cardinalità)
- [Risultati delle Query SQL Chiave](#risultati-delle-query-sql-chiave)
- [Analisi OLAP dal Data Warehouse (Età, Geografia)](#analisi-olap-dal-data-warehouse-età-geografia)
- [Analisi dei Cluster di Donatori (K-means)](#analisi-dei-cluster-di-donatori-k-means)
- [Modellazione Predittiva (Albero Decisionale, Naive Bayes)](#modellazione-predittiva-albero-decisionale-naive-bayes)
- [Visualizzazione dei Dati (Nazionalità, Gruppi Sanguigni)](#visualizzazione-dei-dati-nazionalità-gruppi-sanguigni)
- [Raccomandazioni](#raccomandazioni)
- [Ipotesi e Limitazioni (Eventuali)](#ipotesi-e-limitazioni-eventuali)

 ## Contesto del Progetto
Questo progetto universitario si basa sulla creazione, implementazione e analisi di un sistema informativo per la gestione delle donazioni di sangue. L'obiettivo è creare una base dati strutturata per tracciare le informazioni relative a medici, donatori, donazioni, centri di raccolta, magazzini e test associati, al fine di estrarre insight utili per comprendere e ottimizzare il processo di donazione.


## Somamario Esecutivo 

L'analisi del Sistema di Donazione del Sangue, basata su un database e un data warehouse appositamente costruiti, ha rivelato pattern chiave per ottimizzare le operazioni. L'identificazione di quattro distinti cluster di donatori (tramite K-means), con profili specifici come "Giovani Adulti B+" e "Donatori Maturi A+", permette ora una segmentazione mirata per le campagne di sensibilizzazione. L'analisi OLAP ha confermato concentrazioni significative di donazioni per fascia d'età (picco 45-54 anni) e geografia (es. Roma), fornendo basi concrete per ottimizzare la logistica delle raccolte. Inoltre, modelli predittivi sviluppati raggiungono un'accuratezza di circa l'80-84% nel determinare la fascia d'età del donatore, offrendo uno strumento potenziale per la pianificazione. Si raccomanda di implementare strategie di comunicazione differenziate per cluster, pianificare raccolte basate sui dati geografici e monitorare proattivamente i gruppi sanguigni critici (come 0+) identificati tramite query specifiche, al fine di migliorare l'efficienza complessiva e la disponibilità delle scorte.


