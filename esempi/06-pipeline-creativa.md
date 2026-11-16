# 06 — Pipeline creativa (anteprime 3D e PDF)

**Quando serve:** devi produrre più viste di una scena 3D e impaginarle in un PDF, e ogni volta rifai gli stessi passaggi a mano.

**Brief:**

```text
Nella scena <file_scena> genera 6 anteprime dai seguenti punti di vista:
<elenco_angoli>. Salva i PNG in <cartella_output> con nomi ordinati
(anteprima_01.png ... anteprima_06.png), risoluzione <risoluzione>, sfondo
trasparente.
Poi impaginale in <file_pdf> A4 verticale, 2 immagini per pagina, con etichetta
sotto ogni anteprima e margini coerenti.
Requisiti:
- nessuna immagine ritagliata: ogni anteprima deve stare intera nella sua cella;
- se un angolo produce un'immagine vuota, fermati e segnalalo invece di
  sostituirlo.
Condizione di fine: mostrami l'elenco dei file prodotti con le loro dimensioni in
byte, e conferma che il PDF si apre e contiene 3 pagine.
```

**Perché la condizione di fine funziona:** "dimensioni in byte" e "3 pagine" sono controlli oggettivi: un'immagine vuota pesa pochi kilobyte e si riconosce subito, mentre a occhio in un'anteprima piccola non si nota.

**Cosa aspettarsi:** il rendering è la parte lenta: conviene chiedere prima una risoluzione bassa per validare la composizione, e solo dopo lo scatto finale. Il vincolo "fermati e segnala" evita che un angolo sbagliato venga coperto da un'immagine simile.

**Cosa controllare prima di tenere il risultato:**
- apri il PDF e guarda ogni pagina, non solo la prima;
- controlla che i nomi siano nell'ordine giusto: con la numerazione a due cifre (`01`…`06`) l'ordine alfabetico coincide con quello numerico, ma verifica che l'angolo 1 non sia finito in `anteprima_06.png`;
- conserva il file di scena originale: la pipeline deve essere ripetibile, non una modifica una tantum.
