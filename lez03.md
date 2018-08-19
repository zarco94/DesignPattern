---
author: Gabriele Zarcone
date: Lezione 3
title: Processi - Processo di produzione del software
---
---------------------------------------------

I modelli possono essere prescrittivi o descrittivi: 

* prescrittivi: ti dicono esattamente cosa devi fare, e sono spesso messi in discussione perchè non sempre si adattano
* descrittivi: sono più generici e vogliono mettere attenzione su alcuni concetti principali e su delle problematiche precise. E' più generico e applicabile a più aspetti. 

## Problemi del modello a cascata 

> leprechauns of software engineering
    >   parla dei miti della software engineering che sono per tutti veri ma che non sono veri però

Inizialmente il modello a cascata non era così rigido, e diceva che potevano esserci dei problemi facendo così. Ci sono alcune modalità del modello a cascata che potrebbero funzionare.

# Varianti del modello a cascata

## Singola retroazione

Posso tronare in dieetro di un passo solamente. Posso così però anche così tornare indietro di n passi. 

Perdo una caratteristica positiva del modello a cascata di sapere cosa ho finito e i tempi che mi mancano. Cosa che però non avevo nenache prima perchè se dovevo fare una patch comunque ci tronavo indietro. 

E' un modello iterativo, posso iterare tra le diverse fasi, passo da una fase all'altra come voglio. Iterativo perchè sto mantenendo una consegna monolitica, ad un certo punto dico: "ok ho finito, consegno!"

Il contrario di iterativo è **incrementale**, e cioè quando arrivano al cliente diverse versioni del software man mano fatte meglio

# Modello a fontana

Modello incrementale

Ho l'acqua e una pompa che la spinge verso l'alto. Si creano degli zampilli di diversa altezza che possono ricadere in basso. Ogni zampillo è una fase e se c'è un errore ritorno da zero (=! ricominciare tutto)  così da ricontrollare tutto così da considerare ogni fase se viene intaccata dall'errore. Vedo se l'errore ha un impatto su tutte le fasi precedenti. E' un modello a cascata con il daccapo. 

Quando ricado però non è detto che io ritorni alla stessa altezza di prima, potrei ancora fermarmi prima perchè trovo un altro errore e ricomincio da capo.

Attenzione: daccapo = porsi la domanda se quella fase è apposto e non rifare tutte le fasi.

Quando consegno il programma è in uso e ho ancora due zampilli:

* manutenzione
* evoluzione

per il modello a fontana questi due sono come gli errori: torni indietro, ma separa la correzzione evolutiva da quella di manutenzione. Quando arrivo in cima alla cascata ho ottenuto 1 incremento del modello **incrementale**

E' una fontana di acqua in movimento, non si ferma mai. Quindi non arrivo mai ad una fine, o evoleve o viene corretto. se spengo la pompa(lo sviluppatore) il progetto muore, dopo anni magari ma muore

## Implementazione Iterativa

Stessa la modularizzazione e l'identificazione di sottosistemi e si ripetono fasi di coding e integrazione

## Implementazione Incrementale

Invece di tagliare orizontalmente taglio verticalmente, e consegno poco di tutte le parti del software (es. db, interfaccia utente, server..)

E' positivo perchè:

* inizio a dare all'utente già qualcosa
* se finiscono i soldi ho comunque qualcosa di consegnabile (motivo di fallimento dei progetti cascata anni 70)
* utente mi fa da tester nella versione precedente

é come se il modello a cascata venga eseguito ad ogni incremento. Faccio tanti piccoli modelli a cascata. 

Sparisce il concetto di manutenzione, la si fa in automatico. 

> NB si parla di incrementale quando nelle specifiche viene inclusa la consegna. 

# Modello Prototipale

è un modello particolare, diverso dagli altri che analizzeremo. 

Creo un prototipo del progetto prima di fare il progetto vero e proprio. Lo faccio velocemente e approssimativamente così da capire bene il problema e le varie problematiche che si possono affrontare e poi buttare via tutto e farlo con i dettami dell'ingegneria del software. 

Il pericolo principale però è che il cliente a volte vorrebbe prendere il prototipo funzionante e pagare per quello. Ma quello è un lavoro pessimo che sicuramente avrà bisogno di una manutenzione enorme perchè non ha fondamenta. 

> Non cedere alle tentazioni del cliente ;) 

## Prototipi esterni

Posso fare il prototipo anche per capire se ho capito bene le necessit del cliente e posso far vedere al cliente cosa voglio fare. 

## Prototipi inteni (testbed o progetti pilota)

Prototipi fatti per testare un altro ambito o che serve a me. Sono cose solitamente che so fare bene e velocemente che mi servono come sostegno per il vero progetto. 


# Problemi modelli incrementali

* viene complicato il lavoro di planning 
    * non posso dare delle deadline perchè posso tornare indietro
* Devo ipotizzare tutte le iterazioni
    * mentre prima dovevo pianificare solamente la singola consegna
* Potrei non arrivare mai a finire
    * il cliente potrebbe aumentare le richieste quando vuole
* cos'è un iterazione? quanto dura?
    * decidere i tagli verticali non è facile, devi avere un allenamento mentale
    * rischio di mettere troppo nella prima iterazione
    * (overlapping)non è detto che l'iterazione successiva inizi dopo la consegna dell'iterazione precedente. Sto lavorando ad una evoluzione di una cosa che ancora non è stata rilasciata
    * perdo più tempo ad organizzarmi che non a scrivere codice

# Modello flipper

ogni fase è un muro rimbalzante. Ho il potere di decidere in che direzione va la pallina, ma una volta che colpisce il muro non so cosa succede, potrebbe succedere qualsiasi cosa. Ogni tanto posso dare un colpo anche io ma non so prevedere nulla.

Non è quindi misurabile quando finirò

# Modello trasformazionale

è l'opposto di quello pessimista del flipper. 

si cerca di ragionare su rappresentazioni formali del problema e che non sono ambigui (per esempio il linguaggio di progr che uso). 

Parto quidni dalla definizione di specifiche **formali** di modo che non sono fraintendibili e che comprnedano tutte le cose principali che so per certo che non cambieranno. 

Trasformo allora le mie specifiche in altre specifiche più formali in linguaggio di programmazione e ad ogni passo mi avvicino sempre di più al programma finale. 

Mi limito quindi in quello che posso scrivere di modo che ogni trasformazione sia perfetta e corretta.

> **Ogni trasformazione deveessere dimostrata come corretta**

Si usa ancora infatti per cose molto delicate (es centrali nucleari) perchè usa dei metodi formali che possono essere verificati formalemente e quindi avere la certezza al 100% la correttezza. E spesso nei programmi si usa questo metodo solo per alcune parti del programma. Per esempio invece di fare tutto il sistema operativo in questa maniera faccio solo il kernel così. Di modo che il kernel è sicuramente funzionante e perfetto. 

# Modello a Spirale

è più un metamodello che non un modello, posso rimappare gli altri modelli all'interno di questo 

E' guidato dall'analisi dei rischi. All'inizio non conosci tutti i rischi, sicuramente ne saltano fuori di nuovi. 

Cambiano i nomi delle fasi:

* determinazione degli obbiettivi, alternative e vincoli
* valutazione alternative, identificazioni rischi
* Sviluppo e verifica
* Pianificazione fase successiva

Spirale perchè ho i queattro quadranti delle quattro fasi e continuo iterativamente e incrementalmente attraverso tutte e quattro formando un cerchio

Il cerchio però diventa una spirale perchè i raggio aumenta ogni volta che spendo soldi per questo progetto. Più tempo passa più la spirale si allarga. 

Mi chiedo ogni tot se convine andare avanti con la valutazione dei rischi. 

# Modello win win

evoluzione del modello a spirale, non ho solo 4 quadranti ma ne ho 7. Allargo la parte di analisi dei rischi. 

# Modello COTS

Parto dai componenti che ho già sviluppato in azienda o che trovo da qualcun altro. Magari mi costa di meno comprare una parte che non svilupparla da me (es lo schermo samsung sui telefoni apple). 

Ho però nuovi probelemi: 

* Come faccio a trovare le cose che mi servono?
* MI serve un metodo per classificare i moduli
* retrieval dei moduli
* non troverò sicuramente esattamente quello che voglio: devo scegliere tra le diverse possibilità quello che assomiglia di più

Devo allora cambire le fasi, devo ricontrattare con il cliente in base a quello che ho trovato. 

E devo soprattutto incollare i componenti che non sono stati pensati per stare insieme. 

# Metodi Agili (Extreme Programming)

i modelli precedenti erano modelli descrittivi ed accademici che venivano applicati in azienda ma pensati in università. I metodi  agili invece nascono da team di sviluppo software come soluzione ai loro problemi. Contemporaneamente quindi diversi gruppi di persone arrivano a questi metodi diversi con elementi comuni. Fanno attraverso internet il **manifesto dei metodi agili** [link](http://agilemanifesto.org)

Definiscono: 

* **Individui e interazioni** prima di processi e tool
    * il team ha un valore altissimo per loro. Il team si autoorganizza
* Diamo più valore ad un **software funzionante** che non ad una documentazione enorme
* **Collaborazione con l'utente** invece che negoziazione con l'utente
* **Prodotti responsivi al cambiamento** piuttosto che seguire un piano
    * non è possibile per loiro concelare le cose. E' la cosa che più accomuna tutte queste tipologie. 

C'è in più anche uno spirito all'automiglioramento e quindi cercare un modo per accettare i problemi. Ciclicamente fanno delle retrospettive in cui si parla tutti insieme dei problemi di quello che è successo in quel periodo per migliorare se stessi e il team. Hanno voglia sempre di migliorare e rendere più fine e migliore il loro lavoro. 

Spesso però non c'è uno studio scientifico sul fatto che questi metodi funzionano, si sa empericamnete che spesso funzionano bene. Ma non c'è la sicurezza scientifici. Le loro cose però non sono cose completamente nuove, sono delle cose usate in vari altri metodi. Il loro pregio e averli messi tutti insieme. Questi elementi (es programmaz a coppie) hanno elementi positivi e negativi. Mettendo tutto insieme probabilmente sono riusciti a diminuire le cose negative. 

Libro: 
> Agile! Bertrand Meyer

non c'è una letteratura e quindi ha fatto una ricerca su tutto quello che c'è in giro, analizzando 4 o 5 metodi agile. 

## Lean Software

nasce nell'ambito industriale. Veniva usato dalla toyota. 

> Reduce waste

la sua prerogativa principale è quella di ridurre lo spreco. La toyota produce su ordinazione e non parcheggi nei magazzini le macchine evitando gli sprechi lasciando lì le macchine. Non colorano la carrozzerie finche il cliente non decide. Ritardando il più possibile le scelte che mmi bloccano altre possibilità, avere iterazioni molto brevi ecc..

Nell'ambito software voglio progettare in modo da poter cambiare ogni cosa in qualsiasi momento. 

## Kanbam

anche lui toyota

> Minimize Work in Progress

è più facile preparare un esame in 2 settimane che 3 in un mese. Mi serve tempo per fare il context switch. 

Minimizzo i cambi di processi, finchè uno non finisce non cambia lavoro. MI concentro su una cosa sola. Se tu finisci e un altro ancora non ha finito lo vai ad aiutare. 

Ci sono delle lavagne magnetiche con i postit delle cose da fae e delle cose che gli altri dstanno facendo in quel momento

## Scrum

> Freeze Requirements during short iteration

è la mischia del rugby. Tutti insieme per un brevissimo lasso di tempo concentranno tutte le energie per dare una spinta. é come se si congelasse tutto per pochissimo porto a termine l'obbiettivo. Risolvo così la volatilità delle decisioni del cliente. In quel periodo il cliente non può dire nulla, dopo quel periodo può rimettere in gioco qualsiasi cosa. Ho butato via tempo, ma ci sarà un motivo per il queale il cliente ha cambiato idea, ma il cliente con questo metodo mi paga a tempo e non a progetto finito. Io lavoro al massimo, poi se lui cambia idea fa nulla, anzi meglio. E in più in quel periodo di tempo congelato mi metterò a fare le cose che sono sicuro che il cliente non cambierà. 

## Crystal

> Osmotic Comunication

quando si lavora in team il problema è la comunicazione nel team. FIno ad adesso abbiamo congelato le cose di modo da non dover comunicare continuamente, faccio vedere solo delle interfacce. E con questi posso usare dei team molto grandi. 

Con i team agili però funzioano meglio dei team piccoli. 41:38

## Extreme Programming

> Increment then semplify

si parla di TDD (Test driven development): che è una tecnica di progettazione che guida verso il design più semplice che mi porta a svolgere il mio compito. Ho un obbiettivo devo trovare il moodo più semplice a cui arrivarci. 

Fatto da due concetti:

* test first
    * prima di scrivere il codice scrivo il test. Il test di qualcosa che non c'è, ma quello che dovrò scrivere deve passare quel test. Così so cosa devo scrivere. 
* baby step
    * ognuno di questi passaggi deve essere piccolo  per arrivare alla fine (in 2-10 minuti). Quindi devo avere obbiettivi molto piccoli 

1. All'inizio devo avere il semaforo rosso: devo fare un **test** che non passa
2. scrivo codice che **passa il test** (semaforo verde) nel modo più semplice e veloce possibile
3. faccio **refactoring**: rendo più bello il codice, più leggibile ecc.
    * viene fatto separatamente dalla scrittura del codice, così che mi ci concentro dopo. (estrapolare funzioni, nomi variabili, repeat once ecc...)

L'obbiettivo è quello di fare un design semplice di volta in volta. E in più avendo dei cicli brevi ho una continuo feedback. E i test rimangono lì, quindi ogni nuova feature anche i test vecchi verificheranno le parti nuove. Ma non è un metodo di test ma un metodo per avere un buon design. Faccio design anche quando scrivo il test perchè mi metto nei panni di chi lo deve usare il componente. E in più in questo modo il design supporterà il testing quando dovrò fare la parte di testing: perchè p stato pensato per essere testabile, cosa che di solito non succede. 

> LIBRO: how google test software