---
author: Gabriele Zarcone
date: 8 maggio 2018
title: Design Pattern
---
---------------------------------------------

![](/Users/gabriele/Università/2 anno/2 semestre/ingegneria Software/APPUNTI ing. software/res/freccie.jpeg)

# Adapter

## Intento

Permette a due classi di lavorare insieme nonostante abbiano delle interfacce incompatibili. Converte l'interfaccia di una classe in un interfaccia utile al cliente.

Avvolge una classe esistenza ad una nuova interfaccia.

Se voglio utilizzare un componente non sviluppato da me questo avrà una certa interfaccia per interfacciarsi con l'esterno. Io probabilmente ho bisogno di un altro tipo di interfaccia per collegarlo al mio sistema. 

## Discussione

L'adapter crea una *astrazione intermedia* che traduce la classe da utilizzare in maniera comprensibile al nuovo sistema. 

Il cliente **richiama i metodi dell'oggetto Adapter** e la chaimata viene reindirizzata all'Adaptee. *Può essere creata sia con **AGGREGAZIONE** che con **EREDITARIETA'***

L'adapter avvolge una classe presistente e mi restituisce una traduzione di quest'ultima. 

## Struttura

![](/Users/gabriele/Università/2 anno/2 semestre/ingegneria Software/APPUNTI ing. software/res/adapter.png)

* Il client interagisce solo con l'interfaccia Target la quale implementa dei metodi che il client riconosce
* L'interfaccia poi viene implementata dalla classe Adapter che iplementa i metodi dell'interfaccia in modo che chiamino i metodi dell'Adaptee nella maniera corretta. 






-------------------------------------------------------------------