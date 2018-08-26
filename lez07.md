---
author: Gabriele Zarcone
date: Lezione 7
title: Processi - OpenSource
---
---------------------------------------------

## Pull request (e fork)

a differenza di git flow non lavora localmente ma lavora in remoto, sono dei siti a cui mi devo collegare. 

Permette di gestire le iterazioni tra gli utenti di bitbucke o github ecc...

E' legato ai fork. Quando faccio un fork il meccanismo si ricorda qual'è la repository originale e mi avvisa se la versione originale viene cambiata e mi chiede se voglio aggiornare.

Inoltre questo workflow permette, più importante di dare delle pull request alla repository originale. Chi fa fork e modifica quella originale, se si accorge che ha fatto qualcosa di buono invia una pull request all'originale. Così che l'originale si chiede se fare o meno il pull dall'altra repository di quella cosa o se dire al collaboratore attraverso dei messaggi cosa c' che non va e cosa aggiungere. Oppure chiudere la pullrequest senza fare pull. In questo modo l'originale non deve tenere sotto controllo tutti i suoi collaboratori ma solo quelli che gli mandano le richiestee. 

La responsabilità di risolvere tutti i conflitti nella pull request è del figlio, se rimane indietro rispetto alla versione ufficiale deve essere lui a fare l'**integrazione**. NOn lo deve fare il proprietario. 

Nelle pull request di solito ci sono dei piccoli forum su cosa c'è che non va, su cosa manca per essere accettata ecc. Ogni pull request ha una vita. E alla fine muore o inglobandola o chiudendola senza inglobarla. 

## Gerrit

ci sono progetti che sono talmente tanto grandi che non è possibile che ci sia solamente una sola persona che accetta la pull requet e basta 

Per esmpio android non ci può essere solo una persona, ci sono centinaia di richieste al giorno. serve un meccanismo di strbuito di moderazione (una peer review). Ma non posso fidarmi di tutte le persone che lo fanno, quindi c'è un meccanismo di voting. Se almeno 5 delle persone che possono votare gli piace la modifica fatta allora viene accettata. Deve raggiungere una soglia di votazione per essere approvato e inserito. Ma quando il singolo guardava se accettare la pull request guardava un sacco di cose diverse nessuna sufficente da sola. MAgari una cosa compila, passa i test, ma non serve a nulla. Bisogna tenere in considerazione un sacco di cose e hanno tutte un livello di maturità e esperienza deiversa. 

Posso quindi avere gruppi diversi per controllare l'usabilità dell'interfaccia e altri per capire se nel futuro questa cosa farà bene all'azienda. 

Gerrit mi permette di definire diverse categorie di votanti e ogni votante ha una sognlia diversa in base alla sua categoria, ha un valore e un peso diverso in base agli ambiti. Ed è completamente customizabile

gerrit è costituito da tanti componenti:

* 2 server git
    * 1 ha la parte stabile approvavata
    * 1 è dove vengono sottoposti i cambiamenti
    * il merge tra i 2 avviene solo al passaggio di votazioni con soglie
* server automation

ci sono:

* i developer che fanno fetch da un git e push dall'altro 
* i reviewer che possono fare fetch delle cose pendenti e approvano quello che funziona.

Ogni cambiamento a differenza delle pull request deve essere contenuto in un singolo commit. E' limitato perchè nonn mi fa vedere tutta la storia, ma serve per diminuire la grandezza delle cose da valutare, di modo che ogni cosa da valutare si aveloce, altrimenti diventa troppo lungo farne uno e devo lasciare in attesa degli altri altrettanto grossi che magari nel frattempo diventano obsoleti. Non si chiamano commit quindi ma **change**, che possono anche cambiare. Ogni change ha un id che rimane costante nelle diverse versioni. Localmente dovremo usare `git commit --ammend` per sovrascrivere il commit precedente invece che continuare a creare una sua evoluzione. 

Se facendo il merge e la situazione nel frattempo è cambiato allora se ci sono conflitti sarà chi propone la change a doverlo aggiustare, ma anche se non ci sono conflitti bisogna essere sicuri che non sia qualcosa di dublicati.

Gerrit aggiunge dei comandi ad alto livello che amplificano git (come per git-flow)

# Build automation tool

perchè fare build automation?

* per proteggersi se qualcuno fa versione non funzionante. 
    * può capitare di avere localmente tutto funzionante ma creare dei commit che siano non funzionante. Per esempio non aggiunto un file nuovo nel commit o non  aver aggiunto una dipendenza nuova. Se non metto delle cose nuove necessarie per farlo funzionare che non ci sono sulla repository generale ma solo nella mia locale. 
    * con la build automation posso creare dei test automatici che mi controllano prima di accettare un commit se funziona guardando anche solo guardando cosa c'è dentro la repository. 
    * automatizzo quinid la ricompilazione e il testing
    * posso automatizzare anche la creazione dell'ambiente di lavoro. Di modo che mi scarica in automatico tutte le dipendenze che servono. Gradle quando lo avvi ti scarica infatti tutte le dipendenze e le librerie che ti servono
    * voglio quindi che la creazione dell'ambiente, la ricompilazione e il testing vengano fatte tutte con un comando solo.

Ci sono molti tool disponibili:

* make
    * abbastanza vecchio
    * di basso livello = shell
    * crea una serie di dipendenze che se cambiano viene fatta nuovamente la compilazione in automatico. Le dipendenze dipendono da  altri file a loro volta. 
    * Dipendendo solo da comandi di shell posso fargli fare quello che voglio. Ma questo diventa molto oneroso come tempo e come attenzioni da prestare (tipo il path delle dipendenze non può cambiare). Dipendeva molto dalla macchians su cui mi trovo: se sono su windows o su mac cambiano i percorsi per esempio
* ant
    * prende come astrazione elementare una cosa diversa rispetto a make per evitare quei problemi
    * è scritto in JAVA da un progetto apache. Essendo in java è comodo solo se scrivi in java, con gli altri linguaggi non è così comodo
    * ha tutti i file di configurazione in XML
* Maven
    * molto complesso 
    * si concentra su quello che è il processo di generazione del software
    * fa il paio con una serie di repository e libreria di modo che possono essere ritrovate 
    * tende a isolare ogni progetto e qundi scaricava ogni dipendenza anche se c'era già sul pc. La salvava nella cartella del progetto così che fosse più trasportabile.
* Gradle
    * prende le cose migliori dei precedenti
    * ha origini in java anche lui, ma ha un sistema di plugin che lo rendono utile anche per gli altri linguaggi. 
    * ha un linguaggio dichiarativo con una nuova sintassi che mi permette di allontanarci da java anche se sotto sotto è java. 

```java
// pluggin da applicare
apply plugin: 'java'
apply plugin: 'eclipse'

// dove deve cercare le dipendenze
repositories{
    jcenter()
}

// quali dipendenze mi servono, specificando se mi servono in fase di test o di compilazione ecc
dependencies{
    testCompile 'junit:junit:4.12'
    test
}
```
Non c'è codice, sa lui per convenzione dove andare a prendere le cose e come farlo, se voglio modificare come lo fa posso farlo, altrimenti lui lo fa di default. Se non voglio modificare il comportamento mi basta usare il liguaggio dichiarativo semplice. 

Lavora per convenzioni, se tu non specifichi i percosi lui salva tutto sempre nelle stesse cartelle. Così non devo sempre specificare le cose ogni volta

## Make 

sono comandi di shell che creano dipendenze tra file. 

```
hellomake: hellomake.c hellofunc.c
    gcc -o hellomake hellomake.c hellofunc.c -I
```

dico che hellomake dipende dai file hellomake.c e hellofunc.c

* se non ho un file hellomake allora lo genera
* se ho un file hellomake allora lo rigenera se la sua data è più vecchia delle date dei file da cui dipende

Ragiona su file e sulle loro date di creazione. 

La prima riga mi dice i file che devo controllare, le righe successive mi dicono la lista di comandi shell che deve fare

Posso creare delle regole, dei file con questi comandi da lanciare ogni volta. E usare queste regole come se fossero delle funzioni all'interno di altre regole. 

E' però molto dipendente dal computer su cui gira, non è portatile. Problemi se non hanno le stesse librerie ecc. 

Ci sono dei comandi in cui dovevi prima dichiarare le dipendenze che ti servono e se non ci sono devi gestire che cosa deve fare il comando per gestire l'eccezione. Devo costurire dello script apposta per ogni eccezione. Non come gradle che semplicemente me lo scarica automaticamente. 

* automake
* autoconf
* imake

## Ant

nace come supporto al progetto tomcat

scritto in java per progetti java e supporta i tool di versioning

Non fa solo compilazione ma anche test e deploy

Com'è un build file:

* XML format
* sintassi dichiarativa
* contiente un project da costruire testare e installare
* può contenere un altro progetto dentro ad un altro. Ho dei *subproject* ognuno con il suo build file. 

L'XML non sempre è molto leggibile e ci sono dei tool che ti aiutano a leggerlo. 

Ogni progetto contiene più target (es compilazione o deploying) che possono avere dipendenze tra di loro. Non posso fare uno se prima non faccio un altro per esempio. 

## Gradle

Ha un linguaggio *groovy* ovvero una forma più dichiarativa di Java. E' sempre java, quando scrivo dei comandi dichiarativi poi questi vengono eseguiti attraverso script java. 

Funziona attraverso delle convenzioni ed è estendibile tramite plugin

# Bug Tracking system 

ci serve per tenere tracci e organizzare meglio la comunicazione tra i beta tester e gli sviluppatori. 

Succede spesso che se ho 300 persone e ho un errore mi arrivano 300 segnalazioni dello stesso errore. Ma mi devo mettere a riparo dall'overflow di comunicazione. Creo allora un database di segnalazioni già fornite in cui se voglio fare una sgnalazione allora prima controllo se è già stata segnalata. Al massimo scrive un +1 e non la riscrivo da capo. 

Devo far capire a chi mi ha comunicato l'errore che ho visto la sua segnalazione  e l'evoluzione fino alla chiusura del bug. 

Mi da anche un segnale dello stato di avanzamento del progetto e la sua reattività. Se ci sono errori del 2013 ancora non risolti allora magari non ha senso che ci perdo tempo. 

Non posso usare un forum genereico o una mail generico. La segnalazione dell'errorre deve essere guidata. Non mi possono dire solamente "il programma è crushato" Devono compilare un form che chiede su quale versione sei, su quale sistema lo usi ecc. 

Un bug per esssere utile deve essere:

* vero (ovviamente)
* ripetibile
* isolato (non una serie di errori tutti insieme)

### BTS noti:

* Bugzilla
* Scarab
* GNATS
* BugManager
* Mantis

Quando arriva un bug noto può succedere:

* che venga aperto perchè non noto
* aperto ma con richiesta di info ulteriori
* chiuso perchè non è un baco perchè magari non hai capito il programma
* chiuso perchè non riproducibile
* chiuso perchè già segnalato

una volta aperto viene assegnato a qualche sviluppatore che lo risolva. 

Una issue però può essere aperta quante volte si vuole anche dopo la risoluzioni se c'è ancora qualche problema. 

Se faccio un fix su un ramo del versioning è difficile farlo mergiare nel ramo master. Succedede in progetti che hanno delle versioni sviluppate in contemporanea. Capita anche a  volte che quello che vedano i tester sia il master e che i loro problemi siano stati risolti in versioni successive ancora in produzione , e quindi nell'errore si dice: vai a vedere la versione nightly (che viene rilasciata ogni notte con tutti progressi testati ma non finali)

Nella realtà non c'è bisogno di gestire singolarmente tutti i singoli tool. Spesso vengono tutti insieme su siti di hosting:

* sourceforge/berlios
* gotdotnet (solo progetti .NET)
* tigris
* code.google.com (chiuso usano github)
* openhub.net
* github
* bitbucket
* gitlab

e ci sono anche siti di **continuos integretion** che si aggiungono a questi per fare l'ultimo step 

# Unified process (o USDP o RUP)

fino ad adesso abbiamo visto modelli didattici (cascata, spirale ecc), l'XP un po' più anartica ma che comunque ha delle linee guide non sempre semplici da seguire. 

Questo invece è un modello che viene venduto alle aziende

Chiamato anche come:

* Unified Software Developmente Process (USDP)
* Rational Unified Process (RUP): dove rational è il nome dell'azienda che lo ha inventato e lo vende 

Utilizza UML. Hanno inventato l'UML e hanno deciso di dare un senso a quello che era solo un linguaggio che poteva essere usato bene o male. Hanno creato quindi un modello di processo per utilizzare nel modo corretto UML e hanno fondato Rational. 

Non è l'unico modello che usa l'Object orientation e non è l'unico che usa l'UML

## Cosa lo distingue dagli altri modelli

* si definisce come Sequenziale, Iterativo e Incrementale
    * va  adistruggere le consapevolezze fino ad adesso. Ma è solo una frase da marketing. Così che sembra di andare in contro a qualunque cliente.
    * **Sequenziale** lo dice perchè lavora a livelli di granaluratità temporale differenti. Ci sono 4 fasi e poi hai la consegna
    * **iterativo:** all'interno di ogni fase però devo iterativamente svolgere una serie di attività. Sono iterativo quindi a livello giornaliero e non mensile
    * **incrementale:** finite le quattro fasi le posso ricominciare e creare un nuovo incremento

da dei nomi nuovi alle fasi:

* inception
* elaboration: deettagliare il lavoro e fare progettazione
* construction: costruirlo e implementarlo
* transition: portarlo sulla macchina dell'utente


Di modo da non avere ambiguità con gli altri processi. I nomi classici delle fasi invecce gli usa come cose che devo fare durante le frasi, ma non sono una dopo l'altra come nella cascata. NOn le inserisce nel nome delle fasi, ma le usa comunque. 

Per esempio in iception che è la fase iniziale in cui l'idea germoglia devo fare molta raccolta requisiti, di analisi del mercato, non faccio test. Non è solo una cosa. è la somma di ognuna di queste cose. Ci sono delle curve anche all'interno della stessa fase. C'è  un diagramma da seguire con le 4 fasi e le varie attività e quanto di questa attività devo fare all'interno di ogni fase. C'è una guida poi per poter seguire il diagramma

Le varie attività continuano anche nelle fasi successive, non c'è congelamento. E' tutto mescolato ma in maniera studiata. 

## Best practice

dice una serie di pratiche che possono essere comode per lui

* sviluppare iterativamente
* gestire i requisiti di modo che siano sempre alla base del mio sviluppo. Non faccio nulla che non abbia a che fare con i requisiti. C'è collegamento tra tutti i documenti
* Usare componenti che si hanno già
* creare modelli visivi del software (es UML)
* Verificare la qualità del software
* COntrollare modifiche del software

## Parole chiave

### Use case Driven

è l'equivalente delle use stories nel mondo UMl anche se è molto più formale e quidata. Viene guidato con uno schema di domande rigide che ti fanno specificare ogni cosa. Usato per:

* definizione e negoziazione dei requisiti e la loro validazione:
    * praticamente ogni interazione con il cliente
* la definizione dei test di accettazione
    * vengono ripresi  in mano anche per pianificare i test
* la pianificazione dei rilasci
    * se voglio decidere cosa fare nel prossimo incremento

Sono dei documenti in evoluzione che possono cambiare e posso aggiunger più dettagli finchè voglio

Sono centrati sull'architettura. Di solito vengono fatte stime di produttività per capire i vantaggi e svantaggi delle architetture. Una volta che si sceglie non si cambia più e si va avanti su quello. Ma per UP fare una scelta così importante quando ancora non si conosce bene il problema nella fase di inception è rischioso, qundi anche quello si può mettere in discussione. Soprattutto nell'ultima fase quando si conosce molto meglio il problema. 

## Framework

si può vedere Up come framework di modelli che include altri modelli. SI può adattare per essere usato con le pratiche XP per esempio. Si usa nelle pratiche giornaliere con XP mentre nella fase macroscopico si utilizza la filosofia UP. 

Vi è una versione che sic chiama Enterprise che aggiunge anche due fasi:

* Production : tutto quello che c'è dopo l'uscita del programma(call center ecc)
* Rwtirement: se non voglio più continuare o se devo passare ad altri il progetto

# Qual'è il miglior processo?

Confrontare i processi non è semplice eprchè sono tutti diversi ma mi è utile per:

* confrontare le ditte
    * so qunato sono affidabili le ditte rispetto a quello che promettono al bando
* per confrontare me stesso nel futuro
    * non solo il singolo progetto, ma come posso avere dei miglioramenti usando i diversi processi possibili


Un processo di qualità mi porta, mi aiuta ad avere un prodotto fatto bene. Quindi conviene trovare il processo migliore per noi. 

## CMMI (Capability maturity model integrated)

il SEI, un ente svizzero diing software ha creato un modello con delle metriche di valutazione e certificazione dei processi

Utile per migliorare il processo o confrontare le ditte

Identifica 22 aree in quanttro categorie:

* ingegneria
* gestione del processo
* gstione del progetto
* supporto



 e per ognuna di queste categorie identifica delle aree di intervento, delle pratiche e delle obbiettivi. Poi vado a barrare delle caselle per vedere se gli obbiettivi vengono raggiunti ecc. 

Identifica per ogni area un:

* SG specific goal
* SP specific practice
* GG generic goal
* GP generic practice

per ogni goal ho delle practice che devo controllare se vengono attuate 

es:

* SG 1
    * SP 1
    * SP 2
    * SP3
* SG 2
    * SP 1


quelli specifici sono diversi per ogni area mentre i generici sono uguali per ogni area, ma per ogni area devi capire come usarli in quell'area. 

Nel momento in cui ho soddisfatto tutte le practice ottengo il goal. I goal sono man mano crescenti. Ogni volta che ottengo un goal allora in quell'area sono a quel livello. 

Ho una scala di livelli da 0 a 5:

0. incompleta
1. eseguita
2. gestita
3. definita
4. gestita quantitativamente
5. ottimizzata

Non è però sufficente per confrontare due processi 

(? vedere fine lezione con video da minuto:50 per la spiegazione dei livelli)
