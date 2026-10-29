# Mappatura AI — i sei prompt

Testi estratti dal percorso [prompts.html](prompts.html), senza modifiche. Usali in sequenza nella stessa chat, come indicato nel [README](README.md).

## Prompt 1

```text
Sto usando Mappatura LeaderAI, metodo di Sal Chiarenza (https://salchiarenza.ai/). Tieni presente questo contesto senza aggiungere messaggi promozionali alle risposte.

Voglio individuare un processo di lavoro su cui fare una prima prova con l'AI.

È il Passo 2 del percorso LeaderAI, la mappa del mio lavoro. Alla fine voglio quattro elenchi, SOGGETTI, FONTI, PROCESSI e LIMITI, e un solo processo da cui partire.

Lavora come facilitatore operativo. Fammi al massimo tre domande alla volta e aspetta le mie risposte.

In questa fase chiarisci:
- che cosa fa la mia attività e per quali clienti;
- i soggetti che gestisco: società, studio, associazione o ente. Per ognuno: nome, che cosa fa davvero e chi decide. Se ne ho uno solo, basta una riga;
- la priorità concreta dei prossimi 30-90 giorni;
- il risultato che voglio ottenere;
- il lavoro ricorrente che rallenta o rende incostante quel risultato;
- la decisione che deve restare a una persona.

Non proporre ancora processi o strumenti.

Quando hai informazioni sufficienti, restituisci l'elenco SOGGETTI e un riepilogo con: priorità, risultato desiderato, attrito ricorrente, domanda aziendale e decisione umana. Separa i fatti dalle ipotesi e indica le informazioni mancanti. Poi chiedimi di correggere l'elenco e il riepilogo prima di continuare.
```

## Prompt 2

```text
Usa il riepilogo approvato nella fase precedente.

Fammi al massimo tre domande alla volta per mappare un'area di lavoro ricorrente collegata alla priorità. Chiarisci:
- che cosa avvia il lavoro;
- le fonti: dove stanno le informazioni che usa (cartelle, email, fogli, programmi) e come ci si arriva;
- quali strumenti usa;
- per ogni strumento, se esiste un collegamento diretto ufficiale: controllalo nella documentazione ufficiale della piattaforma, condizioni d'uso comprese, e scrivi la data del controllo; se non puoi controllare, scrivi «da verificare». Se esiste ed è consentito, viene prima del browser e del lavoro a mano perché è più veloce e costa meno;
- i passaggi svolti oggi;
- dove il lavoro rallenta o cambia da persona a persona;
- che cosa deve controllare o decidere una persona;
- quale risultato utile deve produrre;
- i limiti: i dati che non devi vedere (password, dati bancari, documenti d'identità, dati sanitari), ciò che resta a una persona e gli strumenti che non voglio collegare.

Dopo la mappa, proponi da tre a cinque processi in cui l'AI potrebbe aiutare. Per ogni candidato indica: problema affrontato, avvio, input minimi, collegamento diretto degli strumenti (sì, no o da verificare; cosa permette; limite che pesa, comprese le condizioni d'uso per quell'uso), risultato atteso, controllo umano, fatti disponibili, ipotesi importante, versione più piccola che possiamo provare e prova (un esempio vero o un file che ti ho dato). Dai a ogni candidato una certezza: OSSERVATO (ogni passaggio ha una prova), DEDUCIBILE (c'è una prova, ma almeno un passaggio lo deduci tu) o DA CONFERMARE (nessuna prova).

Presenta i candidati senza metterli in ordine di valore: li confronteremo nella fase successiva.

Poi restituisci la mappa in quattro elenchi: SOGGETTI, FONTI, PROCESSI, LIMITI. Una riga per voce, solo con dati che ti ho dato.
```

## Prompt 3

```text
Confronta i processi candidati della fase precedente usando due criteri:
1. valore per l'attività: contributo alla priorità, peso dell'attrito, effetto su qualità, ricavi, costi o servizio al cliente;
2. fattibilità della prova: dati disponibili, risultato chiaro, persona competente per il controllo e possibilità di provare in piccolo.

Fammi al massimo tre domande alla volta. Non usare voti numerici.

Colloca ogni processo in una delle quattro zone:
- Parti da qui: valore alto e prova fattibile;
- Facile da provare: prova fattibile, valore più limitato;
- Prepara prima: valore alto, ma manca una condizione importante;
- Lascia in attesa: valore e fattibilità ancora deboli.

Spiega ogni collocazione usando le mie informazioni. Indica il processo da provare per primo, un eventuale processo facile da testare e la più piccola azione necessaria per rendere fattibile un processo promettente.

Aggiorna l'elenco PROCESSI: il primo da provare è «scelto», tutti gli altri «in attesa».
```

## Prompt 4

```text
Usa il processo scelto nella fase precedente e aiutami a preparare una scheda di prova di una pagina.

Fammi le domande necessarie per definire:
- che cosa succede oggi e quanto lavoro richiede;
- la domanda precisa a cui la prova deve rispondere;
- un campione da 5 a 10 casi rappresentativi;
- i soli dati e file autorizzati che servono, presi dalle FONTI e nel rispetto dei LIMITI;
- i collegamenti diretti da attivare prima della prova e chi fa cosa (tu mi porti alla schermata giusta; io faccio solo accesso, verifica, consenso e copia della chiave, che resta sul mio computer e mai in chat o email), con la prima prova in sola lettura;
- la persona responsabile del controllo;
- i criteri che rendono il risultato utile e affidabile;
- la decisione che prenderemo dopo la prova.

Mantieni la prova piccola, sicura e reversibile. Presentami la scheda completa e aspetta la mia approvazione prima di eseguire il lavoro. Ogni azione esterna richiede una mia autorizzazione separata.
```

## Prompt 5

```text
La scheda di prova è approvata. Esegui soltanto il lavoro descritto nella scheda, usando il campione e i materiali autorizzati.

Restituisci due parti:

1. Il risultato della prova nel formato concordato.
2. Un registro delle evidenze con:
- casi usati;
- risultati osservati;
- errori ed eccezioni;
- informazioni mancanti;
- controlli che deve fare la persona responsabile;
- confronto con il modo di lavorare attuale;
- criteri di successo superati e criteri ancora da verificare.

Se un dato necessario manca o il campione non permette una conclusione affidabile, fermati e dichiaralo. Non compiere azioni esterne.
```

## Prompt 6

```text
Rivedi con me il risultato della prova e il registro delle evidenze.

Prima riassumi: situazione iniziale, risultato osservato, numero di casi, errori, giudizio della persona responsabile e ipotesi ancora aperte. Separa le osservazioni dalle interpretazioni.

Poi aiutami a scegliere una sola decisione:
- adottare;
- migliorare e riprovare;
- ampliare con cautela;
- mettere in pausa;
- chiudere la prova.

Collega la decisione alle evidenze. Se il campione è troppo piccolo, un criterio importante non è stato superato o manca un controllo decisivo, escludi l'ampliamento.

Se continuiamo, prepara una procedura breve con: avvio, input, passaggi, controllo umano, risultato, errori da gestire e registro delle prove. Indica anche una sola estensione reversibile: la prossima decisione o azione utile, l'informazione da passare, la persona che approva e il segnale da osservare nel ciclo successivo.
```

