fx2048
======


*Pr2 Project 2014*

*Francesca Trudu* -
*Fulgheri Nadia Jolanda*

Modifica dell'implementazione del gioco 2048 in modo da permettere, opzionalmente, di giocare autonomamente con un giocatore automatico. 



Strumenti utilizzati:

git - distributed version control system


*Game2048.java*
classe contenente il main e il metodo start.
Implementa le funzioni e le variabili che si occupano di inizializzare e gestire l interfaccia grafica,
da qui viene inizializzato anche un oggetto di tipo GameManager che si occupa di tutte le funzioni di gestione del gioco: 
-i meccanismi di somma e spostamento delle caselle, 
-aggiornamento della griglia (a livello grafico), 
-aggiornamento dello score, 
-conclusione del gioco in caso di game over e vittoria del gioco.


Modifiche effettuate:
-aggiunta del package giocatoreAutomatico (e giocatoreAutomatico.player);
-aggiunta delle classi implementate dalle interfacce.

aggiunta di 3 variabili in GameManager -> boolean: gameOver e gameWon pubbliche e Griglia: myGriglia che viene aggiornata in base alla situazione del gioco


aggiunta di variabili , ascoltatore e Thread in Game2048 -> 
giocatoreAutomatico: viene creato un oggetto giocatoreAutomatico tramite il suo metodo; 
button per attivare il giocatore automatico e conseguente azione che crea un Thread permettendo di simulare la pressione del tasto H tramite un oggetto di tipo Robot, evento che viene catturato da un ascoltatore apposito addBtnClicked che implementa l'azione da eseguire: 
chiamata al metodo del giocatoreAutomatico prossimaMossa che restituisce un int random da 0 a 3, switch nel valore int con conseguente creazione di un valore Direction che viene passato al metodo move() del GameManager che si occupa di gestire tutto il procedimento del movimento di una casella e le sue conseguenze. 
Finchè non si ha il gameOver (e anche il gameWon) il Robot continua a premere H e ogni volta l'ascoltatore intercetta l evento permettendo l esecuzione del gioco in autonomia.












