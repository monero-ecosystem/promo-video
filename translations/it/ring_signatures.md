## 1) Introduzione

Monero è una moneta elettronica, sicura e non tracciabile. E' opensource, decentralizzata e liberamente accessible a tutti.
In questo video, ci concentreremo sulle firme ad anello.
 
## 2) Ripasso sulla tecnologia
 
Nel video precedente abbiamo spiegato come gli indirizzi nascosti Monero assicurano che gli output non possano essere associati all'indirizzo pubblico del destinatario.
Questo è possible grazie all'utilizzo di chiavi di destinazione pubbliche monouso.
Le chiavi pubbliche monouso sono spendibili solamente dal destinatario, e solo il destinatario è in grado di rilevare il suo output designato sulla blockchain.
Dal momento che tutti gli output non sono collegabili fra loro, viene garantita la privacy del destinatario.

Dal lato dell'input della transazione, la privacy del mittente è protetta mediante l'utilizzo delle firme ad anello.

## 3) Terminologia - Firme ad Anello (Ring Signatures), Immagine della chiave (Key Image)

Una firma ad anello (ring signature) è un tipo di firma digitale nella quale più potenziali firmatari vengono fusi insieme per produrre una firma distintiva che autorizza una transazione.
E' l'analogo di una firma su un assegno di un conto bancario cointestato, ma di cui il vero firmatario resta ignoto.
La firma digitale è composta da quella del vero firmatario combinato con quella dei non firmatari per formare un "anello", dove tutti i membri sono uguali fra loro ed altrettanto validi.
Il vero firmatario è una chiave monouso di spesa associata ad un output che viene speso dal portafoglio del mittente.
I non firmatari sono output di transazioni precedenti, estratti dalla blockchain, che funzionano come esche (decoy).
Questi output, combinati insieme, vanno a formare gli input di una transazione.
Ad un osservatore esterno tutti gli input appaiono, in egual misura,  equivalenti all'output che viene speso nella transazione.
Questa funzionalità aiuta il mittente a nascondere l'origine della transazione, rendendo tutti gli input indistinguibili fra di loro.

Ora potreste chiedervi: "se un osservatore esterno non ha la possibilità di verificare quale output viene speso, chi mi assicura che qualcuno non possa spendere lo stesso output due volte?"
Questo potenziale problema viene risolto mediante l'uso delle "immagini della chiave" (key images).
Un'immagine della chiave è una chiave crittografica derivata da un output che viene speso e viene inclusa in ogni transazione basata su firme ad anello.
Può esistere solamente un'immagine della chiave per ogni output sulla blockchain ed inoltre, grazie alle sue proprietà crittografiche, non è possibile determinare quale output abbia generato una determinata immagine della chiave.
All'interno della blockchain viene mantenuta una lista di tutte le immagini delle chiavi utilizzate, dando la possibilità ai minatori di verificare che nessun output venga speso due volte.

Ora vediamo un esempio di come funziona tutto questo.

## 4) Transazione basata su firme ad anello

Alice vuole inviare dei Moneroj a Bob con un "ringsize" (dimensione dell'anello) pari a cinque.
Uno di questi cinque input proverrà dal portafoglio di Alice e verrà consumato nella transazione.
Gli altri quattro input sono arbitrariamente estratti dalla blockchain e vengono usati come esche.
Viene formato quindi un gruppo di cinque possibili firmatari ed ognuno di questi potrebbe essere il vero firmatario della transazione.
Ad un osservatore esterno, Bob incluso, non è chiaro quale input sia stato veramente firmato dalla chiave monouso di spesa di Alice.
Eppure, grazie all'immagine della chiave, la rete è in grado di confermare con sicurezza che i Moneroj trasferiti a Bob non siano stati spesi due volte.
Come potete vedere, grazie all'utilizzo delle firme ad anello, Monero protegge la privacy del mittente oscurando la sorgente degli input e, facendo questo, garantisce che l'origine di ogni Monero rimanga non tracciabile.

## 5) RingCT

Per aumentare la privacy di entrambe le parti sono state implementate le Transazioni Confidenziali ad Anello (Ring Confidential Transactions), comunemente note come RingCT, al fine di nascondere l'ammontare delle transazioni.
RingCT porta alcuni miglioramenti al protocollo delle firme ad anello.
Affronteremo in dettaglio l'argomento RingCT nel nostro prossimo video.

## 6) La fine?

Se siete interessati a ciò che rende Monero la criptovaluta leader focalizzata sulla privacy, guardate gli altri video o visitate il sito getmonero.org.
