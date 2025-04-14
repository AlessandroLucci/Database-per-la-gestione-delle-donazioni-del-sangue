## Indice dei Contenuti
- [Contesto del Progetto](#contesto-del-progetto)
- [Sommario Esecutivo](#sommario-esecutivo)
- [Struttura del Database](#struttura-del-database)
- [Risultati delle Query SQL](#risultati-delle-query-sql)
- [Struttura del Datawarehouse](#struttura-del-datawarehouse)
  - [Età](#analisi-olap-età)
  - [Geografia](#analisi-olap-geografia)
- [Analisi OLAP dal Data Warehouse](#analisi-olap-dal-data-warehouse-età-geografia)
- [Analisi dei Cluster di Donatori (K-means)](#analisi-dei-cluster-di-donatori-k-means)
- [Modellazione Predittiva](#modellazione-predittiva-albero-decisionale-naive-bayes)
  - [Albero Decisionale](#albero-decisionale)
  - [Naive Bayes](#naive-bayes)
- [Visualizzazione dei Dati](#visualizzazione-dei-dati-nazionalità-gruppi-sanguigni)
  - [Nazionalità](#nazionalità)
  - [Gruppi Sanguigni](#gruppi-sanguigni)
- [Raccomandazioni](#raccomandazioni)
- [Ipotesi e Limitazioni](#ipotesi-e-limitazioni-eventuali)

 ## Contesto del Progetto
Questo progetto universitario si basa sulla creazione, implementazione e analisi di un sistema informativo per la gestione delle donazioni di sangue. L'obiettivo è creare una base dati strutturata per tracciare le informazioni relative a medici, donatori, donazioni, centri di raccolta, magazzini e test associati, al fine di estrarre insight utili per comprendere e ottimizzare il processo di donazione.


## Sommario Esecutivo 

L'analisi del Sistema di Donazione del Sangue, basata su un database e un data warehouse appositamente costruiti, ha rivelato pattern chiave per ottimizzare le operazioni. L'identificazione di quattro distinti cluster di donatori (tramite K-means), con profili specifici come "Giovani Adulti B+" e "Donatori Maturi A+", permette ora una segmentazione mirata per le campagne di sensibilizzazione. L'analisi OLAP ha confermato concentrazioni significative di donazioni per fascia d'età (picco 45-54 anni) e geografia (es. Roma), fornendo basi concrete per ottimizzare la logistica delle raccolte. Inoltre, modelli predittivi sviluppati raggiungono un'accuratezza di circa l'80-84% nel determinare la fascia d'età del donatore, offrendo uno strumento potenziale per la pianificazione. Si raccomanda di implementare strategie di comunicazione differenziate per cluster, pianificare raccolte basate sui dati geografici e monitorare proattivamente i gruppi sanguigni critici (come 0+) identificati tramite query specifiche, al fine di migliorare l'efficienza complessiva e la disponibilità delle scorte.

## Struttura del Database
La base dati è stata strutturata per mappare fedelmente il flusso operativo della donazione del sangue, articolandosi attorno alle entità chiave: Medico, Donatore, Donazione, Centro di Raccolta, Magazzino, con dettagli specifici per i Test Sangue Intero e Test Infezioni Virali. L'integrità referenziale e l'aderenza alle regole del processo sono assicurate dalle cardinalità definite tra le entità (es. un Medico può non avere donatori (0) o averne molti (N), mentre una Donazione deve avere un solo Donatore (1-1)). Il design è il risultato di un processo iterativo documentato da schemi ER (in versione non ristrutturata e ristrutturata) e da un modello logico, che include ottimizzazioni specifiche come la gestione dedicata delle 'Mail' e una rappresentazione dettagliata delle scorte, fornendo così le fondamenta per il sistema informativo.
### Modello Non ristrutturato
![image](https://github.com/user-attachments/assets/2b72f657-06de-452f-9a14-294c5d2ec671)
### Modello Ristrutturato
Qui riportato lo schema ER dopo un processo di ristrutturazione mirato a ottimizzarne la struttura. Le modifiche chiave rispetto allo schema non ristrutturato includono:
La creazione di una nuova entità 'Mail', separata da 'Donatore', per una gestione più efficace degli indirizzi.
L'eliminazione dell'attributo composto 'Scorte Disponibili' nel 'Magazzino', sostituito da un insieme di attributi specifici per ogni tipo di scorta, migliorando la granularità.
La rimozione dell'entità padre 'Test' nella gerarchia dei test. Essendo la specializzazione Totale ed Esclusiva, gli attributi comuni sono stati migrati direttamente alle entità figlie ('Test Sangue Intero', 'Test Infezioni Virali'), semplificando il modello."
![image](https://github.com/user-attachments/assets/964c5aa3-f12a-4ed0-942c-4acfc729f5bc)


