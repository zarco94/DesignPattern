---
author: Gabriele Zarcone
date: Lezione 2
title: Processi - Processo di produzione del software
---
---------------------------------------------

# Processo

il processo deve favorire il nascere delle qualità che cerco nel prodotto fiinale. Una volta la produzione del software era prerogativa dei singoli, come artigianato. Produrre software non è solo scrivere codice, c'è molto di più che ha la stessa importanza. Bisogna raccogliere requisiti, scrivere le specifiche ecc. 

Bisogna risolvere tutti i problemi di comunicazione, bisogna spiegare le cose come se l'altra persona non sappia nulla. Avrò quindi bisongo sia di linguaggi formali ma anche di linguaggi meno tecnici per i clienti e i manager. Devo saper usare argomenti e linguaggio adatti alla situazione. 

Bisogna essere **rigorosi** (che è diverso da formali, perchè è impossibiile). La formalità diventa troppo faticoso come formazione delle persone, ma se uso dei metodi formali allora riduco **significamente** il numero di errori o almeno li riduco presto. Se mi accorgo di un errore mentre scrivo le specifiche posso cambiarlo subito, se me ne accorgo dopo avertlo mandato al cliente ho sprecato un sacco di ore/uomo. 

Ci sono tanti aspetti da considerare nella produzione di un software, da considerare uno alla volta. 

# Modellare un ciclo di vita di un softare

bisogna capire quali sono le attività da fare oltrer al coding. Devo decidere quando farlo, capire quando è finita una fase ecc. 

## Studio di fattibilità

mi chiedo se è opportuno entrare nel mercaqto con quesrta cosa o se è conveniwnte economicamente.

* definire qual'è il problòema e chi sono i miei concorrenti
    * c'è già la stessa cosa?
* studio come potrei realizzarlo
    * come mobile? web? con quale linguaggio?
    * sviluppo in proprio o subappalto?
    * hardware necessario?
* infine l'analisi dei costi per ogni possibiule soluzione per capire se conviene iniziare

è una mole di lavoro non indifferente però. Serve farlo in maniere preliminare e non approfondita altrimenti perderei un sacco di tempo che non mi frutta denaro. Molto spesso quindi la cosa viene data all'esterno. Utile soprattutto perchè solitamente è un ambito nuovo quello in cui mi sto inserendo. Chiedo a qualcuno che conosca meglio quel mercato. Oppure ho tutto il mio personale impegnato in altro e quindi chiedo ad altri.

### Output

il risultato di solitoi lo leggge il manager e quindi viene fatto in linguaggio naturale. Una relazione con grafici e tabelle economiche. Con magari una descrizione dei problemi. 

## Analisi e specifica dei rtequisiti

bisogna capire cisò che l'utente vuole e quali sono le sue necessità. Sppesso il dominio applicativo in cui entriamo non è il nostro, quindi spesso non è facile comprendere il bisogno dell'utente. Bisonga **comprendere il dominio applicativo**

Bisogna identificare gli **stakeholders**: ovvereo coloro che hanno investito in questo problema. Sono tutti gli interessati al programma:

* coloro che mi pagfano
* il cliente a cui serve il programma
* i clienti del cliente se sono loro che useranno il programma. 
* ecc

Spesso ogni stakeholder però ha altre idee rispetto agli altri. Duranbe la fase dei requisiti tutto deve essere preso in considerazione e va fatto tutto combaciare. 

Bisogna capire qualio sono le funzionalità richiestre. **Cosa** deve fare il sistema. 

* raccolta requisiti: cosa viene fatto, i compiti del programma
* progettaszione: come il programma lo fa, il linguaggio che usa ecc

la progettazione non va all'interno delle specifiche. I requisiti sono quello che interessa al cliente

Una cosa che dovrebbe essere anche quella nei requisiti sono anche le **qualità** che voglio del programma ma che non sono funzionali. Per esempio l'affidabilità o la lincenza che gli devo mettere (lo devo vendere o no?) ecc. Devono essere considerate una volta che diventano dei requisiti dell'utente, anche se non servono a far funzionare il programma. 

### Output

documento di specifica: è la base contrattuale del lavoro e deve essere approvato dal committente. Viene usato per progettare e per in seguito la verifica. Deve essere un documento formale, così che nulla possa essere interpretato da nessuno e le parole significhino lo stesso per tutti, progettista e cliente. 

Deevo scegliere il linguaggio del mio output deve essere adeguato per il mio ambito, non ne esiste uno universale. 

Sepsso come outpèut si ottine anche il **manuale utente** che è la vista perfetta di quello che dovrebbe fare il programma. 

All'interno delle specifiche ci possono essere anche dei test di validità. Stabilisco nel contratto i test che se vengono passati allora il programma per me funziona. 

## Proigettazione

= come i requisiti possono essere realizzati. 

Prima ancora di mettermi a scrivere codice mi devo mettere a scegliere l'**architettura** del mio lavoro (framwork, linguaggio ecc), la scomposizione del lavoro in **moduli**, la definizione dei **pattern** (problemi tipici che posso risolvere sempre in maniera standard)

### Output 

documento formale del progetto (=UML)

## Modularità

divide et impera ==> scompongo un problema complesso in problemi più semplici(top-down). Può però essere vista anche in maniera inversa (bottom-up) ==> Posso riutilizzare delle cose che già funzionano per fare cose più complesse. 

Comprendere  per l'uomo una somma di pezzi è più facile da comprendere che non un problema enorme tutto insieme. 

In più è èiù facile modificare delle caratteristiche o trovare degli errori. Mi basterà cambiare solo un modulo o cercare solo in quel modulo il problema. 

COme si divide in moduli? Non è detto che se è mopdulare sia perfetto, deve avere delle **caratteeristiche** ==> deve essere **stabile**+

ovvero quando è basssa la coesione e forte l'accoppiamento

* **coesione**: tutto quello che serve a quel modulo deve essere all'interno di quel modulo
* **accoppiamento**: tutto ciò che è all'esterno deve essere collegato pochissimo con quello che è all'interno (magari solo chiamate ai metodi)

i moduli devono essere autonomi

La modularità è facile, ma è difficile da usare bene. Bigogna acquisire con il tempo l'abilità di creare moduli.


è legato alla modularizzazione anche:

* **information hiding**: nascondo cose agli altri così che posso cambiarlo senza rischioi. Se è nascosto nessuno lo può usare, se nessuno lo può usare allora lo posso cambiare senza che nessuno abbia problemi. Cambio l'implementazione senza cambiarer gli effetti visibili al cliente. Non cambio la sua interfaccia, ma il suo core. 
* **data abstraction**
* **object orientation**

## Programmazione e test di unità

la parte di coding vera e propria. Faccio insieme anche però il test del componente che sto sviluppando. Indipendentemente dagli altri moduli del programma. Faccio così la prima verifica. Successivamente ci sarà il test del sistema ma potrà essere delegato ad altre persone (team specializzati che fanno quello)

In questa fase vengono realizzati oduli che prima erano solo scatole nere. E ogni modulo viene testato indipendentemente. 

Testing: sembra codice che devo scrivere che poi non vendo, ma non è tempo perso. Quindi va semplificato sempre di pù e velocizzato===> esistono dei framework di test. 

Mi permettono di creare dei moduli fittizi(stub) che mi sostituiscono i moduli che stanno costruendo le altre persone. I moduli stub non devono essere completi, devono solo simulare il **comportamneto** del modulo che sto simulando, si deve comportare come si comporterebbe il vero modulo. 

### Output

una serie di modulki separati e verificati singolarmente che seguono l'interfaccia concordata. 

## Integrazione e test di sistema

Una volta finiti separatamente i componeneti si mettono tutti insiemee e si fa un **test di integrazione**. Si deve testare tutta l'unità insieme perchè cose che funzionano da sole potrebbero non funzionare separatamente. E sono problemi che non si possono vedere nell'uso isolato. Ma non si possono testare tutti insieme, perchè potrebbero uscire dei problemi enormi. Si inseriscono quindi in modo graduale, prima in due, poi in tre ecc... 

Ho i moduli driver e i moduli stub. Posso allora sostituire gli stub con i moduli veri oppure posso 

* metodo top-down:
    * parto dal modulo main e inserisco man mano i moduli reali. Ho comunque un sistema non reale perchè il modulo che inserisco avrà anche lui collegamenti cvon moduli stub, ma pian piano diventa sempre più reali
* metodo bottom-up:
    * parto da una foglia che non ha stub e arrivo al main

### Test di sistema

quando arrivo alla vera applicaione posso fare dei test più reali e dare per esempio in pasto all'utente il programma (**Test di accettazione**). Ma lo posso fare solo se ho il cliente specifico a cui rivolgermi. Se invece lo creo io come idea. Allora specializzo sempre di più il mio test di modo che sia più sicuro che si possa testare. Si crea un problema però che se ho un utente conosco la macchina su cui girera, se faccio un test senza clienti allora devo essere attento alle molte combinazioni possibili. 

* Faccio per prima cosa un **alhpa test**: 
    * ovvero solamente all'interno dell'azienda. Non esce dall'azienda. 
* Faccio un **beta test**: 
    * si da ad una ditta esterna che si impegna a non distribuire il software e soprattutto si impegna a inviare feedback nel caso di errori. 

### Output

sono arrivato ad ottenere il mio **sistema**

## Manutenzione

è tutto ciò che devo fare dopo aver consegnato.

* Correttiva
* Adattativa
* Perfettiva

### Output

un prodotto migliore se fatta bene. 

## Altre attività 

### Documetnazione

può essere fatta in maniera trasversale ai vari processi. Spesso è lasciata per ultimo perchè è noiosa, lunga da fare e potrebbe cambiare cmabiando il codice. Bisonga spiegare tutto. Però alcune parti della documentazione (tipo uml) si possono fare anche in corso d'opera. 

Alcune metodologie agili usano come documentazione i test del prodotto, così che la documentazione sia corretta e sempre aggiornata, perchè è codice eseguibile. 

### Verifica e controllo qualità

Quality assurance

### Gestione del processo

* premi fine anno
* responmsabilità
* eccezzioni, problemi trovati
* formazione

### Gestione delle configurazioni

gestire le varie versioni del mio programma (es il progetto iOs e il progetto Android)

# Cicli di vita del software

In che modo fare questi passaggi? Cosa fare prima e dopo?

## Modello a cascata

La cosa più logica sembra quello di mettere in ordine una dopo l'altra queste cose. Come in una cascata dove posso solo scendere e non posso tornare indietro. Se sono nella progettazione non torno nelle specifiche. 

Nato negli anni 50 (puntamento automatico difesa aerea americana: contraerea) e diventato famoso negli anno 70 con la crisi di alcun progetti. 

Non è un unico processo ma è una famiglia di processi (tutti con un numero diverso di fasi), ma tuytti hanno la caratteristica di non tornare mai indietro. 

Ho la necessità di congelare la fase precedente attraverso un semilavorato prodotto dalla fas. Gli output delle fasi quindi sono il mezzo di comunicazione tra le fasi. Ho congelato nel tempo, nello spazio (posso usare le persone in parallelo) e nelle responsabilità, ognunoo ha la responsabilità del suo pezzo. é come una catena di montaggio, non fai tuttas la macchina ma solo un pezzo. 

Il manager inoltre può gestire il tempo come vuole. Entro tot mesi devi fare quesate fasi. Fisso delle deadline sulle fìvarie fasi del progetto. So se sono in ritardo o meno. Posso pianificare e monitorare il rispetto delle scadenze. Ho delle scadenze intermedie prima della scadenza vera e propria. 

Tutto questo però è a senso unico. Se mi accorgo mentre sto progettando di aver sbagliato qualche specifica non posso tornar4e indietro. Assumo che ho fatto tutte le cose precedenti nel modo migliore possibile. Una volta che cosegno il documento l'ho congelato. 

### Manutenzione

è qualcosa di imprevisto nel modello a cascata, non ci dovrebbe essere. Non vieni pagato, dovrei farlo come patch. 

Non è contemplabile nel modelllo a cascata, perchè ti obbliga a scongelare le cose congelate e non si può tornare indietro. 

Ma il 70% dei costi di sviluppo ricadono in manutenzione. 

### Proiblemi
(wicked problem: non so che c'è un problema finchè non lo vedo (?))

* RIGIDITà:
    * non è in grado di gestire gli imprevisti (non è robusto)
* CONGELAMENTI SOTTOPRODOTTI
    * faccio una piannificazione di tempi su cose che non so come andranno, dovrei poter correggere on the go
* MONOLITICITà
    * tutto è incentratto su un unico rilascio. Il cliente compare solo all'inizio e alla fine del processo. 
    * la manutenzione viene fatta solo su codice 

## Modello a V

è ancora un modello a cascata, in cui le rdine delle cose è sempre lo stesso, ma ci sono delle attività di controllo qualità di (verifica e convalida). 

Controllo se il sistema è corretto (se funziona) e se è valido (se corrisponde a quello che vuole il cliente). Nel modello a V ogni volta che finisco una fase lo faccio vedere al cliente. ANticipo così il momento in cui si scoprono gli errori. 

Contemporaneamente ho anche la fase di verifica. La fase successiva controlla la fase precedente. 

FINE

-----