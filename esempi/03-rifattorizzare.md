# 03 — Rifattorizzare senza cambiare comportamento

**Quando serve:** un file è cresciuto fino a diventare illeggibile, ma non puoi permetterti di romperlo: ha utenti o test che dipendono da lui.

**Brief:**

```text
In <file> la logica di <descrizione_logica> è duplicata in <n> punti.
Estraila in una funzione pura chiamata <nome_funzione>, senza cambiare il
comportamento esterno.
Requisiti:
- nessuna modifica alle firme pubbliche;
- nessuna nuova dipendenza;
- se un punto non si può estrarre senza cambiare comportamento, lascialo e
  segnalalo alla fine invece di forzarlo.
Condizione di fine: <comando_test> passa con lo stesso numero di test di prima,
e mostrami il diff completo.
```

**Perché la condizione di fine funziona:** "stesso numero di test di prima" impedisce il trucco più comune, cioè far passare i test cancellandone qualcuno.

**Cosa aspettarsi:** il vincolo "segnala invece di forzare" è quello che salva la qualità: senza, l'agente tende a estrarre tutto, anche i casi che condividono solo tre righe per caso.

**Cosa controllare prima di tenere il risultato:**
- il conteggio dei test è identico, non solo "verde";
- il diff non tocca niente fuori dal file indicato;
- se hai un branch di confronto, prova a eseguire il codice vecchio e il nuovo sullo stesso input.
