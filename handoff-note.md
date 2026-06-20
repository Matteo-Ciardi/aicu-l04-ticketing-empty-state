## Scope

- Modifica richiesta: Aggiungere un empty state semplice quando la lista ticket e' vuota.
- Fuori scope: Redesign, filtri, routing, creazione ticket, refactor, CSS, App.jsx, API, server.

## Prompt Strategy

- Zero-shot o few-shot: Zero-shot.
- Esempi usati, se presenti: Nessuno. Pattern React base (conditional rendering su array vuoto).
- Evidenze sintetiche richieste: File toccato, diff leggibile, verifica stato vuoto e stato con ticket.

## Changes

- File principali: `src/components/TicketList.jsx`
- Sintesi: Aggiunto ternario `tickets.length === 0` per mostrare un `<p className="state-message">` con copy "Non ci sono ticket aperti. Quando verra' creato un nuovo ticket, lo vedrai qui." al posto della lista vuota. Classe CSS `.state-message` gia' esistente, riutilizzata senza modifiche.

## Validation

- Controlli eseguiti: Build `pnpm run build` passato senza errori.
- Controlli non eseguiti: Verifica visiva a runtime (`pnpm dev` su `/?empty=true` e `/`). Build conferma che il codice compila ma non sostituisce la prova visiva.

## Review Notes

- Punti da controllare in review: Riga 15-16 del ternario e copy del messaggio.
- Rischi o dubbi residui: Nessuno. Modifica locale, reversibile, nessun effetto collaterale.
