Create un nuovo progetto utilizzando Vite e Vue 3 e definite i componenti necessari per strutturare il layout come da screenshot allegato.
// Creo i vari SFC (header, main, card-wrapper, card).

Al caricamento della pagina, effettuate una chiama ajax all'API di Yu Gi Oh: https://db.ygoprodeck.com/api/v7/cardinfo.php e con i dati restituiti, stampate una card per ogni carta.
// Con una funzione effettuo la chiamata ajax all'API e inserisco gli oggetti ricevuti in risposta in un array nel file store.js. Per ogni oggetto stampo una card con i dati necessari come da layout.

ATTENZIONE:
l’api restituisce tutti i risultati in un colpo solo.
Per evitare attese e/o rallentamenti nelle richieste, potete diminuire il numero di risultati sfruttando i parametri num e offset
https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0


Bonus:
Creare un componente loader da visualizzare fintantoché i risultati non sono pronti.
// Creo una variabile, settata su false, che diventa true una volta ricevuti i dati rischiesti. Se la variabile è false viene visualizzato il loader.


Aggiungete una select per filtrare i risultati in base all’archetipo.
Le option della select devono essere popolate dinamicamente chiamando questo endpoint dell'api:
https://db.ygoprodeck.com/api/v7/archetypes.php
Quando l'utente seleziona un valore dalla lista, viene effettuata una chiamata alle API con l'archetipo selezionato.


Bonus:
Creare un componente che mostri il numero totale di risultati ottenuti.

Nota:
Per capire come comunicare alle API le carte dell'archetipo che volete, è necessario fare riferimento alla documentazione che trovate qui:
https://ygoprodeck.com/api-guide/