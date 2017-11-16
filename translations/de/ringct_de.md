## 1) - Einleitung

Monero ist sicheres, nicht nachverfolgbares, elektronisches Bargeld. Es ist open-source, dezentral und frei zugänglich für alle.
In diesem Video werden wir uns auf Ring Confidential Transactions (vertrauliche Ringtransaktionen) konzentrieren, gemeinhin bekannt als RingCT.

## 2) - Kurze Wiederholung der Technologie

In unserem letzten Video haben wir gezeigt, wie Monero-Ringsignaturen die Privatsphäre der Sender schützen, indem sie verhindern, dass Transaktionsinputs voneinander unterschieden werden können.
Dies wird durch die Verwendung digitaler Signaturen erreicht, bei denen ein tatsächlicher Unterzeichner unter mehreren Ringmitgliedern versteckt ist, um eine Transaktion zu autorisieren.
Außerdem haben wir gelernt, dass Schlüsselbilder (Key Images) verwendet werden, um zu verhindern, dass Monero-Inputs öfters als einmal ausgegeben werden.
Ringsignaturen stellen die Privatsphäre des Senders sicher, da Inputs nicht nachverfolgbar sind.
Zur Erhöhung der Privatsphäre beider Parteien in einer Transaktion wurde RingCT implementiert, um die Transaktionsbeträge verborgen zu halten.

## 3) - Der Aufbau von Ring CT

Vor der Implementierung von RingCT mussten Monero-Transaktionsbeträge in bestimmte Stückelungen aufgeteilt werden.
Zum Beispiel würde ein Output von 12,5 Monero in drei separate Ringe mit Beträgen von 10, 2 und 0,5 aufgeteilt werden.
Diese Technik stellte sicher, dass es genügend Ringmitglieder geben würde, da eine Ringsignatur nur Outputs desselben Werts verknüpfen konnte.
Ein Nachteil dieses Prozesses ist jedoch, dass ein externer Beobachter in der Lage war, die transferierten Beträge zu sehen.
Um diesen Mangel zu beheben, hat Monero im Januar 2017 RingCT aktiviert.
RingCT verhindert Lecks in der Privatsphäre, indem Transaktionsbeträge in der Blockchain versteckt werden.
Einen Monat nach der Aktivierung von RingCT nutzten etwa 98% der neuen Transaktionen das RingCT-Protokoll.
Ab September 2017 ist die Nutzung von RingCT für alle Monero-Transaktionen verpflichtend.


## 4) - Nicht-technische RingCT-Attributes

Mit RingCT liegt heute ein neu geschöpfter Monero zunächst in Outputs, die sichtbare Beträge haben.
Wenn der neue Monero erstmals transferiert wird, werden RingCT-Outputs mit maskierten Beträgen erzeugt.
Infolgedessen müssen Transaktionen nicht mehr in verschiedene Stückelungen aufgeteilt werden.
Dies bedeutet, dass eine Wallet Ringmitglieder von beliebigen RingCT-Outputs auswählen kann, was die Privatsphäre erheblich erhöht.
Es sollte beachtet werden, dass Monero-Ringsignaturen nicht sowohl Vor-RingCT-Outputs als auch maskierte RingCT-Outputs in einem einzelnen Ring enthalten können, also - wie bei neu geschöpften Monero - muss ein Vor-RingCT-Output zuerst in einen RingCT-Output umgewandelt werden, bevor er in eine Ringsignatur mit anderen RingCT-Outputs eingeschlossen werden kann.
Lassen Sie uns ein Beispiel gemeinsam durchgehen und dann tiefer eintauchen, um zu sehen, wie RingCT funktioniert.

## 5) – RingCT-Transaktion und technische Attribute

Alice hat einen Output von 12,56 und möchte Bob 2,5 Monero senden.
Da Outputs nicht zweimal ausgegeben werden können, muss Alice den Output zur Gänze ausgeben und den Restbetrag an sich selbst zurückgeben.
Also hätte Alice' Transaktion einen Input von 12,56 Monero und zwei Outputs - einen für Bob bestimmten von 2,5 Monero und einen anderen, der 10,06 Monero beträgt und an ihre Wallet als „Wechselgeld“ der Transaktion zurückgesendet wird.
Um zu beweisen, dass keine Monero auf betrügerische Weise in einer Transaktion erzeugt wurden, muss die Summe der Inputs einer Transaktion der Summe ihrer Outputs entsprechen.
Aufgrund der kryptographischen Eigenschaften von RingCT ist Alice dazu angehalten, sich an den Betrag eines Outputs zu „binden“, wobei sie dem Netzwerk gerade genug Informationen offenbart, um die Transaktion zu bestätigen, während sie den Betrag, den sie ausgibt, nicht öffentlich mitteilt.
Obwohl Bindungen wie Zufallszahlen aussehen, können Miner dennoch bestätigen, dass der an Bob gesendete Betrag an Monero dem der verfügbaren Mittel entspricht. [Siehe Note 1]
Ein weiterer wichtiger Aspekt einer RingCT-Transaktion ist der „Range Proof“ (Beweis des Wertebereichs), der Sender daran hindert, sich an negative Werte zu binden, um das Moneroangebot zu sichern.
Ein Range Proof beweist kryptographisch, dass die in einer Transaktion verwendete Beträge größer 0 und kleiner als eine beliebige Zahl sind.
Während ein externer Beobachter nicht in der Lage ist, die tatsächlichen Beträge in den Outputs einer Transaktion zu sehen, kann er bestätigen, dass die Transaktion legitim ist und das Netwerk sie akzeptieren sollte.

## 6) - Fazit

Als Ergebnis der integrierten Datenschutzfunktionen von Monero können Nutzer Monero senden, an wen auch immer sie möchten. Und niemand wüsste, wie viel gesendet wurde noch wer der Sender oder der Empfänger war.
Diese Qualitäten machen Monero zu einer führenden privatsphärezentrierten Kryptowährung, doch die Innovation hört dort nicht auf.
In unserem nächsten Video besprechen wir Kovri: einen C++-I2P-Router, der Monero-Transaktionen sicherer macht als je zuvor.

## 7) - Das Ende?

Wenn Sie interessiert daran sind, was Monero zur führenden privatsphärezentrierten Kryptowährung macht, sehen Sie sich gerne die anderen Videos an oder besuchen Sie getmonero.org.

--------------------------------------------------

Note 1. Folgendes könnte auf dem Bildschirm im Abschnitt zu den Bindungen wiedergegeben werden, sollte aber nicht gesprochen werden.

Diese Bindung nimmt die Form dieser Formel an (rct = x*G + a*H(G)).
Die zwei wichtigsten Variablen, die hier betrachtet werden sollten, sind a und x.
H(G) und G sind von vielen anderen Faktoren abhängig, die außerhalb des Rahmens dieses Videos liegen.
a ist der tatsächliche Betrag, der in der Transaktion gesendet wird, in diesem Fall 2,5.
x ist eine Zufallszahl, die als Maske fungiert und automatisch von Ihrer Wallet-Software erzeugt wird.
Im einfachsten Sinne können wir diese Gleichung umschreiben als rct = ein Zufallswert + ein realer Wert.

Sie können den Wert 'rct' dem Rest des Netzwerks als Ouput mitteilen und das Netzwerk kann damit überprüfen, dass Ihre Transaktion legitim ist. Dies kann genutzt werden, um zu überprüfen, dass die Summe der in der Transaktion verwendeten Inputs der Summe der Outputs entspricht.
Da ein externer Beobachter jedoch die zuvor von Ihnen erzeugte Variable x nicht kennt, hat er keine Möglichkeit zu wissen, wie viel in der Transaktion ausgegeben wurde.
