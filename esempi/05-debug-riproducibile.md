# 05 — Debug riproducibile

**Quando serve:** un test fallisce una volta su cinque, o solo in CI, e ogni volta che lo lanci a mano passa.

**Brief:**

```text
Il test <file_test> fallisce a intermittenza (circa 1 volta su 5).
Prima di modificare qualsiasi cosa, riproduci il fallimento: esegui
<comando_test> --repeat 20 e mostrami l'output.
Poi individua la causa: non aggiungere attese arbitrarie (sleep) e non
disabilitare il test.
Condizione di fine: <comando_test> --repeat 20 passa 20 volte su 20, e mi spieghi
in tre righe perché il test era instabile.
```

**Perché la condizione di fine funziona:** il numero ("20 su 20") trasforma un problema probabilistico in un criterio binario. La richiesta di spiegazione in tre righe impedisce la "riparazione" per tentativi.

**Cosa aspettarsi:** il divieto esplicito di `sleep` è necessario: senza, la soluzione proposta sarà quasi sempre un'attesa più lunga, che sposta il problema invece di risolverlo. Le cause tipiche sono una condizione di gara su una scrittura o un ordinamento non deterministico.

**Cosa controllare prima di tenere il risultato:**
- il test non è stato marcato come `skip` o allentato nelle asserzioni;
- la spiegazione corrisponde al diff (se non corrisponde, il diff è un caso e la spiegazione un racconto);
- rilancia tu il comando: la verifica non è quella che ti è stata mostrata, è quella che esegui.
