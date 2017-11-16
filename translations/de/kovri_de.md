## 1) - Einleitung

Monero ist sicheres, nicht nachverfolgbares, elektronisches Bargeld. Es ist open-source, dezentral und frei zugänglich für alle.
In diesem Video werden wir uns auf eine Anonymitätstechnologie namens Kovri konzentrieren.

## 2) - Kurze Wiederholung der Technologie

Bis jetzt haben wir behandelt, wie Monero in der Blockchain gespeicherte Informationen verschleiert, Ringsignaturen den Sender verdecken, Tarnadressen (Stealth Addresses) verhindern, dass externe Beobachter die Empfangsadresse kennen, und RingCT den Betrag an Monero verbirgt, der gesendet wird.
Dennoch können einige persönliche Informationen auf Netzwerkebene durchsickern, wenn man eine Transaktion durchführt.
Dieses Datenleck wird mit Kovri behoben.

## 3) - Der Begriff - Kovri

Kovri ist eine kostenlose, dezentrale Anonymitätstechnologie, die auf den offenen Spezifikationen von I2P basiert.
Kovri verwendet sowohl Verschlüsselung als auch ausgefeilte Routing-Techniken, um ein privates Overlay-Netz über das Internet zu erzeugen.
Mit diesem geschützten Overlay können Benutzer ihren geografischen Standort und ihre IP-Adresse verbergen.
Eine IP-Adresse ist wie eine Privatanschrift für das Internet, also eine ziemlich sensible Information, um es gelinde auszudrücken.

## 4) Beispiele

Gehen wir ein paar Szenarien durch, um zu sehen, wie diese schlanke, sicherheitsorientierte Software hilft, die Privatsphäre eines Nutzers zu stärken.

Angenommen, Alice möchte Bob Monero schicken.
Alice' Wallet erstellt eine Transaktion und sendet sie dann ans Monero-Netzwerk.
Das Monero-Netzwerk besteht aus Netzwerkknoten, die miteinander kommunizieren, indem sie Nachrichten mithilfe von IP-Adressen weiterleiten.
Das bedeutet, dass es möglich sein kann, Daten geografisch zu verfolgen, während sie sich über das offene Internet bewegen, von Anfang bis Ende und überall dazwischen.
Obwohl die Wallet-Adressen des Senders und des Empfängers - wie auch die gesendete Menge an Monero - privat bleiben, geht Alice bei der Übermittlung ihrer Transaktion ein Risiko ein, da einige Netzwerkknoten IP-Adressen aufzeichnen könnten.
Ein Widersacher mit ausreichenden Ressourcen könnte versuchen, Transaktionen mit IP-Adressen zu verknüpfen, um festzustellen, woher die Transaktionen stammen.
Dies könnte potentiell dazu führen, dass ein Widersacher ihre Transaktionen nicht ans restliche Netzwerk weiterleitet oder - schlimmer noch - vor ihrer Haustür steht.

Stellen wir uns nun ein anderes Szenario vor.
Nehmen wir an, Charlie möchte das Monero-Netzwerk unterstützen, indem er einen vollständigen Netzwerkknoten (Full Node) bei sich zu Hause laufen lässt.
Nach ein paar Wochen erhält er von seinem Internetanbieter eine Abmahnung, in der behauptet wird, der Betrieb eines Netzwerkknotens verstoße gegen die Nutzungsbedingungen.

Oder bedenken Sie Folgendes, angenommen, Dave ist ein Betreiber eines Miningpools, der einen Teil der Blockbelohnungen an eine politische Partei oder eine kontroverse Sache spendet.
Andere Netzwerkknoten könnten seine gelösten Blöcke absichtlich ablehnen, um ihre Meinungsverschiedenheiten mit seinen politischen oder gesellschaftlichen Ansichten auszudrücken.

Alice, Bob, Charlie, und Dave haben alle mindestens eines gemeinsam: ihre IP-Adressen wurden offengelegt.
Benutzer könnten versuchen, ihre IP-Adressen mit Tor oder einem VPN zu verbergen. Beide dieser Strategien haben jedoch gravierende Schwächen.
Das Tor-Netzwerk hat „halb vertrauenswürdige“ Verzeichnisserver, die einer Handvoll von Tor-Netzwerkknoten-Betreibern übergreifenden Einfluss auf den Netzwerkkonsens geben.
Der Netzwerkkonsens bestimmt letztlich, wer den Datenverkehr auf dem Tor-Netzwerk weiterleiten darf, basierend auf den Ansichten der Verzeichnisserver.
Darüber hinaus sind Korrelationsangriffe mit vertrauenswürdigen VPNs leicht möglich, was es großen Angreifern einfach macht, den Datenverkehr eines Nutzers zu entanonymisieren.

Was können Alice, Bob, Charlie, und Dave also tun, um diese Bedrohungen zu entschärfen?
Sie könnten Kovri nutzen!
Wenn sie ausschließlich Kovri verwenden, um sich mit dem Monero-Netzwerk zu verbinden, wird niemand ihre IP-Adressen erfahren, wodurch passive Überwachung unpraktisch wird, während die Zensurresistenz von Monero wesentlich verbessert wird.

Wie Sie sehen können, ist Kovri eine Software, mit der Benutzer Transaktionen so privat wie nie zuvor senden können.
Betrachten wir uns als nächstes einige technische Details, um besser zu verstehen, wie Kovri unter der Haube funktioniert.

## 5) Kovri und technische Attribute

Kovri leitet Datenverkehr durch Tunnel im I2P-Netzwerk unter Verwendung von „Garlic-Verschlüsselung“ und „Garlic-Routing“.
Informationen werden innerhalb eines privaten Overlay-Netzes mittels Nachrichten übermittelt, die schichtweise jedes Mal verschlüsselt werden, wenn die Nachricht an Peers im Netzwerk weitergeleitet wird, ähnlich wie bei einer Matrjoschka-Puppe.
Für jede innere Puppe gibt es ein Schloss und einen öffentlichen Schlüssel für die nächste Puppe.
Peers im Netzwerk können den Inhalt der weitergeleiteten Nachricht nicht lesen, Informationen, die vom Sender an ihr Ziel (und vice versa) geschickt werden, sind also geschützt.
Die einzige Information, die für Peers sichtbar ist, ist die Anweisung zum Senden von Nachrichten an den nächsten Peer.
Um für eine größere Privatsphäre bei geringen Leistungseinbußen zu sorgen, können sich Nutzer mit mehreren Peers verbinden.
Im Wesentlichen ummantelt Kovri den Internetverkehr einer Anwendung mit dem Ziel der Anonymität innerhalb des Netzwerks.
Angesichts dieser Eigenschaft ist Kovri eine großartige Lösung, um anonym über IRC, E-Mail zu kommunizieren oder um auf versteckte Dienste zuzugreifen.

## 6) - Fazit

Kovri wird Peer-to-Peer-Verbindungen revolutionieren und weltweit die Netzwerkresilienz sowie den Datenschutz verbessern.
Bösartige Netzwerkknoten können nicht länger Nutzer bedrohen, die Transaktionen erstellen, oder sie daran hindern, sich über das Netzwerk auszubreiten.
Kovri wird gebündelt mit zukünftigen Monero-Versionen erscheinen und standardmäßig aktiviert sein.
Zusätzlich wird Kovri über eine allgemeine API verfügen, die anderen Kryptowährungen und Anwendungen die Nutzung ermöglichen würde, nicht nur Monero.

Um mehr über Monero und das Kovri-Projekt zu erfahren, besuchen Sie getmonero.org und getkovri.org.
