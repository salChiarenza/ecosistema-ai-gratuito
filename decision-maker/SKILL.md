---
name: decision-maker
description: Metti alla prova un progetto o una scelta importante con fatti verificati, due tesi contrapposte e tre controlli sui rischi. Usa anche quando la persona richiama Decision Maker. Non attivare il team per refusi, semplici bozze o domande di fatto.
metadata:
  version: 0.1.0
  author: Sal Chiarenza - LeaderAI
---

# Decision Maker

[Installazione e uso](README.md).

Formula una raccomandazione motivata dopo aver verificato i fatti e messo alla
prova le alternative. La sessione principale coordina e giudica; ogni incaricato
svolge il proprio compito senza sotto-deleghe. La decisione resta alla persona.

## 1. Prima i fatti e i criteri

Definisci la scelta: risultato cercato, alternative, vincoli, scadenza e conseguenze.
Considera anche rinviare o fare una prova più piccola. Recupera autonomamente il
materiale pertinente disponibile nel progetto: istruzioni, stato del lavoro, note,
call o trascrizioni, accordi e ultime decisioni approvate. Segui i rimandi e leggi
le fonti; evita scansioni indiscriminate di altri progetti o file personali.

Per fatti che cambiano, verifica la fonte viva con gli strumenti e gli accessi già
disponibili. Non chiedere dati che puoi recuperare; fai una sola domanda se manca
una scelta della persona o un materiale essenziale non accessibile. Le sue
preferenze sono vincoli, non prove a favore della soluzione preferita.

Se servono ricerche indipendenti, incarica ricercatori separati per i buchi distinti:
raccolgono fatti, fonti, date, contraddizioni e lacune, senza raccomandare un'opzione.
Prepara una sintesi comune con obiettivo, storia delle decisioni, impegni, vincoli,
fonti realmente lette, ipotesi e lacune. Una citazione non equivale a una lettura.
Se una fonte decisiva resta irreperibile, rispondi **SERVE PROVA** e indica cosa
recuperare: non avviare un dibattito su una premessa inventata.

Prima dei pareri fissa criteri osservabili di successo e condizioni che farebbero
scartare ciascuna opzione. Numeri e soglie richiedono una base esplicita: distingui
misure, stime e ipotesi. Sintesi e criteri formano lo stesso pacchetto per i due
interlocutori e i tre critici. Se un fatto nuovo cambia i criteri, spiega quale
fatto e invia l'aggiornamento a tutti prima di riprendere il confronto.

## 2. Due tesi e una replica ciascuno

Avvia due agenti nativi separati sullo stesso pacchetto neutro: uno cerca il caso
migliore per procedere, l'altro il caso migliore per scegliere un'alternativa.
Ogni incarico chiede tesi, prove, assunzione più fragile e condizione che farebbe
cambiare idea. Le prime risposte non vedono la tesi rivale né una conclusione
suggerita dal coordinatore. Usa contesti separati, trasmettendo soltanto il
pacchetto e il ruolo; evita di ereditare una conversazione che contiene già pareri.

In Codex usa gli strumenti nativi di collaborazione disponibili e un agente
generico adatto al compito; scegli un contesto senza storia ereditata quando
l'interfaccia lo consente. In Claude Code usa Agent con un incarico autosufficiente
e il tipo general-purpose o un equivalente disponibile. Non occorrono agenti con
nomi preinstallati. Gli incaricati ricevono il pacchetto nel mandato: non presumere
che ereditino questa skill o altri file.

Rimanda a ciascuno la tesi dell'altro. Una replica deve affrontarne l'argomento
più forte, citare la prova che lo sostiene o lo indebolisce e dire se la posizione
cambia. Non creare opposizione artificiale se le prove convergono. Chiedi motivi
brevi e fonti, non il ragionamento interno integrale.

La principale pesa le prove e formula un piano provvisorio. Maggioranza, sicurezza
del tono e preferenze non sostituiscono una prova. Se le alternative dipendono da
una condizione, individua quale dato permetterebbe di scegliere fra loro.

## 3. Tre controlli sul piano

Tre agenti nuovi ricevono lo stesso pacchetto, il piano provvisorio e le prove;
non vedono inizialmente i pareri degli altri critici. Non riutilizzare un
interlocutore per certificare il piano che ha difeso.

| Critico | Cerca | Consegna |
|---|---|---|
| Propenso al rischio | Opportunità persa, costo dell'attesa, ambizione insufficiente | Obiezione più forte e modifica concreta |
| Prudente | Peggior esito plausibile, promesse fragili, costi e dipendenze | Obiezione più forte e modifica concreta |
| Neutrale | Assunzione decisiva, rapporto fra beneficio e rischio, prova discriminante | Obiezione più forte e modifica concreta |

Rispetta gli slot realmente disponibili: avvia gli incarichi in ondate e attendi
i ritorni prima delle fasi dipendenti. Riusa i due interlocutori per le repliche.
Un ciclo completo; un altro solo se emerge un nuovo fatto decisivo. Adatta qualità
e impegno degli agenti alla scelta, senza promettere risparmi di tempo o consumo.

## 4. Il giudizio e il prossimo passo

Integra obiezioni e correzioni e scegli **FAI**, **NON FARE**, **FAI INVECE** oppure
**SERVE PROVA**. Puoi respingere il piano dopo il confronto. Indica quale fatto
cambierebbe il giudizio; se manca un dato decisivo, proponi la prova minima e una
scelta provvisoria reversibile, quando esiste.

Alla persona consegna una risposta breve: raccomandazione e motivo, obiezione
decisiva e risposta, rischio residuo, cosa cambierebbe il giudizio e un solo passo
successivo. Il confronto resta dietro le quinte, salvo richiesta di dettaglio.
Una raccomandazione non autorizza spese, invii, pubblicazioni, nuovi impegni o
modifiche agli accessi. Conserva le autorizzazioni e le istruzioni del progetto.
Se serve una traccia, usa lo stato del lavoro già presente; evita un file per parere.

## Limiti e controllo

Se i subagenti non sono disponibili o non sono autorizzati, dichiaralo prima del
confronto. Puoi offrire un'**analisi a più prospettive nella stessa chat**, ma non
chiamarla squadra o confronto indipendente e non inventare agenti mai avviati.
Agenti separati possono condividere gli stessi errori: cinque pareri non
garantiscono una scelta corretta. Rendi visibili le fonti decisive e le lacune.

Controlla il risultato contro i criteri iniziali e almeno un'alternativa reale.
Per verificare l'adozione, osserva l'avvio effettivo dei due interlocutori, le loro
repliche e i tre controlli distinti, non soltanto un riepilogo scritto dal modello.
Prova anche una fonte decisiva mancante e una richiesta semplice senza squadra.

## Scuola

Adattamento pubblico di Sal Chiarenza, LeaderAI, 02/11/2026. Ispirazioni metodologiche:
[TradingAgents](https://arxiv.org/html/2412.20138v1) per separare fatti, confronto e
rischio; [Debate](https://github.com/LeSingh1/debate-skill/blob/main/debate/SKILL.md)
per le repliche; [Council Review](https://github.com/ngmeyer/skills/blob/main/skills/productivity/council-review/SKILL.md)
per i giudizi iniziali separati. Non ne derivano promesse di accuratezza o rendimento.

Esempio: un fornitore promette un lavoro in cinque giorni; il materiale precedente
parla di venti. Recupera entrambi, fissa cosa deve essere consegnato, verifica la
capacità e confronta l'incarico completo con una prova limitata prima di suggerire
un impegno. L'interesse delle parti non dimostra fattibilità.
