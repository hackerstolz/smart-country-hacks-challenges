# ITDZ Berlin

<div align="center">
  <img src="https://smartcountry-hacks.de/wp-content/uploads/2018/08/itdz_logo.svg" width="300px"/>
</div>

## Challenges

## Smarter Bürger - Smarte Terminbuchung
„Wer einen neuen Pass braucht oder sich ummelden will, muss in deutschen Ämtern stundenlange Wartezeiten auf sich nehmen. Die Schlangen vor den Schaltern der Verwaltungen in München, Hamburg oder Berlin werden immer länger. Die Mitarbeiter sind überfordert und die Bürger genervt.”
**Focus Online, 10.06.2016**


Berlin ist eine wachsende Stadt mit wachsenden Aufgaben. Insbesondere bekommen dies die Bürgerämter zu spüren, die für eine Vielzahl von wichtigen Dienstleistungen wie die Beantragung eines Personalausweises, der Anmeldung/Ummeldung eines Wohnsitzes oder der Ausstellung eines Führungszeugnisses zuständig sind. Lange Wartezeiten für Bürgerinnen und Bürger sind teilweise die Folge.

Seit 2013 gibt es deshalb in Berlin die Möglichkeit, online über die Seite des Landes (service.berlin.de) ganz bequem von zuhause aus einen Termin zu buchen. Die Bürgerämter sind jedoch nachwievor stark ausgelastet und so sieht man häufig, wenn man online einen Termin sucht nur einen rot eingefärbten Kalender: „Keine freien Termine verfügbar.“

### Challenge Beschreibung

Im Backend der Online-Terminbuchungsfunktion arbeitet das sog. Zeitmanagementsystem (ZMS), eine Eigenentwicklung des IT-Dienstleistungszentrums Berlin (ITDZ). Es wird von den Mitarbeitenden in den Bürgerämtern mit Terminkapazitäten gefüttert, zeigt diese auf dem Service-Portal an, vergibt online Wartenummern, verschickt Erinnerungs-SMS, und hilft bei der Abwicklung am Tag des Termins indem es auf den digitalen Anzeigetafeln die Wartenden aufruft und zum Schreibtisch der jeweiligen Sachbearbeiterin oder Sachbearbeiters lotst.

Die Datenbank des ZMS ermöglicht rückwirkend Auswertungen für alle Bürgeramtsstandorte Berlins hinsichtlich Anzahl der Termine und Art der Dienstleistungen aufgeschlüsselt nach Jahren, Monaten und Tagen.

### Mehr Transparenz für Bürgerinnen und Bürger
Für die Bürgerin oder den Bürgerin ist es oft nicht leicht nachzuvollziehen, wieso, wann, wo und wie viele Termine verfügbar sind und wie es z.B. um die Auslastung der Bürgerämter im eigenen Bezirk steht. Hochzeiten, die Anmeldung eines gekauften Autos oder die Erneuerung des Reisepasses für den anstehenden Urlaub sind Ereignisse, bei denen eine unvorhergesehene Wartezeit von 2 Monaten bis zum Termin einer Bürgerin oder einem Bürger schnell einen unangenehmen Strich durch die Rechnung machen kann.

Nutzen Sie die zur Verfügung stehenden Daten, um für Bürgerinnen und Bürger transparenter zu machen, wie lange die Wartezeiten für verschiedene Dienstleistungen an den verschiedenen Standorten sind, um mehr Planungssicherheit zu ermöglichen. Gibt es Auffälligkeiten und Muster, die wiederum die Führungskräfte in den Bürgerämtern z.B. bei der Personal- und Urlaubsplanung berücksichtigen sollten?

### Smarte Terminbuchung
Unterschiedliche Personalaustattung der verschiedenen Bezirke gepaart mit z.T. gegensätzlicher Nachfrage nach bestimmten Dienstleistungen führt dazu, dass die Wartezeit für z.B. die Anmeldung einer Hochzeit in einem Standesamt ein vielfaches länger dauert als in einem anderen.
Entwickeln Sie aufbauend auf den Erkenntnissen der vorangegangenen Aufgabe ein Tool, dass Bürgerinnen und Bürgern hilft, ihre Terminbuchung intelligenter vorzunehmen und so die Wartezeit zu optimieren.

Es könnte z.B. die Inanspruchnahme einer bestimmten Dienstleistung zu der jeweils günstigsten Jahreszeit oder im Bezirk mit den größten entsprechenden Kapazitäten empfehlen und die Terminbuchungsanfrage an das ZMS zu der optimalen Tageszeit vornehmen.
Welche Daten müssten zusätzlich erfasst oder verfahrensseitig miteinander verknüpft werden, um den Funktionsumfang eines solchen Tools langfristig zu erweitern?   

### Zusatz-Aufgabe: “Nicht-Kommer”

Ein weiteres Problem sind Termine, die ausfallen, weil die Bürgerin oder der Bürger nicht zum vereinbarten Zeitpunkt im Bürgeramt erscheint. Dies wird unter anderem durch die Anonymität bei der Terminbuchung begünstigt.

Eine Anbindung des ZMS an das Service-Konto Berlin (service.berlin.de/konto/), bei dem die Authentifizierung bei der Anmeldung erforderlich ist und das die eindeutige Zuordnung eines Termins zu einer Bürgerin oder einem Bürger möglich machen würde, wäre denkbar. Jedoch stammen viele Terminbuchung aus dem Callcenter der 115. Eine telefonische Authentifizierung der Anrufenden ist hier nicht möglich. Dennoch soll dieser telefonische Zugang zu Dienstleistungen für Bürgerinnen und Bürger erhalten bleiben.

Skizzieren Sie mögliche Inzentivierungsmaßnahmen, die die Wahrscheinlichkeit erhöhen, dass eine Bürgerin oder ein Bürger einen zuvor gebuchten Termin auch wahrnimmt – oder zumindest rechtzeitig vorher absagt, damit der Termin im ZMS wieder freigegeben werden kann.
Beschreibung der Datensätze

### Zur Verfügung stehen 2 Datensätze.

* Auswertungen der Termine in allen Bürgeramtsstandorte aufgeschlüsselt nach Dienstleistungsart, Jahr, Monat & Tag – rückwirkend bis ~2013 (je nach Standort)
* Report einer automatisierten Abfrage an das ZMS, das im 15-Minuten-Takt für jedes Bürgeramt auswertet, wann der nächste freie Termin verfügbar ist
Viel Spaß!
