## 1) - Intro

Monero è una moneta elettronica, sicura e non tracciabile. E' opensource, decentralizzata e liberamente accessible a tutti.
In questo video, ci concentreremo sugli indirizzi nascosti.
 
## 2) - Ripasso sulla tecnologia

Facciamo un passo indietro, e ripassiamo brevemente alcuni concetti esposti nel video precedente.
Abbiamo imparato che Monero utilizza una rete di consenso peer-to-peer distribuita per registrare gli output delle transazioni in una blockchain.
Se Alice possiede dei Moneroj, significa che lei ha un controllo esclusivo su alcuni di questi output.
Quando Alice invia dei Moneroj a Bob, Alice annuncia alla rete di voler trasferire il valore di alcuni degli output in suo possesso ad un nuovo output di Bob, che solo lui può controllare.
In altre parole, una transazione è la trasformazione di vecchi output che appartengono ad un portafoglio in nuovi output che appartengono ad un altro portafoglio.
Facciamo ora un passo avanti, per vedere come gli indirizzi nascosti migliorano la privacy degli utenti.

## 3) - Terminologia - Indirizzi Nascosti (Stealth Addresses)

In ogni transazione, un indirizzo nascosto (stealth address), noto anche come chiave pubblica monouso, viene automaticamente generato e registrato come parte della transazione per indicare chi può spendere un output in una transazione successiva.
Un osservatore esterno non può sapere se i fondi si muovono da Alice a Bob e non può neanche collegare fra loro gli indirizzi dei loro portafogli solamente guardando la blockchain.
Pertanto, quando Alice invia dei Moneroj a Bob, l'output che Bob riceve non sarà pubblicamente associato all'indirizzo del portafoglio di Bob.
Comunque, se Alice volesse ottenere prova di aver inviato Moneroj a Bob, il suo portafoglio consentirebbe di verificare che il pagamento è stato effettuato.
Bob può stare certo che nessun altro può vedere se e quando gli sono stati inviati dei Moneroj.
Se Bob fosse un venditore, questa funzionalità potrebbe risultare molto comoda, poiché nessuno potrebbe capire quanti clienti ha, se questi clienti sono di ritorno, men che meno se Bob ha clienti.
Ed ora allacciate le cinture: stiamo per affrontare questioni un po' tecniche.

## 4) - Destinazioni monouso

Un indirizzo di portafoglio Monero è una stringa di 95 caratteri, la quale consta di una chiave pubblica di visualizzazione ed una chiave pubblica di spesa.
Quando Alice invia dei Moneroj a Bob, il portafoglio di Alice userà la chiave pubblica di visualizzazione e la chiave pubblica di spesa di Bob, insieme ad alcuni dati casuali, al fine di generare un'unica chiave pubblica monouso per il nuovo output di Bob.
Chiunque può vedere la chiave pubblica monouso sulla blockchain, ma solamente Alice e Bob sanno che Alice ha inviato dei Moneroj a Bob.
L'output è creato in modo tale che Bob sia in grado di localizzare l'output a lui destinato scansionando la blockchain con la chiave privata di visualizzazione del suo portafoglio.
Una volta che l'output viene trovato e recuperato dal portafoglio di Bob, Bob è in grado di calcolare una chiave privata monouso associata alla chiave pubblica monouso e spendere tale output utilizzando la chiave privata di spesa del suo portafoglio.
L'intero processo avviene senza che l'indirizzo del portafoglio di Bob sia legato ad alcuna transazione.

## 5) - Legami con le firme ad anello (ring signatures)

Abbiamo visto che gli indirizzi nascosti assicurano che gli output non possano essere associati agli indirizzi di portafoglio.
La privacy del mittente è assicurata grazie all'uso delle firme ad anello (ring signatures).
Le firme ad anello aiutano ad offuscare la sorgente degli output.
Nel prossimo video, esporremo più in dettaglio il concetto delle firme ad anello e vedremo come questa caratteristica garantisce la non tracciabilità in Monero.

## 6) - La fine?

Se siete interessati a ciò che rende Monero la criptovaluta leader focalizzata sulla privacy, guardate gli altri video o visitate il sito getmonero.org.
