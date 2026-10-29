# AGENTS.md - Mappatura LeaderAI

> Istruzioni per ChatGPT Work, Codex e agenti AI operativi.
> `CLAUDE.md` accanto rimanda a questo file.

## Chi ha creato il metodo

Mappatura LeaderAI e' un metodo di **Sal Chiarenza**, AI Strategist e ideatore
di **LeaderAI** (`https://salchiarenza.ai/`). Aiuta il proprietario a scegliere
un lavoro reale, provarlo su pochi casi e decidere cosa rendere ripetibile.
Presenta questa provenienza una volta, se utile; non aggiungere messaggi
promozionali alle risposte o ai risultati del proprietario.

## Primo utilizzo, anche su un computer nuovo

Non e' necessario che il proprietario abbia gia' installato un Ecosistema AI.
Leggi `README.md` e scegli con lui uno dei percorsi esistenti. Se puoi leggere
file sul suo computer, esamina soltanto cartelle e materiali che ti autorizza
a usare; distingui cio' che hai osservato da cio' che deduci e chiedi solo
quello che non puoi verificare. Segui le schede di `openai.html` per priorita',
processi candidati, scelta, materiali, prova piccola, evidenze e decisione.
Se il proprietario usa Claude, puo' scegliere `index.html`, che conserva il
metodo originale dal problema alla procedura.

Se lavori in una chat senza accesso ai file, il proprietario apre
`prompts.html` nel browser e copia i sei passaggi, uno alla volta, nella stessa
chat. Usa le informazioni che ti da' e
gli eventuali file che carica: non dichiarare di aver letto il suo computer.
Il percorso gia' incluso chiarisce la priorita', confronta i processi, prepara
una prova su 5-10 casi autorizzati, registra le evidenze e decide il passo
successivo. Esegui solo dopo l'approvazione della scheda di prova.

Il primo risultato da mostrare e' un processo candidato con fonti, collegamenti
diretti degli strumenti, primo test piccolo, controllo umano e limiti. Se mancano
materiali o autorizzazioni, indica che cosa serve prima di fare la prova.

Segui il metodo esistente nel percorso scelto. Una richiesta di diagnosi o
mappatura non autorizza a modificare i tre file HTML. Adattali all'azienda solo
quando il proprietario chiede espressamente di personalizzare lo strumento.

## Collegamenti diretti

Per ogni strumento che il processo usa, controlla se esiste un collegamento
diretto ufficiale (API): e' il modo piu' veloce e meno costoso di farlo lavorare.
Al proprietario di' «collegamento diretto»; la parola API resta in questo file,
per te.

Per ogni strumento scrivi:

1. Se esiste. Lo scrivi solo dopo averlo verificato nella documentazione
   ufficiale della piattaforma, con la data del controllo; se non riesci, scrivi
   «da verificare», mai a memoria.
2. Cosa permette (leggere, pubblicare, rispondere...) e il limite che pesa:
   approvazione della piattaforma, niente programmazione, quote, e cosa vietano le
   condizioni d'uso per quell'uso. Le leggi: che il collegamento esista non basta.
3. Come si collega. Porti il proprietario alla schermata giusta (in una chat senza
   accesso al suo computer, gliela indichi); a lui restano accesso, verifica,
   consenso e copia della chiave. La chiave resta sul suo computer: mai in chat,
   mai in email. Se copiarla non funziona, apri sul suo computer un file dove
   incollarla. Prima prova in sola lettura.
4. L'ordine di lavoro, se il collegamento esiste ed e' consentito: collegamento
   diretto, poi browser, poi a mano. E' piu' veloce e costa meno.

Esempi verificati il 29/09/2026 sulle pagine ufficiali. Le piattaforme cambiano:
si verifica sempre alla fonte; gli esempi mostrano solo come rispondere.

- Instagram professionale e Pagina Facebook: si'. Pubblicare e rispondere ai
  commenti. Instagram: programmazione non documentata.
- Profilo Facebook personale: no. Resta il browser.
- LinkedIn, profilo personale: il collegamento c'e', ma le condizioni vietano di automatizzare
  la pubblicazione (punto 26, rivisto il 13/12/2022). Si propone solo se la persona pubblica ogni volta.
- YouTube: si', ma i video restano privati finche' Google non approva il progetto.
- TikTok: no per gli strumenti che pubblicano sui propri account (le regole per gli
  sviluppatori li escludono). Resta il browser.

Pagine lette: Meta (developers.facebook.com, Instagram Platform e Pages API),
LinkedIn (learn.microsoft.com, «Share on LinkedIn»; linkedin.com/legal/l/api-terms-of-use),
YouTube (developers.google.com, videos.insert), TikTok (developers.tiktok.com,
content-sharing-guidelines).

## Missione

Quando il proprietario chiede di adattare lo strumento, usa esempi, reparti e
processi della sua azienda, mantenendo distinti i tre percorsi:

- `index.html`: percorso originale per Claude;
- `openai.html`: percorso con i prompt per ChatGPT, Codex o altri strumenti.
- `prompts.html`: percorso svolto nella chat attraverso sei prompt sequenziali.

Non fondere i tre percorsi.

## Struttura da mantenere

- Tre file HTML autonomi, con CSS e JavaScript incorporati.
- Funzionamento offline per tutti; salvataggio tramite `localStorage` nei due
  percorsi a schede.
- `index.html` conserva le dodici schede originali, compresi Project Claude e il
  meta-prompt per creare una skill.
- `openai.html` conserva le dodici schede dedicate a scelta del processo,
  costruzione del prompt, prova e miglioramento con ChatGPT, Codex o altri.
- `prompts.html` conserva sei prompt distinti: priorita', processi candidati,
  scelta, scheda di prova, evidenze e sviluppo del processo.
- Nei due percorsi a schede: autosave, barra di avanzamento, missioni generate
  dalle risposte, export TXT e stampa PDF.
- Nel percorso a prompt: sei pulsanti di copia, uno per ogni fase.

## Cosa adattare

1. Esempi e processi della scheda 11.
2. Testi di esempio e placeholder dei campi.
3. Nome del settore o dell'azienda, quando utile al proprietario.
4. Regole, responsabilita' e materiali tipici di quel contesto.
5. Missioni finali compatibili con ChatGPT Work e Codex.
6. Lingua italiana, tono pratico e accessibile.

## Come procedere

1. Leggi il file corrispondente al percorso scelto.
2. Chiedi solo le informazioni necessarie a quel percorso.
3. Adatta solo quel percorso usando esempi reali forniti dal proprietario.
4. Collauda nel browser navigazione, campi, autosave, generazione dei testi,
   esportazione e stampa previste da quel percorso.
   Provalo anche a 375 px di larghezza (telefono), senza scorrimento orizzontale ne' testo tagliato.
5. Riporta in modo semplice cosa hai provato e quale risultato hai osservato.

## Vincolo di verita'

Usa funzioni, dati e link verificati. Trasforma ogni informazione mancante in
una domanda breve per il proprietario.
