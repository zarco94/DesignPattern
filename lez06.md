---
author: Gabriele Zarcone
date: Lezione 6
title: Processi - OpenSource
---
---------------------------------------------
# 3 articoli sull'OpenSource

il problema dell'open source viene spiegato in questi 3 articoli

* la cattedrale e il bazaar 
    * [www.catb.org/...](link)
    * è stato uno dei primi da cui è partitas tutta la discussione sull'opensource. ragiona sul processo 
* the care and the feeding of foss
    * ragiona più sulle fammiglie di prodotti e come evolvono questi prodotti
* the emerging economic paradigm of open source
    * più economico e analizza come mai ha mercato e funziona dal punto di vista economico una cosa che sembra quasi beneficenza

## The care and the Feeding of foss [Craig A. James]

è una visione evoluzionistica della vita del software, non solo open source. 

Identifica diverse fasi del software. Da quando nasce l'idea del proogramma fino a quando c'è un suo successore.  E fa il paragone tra i 2 animali: open source e a chiuso

* FASE 1: Invenzione, l'idea
* FASE 2: Espansione e Innovazione
    * si aggiungono idee e cose
* FASE 3: Consolidazione
    * c'è una fase di fusione intorno alle cose più promettenti
* FASE 4: Maturità
    * il mercato è dominato dal igliore e 
* FASE 5: FOSS domination
* FASE 6: FOSS era
    * ci sarà solo la parte foss

## Invention

### WebServer

nel 1989 nasce il primo sistema ipertestuale globale. era possibile crearlo, ma nessuno non ci aveva ancora pensato. Serviva un **web server**

### UNIX

nel 1973 nasce il primo OS scritto in linguaggio di alto livello (**UNIX**) e quindi portabile e separabile dalla macchina (es. una volt l'IBM aveva un OS per ogni diverso HW)

## Espansion and Innovation

lìidea si arricchisce e ci sono le aziende che vedono una fetta nuova di mercato e ci si fiondano al momento giusto cercando di differenziarsi per offrire qualcosa di diverso dai concorrenti. 

Per craig questo non è il momento giusto per produrre open source perchè le aziende sono molto più veloci a produrre. l'opensource rimarrebbe indietro

### WebServer

viene popolato di un sacco di cose in più:

* criptazione
* streaming
* cgi
* ssi

Nascono dei sistemi che si fanno strada

* Sun
* Microsoft
* Netscape

viene data la parte client gratuitamente ma veniva venduta la parte server. Quindi era tutto commerciale

Nasce comunque APache opensource


### UNIX

Diventano disponibili un sacco di variabili di unix che fanno concorrenza

* Berkley
* AX di ibm
* SOlaris

cercavano di essere uno compatibili tra di loro ma comunque erano in concorrenza perchè commerciali

Nascono i PC grazie ai sistemi operativi.

Anche se c'è una forte concorrenza nel mondo software comunque il codice è difficile da tenerlo segreto. Anche per i prodotti commerciali e non opensource. E? un continuo rincorrersi. 

## Consolidation

non tutti riescono a sostenere la lotta e alcune ditte falliscono o si aggregano tra di loro. REsistono quelle di più successo o con più finanze. 

Quelle che resistono posso sfruttare la loro posizione dominante per superare le altre

### WebServer

Microsoft sfrutta la sua supremazia sugli OS dando gratis il suo internet explorer. In questo modo lato client tutti hanno microsoft e quindi è meglio comprare lato server microsoft. Uccidendo la concorrenza

Assorbe così i suoi concorrenti (es Mosaic) inglobando le feature che rendevano i concorrenti migliori

NAche dalla parte  open si afferma una sola soluzione: Apache


### UNIX

Scompaiono alcuni OS (commodore, atari ecc) mentre altrin invece si tengono in posizioni di nicca (Mac)

Resistono Unix che si riuniscono nel posix e msdos/windows

## Maturity

Si sa adesso come deve essere il prododtto, non voglio ne aggiungere cose ne toglierle rallentando le nuove idee

Esistono ditte nuove, ma sono molto poche e molto di nicchia (es OS per la lavatrice). Non per il grande mercato

### WebServer

si sa cosa deve fare un web server

### UNIX

si sa cosa deve fare un OS: quello che ti spiegano al corso di OS. Niente di più ne di meno

## FOSS Domination

la lepre che è andata veloce e ha già aggiunto tutto quello che poteva la tartaruga recupera terreno e riaggiunge le feature che mancano al prodotto open rispetto a quello commerciale

Il prodotto open quindi si avvicina di più al commerciale, ma molto più **flessibile**, perchè chiunque può modificarlo dato che il codice è libero e posso personalizzarlo. 

Ho maggiore **affidabilità**. In un software commerciale non so cosa c'è dentro e mi devo fidare di quello che mi da il produttore. Un programma open invece posso andarmi a guardare tutto il codice e in più ci sono centinaia di persone che guardano il codice e che si sarebbero accorti se ci fosse qualcosa di sbagliato. 

è il momento giusto per l'open perchè si conoscono già le problematiche, le necessita, e tutto quanto, è come se i commerciali avessero fatto un prototipo e io posso incominciare da zero

### Web server

apache ha superato tutti, è il migliore adesso

### UNIX

nasce Linux

Scompaiono i prodotti commerciali oppure diventano gratuiti oppure abbracciano le versioni opensource. ANche se corrono il rischio di arrivare troppo tardi rispetto all'open che si sono già affermati

## FOSS era

non ancora verificata ai giorni d'oggi. 

I prodotti commerciali diventano di nicchia e gli open diventano i dominatori del mercato

## Conclusioni

Questa evoluzione è possibile solo per i software perchè sono soft! Non hanno tutti i lati negatii di un prodotto solido. Posso riprodurre infiniti prodotti a costo zero, mentre non posso fare 100000 fiat 500 a costo 0. Il prodotto è impalpabile. 

## La cattedrale e il bazaar [Eric Raymond]

su come si sarticola un progetto open source. 

Dice che il bazaar e la cattedrale sono due prodotti affascinanti e belli allo stesso modo. Lo stesso numero di turisti. Nascono in maniera diversa ma sono belli alla fine entrambi. 

### Come inizia un opensource

1. Il punto di partenza del software inizia dalla frenesia iniziale da uno sviluppatore
2. chiede poi ad amici e colleghi in una cerchia piccola 
3. si iniziano a scambiarsi pareri
4. le persone interessate danno vita ad un progetto iniziale

Da qui posso iniziare e rendere noto al mondo. Deve esserci una promessa plausibile. Non deve esserci il prodotto finale, solo una idea iniziale

### Come Continua

5. I membri del progetto lavorano al problema fino a che non raggiungono dei risultati presentabili
6. si rende noto il lavoro svolto dal gruppo
7. Arrivano i primi suggerimenti esterni al gruppo.
8. c'è interazione tra vecchi e nuovi membri del gruppo 
9. Nuove info vengono acquisite
10. si ritorna al punto 5

c'è solo moderazione e mettersi d'accordo. 

### Alcune frasi importanti dell'articolo

* se dai a tutti il codice sorgente ognuno diventa un tuo ingegnere
* se ci sono abbastanza occhi che cercano errori, gli errori diventano di poco conto. 
* se tratti i tuoi beta tester come la tua risorsa più importante lo diventeranno.
    * più persone provano il tuo programma più errori saltano fuori. 
* Quando hai perso interesse in un programma l'ultimo tuo dovere è passarlo ad un successore competente. 

### Confronto bazar cattedrale

| |Proprietario|OpenSource
|--|-------------|--------
|MODELLO | Cattedrale| Bazaar|
|RISORSE | Definite | Sconosciute |
|PLANNING | INtero progetto | Step by step|
|UTENTI | Utente paganti | Co-developer |
|OBBIETTIVO | Ripetto contratto | Risolvere un problema
|MOTIVAZIONE | Stipendio | Voglia |
|STATO PROGRESSO | Segreto | Pubblico |
|COLLABORAZIONE | Faccia a faccia| Internet|
|QUALITà | managament | tanti occhi|

### Problemi open

* il codice è pubblico ho il problema se qualcuno fa un fork per andare in una direzione diversa dalla mia e mi spezza la comunity di dev
* ci sono delle parti noiose da fare che probabilmente non vorrà fare nessuno. Parti non visibili che difficilmente attirano qualcuno


## The emerging economic paradigm of open source [Bruce Perens]

Il software non sempre è il cnetro del bussines dell'azieneda. Magari è solo il mezzo. ES amazon non è il sito, lei vende libri, non è quello il principio. Non vende software. C'è differenza tra il mio bussiness e uello che faccio per farlo crescere. 

Bisonga tenere conto se la mia tecnologia è differenziante o non differenziante. E' una cosa che gli altri non hanno, è una cosa che mi differenzia dagli altri? Posso non farlo fare agli altri concorrenti? 

Sono tecnologie che mi servono per vendere ma non mi produce soldi quello, è un centro di costo quello. 

Se è differenziante o non differenziante ci si accorge se il cliente lo può vedere oppure no. Ad esempio se quelli di amazo usano C o Java l'utnet non se ne acorge, non gli da vantaggio sugli altri

Mi devo chiedere se è una cosa che posso fare solo io o lo può fare anche il cliente.
 
Paradigmi differenti con cui posso sviluppare dal punto di vista economico:

* come ditribuiscono il rischio di development
* come ditribuisco il rischio di fallimento
* come sono efficenti nel distribuire i soldi allo sviluppo rispetto agli altri
* con che grado a differenziarmi dagli altri 
  
vedi tabella su slides. 

### Retail

non fatto per uno specifico cliente, ma per chiunque lo voglia comprare. es windows o office

* efficenza: bassissima rispetto allo sviluppo. la maggiorparte dei soldi va in marketing o magazzino ecc. Ho dei ritorni solamente perchè lo vendo al mercato di massa e ne vendo milioni. 
* distribuzione dei costi: inizio a vedere dei costi solamnete quando l'ho finoito. Tutti i rischi di fallimento sono a mio carico. 
* cusstomer differentiotion: il cliente non si può differenziare dagli altri clienti se ha questo prodotto perchè è di massa
* l'azienda però si può differenziare dalle altre produttrici di softw.

## In-House contract

* efficenza alta: pago gli sviluppatori per la maggior parte
* non c'è ne distribuzione dei costi ne di rischi
* differenzia i clineti: lo fai proprio e solo per loro. Possono mettere a contratto di non venderlo a nessuno. 
* mercato: 1 solo cliente

## Consorzio o collaborazioni non open

4 o 5 ditte che hanno il 90% del mercato fanno cartello e si presentano con unico prodotto. Spesso fallisconoo però perchè alla fine vincono gli interessi personali. 

* non ho differenziazione del mercato per l'azienda
* ma c'è distribuzione dei costi
* ma non funzionano

## Open Source

* falliscono molto spesso o addirittura non partono proprio mai. 
* non c'è differenziazione tra i clienti e nenache tra le aziende
* ho distribuzione dei rischi

L'unico modo in cui il cliente vuole una differenziazione l'unico modo è farlo fare pagando per quello altrimenti allora posso abbattere i costi facendo la cosa in maniera open source. Magari amazon che il software non è un suo valore aggiunto di vendita allora potrebbe farlo fare con un progetto open source,così da non pagare tutto il processo. Dietro ai più grandi lavori open source di adesso (eclipse ecc) c'è una o più aziende solitamnte

Perchè partecipare ad un processo open source

* per una azienda potrebbe esserci l'abbattimmento di costi di sviluppo di un software che le serve. per esempio un IDE java sviluppa eclipse invece di farlo da capo
* visibilità e pubblicità per un azienda
* visibilità e pubblicità per un developer da mettere a curriculum

## Validare le impressioni

è un articolo che ananlizza degli articoli che hanno fatto degli esperimenti empirici sull'open source su alcune ipotesi sull'open source:

* "Un progetto open source aumenta la velocità di crescita del progetto"
    * posso tracciare il tool di versioning e vedere la crescita del progetto con delle metriche
* "I progetti open source aumentano la creatività"
* "HAnno successo per la loro semplicità"
* "Hanno meno difetti dei commerciali e sono trovati più facilemente"
* "sono più modulari dei commerciali"

3 su 5 di queste ipotesi sono false

# Vecchie sfide che si amplificano

quali sono i vantaggi dell'open source?

Sfide:

* INTEGRAZIONE DEL SOFTWARE
    * modello a cascata: è una fase a se stante
    * modello microsoft: compilo solo a fine giornata  e integro con il sfotware intero. 
    * modello XP: più volte al giorno escludendosi a vicenda con il token o il pupazzo. 
    * F/LOSS: continuamente e senza coordinazione----> prota a problemi nuovi e diversi 

# Nuove sfide

* Come comunicare?
* come tenersi uniti?
* come coordinarsi?
* come ottenere collaborazioni?

# GIT (again)

## Scenari uso di git

[http://wiki.bazaar.canonical.com/Workflows](link)

Che scenari ho per l'uso di GIT?

* da soli
* partner (coppia)
    * posso fare push e pull dal computer di un altra persona, sneza passare da github (coffee shop)
* centralizzato
* centralizzato con commit locali
* decentralizzato con shared mainline
* decentralizzato con guardiano
    * vuol dire con una sorta di controllo umano o automantico (test) dei commit
* gerarchico
    * usato con linux ad esempio. I commit passano da un sacco di scalini prima di arrivare al capo. Divido in una piramide divisa in settori tecnologicie arrivno poi tuttiin cima solo quelli importanti e che funzionano

## Workflow

git è molto personalizzabile e posso usarlo in un sacco di maniere diverse. Esistono quindi molti workflow che personalizzano git di modo da dargli una struttura o una direzione precisa

In piccolo:

* git-flow: è un uso particolare dei meccanismi del branch. 

In Grande:

* push request
* gerrit


### GIT-flow

in team piccoli di 15-20 persone. 

git ha il concetto di branch ma non mi dice come li devo usare. A cosa servono i diversi branch. Non c'è distinzione sul tipo di branch. Non c'è pulizia o distinzione, ha solo meccanismi base.

git-flow ho dei branch che hanno vita infinita :

* master: 
    * dove ho la mia versione stabile
* develop: 
    * dove ho la versione in sviluppo in questo momneto

ci sono altri branch invece che devono morire

* feature: 
    * se parallelamente sto lavorando ad una singola feature non ci lavoro direttamnete su develop ma apro un branch mio che chiuderò una volta terminata la feature mergiando su develop che una volta finita la versione mergerà su master. FAcendo così l'integrazione. 
    * posso averne molti
    * non tutti si chiuderanno
    * una feature parte sempre dall'ultima versione di sviluppo di develop. In questo modo mi aiuta con la pulizia  e l'ordine. Non parto da una altra feature parziale
    * parto da ciò che è stato fatto fin ora e continuo da lì
* hotfix
    * se nella versione di master trovo un qualche problema allora faccio partire un branch da lì, risolvo e poi mergio sia in develop che in master, così da avere tutto corretto. 
* release
    * parte da develop e congela le funzionalità di develop fatte fino ad ora che entreranno nella prossima versione
    * tuttoe le feature che avviene dopo l'apertura del branch saranno nella prossima release
    * in questo branch posso ultimare le ultime cose di verifica della qualità prima di mergiare in master

git flow non fa nulla che non potrei fare anche con git, ma dovrei stare attento ogni volta a quale branch apro e quale chiudo. Con git flow invece le cose sono forzato a farle non posso sbagliare. Git flow non sono altro che una serie di comandi kdi più alto livello di git. Ogni comando git-flow equivale a tanti comandi git tutti insieme

Esistono anche delle estensioni di git-flow