# 04 — Documentazione dal codice

**Quando serve:** un modulo funziona ma nessuno ricorda più cosa fa, e la documentazione esistente descrive una versione di due anni fa.

**Brief:**

```text
Leggi <modulo_o_cartella> e scrivi <file_doc> in italiano.
Deve contenere, per ogni funzione pubblica: cosa fa, input attesi, cosa
restituisce, casi di errore e un esempio d'uso ricavato dal codice reale.
Requisiti:
- ogni affermazione deve essere verificabile nel codice: se qualcosa non è
  deducibile, scrivi "da confermare" invece di inventarlo;
- non descrivere funzioni private;
- niente frasi generiche tipo "questa funzione gestisce i dati".
Condizione di fine: elenca le funzioni pubbliche trovate e mostrami che ognuna
compare nel documento, con il riferimento al file e alla riga.
```

**Perché la condizione di fine funziona:** l'elenco finale rende visibile il tasso di copertura. Senza, la documentazione sembra completa ma spesso salta le funzioni più complicate (che sono quelle che servono).

**Cosa aspettarsi:** la frase "da confermare" è la parte più utile del brief. Un documento con tre punti incerti è più affidabile di uno che finge di sapere tutto.

**Cosa controllare prima di tenere il risultato:**
- apri a caso due funzioni documentate e verifica gli esempi;
- cerca quanti "da confermare" ci sono: se sono troppi, il codice è illeggibile e va prima rifattorizzato (brief 03);
- controlla che nessun esempio contenga dati reali o credenziali.
