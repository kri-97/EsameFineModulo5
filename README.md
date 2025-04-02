# EsameFineModulo5

### Le origini dati vanno messe in una cartella chiamata "archive", altrimenti potrebbe non funzionare. Consultare ultima versione del file.

## Passaggi e Svolgimento del Report

### 1) EDA e Data Cleaning
La prima attività svolta è stata quella di analisi e studio del dataset per capire i dati a disposizione; sono state rimosse colonne superflue e influenti ai fini del report.

### 2) Costruzione Schema
L'obiettivo era quella di creare uno star schema per avere un'unica tabella dei fatti al centro con le varie dimensioni intorno. Tuttavia questo non è stato possibile in quanto una join avrebbe appesantito molto la tabella dei fatti creando duplicati inutili. Nello specifico le tabelle Payments e Reviews, se messe in join con la tabella Orders avremmo avuto tante righe duplicate quante recensioni o tipi di pagamento avesse uno stesso ordine.
Un tentativo di join è stato fatto tra la tabella Orders e Items. In Power Query si è riusciti di ottenere l'ultimo valore di ItemsId dell'ordine; in questo modo per ogni ordine si conosceva il valore di items totali (perchè era il maggiore tra tutti gli ItemsId). Ciò nonostante, nel caso di ordini con prodotti diversi si perdeva informazione di quest'ultimi, impedendo lo sviluppo di operazioni utili al report. Si è deciso quindi di tenere separati Items e Orders, scegliendo di avere uno schema a "Fiocco di Neve" invece di uno a "Stella".

### 3) Task Richieste
Le 3 task sono state soddisfatte in 3 pagine diverse: Ordini, Ricavi e Rating. Si è deciso di tenere per ogni pagina delle visual "Schede" non aggiornabili ingnorando il contesto di filtro. Esse mostrano una visual generale del contesto in questione. Le pagine possiedono menù e pulsanti interattivi per visualizzare diversi aspetti. 
Sono state aggiunte 2 pagine aggiuntive che visualizzano il lato geografico e il lato dei pagamenti, mostrando in quest'ultima un ranking dei vari customer e seller.

## Aggiornamento file .pbix (Versone 2)
### Modificato file (02/04/2025)
Mi era sfuggito aggiornare la misura dei Prodotti Non Venduti. Come descritto nel punto 2) si era provato ad avere un'unica tabella dei fatti, riuscendo parzialmente. La prima versione della misura era collegata in maniera implicita a questa tabella in join alla quale ho disabilitato il caricamento in power bi (su power query è visbile). Dopo esser tornato con le tabella separate, la misura non è stata aggiornata.
Nella vesione 2 del file .pbix, la stessa misura è collegata correttamente. Per maggiore chiarezza, consultare la tabella in power query "ProdottiNonVenduti".
