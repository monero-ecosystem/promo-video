## 1) - Einleitung

Monero ist sicheres, nicht nachverfolgbares, elektronisches Bargeld. Es ist open-source, dezentral und frei zugänglich für alle.
In diesem Video werden wir uns auf Ringsignaturen konzentrieren.
 
## 2) - Kurze Wiederholung der Technologie

In unserem letzten Video haben wir gezeigt, wie Monero-Tarnadressen (Stealth Addresses) verhindern, dass Outputs der öffentlichen Adresse eines Empfängers zugeordnet werden.
Dies erreicht man durch die Verwendung öffentlicher Schlüssel mit Einmalzielen.
Einmalige öffentliche Schlüssel können nur vom Empfänger ausgegeben werden und nur der Empfänger kann seinen vorgesehenen Ouput in der Blockchain ausfindig machen.
Da Outputs nicht verknüpft werden können, ist die Privatsphäre des Empfängers gewährleistet.
Auf der Inputseite der Transaktion wird die Privatsphäre des Senders durch die Verwendung von Ringsignaturen geschützt.

## 3) - Der Begriff - Ringsignaturen, Schlüsselbild (Key Image)

Eine Ringsignatur ist eine Art digitaler Signatur, bei der eine Gruppe möglicher Unterzeichner miteinander verschmolzen werden, um eine unverwechselbare Signatur zu erzeugen, die eine Transaktion autorisiert.
Dies ist analog zur Unterzeichnung eines Schecks von einem gemeinsamen Bankkonto, wobei jedoch der eigentliche Unterzeichner unbekannt bleibt.
Die digitale Signatur besteht aus dem tatsächlichen Unterzeichner, der mit Nicht-Unterzeichnern vermischt wird, um einen „Ring“ zu bilden, in dem alle Mitglieder gleichwertig und gültig sind.
Der eigentliche Unterzeichner ist ein einmaliger Ausgabeschlüssel (Spend Key), der zu einem von der Wallet des Senders ausgegebenen Output passt.
Die Nicht-Unterzeichner sind der Blockchain entnommene vergangene Transaktionsoutputs, die als Ablenkung dienen.
Diese Outputs bilden zusammen die Inputs einer Transaktion.
Für eine dritte Partei scheinen alle Inputs gleich wahrscheinlich der Output zu sein, der in der Transaktion ausgegeben wird.
Diese Funktionalität hilft dem Sender, den Ursprung der Transaktion zu verbergen, in dem sie dafür sorgt, dass alle Inputs nicht voneinander zu unterscheiden sind.

Sie fragen sich jetzt vielleicht: „Wenn es keine Möglichkeit für eine dritte Partei gibt, zu überprüfen, welcher Output ausgegeben wird, was würde jemanden daran hindern, denselben Output zweimal auszugeben?“
Dieses potentielle Problem wird durch die Verwendung von „Schlüsselbildern“ (Key Images) angegangen.
Ein Schlüsselbild ist ein kryptographischer Schlüssel, der von einem ausgegebenen Output abgeleitet wird und Teil jeder Ringsignatur-Transaktion ist.
Es kann nur jeweils ein Schlüsselbild für jeden Output in der Blockchain existieren, aufgrund seiner kryptographischen Eigenschaften ist es trotzdem nicht möglich zu ermitteln, welcher Output welches Schlüsselbild erzeugt hat.
Eine Liste aller verwendeten Schlüsselbilder wird in der Blockchain verwaltet, sodass Miner überprüfen können, dass keine Outputs doppelt ausgegeben werden.

Schauen wir uns ein Beispiel an, um zu sehen, wie all das funktioniert.

## 4) – Ringsignaturen-Transaktion

Alice möchte Bob Monero mit einer „Ringgröße“ von fünf schicken.
Einer der fünf Inputs wird aus Alice' Wallet stammen und bei der Transaktion verbraucht werden.
Die anderen vier Inputs werden beliebig aus der Blockchain ausgewählt und als Ablenkung verwendet.
So entsteht eine Gruppe von fünf möglichen Unterzeichnern, wobei alle Ringmitglieder glaubhaft der tatsächliche Unterzeichner der Transaktion sind.
Einem externen Beobachter, einschließlich Bob selbst, ist nicht klar, welcher Input wirklich von Alice' einmaligem Ausgabeschlüssel signiert wurde.
Mit dem Schlüsselbild kann das Netzwerk jedoch sicher bestätigen, dass der an Bob gesendete Monero nicht vorher schon ausgegeben wurde.
Wie Sie sehen können, schützt Monero durch die Verwendung von Ringsignaturen die Privatsphäre des Senders, indem der Ursprung der Inputs verschleiert wird, und stellt dadurch sicher, dass der Ursprung jedes Monero nicht nachverfolgbar bleibt.

## 5) RingCT

Um die Privatsphäre beider Parteien zu erhöhen, wurden Ring Confidential Transactions (vertrauliche Ringtransaktionen), gemeinhin als RingCT bezeichnet, implementiert, um Transaktionsbeträge zu verbergen.
RingCT sorgt für einige Verbesserungen des Ringsignaturprotokolls.
Wir werden in unserem nächsten Video mehr über RingCT sprechen.

## 6) - Das Ende?

Wenn Sie interessiert daran sind, was Monero zur führenden privatsphärezentrierten Kryptowährung macht, sehen Sie sich gerne die anderen Videos an oder besuchen Sie getmonero.org.
