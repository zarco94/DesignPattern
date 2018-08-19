---
author: Gabriele Zarcone
date: Lezione 4
title: Processi - eXtrem Programming
---
---------------------------------------------

# eXtreme programmin

## Variabili dell'extrem programming

* Portata
    * è la quantità di funzionalità richieste dal cliente. Per le metodologie agili è variabili e lo devo considerare come variabile, non posso pretendere che non cambi mai. 

* Tempo 
    * è il tempo che si può dedicare al progetto.

* Qualità 
    * la qualità che il progtto deve avere, solitamente:
        * correttezza
        * manutenibilità



* Costo
    * Qnto si può spendere

Per XP queste 4 variabili non sono indipendenti, ne posso al massimo fissare 3 e calcolare la 4. Ma non si possono decidere tutte. 

Per XP la **qualità** però è una costante: deve essere per forza quella massima. Tra le altre tre quella da calcolare è la portata. Io lavoro al mio massimo per tot tempo ma non  ti garantisco nulla su quello che posso darti. Una volta che mi dici quanto mi dai, quanto tempo ho allora ti dico quante feature ti posso dare con quei soldi e quei tempi. 

E' un contratto molto diverso dai precedenti. E non sempre è molto conveniente per lo sviluppatore. Non posso più riutilizzare le mie cose già fatte. Se ci metto di meno mi pagano di meno. Non mi pagano più 20 ore quando ne lavoro 2, ma almeno ho semore il lavoro pagato, è come la differenza tra un lavoro fisso e un libero professionista. 

## i Principi

* feedback rapido:
    * voglio trasparenza su quello che sta accadendo, lo sviluppatore vuole feedback sugli errori e il cliente vuole che ci sia feedback rapido sui cambiamenti che lui vuole
* presumere la semplicità 
    * Design for change. Devo già predisporre il mio software presupponendo già che dovrà cambiare in futuro. Perchè il costo delle modifiche aumenterà sempre di più più vado avanti. (empiricamente succede così), ma dewvo comunque fare la soluzione più smeplice possibile, non defvo aggiungere feature che non mi servono.
* accettare il cambiamento
    * non è in antitesi con la precedente. Devo sempre scegliere la strada che mmi lascia più strade aperte.
* modifiche incrementali
    * le modifiche vanno fatte in piccoli stadi (per tutto: il progetto, il piano di lavoro, aggiungere persone nuve ecc)
* lavoro di qualità
    * volgio che le persone stiano bene, voglio fidelizzare i miei sviluppatori. Dal punto di vista psicologico. 

## Figure in gioco e responsabilità

### Doveri

* `MANAGER e/o CLIENTE` che decide 
    * la **portata**
        * cliente: decide cosa vuole dal progetto
        * manager: cosa fare ad ogni iterazione
    * la **priorità** tra le funzionalità
    * **date dei rilasci**
        * in XP sono periodi molto corti, anche ogni 2 settimane. Così da dare modo al cliente di dire le sue opinioni e i feedback e lo sviluppatore comunuque ha il tempo per fare feature significative. 
* `SVILUPPATORI` (team)
    * fa la stima dei tempiper implemntare le singole funzionalità. Solitamente è  una cosa che non fa il tecnoco ma lo fa il manager. in XP invece lo fa il team che comunque poi ci deve lavorare e quindi sa di cosa parla. Ho una *responsabilizzazione del team*: non posso dare la colpa a qualcun altro se non funziona. 
    * dice quali sonon le conseguenze delle scelte tecnologiche. 
    * decide il processo
        * non mi impongono come farlo, ma lo decide il tecnico
    * pianificazione dettagliata:
        * decide lui da cosa iniziare, l'ordine delle cose da fare tra quelle date dal manager ecc..

### Diritti

* `MANAGER e/o CLIENTE` 
    * sapere cosa può essere fatto con quali tempi e costi
    * vedere i progressi nel sistema provati dal superamento di test da lui definiti
    * cambiare idea, sostituire funzionalità e cambiare priorità
* `SVILUPPATORI`
    * sapere cosa è necessario attraverso dei requisiti chiari:
        * per XP sono degli esmpi di utilizzo (*storie*) che chiarificano le priorità 
    * dire quanto serve per implementare la funzionalità 

## Appriccio di XP

1. Planning game
2. Brevi cicli di rilascio
3. Uso di una metafora
4. Semplicità di progetto
5. Testing
6. Refactoring
7. Programmazione a coppie
8. Proprietà collettiva
9. Integrazione continua
10. Settimana di 40 ore
11. Cliente sul posto
12. Standard di codifica

Sono cose che vengono presi da altri metodi e messi inieme. Ognuno di questi però ha dei pregi e dei difetti, devo fare in modo che tutto sia in armonia e combaci tutto

### Planning game

ci si riunisce tutti insieme e si decide la pianificazione bisettimanale. Con un aspetto molto ludico tipo gioco di ruolo.

#### Svolgimento:

* il cliente scrive ciò che vuole come priorità su delle schedine piccoline. Di modo che non si possa scrivere molto e siano qualcosa di fisico e maneggiabile. 
* possono essere viste come un informale Use Case di UML
* ci sono 3 fasi cicliche:
    1. ESPLORAZIONE: scoprire cose nuove del sistema
    2. IMPEGNO: si decidono quali carte fare in quelle 2 settimane
    3. GESTIONE: si guardano le 2 settimane precedenti e si capisce come è andata e cosa si può cambiare. (C'è uno sviluppatore apposta che si chiama tracker che tiene traccia delle cose che andrebbero dette al planning game successivo)

#### La Carta deve contenere:

* id
* frase che descrive uno scenario d'uso
* un test di accettazione
* un valore di prorità per il cliente

Sono tutti gli imput che da il cliente. 

* tempo

Gli sviluppatori prendono la carta e in team decidono quanto è difficile fare quella carta (senza guardare il valore per adesso). Per evitare l'effetto ancora si fa il Planning poker

> Effetto Ancora: la prima persona che parla influenzerà sempre quello che diranno gli altri. Perchè la mente umana è fatta così. Quando uno ha un punto di riferimento ragiona poi per scostamento da quel punto. Se il punto di partenza non è affidabile mi porta fuori strada. E gli studi di psicologia dicono che non dipende da chi lo dice. 

Ognuno da una stima senza dire agli altri alla carta e poi contemporaneamente isi gira tutti le carte. Non tutti sicuramente daranno lo stesso valore e allora quelli che hanno detto la stima più alta e più bassa hanno un minuto a testa per parlare e si rivota da capo e si ripete due o tre volte senza perdersi in discussioni lunghe e inutii. 

La stima del tempo la fa tutto il team così tutto il team si sente responsabile a farlo in quel tempo e non in più tempo. 

Se c'è molta disparità tra alto e basso vuol dire spesso che la carta non sia molto chiara e allora si chiede spiegazioni al cliente che comunque è lì presente al planning game

Se tutti danno dei tempi troppo alti vuol dire che le storie probabilmente sono troppo complesse e ampie e quindi si chiede al cliente di fare degli split delle storie.

* criticità

sempre gli sviluppatori aggiungono la criticità che è indipendente dal valore del cliente. Sono cose che magari il cliente non coglie ma lo sviluppatore lo sa. Più è critico più va fatto prima, così da non perdere soldi se le cose più complesse diventano impossibili da fare. 

Per finire il planning game si decide quali carte fare in quel tempo della prossima iterazione. 

La produttivitò a volte viene inserita come POMODORI. Si fanno 25 minuti (=1 pomodoro) in cui non faccio context switch e mi concentro solo su una cosa e quindi non mi devo perdere la concentrazione e riprenderla ogni 5 minuti. Ogni pomodoro faccio una pausa di 5 minuti ma dentro al pomodoro faccio solo una cosa e non guardo altro (telefono, instagram ecc). Quindi le schede si possono sstimare in pomodori: in 20 pomodori faccio queste schede ecc

Una volta finita l'iterazione posso aver fatto più o meno carte di quelle che volevo allora alla prossima iterazione modifico la mia stima

### Brevi cicli di rilascio

in questo modo ho dei feedback dall'utente frequenti e sono sicuro così che non sto sbagliando sicuramente. Evito di arrivare alla fine sbagliando tutto. MA devono comunque essere dei rilasci significativi con funzionalità nuove visibili e utili per il cliente. 

### Uso di una metafora

è una cosa che viene usata molto poco. Uno dei difetti che di solito viene attribuito ad XP è che è difficile avere un disegno globale con una idea delle dipendenze tra le varie storie ecc. 

Si usa quindi una metafora o una similitudine del mondo reale e non informatico che possa rappresentare il mio progetto così da spiegare all'utente quale parte del mio oggetto reale sto costruendo. Così che ci si possa orientare meglio.

Se la metafora è scelta bene può diventare anche un valore aggiuntivo, e non solo un moto per comunicare. Mi può dare idee nuove partendo dalla metafora per arrivare ak software. Solitamente però si usa poco e male. 

### Semplicità di progetto

* Once and once only:
    * scrivi una volta sola, se c'è una ripetizione astrai
* KISS: keep it simple, stupid
    * più è semplice più è comprensibile, evolvibile, e aggiustabile. 
* Non Design for change:
    * non pensare a programmare così che sia meglio evolvibile dopo, ma fai il design più semplice e veloce per risolvere il problema. Non aggiungere robe inutili per il fututro che magari nenache funzionerà 

### Testing

è una cosa molto pervasiva:

* è il cliente che scrive i test
    * aumenta la fiducia nel progresso del software
* c'è nel tdd così che lo sviluppatore si fidi di quello che scrive e lo fa per progettare cose ancora non scritte. Diventa parte del programma stesso. 

Costrundo il test durante lo sviluppo mi aiuta anche nella fiducia se cambio qualcosa fatto da un altro. Se passo anche i test fatti da un altro allora aumenta la mia fiducia sulla correttezza. 

ANche se ho ereditato del software da una ditta esterna scrivo dei test per la parte che devo modificare prima di toccare del codice che funziona. Così da stare più sicuro che funzioni tutto. 

### Refactoring

In questo modo non ho più **paura di fare refactoring**. Il refactoring deve essere fatto senza pietà se c'è un modo più semplice per farlo. Più smeplifico il progetto meglio è. Il refactoring mi permette di mantenere semplice il software anche se continuo a modificarlo, è il mio sforzo che mi serve per non far aumentare l'entropia. Grazie al refactoring non aumento la complessità esponenzialmente dei cambiamenti con il passare del tempo come invece succede negli altri processi. 

Posso farlo:

* dopo il semaforo verde
    * per sistemare il disordine creato con la nuova feature
* prima del nuovo semaforo rosso
    * in modo da sistemare tutto e fare spazio per la nuova funzionalità che arriverà

### Programmazione a coppie

fa venire il dubbio che sto sprecando forza lavoro. Ho 2 persone che pago come due e mi lavorano come 1. UNo scrive e l'altro guarda in questo modo. Diminuisce la gente che scrive codice, Ma non è vero che si dimezza la produttività. 

* con il foglio bianco davanti si dimezza la possibilità che ci si blocchi, vengono più idee. 
* empiricamente ci si accorge che quello che scrive una coppia scrive 1,5 quello che scrive un singolo
* prendere il nuemro di righe scritte però non significa correttezza, una cosa che funziona meglio con 10 righe è meglio di una che ce ne voglionoo 100. Bisogna guardare la qualità delle righe e non la quantità e in 2 c'è sempre uno che controlla la qualità. Perdo meno tempo in futuro nel dover tornare indietro a riguardare il codice
* un occhio in più mi serve anche per evitare di fare errori di codice che mi fanno perdere tempo e tronare indietro e perdere tempo.
* in due c'è più rispetto delle regole del XP
* ci si può dividere i ruoli tipo rally. L'altro guarda già un po' più aventi dell'altro e magari pensa già al refactoring o al buon design.
* ti aiuta meno a distrarti
* aiuta nella formazione di nuovo personale che avviene per baby step e quindi una alla volta. IN più viene subito messo in prima linea il nuovo e impara subito orientandosi pian piano nel progetto 
* le coppie non sono mai fisse e quindi aiuto a formare meglio il team e ci si scambiano e mescolano di più le info del team. 

Non è un ruolo passivo: chi scrive deve spiegare e spiegre aiutq sempre a capire meglio le cose. E anche l'altro mi fa delle domande che possono portare stimoli e conoscenza. 

### Proprietà collettiva

Non ci deve essere il proprietario o il responsabile di una parte di codice, ma tutto è di tutti. Di modo che se una persona si ammala o si licenzia possa essere intercambiabile con un altro. Non vuol dire anarchia che nessuno è responsabile, ma che tutti sono responsabili. Ognuno si sente responsabile che tutto sia fatto per bene. E tutti sono autorizzati a cambiare tutto, di modo però che sia più pulita e che rispetti i test. I test mi danno questa libertà.

Non è tempo perso toccare i componenti degli altri perchè non è una roba sua, ma è di tutti, è anche roba mia. Non sto facendo un favore all'altro ma lo faccio anche a me. 

### Integrazione continua

Qunado sviluppo un componente non ho finito la storia. LA storia fnisce quando il mio componente è integrabile nella macchina con tutti i componenti. C'è un unica macchina in tutto il team nella quale c'è l'ultima versione generale del progetto. E finchè il mio lavoro non funziona sulla macchina comune e passa tuttii test anche precedneti allora non ho finito la storia. La macchina dovrà risolvere i conflitti tra le varie versioni. 

In questo modo ho un feedback rapido e continuo che tutto funzioni e vedo la progressione del lavoro degli altri del team. 

### Settimana di 40 ore

Non serve fare straordinari. E' un lavoro in cui serve attenzione e concentrazione. NOn è produttivo e non è soddisfacente. Devo creare un bel clima

### Cliente sul posto

il cliente deve essere parte del team, perchè deve dare supporto per le storie. Non ho una specifica enorme, ma mi serve il cliente per capire cos avuole. Lui deve essere però sempre disponibile altrimenti perdo tempo e si crea la coda. Di modo che ho continuo feedback dal cliente. 

Il cliente lì non deve essere l'ultimo arrivato ma deve essee qualcuno di importante e che sappia le decisioni da prendere. 

In più il cliente vede che il team sta lavorando per lui e c'è più trasparenza. 

Il problema è che non è rappresentativo di tutti gli stackholders. 

### Stnadard di codifica

Ognuno deve scrivere allo stesso modo, le parentesi, l'identazione. Così che il codice che scrive un altro mi sembri uguale identico a come lo scrivo io. Così che ci possa lavorare da subito sopra. 

Se uso queste 12 regole allora sto usando XP, ma c'è una 13 regola che mi dice: sono solo regole anche se potrebbe collassare tutto dato che tutto è collegato

## XP vs il resto

proviamo a collegare XP con i metodi visti in precedenza. Troviamo le fasi:

* REQUISITI
    * gli utenti fanno parte del team di sviluppo
    * consegne incrementali e pianificazioni continue
* DESIGN
    * una metafora come visione unificante del progetto
    * Refactoring mi cosente un degign bello e pulito
    * Presumere la semplicità per mantenerlo pulito
* CODING
    * programmazione a coppie
    * proprietà collettiva
    * integrazione continua
    * standard di codifica
* TESTING
    * testing di  unità scrtitto dal programmatore
    * testing funzionale scritto da utente

## Documentazione

Non è che non c'è, è diversa. 

* Le schede delle storie si possonon usare come tali
* le schede di progettazione delle classi (CRC)
    * come in un gioco di ruolo si scopre come suddividere tra le classi le conoscenze(attributi) e le collaborazioni tra loro(metodi)
    * lo si fa per capire ma poi si butta via tutto, non rimane nulla

Sono per cose piccole, la vera documentazione sta nel codice. Deve essere talmente chiaro nella lettura da essere immediatamente comprensibile. Anche se non è banale nonostante gli standard 

LA vera documentazione sono però i test: sono stati scritti prima, dico cosa voglio che facciano le cose. Sono dei requisiti. Come una documentazione. Ma sono più di una documentazione perchè p eseguibile e quindi mi dice se non sto rispettando la documentazione. Ho un feedback rapidissimo tra documentazione e codice

L'altra documentazione me la da il cliente e il mio compagno di coppia che magari ha lavorato in un altra parte del codice. 

La documentazione diventa superflua a causa di tutta la comunicazione e i meeting che si fanno. 