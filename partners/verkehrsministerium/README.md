# Bundesministerium für Verkehr und digitale Infrastruktur BMVI

<div align="center">
  <img src="https://smartcountry-hacks.de/wp-content/uploads/2018/09/smartcountry-hacks-verkehrsministerium.png" width="300px"/>
</div>

## Workshop

**Roland Goetzke** vom BMVI gibt **am Dienstag um 12:30** einen einführenden Workshop zu den bereitgestellten Daten.

## Datenbeschreibung

Das BMVI stellt Daten aus der Mcloud zur Verfügung eine ausführliche Beschreibung ist hier zu finden:


<a href="./Datendokumentation_BMVI_SmartCountryHacks_2018_11-16.pdf"> Datendokumentation</a>

# Beispielhafte Ansprache mit Python

Es ist für die meisten Datenpunkte recht einfach die Daten anzusprechen. Meist genügt einfach ein GET Request auf die entsprechende Ressource:

Unten ist es einfach aufgeführt die Daten mit Python anzusprechen.
```

# Get Geschwindigkeitsdaten NRW

url = "http://datarun.s3.amazonaws.com/geschwindigkeitsdaten_NRW.geojson"
headers = {
    'cache-control': "no-cache",
    }
response = requests.request("GET", url, headers=headers)
geschwindigkeit_nrw=response.json()
geschwindigkeit_nrw['features'][0]

```
