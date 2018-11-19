## ITDZ Berlin Hackathon API

Die API für die Daten is unter `https://api.smartcountry-hacks.de/itdz/` zu finden.

### 1. Service- und Kundenstatistiken

#### Standorte: `/itdz/subjects`

Bei dieser Route kann eine Liste aller Standorte (Bürgerämter) abgerufen werden.

**Beispiel Request**: `curl https://api.smartcountry-hacks.de/itdz/subjects`

**Beispiel Response**:
```
[
  {
      "BezirksID": "7",
      "StandortID": "2204",
      "Standortname": "Bürgeramt Schöneberg Tresen",
      "periodstart": "2018-09-20",
      "periodend": "2018-11-15",
      "subjectId": "2204"
  },
  ...
]
```

#### Übersicht Dienstleistungsstatistik: `/itdz/stats/service`

Liefert eine Übersicht aller verfügbaren Dienstleistungsstatistiken.

**Beispiel Request**: `curl https://api.smartcountry-hacks.de/itdz/stats/service`

**Beispiel Response**:
```
[
  {
    "subjectId": "997",
    "date": "2018-09"
  },
  {
    "subjectId": "997",
    "date": "2018-10"
  },
  {
    "subjectId": "997",
    "date": "2018-11"
  },
  ...
]
```


#### Dienstleistungsstatistik: `/itdz/stats/service/:subjectId/:month`

Liefert die Dienstleistungsstatistik für den angeforderten Standort und Monat.

Zur **Dienstleistungsstatistik gibt es folgendes zu berücksichtigen**:
  - Nicht jede Dienstleistung wurde in jedem Bürgeramt oder über den Datenlieferungszeitraum erbracht/angeboten
  - Nicht an jedem Standort gab es in der Vergangenheit für die Sachbearbeiter die Pflicht, die Dienstleistungsstatistik zu pflegen
  - Sonderstandorte enthalten ggf. weniger Dienstleistungen (manche evtl. auch gar keine, wenn sie ausschließlich der internen Organisation dienten)
  - Schließtage sind nicht enthalten (Feiertage, Wochenenden (wobei einige wenige Bürgeramter auch am Wochenende geöffnet sind)
  - Es handelt sich um Rohdaten
  - Hinweis zu zwei „Rückfall“-Dienstleistungen:
    - „Dienstleistung wurde nicht erfasst“ heißt, dass sie vom Sachbearbeiter nicht ausgefüllt wurden, oder der Standort erbringt sie nicht
    - „Dienstleistung konnte nicht erbracht werden“ heißt zum Beispiel: Jemand wollte eine Wohnung anmelden, hatte aber nicht alle erforderlichen Unterlagen dabei oder die Dienstleistung konnte aus anderen Gründen nicht erbracht werden.
  - Muster siehe **Beispiel Response**, Erläuterungen zu den Spalten:
    - `subjectid` = StandortID
    - `date` = Datum
    - `name` = Name der Dienstleistung
    - `requestcount` = erbrachte Menge

**Beispiel Request**: `curl https://api.smartcountry-hacks.de/itdz/stats/service/101/2017-02`

**Beispiel Response**:
```
[
  {
    "subjectid": "101",
    "date": "2017-02-22",
    "name": "Zulassungsbescheinigung Teil I für KFZ wegen Verlust oder Diebstahl ersetzen",
    "requestscount": "1"
  },
  {
    "subjectid": "101",
    "date": "2017-02-23",
    "name": "Zulassungsbescheinigung Teil I für KFZ wegen Verlust oder Diebstahl ersetzen",
    "requestscount": "2"
  },
  ...
]
```

#### Übersicht Kundenstatistiken: `/itdz/stats/customer`

Liefert eine Übersicht aller verfügbaren Kundenstatistiken.

**Beispiel Request**: `curl https://api.smartcountry-hacks.de/itdz/stats/customer`

**Beispiel Response**:
```
[
  {
    "subjectId": "997",
    "date": "2018-09"
  },
  {
    "subjectId": "997",
    "date": "2018-10"
  },
  {
    "subjectId": "997",
    "date": "2018-11"
  },
  ...
]
```

#### Kundenstatistik: `/itdz/stats/customer/:subjectId/:month`

Liefert die Kundenstatistik für den angeforderten Standort und Monat.

Zur **Kundenstatistik gibt es folgendes zu berücksichtigen**:
  - Es gab in der Vergangenheit eine Zeit, wo einige Ämter Spontankunden zugelassen haben, mit der Zeit haben fast alle auf „nur-Terminkunden“ umgestellt.
  - Schließtage sind nicht enthalten (Feiertage, Wochenenden (wobei einige wenige Bürgeramter auch am Wochenende geöffnet sind)
  - Muster siehe Beispiel B, Erläuterungen zu den Spalten:
    - `subjectid` = StandortID
    - `date` = Datum
    - `notificationscount` = Anzahl versendeter Benachrichtigungs SMSen (nicht jeder Standort nutzt diesen Dienst)
    - `notificationscost` = Summe der Kosten für SMS-Versand (15ct / SMS); Aus unserer Sicht könnten diese zwei notification-Spalten entfernt werden, da nur weniger Ämter diesen Dienst nutzen und eine Vergleichbarkeit nicht herstellbar ist
    - `clientscount` = Anzahl der Kunden an diesem Tag (Termin- UND Spontankunden)
    - `missed` = Nicht erschienene Kunden (Termin- UND Spontankunden) an diesem Tag
    - `withappointment` = Terminkunden an diesem Tag (dabei gilt: „clientscout abzügl. withappointment = Spontankunden“ (nicht separat aufgeführt))
    - `missedwithappointment` = nicht erschienene Terminkunden (wie zuvor; ist eine Teilmenge von „missed“)
    - `requestscount` = Anzahl der erbrachten Dienstleistungen an diesem Tag

**Achtung:** Wir haben festgestellt, dass die Anzahl der „requestcounts“ in der Kundenstatistik manchmal von der in der Dienstleistungsstatistik abweichen. Grundsätzlich fehlen hier die „Rückfalldienstleistungen“.)

**Beispiel Request**: `curl https://api.smartcountry-hacks.de/itdz/stats/customer/111/2016-06`

**Beispiel Response**:

```
[
  {
    "subjectid": "111",
    "date": "2016-06-29",
    "notificationscount": "0",
    "notificationscost": "0",
    "clientscount": "69",
    "missed": "6",
    "withappointment": "67",
    "missedwithappointment": "6",
    "requestscount": "94"
  },
  {
    "subjectid": "111",
    "date": "2016-06-30",
    "notificationscount": "0",
    "notificationscost": "0",
    "clientscount": "102",
    "missed": "19",
    "withappointment": "92",
    "missedwithappointment": "19",
    "requestscount": "129"
  },
  ...
]
```
