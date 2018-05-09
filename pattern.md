---
author: Gabriele Zarcone
date: 8 maggio 2018
title: Design Pattern
---
---------------------------------------------

<style>
    @import url('https://fonts.googleapis.com/css?family=Lobster|Muli');
    .titoliPattern {
        font-family:Lobster;
        color:#f72c44;
        font-size:500%;
        text-align: center;
    }
</style>

# UML

![](/Users/gabriele/Università/2\ anno/2\ semestre/ingegneria\ Software/APPUNTI\ ing.\ software/res/freccie.jpeg)

---

<h1 class="titoliPattern">Pattern Strutturali</h1>

# Adapter

[FONTE](https://sourcemaking.com/design_patterns/adapter)

## Intento

Permette a due classi di lavorare insieme nonostante abbiano delle interfacce incompatibili. Converte l'interfaccia di una classe in un interfaccia utile al cliente.

Avvolge una classe esistenza ad una nuova interfaccia.

Se voglio utilizzare un componente non sviluppato da me questo avrà una certa interfaccia per interfacciarsi con l'esterno. Io probabilmente ho bisogno di un altro tipo di interfaccia per collegarlo al mio sistema. 

## Discussione

L'adapter crea una *astrazione intermedia* che traduce la classe da utilizzare in maniera comprensibile al nuovo sistema. 

Il cliente **richiama i metodi dell'oggetto Adapter** e la chaimata viene reindirizzata all'Adaptee. *Può essere creata sia con **AGGREGAZIONE** che con **EREDITARIETA'***

L'adapter avvolge una classe presistente e mi restituisce una traduzione di quest'ultima. 


## Struttura

![](/Users/gabriele/Università/2\ anno/2\ semestre/ingegneria\ Software/APPUNTI\ ing.\ software/res/adapter.png)

* Il client interagisce solo con l'interfaccia Target la quale implementa dei metodi che il client riconosce
* L'interfaccia poi viene implementata dalla classe Adapter che iplementa i metodi dell'interfaccia in modo che chiamino i metodi dell'Adaptee nella maniera corretta. 

## Come implementarlo

1. **Identifica i soggetti**: identificare qual'è il Client e chi è l'Adaptee.

2. **Identifica l'interfaccia**: capire qual'è l'interfaccia di cui ha bisogno il Client.

3. **Creare la classe Adapter** che implementa l'interfaccia e i suoi metodi chiamando i metodi dell'Adaptee

4. Per farlo la classe Adapter deve avere il metodo della classe Adaptee

## Differenze con altri pattern

* con Bridge..

* con Bridge..

* con Proxy

* L'Adapter cambia l'interfaccia di un oggetto esistente, mentre il **Decorator** amplia un dato oggetto senza modificarne l'interfaccia. Per questo motivo l'Adapter è più trasparente all'utente che non l'Adapter e per questo il Decorator permette la composizione ricorsiva e l'Adapter no. 

* **Facade** definisce una nuova interfaccia, mentre l'Adapter riusa una vecchia interfaccia. L'adapter fa in modo che due interfaccie esistenti lavorino insieme piuttosto che crearne una tutta nuova. 


---

# Composite

[FONTE](https://sourcemaking.com/design_patterns/composite)

## Intento

Serve per comporre oggetti dentro a delle strutture ad albero. Permette così di trattare insiemi di oggetti dello stesso tipo come se fossero un oggetto singolo. 

Puo essere ricorsivo e quindi una Directory contiene Entità ma ogni Entità può essere una Directory. 

La gestione di una Directory e di una Entità sarà sicuramente diversa, ma con il composite rendiamo questa differenza trasparente al Client che potrà trattare il gruppo come il singolo. 

## Discussione

Creo una *classe astratta* **Component** che specifica il comportamento che voglio implementare (sia che l'oggetto sia singolo o un gruppo di oggetti). Le classi che rappresentano l'oggetto singolo(**Leaf**) e il gruppo(**Composite**) saranno *figli* della classe Component.

L'oggetto Composite può poi associare un altro oggetto Component. 

Il pattern va quindi usato ogni volta che:

> Ho un Composite che contienen un Component che può essere a sua volta un component.

Quando ho bisgno di una struttura come quella delle cartelle sul PC




## Struttura

![](/Users/gabriele/Università/2\ anno/2\ semestre/ingegneria\ Software/APPUNTI\ ing.\ software/res/composite.png)

 

## Come implementarlo

1. Assicurarsi che si vuole rappresentare una intera relazione gerarchica.

2. Considerando il "Contenitori che contengono contenuti i quali a loro volta possono essere contenitori" e dividere i contenuti dai contenitori. 

3. Creare l'interfaccia che rende intercambiabile i contenuti con i contenitori. Che specifichi il comportamento che deve essere esercitato in modo uguale su Container o Continee

4.  **Container** e **Continee** sono in una relazione *is a* con l'interfaccia

5. I **Container**  sono in una relazione *has a* 1aMOLTI con l'interfaccia

6.  Le classi di contenitori sfruttano il polimorfismo per delegare ai propri oggetti contenitori.

7. I metodi `addChild()` e `removeChild()` avrebbe più senso averli nella classe Component se vogliamo la trasparenza, quindi trattare uniformamente Leaf e Composite. Vengono invece inseriti nella classe Component. Sacrificando la *trasparenza* per la *sicurezza* (spiegato nelle Osservazioni)

## Differenze con altri pattern

* Il composite e il **Decorator** hanno una struttura simile perchè entrambi usano la composizione ricorsiva per organizzare un numero illimitato di oggetti

*  (?) Composite can be traversed with Iterator. Visitor can apply an operation over a Composite. Composite could use Chain of Responsibility to let components access global properties through their parent. It could also use Decorator to override these properties on parts of the composition. It could use Observer to tie one object structure to another and State to let a component change its behavior as its state changes.

*  Mediator ...

*  Composite e **Decorator** spesso vengono usati insieme perchè i loro usi sono complementari: 
    *  Decorator aggiunge caratteristiche agli oggetti senza ricorrere all'ereditarietà
    *  Composite si focalizza di più sulla rappresentazione che non sull'abbellimento

* Spesso si usa il Composite insieme al **FlyWeight** per implementare delle foglie condivise. 

## Considerazioni

Il punto principale del pettern Composite è quello di poter trattare il *gruppo* (COmposite) come se fosse un singolo (Leaf). Si può ottenere similmente anche con un Iterator ma sarebbe una forzatura dello stesso. 

> Grazie al Composite il client può effettuare operazioni su un oggetto senza che sappia che quell'oggetto è composto da più oggetti. 

Può però trattare un insieme di oggetti eterogeneo in maniera **atomica** (o trasparente) solamente se la gestione dei figli viene gestita dall'interfaccia Component così che Leaf e Composite siano trattabili allo stesso modo. Però questo porta ad un problema di **Sicurezza** in quanto l'utente vede solo l'interfaccia Component e in questo modo si permettee al client di creare o cancellare figli. Quindi per aumentare la sicurezza si preferisce lasciare la implementazione dei metodi per la gestione dei figli alla classe Composite. Sacrificando la trasparenza per la sicurezza. Non ho più trasparenza perchè ora Composite può avere diverse interfacce

...da completare...

---

# Decorator

[FONTE](https://sourcemaking.com/design_patterns/decorator)

## Intento

Vuole aggiungere delle funzionalità ad un ogggetto anche **dinamicamente** e lo fa senza ricorrere all'utilizzo di *sottoclassi*. Un componente può essere abbellito da un altro avvolgendolo ricorsivamente.

> "*Incarta un regalo, mettilo in una scatola e quindi incarta anche quella*"

Voglio quindi aggiungere un comportamento o uno stato in *run-time*. Però per farlo non posso usare la ereditarietà perchè non è dinamica ma statica. 

## Discussione

Se lo facessimo con un gerarchia di *ereditarietà* non diamo all'utente la possibilità di scegliere lui la combinazione di abbellimenti da mettere alla classe ma sarebbe forzato ad usare solamente uno dei figli. Se volessimo permettere tutte le combinazioni avremmo il numero di classi che crescerebbe esponenzioalmente. La struttura definità dal pattern è dunque essenziale. 

## Struttura

![](/Users/gabriele/Università/2\ anno/2\ semestre/ingegneria\ Software/APPUNTI\ ing.\ software/res/decorator.png)

 

## Come implementarlo

1. 

2. 

3. 

4.  

5. 

6.  

7. 

## Differenze con altri pattern

## Considerazioni



---





-------------------------------------------------------------------