# Brief che funzionano — Freebuff

*English: six coding-agent briefs with a finish condition — the content is in Italian.*

Una raccolta di brief (le istruzioni che dai a un agente di coding) che ho usato davvero e che hanno prodotto risultati verificabili. Ogni brief include la **condizione di fine**: la frase che dice all'agente quando il lavoro è finito. È la differenza tra un risultato che puoi controllare e una risposta che sembra plausibile e non funziona.

Sei brief e tre anti-pattern, in italiano. Li ho scritti lavorando con Freebuff, ma il brief è testo: funzionano con qualunque agente.

## Come si usa

1. Apri il progetto su cui vuoi lavorare e mettiti su un branch pulito: l'agente modifica file veri.
2. Copia il brief da `esempi/` e sostituisci i segnaposto `<...>` con i tuoi valori.
3. Incollalo nell'agente, senza aggiungere altro.
4. Revisiona il diff. L'agente verifica il comportamento, non il tuo gusto: la decisione su cosa tenere è tua.

## I 6 brief

| Brief | Per cosa | File |
|---|---|---|
| Script di automazione | rinominare, convertire, riorganizzare file | [esempi/01-script-automazione.md](esempi/01-script-automazione.md) |
| Ripulire un file esportato male | CSV con colonne spostate, date in due formati | [esempi/02-pulire-csv.md](esempi/02-pulire-csv.md) |
| Rifattorizzare senza cambiare comportamento | estrarre logica, ridurre duplicazioni | [esempi/03-rifattorizzare.md](esempi/03-rifattorizzare.md) |
| Documentazione dal codice | pagine che descrivono ciò che il codice fa davvero | [esempi/04-documentazione.md](esempi/04-documentazione.md) |
| Debug riproducibile | test che fallisce a intermittenza | [esempi/05-debug-riproducibile.md](esempi/05-debug-riproducibile.md) |
| Pipeline creativa | anteprime 3D e impaginazione PDF | [esempi/06-pipeline-creativa.md](esempi/06-pipeline-creativa.md) |

## I 3 anti-pattern

**1. Richiesta vaga.** "Migliora il sito" non ha una condizione di fine: l'agente esplora, propone, e alla fine hai un diff che non sai valutare. Se non sai scrivere la condizione di fine, non hai ancora deciso cosa vuoi.

**2. Lavorare senza branch.** Le modifiche sono reali e immediate. Senza branch il rollback è a mano, e con un agente che tocca dieci file il rollback a mano è un pomeriggio perso.

**3. Codice privato o con credenziali.** Quello che incolli passa ai provider dei modelli: non è un confine di privacy. Lavora su una copia ripulita, e togli chiavi e dati dei clienti prima di iniziare.

## Cosa non troverai qui

- prompt "magici" e numeri gonfiati: solo brief che ho provato;
- configurazioni, chiavi o credenziali di alcun tipo;
- consigli su come aggirare limiti o regole dei servizi.

## Nota e disclosure

Non sono affiliato a Freebuff: sono un utente. Il link qui sotto è il mio link invito, che mi dà sessioni extra; il servizio è gratuito comunque e per te il prezzo non cambia. Passa da un redirect che conta i click, così so quali canali portano visite.

→ **[Il mio link invito a Freebuff](https://zip1.io/fb-github)**

Se un brief non funziona sul tuo caso, apri una issue con il testo che hai usato e cosa è successo: è il contributo più utile che puoi dare a questa raccolta.

## Licenza

MIT — vedi [LICENSE](LICENSE). © 2026 Eric Anighoro: puoi riusare i brief anche per lavoro, tenendo l'avviso di copyright.
