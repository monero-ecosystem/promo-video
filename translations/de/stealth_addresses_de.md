## 1) - Einleitung

Monero ist sicheres, nicht nachverfolgbares, elektronisches Bargeld. Es ist open-source, dezentral und frei zugänglich für alle.
In diesem Video werden wir uns auf Tarnadressen (Stealth Addresses) konzentrieren.
 
## 2) - Kurze Wiederholung der Technologie

Lassen Sie uns einen Schritt zurückgehen und kurz einige Konzepte aus dem vorherigen Video wiederholen.
Wir haben gelernt, dass Monero ein verteiltes Peer-to-Peer-Konsensnetzwerk verwendet, um Transaktionsoutputs in einer Blockchain zu erfassen.
Falls Alice Monero besitzt, bedeutet dies, dass Sie die alleinige Kontrolle über einige dieser Outputs hat.
Wenn Alice Monero an Bob schickt, dann verkündet Alice dem Netzwerk, dass sie den Wert von einigen ihrer Outputs auf einen ganz neuen Output für Bob übertragen will, den nur er kontrollieren kann.
Mit anderen Worten ist eine Transaktion die Umwandlung alter Outputs, die zu einer Wallet gehören, in neue Outputs, die zu einer anderen angehören.
Gehen wir noch einen Schritt weiter, um zu sehen, wie Tarnadressen die Privatsphäre eines Benutzers verbessern.

## 3) - Der Begriff - Tarnadressen (Stealth Addresses)

Bei jeder Transaktion wird automatisch eine Tarnadresse, auch als einmaliger öffentlicher Schlüssel bekannt, erstellt und als Teil der Transaktion festgehalten, um anzugeben, wer einen Output bei einer späteren Transaktion ausgeben kann.
Ein externer Beobachter kann weder sagen, ob Geld von Alice zu Bob fließt, noch Wallet-Adressen miteinander verknüpfen, einfach indem er sich die Blockchain ansieht.
Wenn Alice also Monero an Bob schickt, wird der von Bob erhaltene Output nicht öffentlich Bobs Wallet-Adresse zugeordnet.
Falls Alice allerdings jemals beweisen muss, dass sie tatsächlich Monero an Bob geschickt hat, kann ihre Wallet belegen, dass die Zahlung getätigt wurde.
Bob kann versichert sein, dass niemand sonst sehen kann, wann oder ob irgendein Monero zu ihm geschickt wurde.
Wenn Bob ein Händler wäre, wäre diese Funktionalität ein großer Vorteil, denn niemand kann sagen, wie viele verschiedene Kunden er hat, ob es sich dabei um Stammkunden handelt oder ob er überhaupt Kunden hat.
Schnallen Sie sich jetzt an, denn wir sind im Begriff, ein paar ziemlich technische Dinge zu besprechen.

## 4) - Einmalziele

Eine Monero-Wallet-Adresse ist ein 95-stelliger String, der aus einem öffentlichen Betrachtungsschlüssel (View Key) und einem öffentlichen Ausgabeschlüssel (Spend Key) besteht.
Wenn Alice Bob Monero schickt, wird Alice' Wallet Bobs öffentlichen Betrachtungsschlüssel und öffentlichen Ausgabeschlüssel sowie einige Zufallsdaten verwenden, um einen eindeutigen einmaligen öffentlichen Schlüssel für Bobs neuen Output zu erzeugen.
Jeder kann den einmaligen öffentlichen Schlüssel auf der Blockchain sehen, aber nur Alice und Bob wissen, dass Alice Monero zu Bob geschickt hat.
Der Output wird so erstellt, dass Bob in der Lage ist, den für ihn bestimmten Output zu lokalisieren, indem er die Blockchain mit dem privaten Betrachtungsschlüssel seiner Wallet durchsucht.
Sobald der Output von Bobs Wallet ermittelt und abgerufen wurde, könnte er einen einmaligen privaten Schlüssel errechnen, der zum einmaligen öffentlichen Schlüssel passt, und den entsprechenden Output mit dem privaten Ausgabeschlüssel seiner Wallet ausgeben.
Dieser gesamte Prozess erfolgt, ohne dass jemals Bobs Wallet-Adresse öffentlich mit irgendeiner Transaktion in Verbindung gebracht wird. 

## 5) - Bindung an Ringsignaturen

Wie Sie sehen können, verhindern Tarnadressen, dass man Outputs Wallet-Adressen zuordnen kann.
Die Privatsphäre des Senders wird durch die Verwendung von Ringsignaturen geschützt.
Ringsignaturen helfen, den Ursprung der Outputs zu verschleiern.
In unserem nächsten Video werden wir das Konzept der Ringsignatur näher behandeln und sehen, wie diese Funktionalität Monero nicht nachverfolgbar macht.

## 6) - Das Ende?

Wenn Sie interessiert daran sind, was Monero zur führenden privatsphärezentrierten Kryptowährung macht, sehen Sie sich gerne die anderen Videos an oder besuchen Sie getmonero.org.
