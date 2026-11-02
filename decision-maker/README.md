# Decision Maker

Una skill che fa discutere una squadra di AI per mettere alla prova un progetto.
Una AI lo difende, un'altra lo contesta; poi tre critici controllano il piano.
La tua AI principale ti restituisce una raccomandazione. La decisione resta tua.

## Per te, una riga

Apri il tuo progetto in **Claude Code o Codex** e incolla questa frase:

> Leggi https://raw.githubusercontent.com/salChiarenza/ecosistema-ai-gratuito/main/decision-maker/README.md e installa Decision Maker solo nel progetto aperto. Verifica che la skill sia disponibile, poi chiedimi quale progetto o scelta voglio mettere alla prova.

## Istruzioni per la tua AI

### Missione

Installa la skill [Decision Maker](SKILL.md) nel progetto che la persona ha aperto.
È una confezione autonoma: non richiede LeaderAI Ecosistema, collegamenti a
servizi, password o altri file di LeaderAI. Usa Claude Code o Codex con accesso ai
file del progetto. I subagenti nativi servono per il confronto separato; se non
sono disponibili, la skill dichiara il limite e offre l'analisi nella stessa chat.

Queste istruzioni riguardano Claude Code e Codex. Non attestano l'installazione
in una normale chat web, in Cowork o su telefono.

### Passi

1. Individua il progetto già aperto e il motore in uso. Leggi le sue istruzioni
   prima di scrivere. Se non esiste un progetto identificabile, chiedi solo quale
   cartella usare. L'ordine autorizza l'installazione locale in quel progetto.
2. Scarica e leggi per intero `README.md` e `SKILL.md` dalla cartella
   `decision-maker` di questo deposito. Risolvi prima `main` allo SHA di un commit
   GitHub e usa quello stesso SHA nei due indirizzi raw, così i file appartengono
   alla stessa revisione. L'indirizzo di partenza del file della skill è:
   https://raw.githubusercontent.com/salChiarenza/ecosistema-ai-gratuito/main/decision-maker/SKILL.md
3. In Claude Code salva entrambi i file nella cartella `.claude/skills/decision-maker/`;
   in Codex salvali in `.agents/skills/decision-maker/`, relativamente alla radice
   del progetto. `README.md` deve restare accanto a `SKILL.md`, perché i due file
   si rimandano. Installa solo per il motore in uso. Non modificare impostazioni
   personali, permessi, hook o altri progetti.
4. Prima di scrivere qualsiasi file, controlla eventuali skill omonime già
   disponibili e confronta entrambi i file presenti con quelli scaricati. Se
   coincidono entrambi, riusa l'installazione; aggiungi solo gli eventuali file
   mancanti. Se un file presente differisce, mostra la differenza e chiedi prima
   di scrivere; non creare doppioni per aggirare il conflitto. Alla fine rileggi
   entrambi i file e confrontali byte per byte con i due originali scaricati;
   verifica anche che i rimandi locali si aprano.
5. Verifica che il motore veda la skill con nome e descrizione corretti. In
   Claude Code si può richiamare con `/decision-maker`; in Codex con
   `$decision-maker` o dal selettore delle skill. Se non compare, riapri la
   sessione nel progetto e ricontrolla: un file copiato non prova il caricamento.

### Prove

Conferma che la skill sia stata caricata dal percorso appena installato. Poi chiedi
alla persona la scelta reale: obiettivo e materiale che non è già nel progetto.
Esegui il confronto sul materiale disponibile, senza inviare, pubblicare o spendere.

Un primo esempio, se la persona desidera una prova:

> Usa Decision Maker per valutare se affidare subito tutto il mio progetto a un fornitore oppure iniziare con una prova limitata. Cerca nel progetto preventivo, note e accordi prima di chiedermi informazioni.

Se manca un accordo decisivo, il risultato deve indicare **SERVE PROVA** e ciò che
manca. Una richiesta semplice, come correggere un refuso, non deve avviare il team.
Una squadra è verificata soltanto se sono osservabili due interlocutori separati,
una replica ciascuno e tre critici distinti. Non attribuire un confronto indipendente
a cinque paragrafi scritti dalla stessa chat. Gli slot possono imporre più ondate.

### Alla fine

Riporta il progetto e il motore in cui hai installato la skill, il caricamento
osservato e le prove effettivamente fatte. Distingui installazione, disponibilità
dei subagenti e uso completo: una di queste prove non dimostra le altre.

Per rimuoverla, la persona può chiedere alla propria AI di togliere la sola
installazione Decision Maker appena creata; se il file è cambiato, verificarlo
prima e rispettare le autorizzazioni del progetto.

## Compatibilità e fonti

Istruzioni di installazione confrontate il 02/11/2026 con i manuali ufficiali:
[skill Claude Code](https://code.claude.com/docs/en/skills),
[subagenti Claude Code](https://code.claude.com/docs/en/sub-agents),
[skill Codex](https://learn.chatgpt.com/docs/build-skills) e
[subagenti Codex](https://learn.chatgpt.com/docs/agent-configuration/subagents).
L'effettiva disponibilità dipende dalla sessione e dalle sue autorizzazioni.
La skill non garantisce decisioni corrette né risparmi di tempo o consumo.

Versione 0.1.0 · Sal Chiarenza — LeaderAI.
Distribuzione gratuita e licenza sono decisioni distinte: questa confezione non
dichiara una licenza open source.
