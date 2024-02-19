---
description: Der Aufbau von MultiRoute Go! in Gebietsplanung und Gehfolgenberechnung
---

## Aufbau 

MultiRoute Go! lässt sich in die beiden Hauptbereiche gliedern:

1. [Gebietsplanung](../gebietsplanung) - :material-earth: Träger-/Verteilbezirke neu planen oder bestehende Einheiten verändern
2.  [Gehfolgenberechnung](../gehfolgen) - :fontawesome-solid-calculator: Berechnung eines Bezirks nur für Abonnenten (Briefe/Zählpunkte etc.), Resthaushalte oder Vollabdeckung (bsp. Anzeigen-/Gemeindeblätter)

![grafik](https://user-images.githubusercontent.com/99329016/158179701-085bf8a2-27f9-46cc-8b4b-60d599353bc9.png "Menüpunkte Gebietsplanung und Gehfolgenberechnung")

Grundsätzlich befindet sich in MultiRoute Go! immer auf der rechten Seite die Karte, in der Sie sehen, wo Sie gerade arbeiten. Auf der Karte können Sie schieben und zoomen. Auf der linken Seite können Sie nach Bezirken oder Gehfolgen suchen (filtern) oder Metainformationen ansehen. 

Ein Klick auf das aktive Symbol (hier die :material-earth: für die Gebietsplanung) vergrößert die Karte auf Bildschirmbreite. Ein erneuter Klick öffnet wieder das Menü auf der linken Seite.


## Grundlagen

Die Berechnung der Gehfolgen basiert auf Karten von [OpenStreetMap](https://www.openstreetmap.org) (OSM). Oben rechts im Kartenfenster ist die Suche im gesamten hinterlegten OSM-Kartenbestand möglich. Diese werden von uns wöchentlich aktualisiert in Ihr MultiRoute Go! eingespielt. Ihre Anpassungen und Änderungen an Gebäuden und Wegen/Straßen, die für das Routing verwendet werden, stehen also immer nach wenigen Tagen direkt für neue Gehfolgenberechnungen zur Verfügung. Bei InHouse Kunden ermöglicht  das  Zusatzmodul "[Straßenanpassungen](../zusatzmodule/#straenanpassungen)" weitere Möglichkeiten zum Eingreifen.

Zusätzlich sind für Sie (je nach Installation und Lizenzierung) weitere Kartendienste frei. Sie wählen zwischen den Hintergrundkartendiensten mit Klick auf :material-layers-triple: auf der rechten Seite im Kartenfenster von MultiRoute Go!. Aktuell sind möglich:

* [BING Maps](https://www.bing.com/maps) (Luftbilder)
* [Basemap](https://basemap.de/viewer/) als amtliche Karte vom Bundesamt für Kartografie und Geodäsie
* [Mapquest](https://www.mapquest.com/) (Luftbilder)
* amtliche Luftbilder (je nach Bundesland und Verfügbarkeit, teilweise mit weiteren Kosten - wir beraten Sie gerne!)

Für die **Gebietsplanung** sind **[Gebäudekoordinaten](../definitionen/#koordinaten)** nötig. Diese können auf drei verschiedenen Wege ins System gelangen:

1. Wir stellen **amtliche [Koordinaten](../definitionen/#koordinaten)** der Vermessungsverwaltungen (aktuell nur für Deutschland) für Sie ins System. gb consite bezieht diese Daten von der TomTom. Leider unterliegen diese Daten räumlichen Qualitätsschwankungen. Dies steht in Abhängigkeit mit den Aktualisierungszyklen der Verwaltung. 
An die Koordinaten spielen wir für Sie auch gleich die **Haushaltsdaten**. Dies beinhaltet die Anzahl der Haushalte und die Anzahl der Gewerbebetriebe. Die Daten werden von [infas360](https://www.infas360.de/) mittels statistischer Methoden aus sozio-demographischen Daten ermittelt. Wie bei den Koordinaten kann es zu räumlichen Schwankungen kommen. In Gebieten mit einer einheitlichen Struktur sind die Daten sehr genau. In gemischten Gebieten kann es zu Schwankungen kommen. Für gebietsplanerische Aufgaben sind die Daten sehr gut geeignet. Gebietsauflagen lassen sich damit gut abschätzen. 

2. Die (nur wenigen) Adresspunkte werden beim Upload über [HERE](https://wego.here.com/) geokodiert.

3. Sie haben bereits **Geokoordinaten** (Latitude, Longitude) und wir können Ihre Koordinaten für das System übernehmen. Gerne auch mit Ihren selbst erfassten Haushaltszahlen für eine exakte Auflage.

## Zusätzliche Daten

Haben Sie weitere Daten in Ihrem Unternehmen erhoben, die wir berücksichtigen sollen? Sprechen Sie uns gerne an! Daten zu **Werbeverweigerern**, Werbestopps, die Sie bereits erhoben haben, sind zu wertvoll, um sie nicht zu verwenden! Auch Ihre Haushaltsdatenbank kann eine Alternative zu den von uns angespielten Haushaltsdaten sein. 


## Layer
Über den Button für die Kartenauswahl und Detaildarstellungen können je nach Bearbeitungsart Karten, Informationen und Layer an- und abgeschaltet werden.

![grafik](https://github.com/gbconsite/MultiRoute-Go/assets/99329016/3090a288-8d03-44d6-99df-04edfaabd5e6)


![grafik](https://user-images.githubusercontent.com/99329016/168080224-0fd8ed04-ad2a-4e03-a149-9ea02038412c.png){ align=right }
Das Ein-/Ausschalten von Labels (Beschriftungen der Bezirke) oder das Einfärben kann für den richtigen Durchblick sorgen! Und noch ein Hinweis: ganz unten in der Karte können Sie die Transparenz der Einfärbungen regulieren über eine Schieberegler:




