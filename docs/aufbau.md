
## Aufbau 

MultiRoute Go! lässt sich in die beiden Hauptbereiche gliedern:

1. **Gebietsplanung** - Träger-/Verteilbezirke neu planen oder bestehende Einheiten verändern
2.  **Gehfolgenberechnung** - Berechnung eines Bezirks nur für Abonnenten (Briefe/Zählpunkte etc.), Resthaushalte oder Vollabdeckung (bsp. Anzeigen-/Gemeindeblätter)


## Grundlagen

Die Berechnung der Gehfolgen basiert auf Karten von [OpenStreetMap](https://www.openstreetmap.org) (OSM). Diese werden wöchentlich aktualisiert. Ihre Anpassungen und Änderungen stehen also immer nach wenigen Tagen direkt für neue Gehfolgenberechnungen zur Verfügung. <!-- Bei InHouse Kunden Zusatzmodul "Straßensperrung -->
Zusätzlich sind für Sie (je nach Installation und Lizenzierung) weitere Kartendienste frei. Möglich sind:

* [BING Maps](https://www.bing.com/maps) (Luftbilder)
* [WebAtlas.DE](https://gdz.bkg.bund.de/) (BKG - als amtliche Karte, deutschlandweit verfügbar)
* [Mapquest](https://www.mapquest.com/) (Luftbilder)
* amtliche Luftbilder (je nach Bundesland und Verfügbarkeit, teilweise mit weiteren Kosten - bitte fragen Sie nach!)

Für die **Gebietsplanung** sind **Gebäudekoordinaten** nötig. Diese können auf drei verschiedenen Wege ins System gelangen:

1. Wir stellen **amtliche Koordinaten** der Vermessungsverwaltungen (aktuell nur für Deutschland) für Sie ins System. gb consite bezieht diese Daten von der Firma TomTom. Leider unterliegen diese Daten räumlichen Qualitätsschwankungen. Dies steht in Abhängigkeit mit den Aktualisierungszyklen der Verwaltung. 
An die Koordinaten spielen wir für Sie auch gleich die **Haushaltsdaten**. Dies beinhaltet die Anzahl der Haushalte und die Anzahl der Gewerbebetriebe. Die Daten werden von [infas360](https://www.infas360.de/) mittels statistischer Methoden aus sozio-demographischen Daten ermittelt. Wie bei den Koordinaten kann es zu räumlichen Schwankungen kommen. In Gebieten mit einer einheitlichen Struktur sind die Daten sehr genau. In gemischten Gebieten kann es zu Schwankungen kommen. Für gebietsplanerische Aufgaben sind die Daten sehr gut geeignet. Gebietsauflagen lassen sich damit gut abschätzen. 
2. Die (nur wenigen) Adresspunkte werden beim Upload über [HERE](https://wego.here.com/) geokodiert.
3. Sie haben bereits **Geokoordinaten** (Latitude, Longitude) und wir können Ihre Koordinaten für das System übernehmen. Gerne auch mit Ihren Haushaltszahlen für eine exakte Auflage.

## Zusätzliche Daten

Haben Sie weitere Daten in Ihrem Unternehmen erhoben, die wir berücksichtigen sollen? Sprechen Sie uns gerne an! Daten zu **Werbeverweigerern**, Werbestopps, die Sie bereits erhoben haben, sind zu wertvoll, um sie nicht zu verwenden! Auch Ihre Haushaltsdatenbank kann eine Alternativ zu den von uns angespielten Haushaltsdaten sein. 
