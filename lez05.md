---
author: Gabriele Zarcone
date: Lezione 5
title: Processi - eXtreme Programming
---
---------------------------------------------

# eXtreme programmin


## Quando non si può applicare XP

* qualunque ambiente in cui una delle 12 pratiche non si possono usare non va bene
    * per esempio se ci sono delle barriere tecnologiche che mi impediscono di avere un feedback in brevo tempo. per esmpio posso esegurie il sistema solo su un supercomputer non sempre disponibile
    * se c'è un ambiente che deve essere prodotto tutto inieme e non posso consegnarlo incrementalmente. per esempio quello delle centrali nucleari
* se ho barriere di tipo manageriale e burocratico
    * se ho un team che è posizionato in palazzi diversi
    * se i team sono troppo numerosi
* se ho necessità di documentazione per certificazioni tipo ISO9000. 
    * potrei usare comunque xp e scrivere una storia in cui mi dice di scrivere una documentazione.
* barriere di tipo fisico logistico
    * sistemazione degli spazi di  lavoro non open space o in edifici diversi

## Critiche ad XP (di Beltrand Meyer)

* Sottovalutazione up-front:
    * devo avere una organizzazione generale a priori di tutto quanto anche se spesso con un up-front mi complico anche troppo la vita
* Sopravvalutazione delle user story
    * delego un compito molto importate della generalizzazione allo sviluppatore. Non sempre è efficace
* Non vengono evidenziate le dipendeze tra le storie
    * dipendenze di funzionamento: quando ho forti dipendenze tra loro. Rischio di pestare i piedi all'altra coppia che modifica il lavoro che sto facendo io
    * dipendenze temporali: quali devo fare prima e quali dopo. 
* TDD può portare a visione troppo ristretta. C'è il rischio di dover rifare il lavoro dovendo pensare solo alla cosa del presente. Rischio di dover rifare tutto da capo per semplificare il lavoro. Ma è compatibile con Agile che mi dice di non aver paura di cambiare, ma ho il vantaggio che mi rimangono i test
* Cross functional teams:   
    * vorrei un programmatore che mi sa fare qualsiasi cosa dal database al front-end, mentre di solito vengono spezzati in competenze. Tutti devono essere capaci di toccare tutto. Ma non vuol dire che tutti devono essere bravi a fare tutto allo stesso modo, ma devono almeno essere in grado di mettere mano.

# Open Source

attezione che open source non vuol dire gratuito. Vuol dire che sto dando il codice al pubblico, non vuol dire che do il programma. 

## Strumenti tecnologici

Spesso viene utilizzato Open come per dire che non ci siano barriere. Ma spesso le cose non sono sempre facilmente raggiungibili, la comunicazione con gli altri sviluppatori trovare le parti di codici cambiate ecc. non serve è facile. Ci sono dei siti che lo fanno

Sono strumenti di **comunicazione**:

* quindi utilizzano internet
* anche scrivere del codice è comunicare ma serve qualcosa di più strutturato
* mi serve creare una comunity di sviluppo unita. Bisogna tener coeso il team anche se è sparso in giro per il mondo e ognuno si deve snetire accetato altrimenti va in un altro progetto. 

Servono anche per la **sincronizzazione del lavoro e verioning**

* sul codice
* sulla documentazione

il versioning è essenziale perchè chiunque può modificare qualsiasi cosa senza cancellare le cose, anche sulla documentazione oltre che il codice

sulla **automatizzazione delle build**

* tutte le persone che usano il mio progetto saranno aggiornate sulle dipendenze che servono e hanno tutti lo stesso ambiente di lavoro. 
* esendo script è ricreabile e lanciabile facilemente

e infine tool di **bug tracking**:

* sono dei tool che mi sostengono sulla ricerca di bug

## SCM - cosa ci serve?

### Version Control

è indispensabile anche se sto lavorando ad una versione nuova e completamente diversa e trovo un problema nella versione precedente. Con il versioning posso tornare indietro e modificare la versione precedente aggiustando anche la versione successiva. 

* Gestisce i lavori mentre sono in evoluzione permettendo di richiamare velocemente una qualunque versione memorizzata degli stessi. 
* Permette anche la condivisione di lavori con altri permettendo accessi contemporanei e aiutando a gestire i conflitti
* Posso tracciare e sapere chi ha fatto una modifica del sistema. Permette la tracciabilità del codice

Approccio di versioning:

#### Approccio Client Server

 ce ne sono tanti proprietari e pochi open source
 
 sono comodi per le aziende avere una cosa centralizzata e organizzata
 
#### Approccio Distribuito

ce ne sono pochi proprietari e molti open source

il mondo open source invece è molto più anarchico e quindi pone delle difficoltà molto più elelvate e che non si pongono all'interno delle azinede. Ora come ora però ci sono delle modalità molto complesse che quindi vengono usati anche nelle azinede. 

#### Prodotti:

* CVS: il più diffuso
* Subversioning (svn)
* Bitkeeper: prodotto commerciale ma distribuito gratuitamente per i prodotti open source. Usato per creare linux ma che continuava a cambiare i diritti e li diminuiva
* Git: sviluppato da Torlvas per lo sviluppo di Linux. Per ovviare alle limitazioni di Bitkeeper. E' quello che ha vinto su tutti. 
* Mercurial: concorrente di git perchè nato nello stesso periodo, un po' più pulito e dusato per progetti anche importanti ma un po' più di alto livello, meno flessibile di git
* Bazaar: usato anche lui per progetti grossi simile ai due precedenti

# Versioning

## Repository

contiene tutta la storia dei cambiamenti delle mie versioni, non contiene solo la ultima versione. Le contiene tutte!

Salva solo le differenze tra una versione e un altra, ma questo modo il sistema è molto letno se devo tornare molto indietro

Git per primo quindi: non salva solo le differenze ma salva tutto il file modificato, ma solo i file modificati, per i file non modificati uso dei link e comprimo i file nuovi. Occupa un po' di spazio in più, ma è decisamente molto più veloce come implementazione. Se ho bisongo di un file di 3 mesi primo non ho bisogno di ricostruire il file ma c'è già lì

Può essere **centralizzata** o **distribuita** a seconda dei prodotti. Ovvero posso creare o meno delle diramazioni private che non modificano il branch principale che è modificato da tutti. Posso avere una unica repository nel cloud o tante copie della stessa repository su ogni macchina diversa e poi fare il merge

Repository quindi è l'insieme di tutti i dati e le etichette 

## Workspace 

è invece la versione a cui sto lavorando in questo momento. Dalla repository posso caricare sulla mia workspace la versione sulla quale voglio lavorare. 

* la repository è tutta la storia
* la workspace è solo una foto

posso avere la workspace sullo stesso pc o su un altra macchina a cui accedo con dei protocolli

## Checkout

è il comando per copiare una cerda versione **da** repository **a** workspace

Sul mio workspace poi posso cambiare alcuni file o aggiungerni di nuovi

## Checkin (Commit)

sposto **da** workspace **a** repository

Aggiorno la repository con il contenuto nuovo della mia workspace. Salvando solo i dati nuovi o modificati

## Conflitti

Se la repository dopo che ho fatto il checkout viene aggiornato da una altra persona e viene cambiato. Potrebbero crearsi dei conflitti, se lo stesso file vienen modificato da due persone diverse nella stessa repository. Salvo tutte le cose che non hanno conflitto e il conflitto viene gestito.

### Gestione

anche se ho modificato lo stesso file non è detto che ci sia un conflitto, magari è 100 righe dopo. Git ha delle euristiche per capire dove può fare in automatico o dove ha bisogno del aiuto manuale. 

## Git

in git ognuno ha una copia della stessa repository, sulla mia macchian ho una repository intera, quindi non capita spesso che ci sia un conflitto. Ci sarà conflitto quando si cerca di far combaciare 2 repository. Git quindi sposta il problema della gestione in locale e non sulla macchina remota. Non coinvolge tutte gli utenti della macchina remota. La macchina remota viene aggiornata solamente quando hai risolto tu in tuo locale i problemi della tua repository che va in conflitto con quella remota, ma gli altri non lo vedono. 

## Tag

serve per definire una specifica versione. Do io un nome che voglio a delle versioni preceise. Prima serviva per creare una versione scegliendo tra le versioni diverse dei file (git lo fa ogni volta, non serve, si usa per rendere più belli i nomi)

## File Annotation

linea per linea mi dice quando è stata cambiata una riga e chi l'ha cambiata

## Lock o Merge

nei vecchi tool di versioning quando facevo un checkout dovevo specificare in lettura o in scrittura. Così che molti  possono prenderlo in lettura ma solo uno puù prenderlo in scrittura. Funzionerebbe malissimo però per l'open source.

Quindi per l'open source si usa il **merge** dove tutti possono scrivere e poi viene fatto un merge con un meccanismo di gestione dei conflitti. 

### Git ne ha 3

* **RESOLVE**
    * Git fa un confronto a 3 vie per capire se c'è conflitto. Confronta due versioni di due persone diverse che hanno un conflitto insieme a quella di un antenato comune ad entrambi. Se la mia versione è uguale ea quella dell'antenato quella dell'altro è diversa allora per git tu non avevi obbiezioni mentro l'altro si e prende la modifica fatta dall'altro. Se entrambe sono diverse allora si genera conflitto che serve risolverlo manualmente. 
* **RECURSIVE**
    * diventano grafi molto complicati, qquindi prende ricorsivamente sempre antenati più vecchi e risolve i conflitti. 
* **OCTOPUS**
    * in assenza di veri conflitti seri con un unico passo di merge risolve più branch insieme. (?)

Gi tinoltre a differenza degli altri tool di versioning permette di modificare la storia della versione. CAncellare file, modificare inizio del branch, cancellare i tag ecc ecc Da la potenza di fare tutto, bisogna stare attenti noi a non fare macelli. Mi da la possibilità di modificare la vista della mia versione. Posso aggiustare tutto o togliere cose che sono sicuramente sbagliate. Se voglio modificare come mi presento in pubblico posso farlo e in più è più facile per chi controlla il codice in un progetto opensource.

## Ditribuito

ditribuito non vuol dire non avere un server centrslizzato. Posso comunque fare in modo che il team decida che una delle macchine sia il server. Ma **posso non averlo!**

Per esempio se metto una repository su github posso usarlo anche come server centralizzato e fare un `git clone` sulla mia macchina. 

Le macchine che non sono centrali poi possono richiedere a quella centrale di fare merge con solo parti della versione

posso fare merge con la repository della mia repository con la repositroy di altro utente però. Cosa che non posso fare con le solite versioning centralizzate. 

### PRO

* offline work perchè ho la mia repository sulla mia macchina. 
* commit molto veloci e leggeri. Mi viene voglia di fare commit ogni 2 secondi. Anche perchè posso modificare la storia se sbaglio
* più flessibile
* backup implicito

CENTRALIZZATO: ho un unica repository

DISTRIBUITO: ho tante repository che sono copia di una centrale (che aggiorno con pull/push)

## Livelli di GIT

oltre a workspace e repository in git ho anche l'*index*, lo *stash* 

[link](ndpsoftware.com/git-cheatsheet.html)

devo fare  `git add` per fare in modo che un file inizi ad essere tracciato. Altrimenti qul file non verrà committato. Mi serve se ho dei file che non voglio facciano parte del commit. 

## Fork 

non è una operazione di git, ma di github. Mi serve per creare una copia di una repository su github. Così che io possa fare push, perchè su quella di un altra persone non posso fare push, ma solo una push request. Se forko la sua posso pushare su una cosa uguale senza modificare la sua e poi mandargli la richiesta di merge,