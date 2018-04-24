## 1) - Intro

Monero è una moneta elettronica, sicura e non tracciabile. E' opensource, decentralizzata e liberamente accessible a tutti.
In questo video ci concentreremo su una tecnologia per l'anonimato chiamata Kovri.

## 2) - Ripasso sulla tecnologia

Finora abbiamo spiegato come Monero offusca le informazioni registrate sulla blockchain.
Le firme ad anello oscurano il mittente.
Gli indirizzi nascosti garantiscono che osservatori esterni non possano conoscere l'indirizzo di destinazione.
Le RingCT nascondono l'ammontare del Moneroj che vengono trasferiti.
Eppure sulla rete possono trapelare alcune informazioni personali quando viene effettuata una transazione.
Questo problema viene affrontato da Kovri.

## 3) - La terminologia - Kovri

Kovri è una tecnologia per l'anonimato gratuita, decentralizzata e basata sulle specifiche aperte di I2P.
Kovri utilizza tecniche sofisticate di cifratura e di routing per creare una sovrastruttura di rete privata su internet.
Questa sovrastruttura protetta consente agli utenti di nascondere la propria posizione geografica ed il proprio indirizzo IP.
Un indirizzo IP è come un indirizzo di casa per internet, pertanto è un dato a dir poco sensibile.

## 4) Esempi

Consideriamo alcuni scenari per vedere come questo software leggero e focalizzato sulla privacy aiuta a rafforzare la privacy dell'utente.
Supponiamo che Alice voglia inviare dei Moneroj a Bob.
Il portafoglio di Alice crea una transazione e la trasmette alla rete Monero.
La rete Monero è formata da nodi che comunicano fra loro trasmettendosi messaggi ed utilizzando i propri indirizzi IP.
Questo significa che è possibile tracciare i dati a livello geografico mentre essi transitano su internet, dal punto iniziale al punto finale passando per tutti i punti intermedi.
Anche se gli indirizzi di portafoglio del mittente e del destinatario - come anche l'ammontare dei Moneroj trasferiti - rimangono privati, Alice corre un rischio quando trasmette la sua transazione poiché alcuni nodi potrebbero registrare gli indirizzi IP.
Un avversario con risorse sufficienti potrebbe tentare di associare le transazioni agli indirizzi IP per determinare il luogo da cui sono state generate.
Questo tentativo potrebbe portare l'avversario a non ritrasmettere la transazione di Alice al resto della rete; o, ancor peggio, a presentarsi alla porta di Alice.
Immaginiamo ora uno scenario differente.
Supponiamo che Charlie voglia supportare la rete Monero tenendo attivo un nodo a casa propria.
Dopo alcune settimane, Charlie riceve una lettera di diffida da parte del suo internet provider il quale sostiene che tenere attivo un nodo costituisce una violazione dei termini di servizio.
Oppure considerate questo: supponiamo che Dave sia un operatore di un pool di minatori che dona una parte della ricompensa di blocco ad un partito politico o per una causa controversa.
Gli altri nodi potrebbero rigettare scientemente i blocchi da lui risolti per esprimere il loro disappunto verso la sua visione politica o sociale.
Alice, Bob, Charlie e Dave, fra di loro, hanno almeno una cosa in comune: i loro indirizzi IP sono esposti.
Gli utenti potrebbero provare a nascondere il proprio indirizzo IP utilizzando Tor o una VPN, ma purtroppo entrambe le strategie presentano debolezze non di poco conto.
La rete Tor possiede Autorità di Directory "semi-fidate" che conferiscono ad un piccolo gruppo di operatori di nodi Tor un'influenza superiore sul consensus della rete.
Il consensus della rete determina sostanzialmente chi ha il permesso di inoltrare il traffico sulla rete Tor basandosi sulla visione di suddette Autorità.
Inoltre, attacchi basati su correlazione sono possibili su VPN fidate, rendendo, per attaccanti di rilievo, molto semplice la de-anonimizzazione del traffico degli utenti.
Quindi cosa possono fare Alice, Bob, Charlie e Dave per rispondere a queste minacce?
Possono usare Kovri!
Se usano esclusivamente Kovri per connettersi alla rete Monero, nessuno conoscerà mai i loro indirizzi IP, rendendo quindi inattuabile la sorveglianza passiva, e allo stesso tempo migliorando in modo sostanziale la resistenza di Monero alla censura.
Come potete vedere, Kovri è un software che consente agli utenti di inviare transazioni in modo ancora più privato.
Addentriamoci ora in alcuni dettagli tecnici per avere una migliore comprensione su come Kovri lavora al suo interno.

## 5) Kovri e gli Attributi Tecnici

Kovri convoglia il traffico attraverso la rete I2P utilizzando una "cifratura ad aglio" e un "routing ad aglio".
Le informazioni viaggiano all'interno di una sovrastruttura di rete privata attraverso messaggi che vengono cifrati in più strati ogniqualvolta il messaggio transita attraverso i diversi nodi della rete, similarmente a come funziona una Matrioska.
Ogni bambola interna possiede un lucchetto e una chiave pubblica verso la prossima bambola. I nodi nella rete non hanno la possibilità di leggere il contenuto del messaggio che viene inoltrato; in questo modo le informazioni inviate dal mittente al destinatario (e viceversa) sono rese sicure.
Le uniche informazioni visibili ai nodi sono le istruzioni per inoltrare il messaggio al prossimo nodo.
Per rafforzare ulteriormente la privacy, pagando un piccolo prezzo in termini di performance, gli utenti possono connettersi a più nodi.
Essenzialmente, Kovri copre il traffico internet di un'applicazione per renderlo anonimo all'interno della rete.
Grazie a queste caratteristiche, Kovri è un'ottima soluzione per comunicare su IRC, via email, o per accedere a servizi nascosti.

## 6) - Conclusioni

Kovri rivoluzionerà le connessioni peer-to-peer ed aumenterà globalmente la resilienza e la privacy della rete.
Nodi malevoli non potranno più minacciare gli utenti che creano transazioni né bloccare la trasmissione delle transazioni sulla rete.
Kovri verrà reso disponibile all'interno dei futuri rilasci di Monero e sarà abilitato di default.
Inoltre, Kovri implementerà delle API che ne consentiranno l'utilizzo anche ad altre criptovalute ed applicazioni, non solo a Monero.

Per conoscere meglio Monero ed il progetto Kovri, visitate i siti getmonero.org e getkovri.org.
