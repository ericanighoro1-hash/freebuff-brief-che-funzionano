# 01 — Script di automazione

**Quando serve:** hai una cartella di file con nomi incoerenti (foto, export, allegati) e rinominarli a mano ti costa mezz'ora ogni volta.

**Brief:**

```text
Scrivi uno script Python in <cartella_progetto>/scripts/rinomina.py che rinomini
i file dentro <cartella_target> secondo questo schema: <schema>.
Requisiti:
- non sovrascrivere mai un file esistente: se il nome è occupato, aggiungi un suffisso;
- stampa un riepilogo finale con quanti file ha rinominato e quanti ha saltato;
- nessuna dipendenza esterna oltre la standard library.
Condizione di fine: lo eseguo su una cartella di 3 file di prova e il risultato
corrisponde allo schema, senza errori e senza file persi.
```

**Perché la condizione di fine funziona:** obbliga l'agente a eseguire lo script su un caso piccolo e a mostrarti l'output. "Funziona" senza esecuzione è un'ipotesi.

**Cosa aspettarsi:** di solito il primo tentativo ignora i conflitti di nome. La riga "non sovrascrivere mai" serve proprio a evitare che il test di prova cancelli qualcosa.

**Cosa controllare prima di tenere il risultato:**
- lancia lo script su una **copia** della cartella, non sull'originale;
- verifica che il numero di file in ingresso e in uscita coincida;
- guarda il riepilogo: se dice "0 rinominati" c'è un problema di percorso, non di logica.

**Variante utile:** chiedi anche `--dry-run` come primo passo. È la differenza tra uno script che provi e uno di cui ti fidi.
