---
author: Gabriele Zarcone
date: 
title: Processi - Qualità del software
---
---------------------------------------------

# Perchè studiare un processo?

definisco un processo che se applicato in maniera rigorosa mi garantisce un prodotto di qualità. Se applico un processo di qualità devo ottenere un prodotto di qualità

## Qualità

Ci sono delle qualità che cerchiamo in un software. 

Potrei dire che un prodotto di qualità sia uno che: 

* che funzioni
* che sia bello
* che mi faccia guadagnare

ma cosa vuol dire "che funziona"? Potrei dire che fa quello che le è stato chiesto. Ma quello che ci è stato chiesto ci è stato chiesto in maniera chiara? Il dialogo con il nostro cliente avviene attraverso delle richieste del cliente. Le richieste le inseriamo nelle specifiche che diventa poi il contratto con il mio cliente. 

## Che Funzioni

### Correttezza

Quindi un programma diventa **corretto** se è conforme con le sue specifiche

### Affidabilità
Le specifiche però devono essere corrette. C'è un altro termine di paragone: quello che aveva in mente il cliente. Il termine si può **fidare** del programma? 

Sono due concetti differenti o la correttezza e affidibilità uno implica l'altra?

Affidabilità: il cliente usa quel software perchè si fida che il software gli darà il risultato giusto. Ma un software non corretto può essere affidabile. Per esempio su una macchina la spia della benzina. Le specifiche dicono: quando l'automia della macchian è inferiore ai 10 km accendi la spia. Lo sviluppo però non è corretto e non fa il calcolo giusto. L'errore può portare a due effetti: 

1. accendere la spia quando sono già a secco
2. accendere la spia quando mancano 9 km

la seconda è accettabile perchè è affidabile per il cliente anche se non è corretto per le specifiche. Nache Word non è infallibile e crasha a volte, ma lo continuiamo ad usare perchè ha una affidabilità alta.

L'affidabilità però è difficile da misurare. Perchè dipende dall'utente e non da qualcosa di preciso. é qualcosa che va chiesta all'utente per suo valore intrinsico.

#### Verifica e Convalida

* Verifica: verifica se il programma è corretto (correttezza)
* Convalida: convalida le aspettative dell'utente (affidabilità)

### Innoquità (safety)

qualunque cosa succede non fa danni. Sono sempre capace di tornare ad uno stato sicuro senza fare danni

### Robustezza

è un software che sopravvive a cose che non erano state previste, fa altre cose oltre a quelle richiesste nelle specifiche che controllano e gestiscono i comportamenti anomali. Ad esempio se mi mettono un char al posto di un int. Cosa fa? si lamenta? Crasha?

Capita spesso che ci siano delle mancanze nelle specifiche e causano spesso il fallimento del progetto. 

## Che sia bello

bello all'interno o all'esterno?

* interno = visibile allo sviluppatore
* esterno = visibile al cliente

### Facile da usare

fino ad adesso abbiamo parlatop di cose visibili al cliente. Ma la bellezza è quella ancora più chiaramente visibile da fuori. Per il cliente è bello ciò che è facile da usare, senza che se ne accorga alle volte (trasparente). Una cosa che è molto facile ottenere quello per cui è fatto il programma. Si parla di **usabilità**

Sembra essere una cosa totalmente soggettiva, per alcuni una cosa comoda potyrebbe non esserlo per un altro. Devo decidere la ccategoria di utenti a cui mi riferisco, o a tutte. I prodotti microsoft posso usare molti modi per farel a stessa cosa (tendina, scorciatoia, telepatia..). 

Come faccio a capire se un programma è poiù usabile di un altro? Si fanno una serie di esperimenti non controllati con molte persone con la richiesta disvolgere una serie di task senza manuale e si guarda quanti di questi clienti potenziali riescono a farlo, in quanto tempo, la frequenza degli errori. Vengono obbligati ad esplicitare il loro flusso di pensieri e con una telecare si guarda l'espressione del volto e la sua emozione e si guarda dove vanno gli occhi con l'eye-tracking. 

> Libro: Nielsen-Norman dice che la "Usabilità è quantificabile"

### Veloce

un programma più veloce è anche più bello. Si parla di **efficenza**. Efficenza si intende sia come tempo di esecuzione come anche di spazio di memoria occupata sul dispositivo. e' già qualcosa ddi molto poco visibile dall'utente. Sp3sso è un gioco mentle dello sviluppatore. è un problema chge ci si pone solamente in casi macroscopici. Se ho dei grandi numeri ha senso ragionarci, altrimenti no. Sarà meno importante.

La velo9cità si misura in 3 modi:

* empiricamente con un timer (profiling)
    * mi aiuta a vedere quali sono le istruzioniinn cui ho il collo di bottiglia e perdo tempo
* studio la complessità dell'algoritmo 
    * per capire come cresce al crescere delle info
* simulazione
    * astraggo il mio programma di modo da far saltare fuori i colli di bottiglia

### Pulito

la più iterna delle qualità. si parla di **verificabilità.** quando è facile testarla, modificarlo, trovare gli errori, capire cosa fa ecc...

Se voglio perseguire la verificab. devo perseguire la riscrittura e la pulizia del codice. Può essere una caratteristica esterna se l'utente nelle specifiche mi chiede di dimostrargli che funziona. 

## Che mi faccia guadagnare

### Riusabilità dei componenti

Non rifare qualcosa che sia già fatto. Ho scritto un componente per un altro progetto in modo da poterlo riiusare neglia ltri progetti. Mi faccio pagare lo stesso valore del primo progetto avendo però lavorato meno e avendo il tempo per fare più lavori insieme. Ho anche maggiore affidabilità pèerchè quel componente l'ho già usato e soprattutto l'ho già testato! Non deevo più usare il tempo per testarlo. Bisogna però stare attenti. esempio il fallimento dell'arian 5. Avevano usato dei compoinenti software dell'arian 4 che però non sopportavano delle velocità così elevate come quelle dell'arian 5 e andava in overflow. Un componente che funzionava benissimo sull'arian 4. Ma l'arian 5 aveva una caratteristiche diverse rispetto all'arian 4. Non era stato progettato per essere trasportabile e in più non era stato testato per l'arian 5. C'è stato un errore di comunicazione tra team di anni diversi.

### Manutenabilità

 Semplificare gli interventi post consegna. Tutto quello che devo fare dopo  la consegna del prodotto deve essere semplice e veloce da fare. perchè solitamente mi viene chiesto gratis. Non è più sviluppo, quindi non è pagato. 
 
 #### Cosè la manutenabilità? 

 è qualcosa che ogni parte del programma è accessibile senza dover toccare le atre parti. Poter toccare le varie parti del mio programma senza toccare le altre. e in più saèere quali sono le cose da toccare. Qualunque errore so quale parte del programma andare a guardare. Accedere ad una parte di codice che svolge quel compito. Deve esserre modulare. 

 è collegata alla 
 
 * riparabilità: correzione di errori
 * evolvibilità: possibilità di aggiungere le feature
 * adattamento a nueve situazioni (es sito mobile)

Un sitema che si evolve tende a diventare più complesso e ad aumentare la sua entropia. Se voglio mantenerlo smeplice devo fare uno sforzo in più. 

# Come deve essere un processo?

Come cognugo i tre punti precedenti?

* Robustezza al cambiamento dei requisiti (funziona)
    * i requisiti non devono cambiare 
    * il  mio sviluppatore si dimette il processo deve poter continuare
* Produttività (veloce)
    * uno dei costi è il tempo che lo sviluppatore ci mette, forse l'unico costo.
* Tempismo (diventare ricco) 
    * se faccio un word adesso non ha senso investirci
    * è meglio arrivare al tempo giusto con una idea piuttosto che averla sviluppata

FINE

---




