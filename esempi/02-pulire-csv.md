# 02 — Ripulire un file esportato male

**Quando serve:** un export da un gestionale o da un foglio di calcolo arriva con colonne spostate, date in due formati e righe di intestazione ripetute.

**Brief:**

```text
In <file_csv> le colonne sono spostate e le date compaiono in due formati
(<formato_a> e <formato_b>). Scrivi uno script che produca <file_pulito> con:
- intestazione singola, nell'ordine: <elenco_colonne>;
- date tutte in formato ISO 8601 (YYYY-MM-DD);
- righe vuote e righe di intestazione ripetute rimosse;
- una colonna finale "note_originali" con il contenuto grezzo della riga, per
  poter risalire all'originale.
Condizione di fine: esegui lo script, mostrami le prime 5 righe del file pulito
e conferma che il numero di righe di dati è uguale a <n_righe_attese>.
```

**Perché la condizione di fine funziona:** "conferma che il numero di righe è uguale a N" intercetta l'errore più frequente in questo lavoro, cioè le righe perse in silenzio.

**Cosa aspettarsi:** la colonna `note_originali` sembra superflua e non lo è: quando una data è ambigua (03/04 è marzo o aprile?) ti serve il dato originale per decidere.

**Cosa controllare prima di tenere il risultato:**
- apri il file pulito e cerca a occhio 3 righe a caso nell'originale;
- verifica le date ambigue: se il formato sorgente è giorno/mese, l'agente può aver assunto mese/giorno;
- tieni l'originale accanto al pulito, sempre.
