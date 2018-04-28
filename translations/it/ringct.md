## 1) Introduzione

Monero è una moneta elettronica, sicura e non tracciabile. E' opensource, decentralizzata e liberamente accessible a tutti.
In questo video ci concentreremo sulle Transazioni Confidenziali ad Anello (Ring Confidential Transactions), note anche come RingCT.
 
## 2) Ripasso sulla tecnologia
 
Nel nostro ultimo video abbiamo spiegato come le firme ad anello di Monero proteggono la privacy del mittente garantendo che gli input della transazione siano indistinguibili gli uni dagli altri.
Questo risultato viene ottenuto grazie ad un particolare uso delle firme digitali per cui il vero firmatario viene nascosto in mezzo a più membri dell'anello per autorizzare una transazione.
Abbiamo inoltre imparato che vengono usate le immagini della chiave per evitare che gli input di Monero vengano spesi più di una volta.
Le firme ad anello garantiscono la privacy del mittente dal momento che gli input non sono tracciabili.
Per aumentare la privacy di entrambe le parti sono state implementate le RingCT al fine di nascondere l'ammontare delle transazioni.

## 3) L'introduzione delle RingCT

Prima dell'implementazione delle RingCT, Monero aveva bisogno degli ammontare della transazione per poter essere diviso in specifiche denominazioni.
Ad esempio, un output di 12,5 Moneroj veniva partizionato in tre separati anelli da 10, 2 e 0,5.
Questa tecnica garantiva che l'anello usato per le firme fosse ampio, poiché a quel tempo la firma ad anello poteva associare solamente output del medesimo valore.
Eppure, lo svantaggio di questa tecnica era che un osservatore esterno aveva la possibilità di vedere gli ammontare della transazione.
Per risolvere questo problema, Monero ha attivato le RingCT nel gennaio del 2017.
Le RingCT evitano perdite di privacy nascondendo l'ammontare delle transazioni sulla blockchain.
Un mese dopo l'attivazione delle RingCT, approssimativamente il 98% delle nuove transazioni usavano il protocollo RingCT.
Da settembre 2017, l'uso delle RingCT è obbligatorio per tutte le transazioni Monero.

## 4) Caratteristiche non tecniche delle RingCT

Oggi, con le RingCT, i nuovi Moneroj creati risiedono dapprima negli output che possiedono ammontare visibili.
Quando viene trasferito per la prima volta un nuovo Monero, vengono generati output RingCT con ammontare mascherato.
Il risultato è che ora le transazioni non devono essere più partizionate in differenti denominazioni.
Questo significa che un portafoglio è libero di selezionare i membri dell'anello da ogni output RingCT, cosa che migliora significativamente la privacy.
E' bene notare che le firme ad anello di Monero non possono includere all'interno dello stesso anello output pre-RingCT e RingCT. Pertanto un output pre-RingCT (ad esempio i nuovi Moneroj generati) deve essere convertito in un output RingCT prima di poter essere incluso in una firma ad anello con altri output RingCT.
Ora vediamo un esempio, per poi entrare nello specifico su come funzionano le RingCT.

## 5) RingCT e caratteristiche tecniche

Alice ha un output di 12,56 e vorrebbe inviare 2,5 Moneroj a Bob.
Dal momento che gli output non possono essere spesi due volte, Alice ha bisogno di spendere l'output nella sua interezza e far tornare il resto a se stessa.
Quindi, la transazione di Alice avrà un input da 12,56 Moneroj e due output - uno composto dai 2,5 Moneroj indirizzati a Bob e l'altro composto da 10,06 Moneroj che vengono inviati al portafoglio di Alice come "resto" della transazione.
Per provare che nessun Monero è stato generato in modo fraudolento in una transazione, la somma degli input della transazione deve essere uguale a quella degli output.
Grazie alle proprietà crittografiche delle RingCT, ad Alice è richiesto di "prendere un impegno" ("commit") sull'ammontare di un output, ovvero rivelando le minime informazioni richieste dalla rete per confermare la transazione, senza però rivelare pubblicamente l'ammontare che sta spendendo.
Nonostante gli "impegni" ("commitments") appaiano come numeri casuali, i minatori sono ancora in grado di confermare che l'ammontare di Moneroj inviati a Bob è lo stesso dell'ammontare di fondi disponibile. [Vedi Nota 1]
Un altro aspetto importante di una transazione RingCT è la "prova di intervallo" ("range proof"), che impedisce ai mittenti di prendere un impegno su valori negativi. In questo modo la fornitura di Moneroj viene resa sicura.
Una prova di intervallo prova crittograficamente che gli ammontare di una transazione sono maggiori di zero e minori di un numero arbitrario.
Sebbene un osservatore esterno non sia in grado di vedere i veri ammontare negli output di una transazione, può comunque confermare che la transazione è legittima e quindi accettabile dalla rete.

## 6) Conclusioni

Grazie alle funzionalità orientate alla privacy offerte da Monero, gli utenti possono trasferire Moneroj a chiunque vogliano; nessuno saprà mai quanti Moneroj sono stati inviati, da chi sono stati inviati e a chi sono stati inviati. 
Queste qualità rendono Monero la criptovaluta leader focalizzata sulla privacy, ma le innovazioni non sono finite qui.
Nel nostro prossimo video parleremo di Kovri: un router I2P, scritto in C++, che rende ancora più sicure le transazioni Monero.

## 7) La fine?

Se siete interessati a ciò che rende Monero la criptovaluta leader focalizzata sulla privacy, guardate gli altri video o visitate il sito getmonero.org.

--------------------------------------------------

Nota 1. Ciò che segue dovrebbe essere proiettato sullo schermo nella sezione degli impegni, ma non dovrebbe essere narrato.

Questo impegno prende la forma di questa formula (rct = x*G + a*H(G)).
Le due variabili più importanti da considerare qui sono a e x.
H(G) e G dipendono da tanti altri fattori che esulano dall'ambito di questo video.
a è il vero ammontare che viene speso nella transazione, in questo caso 2,5.
x è un numero casuale che funziona come maschera e che il tuo software per il portafoglio genererà automaticamente.
Nel significato più semplice, possiamo riscrivere questa equazione come rct = un valore casuale + un valore vero.

Puoi pubblicare il valore 'rct' al resto della rete come un output, e la rete può utilizzare questo valore per verificare che la tua transazione è legittima. Questo può essere usato per verificare che la somma degli input della transazione eguaglia la somma degli output.
Eppure, dal momento che un osservatore esterno non può sapere quale è la variabile x generata prima, non ha la possibilità di conoscere quanto è stato speso nella transazione.
