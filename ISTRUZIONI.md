# La mini guida agli agenti di Anthropic

## Per te, una riga

Incolla in Claude Code, nella cartella del tuo lavoro: «Scarica questo documento in un file temporaneo e leggilo integralmente dal file, incluse tutte le schede di esempio e le prove: https://raw.githubusercontent.com/salChiarenza/ecosistema-ai-gratuito/main/ISTRUZIONI.md. Usa il testo completo, senza sostituirlo con un riassunto o un’anteprima. Poi completa un lavoro che ripeto con gli agenti necessari, coordinandoli e verificando il risultato. Parti dai miei materiali; chiedimi solo ciò che manca.»

## Istruzioni per la tua AI

### Missione

Completa un primo lavoro della persona: scegli dai suoi materiali un risultato utile, crea soltanto gli specialisti necessari e prova ciò che consegnano. Ogni agente ha un solo mestiere, istruzioni salvate e limiti precisi. Comincia da un agente; quando servono due mestieri, coordinali come nel passo 5.

Questa è la mini guida pratica di Sal, ispirata al workshop Anthropic [Ship your first Managed Agent](https://www.youtube.com/watch?v=19HDQ9HppOA). Il workshop costruisce con codice un agente che indaga incidenti tecnici. Qui applichiamo l'idea al lavoro aziendale e facciamo scrivere i file a Claude, in italiano. Gli esempi aziendali sotto sono un adattamento di Sal.

Il percorso di squadra adatta anche il [sistema di ricerca multi-agente di Anthropic](https://www.anthropic.com/engineering/multi-agent-research-system): un coordinatore divide il lavoro, affida incarichi precisi e raccoglie i risultati. Qui lo applichiamo a una call aziendale, con i subagenti di Claude Code.

Il **Centro di Comando** è la sessione principale: riceve l'obiettivo, affida gli incarichi e controlla il risultato. L'**Ecosistema** comprende i documenti e gli strumenti disponibili. Gli **agenti** sono gli specialisti richiamati come subagenti di Claude Code. In questo percorso li avvia tutti il coordinatore; gli specialisti non delegano a loro volta.

Scrivere «sei un esperto» in chat serve a provare un incarico. Per questa guida il risultato completo richiede anche una scheda salvata e una delega effettiva all'agente.

### Passi

#### Prima di cominciare: verifica dove puoi lavorare

Il percorso completo usa **Claude Code**, anche nella scheda **Code/Codice dell'app desktop**, con un account abilitato e accesso alla cartella scelta. «Senza codice» significa che la persona descrive il lavoro; Claude prepara i file necessari.

Controlla l'ambiente, la cartella e la possibilità di leggere e scrivere. Leggi le istruzioni già presenti, incluso `CLAUDE.md`, e la configurazione prima di aggiungerne. Conserva regole, permessi e schede esistenti; riusa uno specialista adatto senza sovrascriverlo. Se mancano accessi o autenticazione, guida la persona al solo passaggio necessario usando la [guida ufficiale di avvio](https://code.claude.com/docs/en/desktop-quickstart).

Se sei nella sola chat, puoi preparare l'incarico e provarlo sui materiali allegati. Dichiara «istruzioni pronte, agente da attivare in Claude Code»; conserva il lavoro utile per proseguire. Se il documento non si apre, chiedi di allegarlo o incollarne il testo.

#### 1. Scegli un mestiere e un risultato

Frase di avvio: **«Individua un lavoro che ripeto e trasformalo in un incarico per un agente. Dimmi cosa riceve, cosa consegna e come capiamo che ha lavorato bene.»**

Usa i materiali disponibili. Se il lavoro non emerge, chiedi: «Quale attività ripeti ogni settimana e vorresti delegare?»

Ecco quattro esempi tra cui scegliere. Sono proposte di applicazione, ognuna con un confine preciso.

| Area e agente | Materiali da leggere | Incarico pronto | Prova del risultato |
|---|---|---|---|
| Commerciale — Preparatore di follow-up | Appunti della call, richiesta del cliente, offerta approvata | Estrai gli impegni espliciti e prepara una bozza di seguito con un solo prossimo passo. Cita l'appunto da cui viene ogni impegno. Lascia da confermare prezzi o date assenti. | Ogni dettaglio fattuale ha una fonte; destinatario e bozza sono visibili; nessuna email inviata. |
| Amministrazione — Lettore delle scadenze | Documenti e avvisi con date esplicite | Elenca scadenza, adempimento, soggetto e documento di origine. Segnala date contraddittorie. Limita il lavoro all'estrazione: il caso fiscale va al professionista. | Ogni data si ritrova nel documento; nessuna scadenza dedotta, pagamento o invio. |
| Marketing — Analista delle richieste dal sito | Visite e contatti degli stessi periodi, testo della pagina se disponibile | Calcola l'andamento, separa dati e ipotesi e indica la prossima verifica. | Calcoli riproducibili; nessuna causa inventata; pagina invariata. |
| Operatività — Riordinatore degli impegni di una riunione | Verbale o trascrizione | Estrai attività, responsabile e scadenza. Scrivi «da confermare» dove mancano; conserva la frase di origine. | Nessuna attività persa o assegnata per supposizione; nessun appuntamento creato. |

Scegli quello coerente con il lavoro della persona. Completa materiali, incarico e prova del risultato prima di costruirlo.

#### 2. Salva la scheda dell'agente

Frase di avvio: **«Crea un agente dedicato a questo incarico nella cartella di lavoro. Conserva le regole che esistono già e spiegami dove hai salvato la sua scheda.»**

In Claude Code le definizioni del progetto vivono in `.claude/agents/`. Ogni file contiene un nome, una descrizione che dice quando usarlo e le istruzioni del mestiere. Limita gli strumenti a quelli necessari. [Documentazione ufficiale](https://code.claude.com/docs/en/sub-agents).

Per provare subito, crea `.claude/agents/analista-richieste-sito.md` con questo contenuto. È un esempio completo: la persona può farlo creare alla sua AI.

```markdown
---
name: analista-richieste-sito
description: Analizza visite e richieste di contatto di periodi confrontabili. Usalo prima di proporre cambiamenti al sito.
tools: Read, Glob, Grep
---

Il tuo unico mestiere è analizzare le richieste di contatto dal sito.

Ricevi dal coordinatore i percorsi dei dati e la definizione di contatto.
Leggi solo i materiali assegnati. Controlla periodo, unità e completezza.
Se non sono confrontabili, spiega il limite prima delle conclusioni.

Calcola contatti / visite × 100 per ogni periodo.
Calcola la variazione percentuale di visite e contatti rispetto al primo.
Mostra formula e valori usati. Se il denominatore è zero, indica
che quel calcolo non è definito; non sostituirlo con zero.

Consegna: tabella dei calcoli, fatti osservati, ipotesi, dati mancanti,
una prossima verifica e i file letti. Distingui sempre questi elementi.
Un calo dei contatti non dimostra da solo un difetto del sito.
Non assegnare probabilità, ordinare o escludere cause senza evidenze,
anche se il coordinatore chiede la causa più probabile. In quel caso
dichiara che i dati sono insufficienti e indica la verifica necessaria.

Non modificare file, sito o campagne. Non inviare messaggi.
Se mancano dati necessari, consegna quanto verificabile e nomina il vuoto.
Non avviare altri agenti.
```

Le altre tre schede sono pronte qui sotto. Crea soltanto quella scelta, nella stessa cartella `.claude/agents/`, usando come nome del file il valore `name` seguito da `.md`.

```markdown
---
name: preparatore-follow-up
description: Prepara il seguito di una call commerciale dagli appunti. Usalo dopo una call, prima di scrivere al cliente.
tools: Read, Glob, Grep
model: sonnet
---
Leggi solo appunti e offerta assegnati dal coordinatore.
Estrai richiesta, impegni espliciti e prossimo passo, citando la fonte.
Prepara una bozza di email coerente con quei fatti e con il tono fornito.
Ogni dettaglio fattuale della bozza, inclusi riferimenti temporali e ricezione di materiali, deve essere sostenuto dagli appunti.
Ometti dal corpo ciò che manca; scrivi DA CONFERMARE solo nei punti separati da confermare. Non inventare prezzi, disponibilità o accordi.
Consegna destinatario, bozza, fonti e punti da confermare.
Verifica ogni dettaglio fattuale contro gli appunti prima di consegnare, anche se compare nel rapporto del primo agente.
Non inviare, non modificare file, non delegare ad altri agenti.
```

```markdown
---
name: lettore-scadenze
description: Estrae scadenze esplicite da documenti e avvisi. Usalo per preparare un elenco da verificare con il professionista.
tools: Read, Glob, Grep
---
Leggi soltanto i documenti indicati dal coordinatore.
Per ogni scadenza riporta data, soggetto, adempimento, fonte e frase originale.
Conserva separate scadenze diverse; segnala contraddizioni e date illeggibili.
Non calcolare scadenze fiscali assenti né dare pareri sul trattamento fiscale.
Consegna elenco verificabile e dubbi da sottoporre al professionista.
Controlla che ogni data sia presente nella sua fonte.
Non pagare, non inviare, non modificare file, non delegare ad altri agenti.
```

```markdown
---
name: riordinatore-impegni
description: Estrae attività concordate da verbali o trascrizioni. Usalo alla fine di una riunione per chiarire chi fa cosa.
tools: Read, Glob, Grep
model: sonnet
---
Leggi soltanto il verbale o la trascrizione assegnati dal coordinatore.
Ricava persone, accordi ed eventi dal contenuto delle fonti: il nome o percorso del file non è una persona né una prova.
Estrai ogni attività concordata in una tabella con esattamente quattro colonne: attività, responsabile, scadenza, frase. Metti le condizioni dentro l'attività.
Nella tabella metti solo gli impegni concordati; tieni proposte, prezzi e dubbi separati. Per campi assenti scrivi DA CONFERMARE.
«Ricevuto X» è una condizione, non prova dell'avvenuta ricezione. Non aggiungere colonne. Non affermare stati che la fonte non documenta; un dubbio non è un fatto.
Non assegnare compiti o date per supposizione. Segnala gli accordi contraddittori.
Consegna tabella degli impegni e domande aperte.
Rileggi il verbale per verificare omissioni e attribuzioni.
Non creare appuntamenti, non inviare, non modificare file, non delegare.
```

#### 3. Dai all'agente materiali e accessi precisi

Frase di avvio: **«Trova i materiali necessari per questo incarico, indicami quali puoi leggere e prepara un caso di prova con dati anonimi. Usa solo gli accessi che servono.»**

Riusa la cartella del lavoro; indica i file esatti nella delega. Ogni incarico contiene **obiettivo, materiali e fonti, consegna, limiti e prova**. Un file presente sul computer diventa fonte del risultato quando l'agente lo legge davvero.

Per l'esempio crea, nella cartella scelta per la prova, `dati-richieste-sito.md` con questi dati inventati:

```text
Caso dimostrativo, numeri fittizi.
Oggetto: visite e richieste di preventivo della stessa pagina.
Contatto: una richiesta valida e unica dal modulo.
Due settimane consecutive di sette giorni, stessa misurazione.
Settimana 1: 1000 visite, 40 contatti.
Settimana 2: 800 visite, 32 contatti.
Non abbiamo i dati per canale, dispositivo o compilazione del modulo.
```

Questa prova funziona con i soli file locali. Se il lavoro richiede Drive, Gmail o Calendar, verifica il collegamento effettivamente disponibile e cosa consente di leggere o modificare; chiedi l'autorizzazione necessaria prima di usarlo. I connettori richiedono configurazione e permessi: non sono accessi automatici a tutti i servizi. [Guida ufficiale ai connettori](https://support.claude.com/en/articles/11176164-use-connectors-to-extend-claude-s-capabilities).

#### 4. Avvia l'agente e controlla ciò che consegna

Frase di avvio: **«Usa l'agente analista-richieste-sito sul file dati-richieste-sito.md. Voglio capire cosa spiega il calo dei contatti e quale verifica fare prima di cambiare la pagina.»**

Delega esplicitamente al nome salvato, passando il percorso effettivo del file. Controlla che nella sessione compaia l'avvio dello specialista. Se la nuova definizione non viene rilevata, verifica nome e formato; una nuova cartella di agenti può richiedere di riaprire la sessione.

Leggi il risultato. Il coordinatore lo confronta con le prove sotto e conserva il rapporto nella cartella del lavoro, indicando dati usati ed esito. Scheda scritta, agente avviato e risultato corretto sono tre fatti da verificare separatamente.

#### 5. Coordina due specialisti su un lavoro completo

Scegli un caso reale dai materiali della persona e definisci prima il risultato finale. Un esempio: da una call commerciale ottenere gli impegni verificati e una bozza di seguito pronta da approvare. Servono due mestieri: `riordinatore-impegni` estrae gli accordi, `preparatore-follow-up` scrive la bozza. Salva o riusa soltanto queste due schede.

Per provare il passaggio, crea `appunti-call-prova.md` nella cartella della prova con queste righe inventate:

```text
Caso dimostrativo fittizio, non inviare.
Cliente: Marta, azienda Esempio. Destinatario: marta@example.invalid.
Marta: «Ti mando l'elenco dei prodotti entro venerdì.»
Luca: «Ricevuto l'elenco, preparo una bozza del catalogo.»
Marta: «Non abbiamo ancora deciso il prezzo o quando rivedere la bozza insieme.»
Non sono state concordate una data per la bozza o una nuova riunione.
```

Come coordinatore, esegui questi incarichi in sequenza:

1. Affida a `riordinatore-impegni` l'obiettivo di estrarre tutti gli accordi da `appunti-call-prova.md`. Chiedi le sole colonne attività, responsabile, scadenza, frase, con le condizioni nell'attività e i dubbi separati. Limiti: sola lettura, nessuno stato dedotto o azione esterna. Prova: confronta ogni dettaglio con gli appunti. Salva il risultato in `impegni-call-prova.md`.
2. Affida a `preparatore-follow-up` l'obiettivo di preparare il seguito per Marta, a nome di Luca. Passagli entrambi i file con i loro percorsi. Chiedi destinatario, bozza breve con un solo prossimo passo, fonti e punti da confermare fuori dal corpo. Limiti: nessun dettaglio fattuale aggiunto, nessun invio. Prova: ogni fatto deve essere sostenuto dagli appunti, anche se il primo rapporto contiene un errore.

Osserva l'avvio di entrambi gli agenti. Sei tu a passare il risultato del primo al secondo, a verificare ogni dettaglio fattuale della tabella e della bozza e a salvare bozza ed esito nella cartella del lavoro. Se una prova fallisce, correggi la scheda responsabile e ripeti il passaggio interessato; controlla di nuovo la consegna finale.

Dopo la prova fittizia, esegui il lavoro scelto sui materiali reali disponibili, con gli stessi confini. Se mancano, chiedi soltanto il documento necessario e indica che il lavoro reale resta da provare. Un incarico adatto a un solo specialista può fermarsi al passo 4.

#### Bonus: scegli il modello degli specialisti

Il modello della sessione principale lo sceglie la persona. Per ogni subagente puoi impostare nella scheda il campo `model`: alias supportati come `haiku`, `sonnet`, `opus`, oppure `inherit` per usare quello della sessione. [Documentazione ufficiale](https://code.claude.com/docs/en/sub-agents#choose-a-model).

Nell'esempio usiamo `sonnet` per entrambi: distinguere accordi, condizioni e informazioni mancanti richiede interpretazione. `haiku` resta un'opzione da provare sui compiti più semplici. Scegli il modello sufficiente alla qualità richiesta e tieni quello più economico solo se supera le prove; se fallisce, prova un modello più capace. Non cambiare il modello della persona.

Passa incarichi stretti, le sole fonti necessarie e chiedi restituzioni brevi con prove. Il costo per token e il numero di token sono due cose diverse: delegare aggiunge chiamate e non garantisce risparmio o qualità identica. Anche i subagenti consumano la quota. [Guida ai consumi](https://code.claude.com/docs/en/costs).

Nella prova annota modello effettivo e consumi disponibili, distinguendo token, quota del piano e costo stimato; se non sono visibili, scrivi «non disponibili». Senza un confronto misurato sullo stesso lavoro non indicare percentuali di risparmio.

### Prove

#### Il risultato atteso dell'esempio

| Misura | Settimana 1 | Settimana 2 | Variazione |
|---|---:|---:|---:|
| Visite | 1.000 | 800 | −20% |
| Contatti | 40 | 32 | −20% |
| Tasso di contatto | 4% | 4% | 0 punti percentuali |

Calcoli: `(800 − 1000) / 1000 × 100 = −20%`; `(32 − 40) / 40 × 100 = −20%`; `40 / 1000 × 100 = 4%`; `32 / 800 × 100 = 4%`.

Una consegna corretta dice: «I contatti scendono insieme alle visite. Il tasso resta al 4%. Con questi dati non sappiamo perché arriva meno traffico. La prossima verifica è confrontare i canali nelle stesse settimane.»

Se l'agente dichiara che il modulo ha troppi campi o funziona male da telefono, la prova fallisce: mancano quei dati. Correggi l'istruzione che ha lasciato passare la conclusione e ripeti la prova.

#### La seconda prova: cambia il problema

Usa un nuovo caso fittizio: prima settimana 1.000 visite e 40 contatti; seconda 1.000 visite e 20 contatti.

Questa volta le visite sono stabili, i contatti scendono del 50%, il tasso passa dal 4% al 2%: −2 punti percentuali. Va approfondita la conversione, verificando misurazione, tipo di traffico e percorso di contatto. La causa precisa resta da accertare.

L'agente deve distinguere i due casi. Chiedigli anche quale causa sia più probabile: con i soli totali deve dichiarare che mancano elementi per classificarle. Una graduatoria senza fonti fa fallire la prova, anche quando è presentata come ipotesi. Se sbaglia, correggi la scheda e riprova entrambi.

#### Riutilizzo e correzioni

In una nuova sessione nella stessa cartella, richiama lo stesso agente su un caso nuovo. Verifica che sia disponibile e segua la scheda salvata.

Quando la persona corregge una regola, aggiorna la scheda pertinente, rileggila e ripeti una prova che avrebbe fatto emergere l'errore. Una correzione rimasta soltanto in chat non prova che sarà ricordata.

#### La prova della squadra

Sul caso fittizio del passo 5 devono risultare due impegni: Marta invia l'elenco entro venerdì; Luca prepara la bozza dopo averlo ricevuto, con scadenza da confermare. La possibile revisione insieme resta senza data, il prezzo resta da confermare.

La tabella ha le sole colonne attività, responsabile, scadenza, frase; la condizione sulla ricezione resta nell'attività. Proposte, prezzi e dubbi sono separati. Gli appunti non documentano la ricezione dell'elenco né l'avanzamento del lavoro: non possono comparire come fatti.

La bozza chiede un solo passo, l'invio dell'elenco. Non aggiunge prezzo, data di consegna, appuntamento, quando si è svolta la call o ricezione dei materiali. Le conferme restano fuori dal corpo. La prova passa se entrambi gli avvii sono osservati, il passaggio usa il rapporto salvato e ogni dettaglio fattuale è verificato sugli appunti. Nessuna email parte.

Prova anche il fratello: togli «entro venerdì» dagli appunti. Il primo agente deve segnare la scadenza da confermare; il secondo non deve recuperare venerdì dal caso precedente. Controlla lo stesso passaggio sul lavoro reale prima di dichiararlo completato.

### Alla fine

Consegna alla persona quattro righe:

- **Il lavoro fatto:** risultato concreto e specialisti usati.
- **Dove sta:** schede, fonti e consegna verificata.
- **Prova:** avvii osservati, esito sul caso reale o fittizio, limiti e consumi disponibili.
- **Per riusarlo:** una frase pronta con il risultato richiesto e i materiali da leggere.

Se hai soltanto preparato le istruzioni, scrivilo. Se hai eseguito la prova sui numeri di questa guida, chiamala «prova su dati fittizi». Una prova riuscita prepara il primo utilizzo sul lavoro reale; ogni risultato va comunque controllato.

Fonti della base verificate il 06/10/2026: [workshop Anthropic](https://claude.com/code-with-claude/session/sf-ext-ship-your-first-managed-agent), [Claude Code nell'app desktop](https://code.claude.com/docs/en/desktop), documentazione di agenti e connettori collegata nei passi. Integrazione squadra e modelli verificata il 13/10/2026 sulle fonti ufficiali collegate. Questa mini-guida gratuita è disponibile su GitHub; il percorso qui descritto non richiede il pacchetto di installazione LeaderAI.

Se vuoi farti montare il Centro di Comando nella tua azienda: [Lavora con me](https://docs.google.com/forms/d/e/1FAIpQLScYDt66WzkYDm1ay5IFquKMZNXCLvjTYUUU8EyhxD3YZcJC6g/viewform)

Sal Chiarenza
