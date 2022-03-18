# **1. Datenintegration**

Ihre Bezirkseinheiten sind noch nicht digital vorhanden? Dann lesen Sie weiter unter "[Bezirke manuell anlegen]](../gebietsplanung/#manuelle-neuanlage-von-verteilbezirken)".

Ansonsten erfolgt grundsätzlich  die Erstbefüllung der MultiRoute Go! Datenbank durch die gb consite. Gibt es die Bezirkseinheiten schon digital, gibt es die folgenden Wege: 

## Übernahme aus einem anderen GIS

Egal bei welchem GIS-Anbieter Sie vorher schon Ihre Bezirksstrukturen abgebildet hatten, wir übernehmen Sie gerne direkt in MultiRoute Go!. Senden Sie uns gerne Beispiele Ihrer Exportmöglichkeiten oder sprechen Sie uns an.


## Import aus (Verlags-)Software

Der Import erfolgt in der Regel über das Excel-Format. Aus Ihrer Software heraus benötigt MultiRoute Go! die Informationen: 

   * Strasse
   * Hausnummer
   * (Straßenabschnitt von bis; gerade/ungerade)
   * PLZ
   * Ortsteil
   * Ort
   * Verteilgebiet/Verteilbezirk

💾 [Musterliste](assets/downloads/Import-Datenformat_MRGo.xlsx)

Optional auch: 

   * Eigene Haushaltsdaten
   * Eigene Werbeverweigerer Daten


## Schnittstelle (automatisierter Import)

Natürlich kann der Import auch automatisiert über eine Schnittstelle erfolgen.


## Was passiert im Hintergrund?

Im Hintergrund werden Ihren Adressen (Straßenabschnitten) Geokoordinaten zugeordnet. Durch die Zuordnung zu (Verteil-)Bezirken werden diese auf der Karte visualisiert. Wir legen die Polygone drumherum. Jeder Adresspunkt, der über den Straßenabschnitt definiert wurde, weiß nun, in welchen Bezirk er gehört. Auf der Karte wird dieser nun grün (oder schwarz) dargestellt. Rote Punkte wurden entweder nicht gefunden oder von Ihnen nicht definiert. Hier lohnt sich nochmal ein zweiter Blick in die Ursprungsdaten. 

