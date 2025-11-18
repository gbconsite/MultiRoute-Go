---
title: Der Aufbau von MultiRoute Go! - Effiziente Gebietsplanung und Gehfolgenberechnung
description: MultiRoute Go! bietet umfassende Funktionen zur Gebietsplanung und Gehfolgenberechnung. Erfahren Sie, wie Sie von Gebäudekoordinaten über Planungsansichten bis zur optimalen Gangfolge innerhalb eines Zustellbezirks alles individuell anpassen können.
keywords: MultiRoute Go, Gebietsplanung, Gehfolgenberechnung, Tourenoptimierung, Gebäudekoordinaten, Zustellbezirke, Logistiksoftware
---

# Aufbau von MultiRoute Go!

MultiRoute Go! ist in zwei Hauptbereiche gegliedert:

1. **[Gebietsplanung](../gebietsplanung)** - :material-earth: Planen Sie Träger- und Verteilbezirke neu oder passen Sie bestehende Einheiten an.
2. **[Gehfolgenberechnung](../gehfolgen)** - :fontawesome-solid-calculator: Berechnen Sie die optimale Gehfolge für Abonnenten, Resthaushalte oder Vollabdeckungen wie Anzeigen- oder Gemeindeblätter.

![Menüpunkte Gebietsplanung und Gehfolgenberechnung](https://user-images.githubusercontent.com/99329016/158179701-085bf8a2-27f9-46cc-8b4b-60d599353bc9.png "Menüpunkte Gebietsplanung und Gehfolgenberechnung")

In MultiRoute Go! finden Sie auf der rechten Seite immer eine Karte, die Ihren aktuellen Arbeitsbereich zeigt. Sie können die Karte verschieben und zoomen. Auf der linken Seite können Sie nach Gebieten (Verteilbezirken) oder Gehfolgen suchen, filtern oder Metainformationen anzeigen. 

Ein Klick auf das aktive Symbol (z. B. :material-earth: für die Gebietsplanung) maximiert die Karte auf die volle Bildschirmbreite. Ein erneuter Klick öffnet wieder das Menü auf der linken Seite. Den linken Bereich und den Kartenbereich können Sie auch einfach nach Belieben größer oder kleiner ziehen.

## Grundlagen der Gehfolgenberechnung

Die [Gehfolgenberechnung](../gehfolgen) basiert auf Karten von [OpenStreetMap (OSM)](https://www.openstreetmap.org). Oben rechts im Kartenfenster können Sie im gesamten OSM-Kartenbestand suchen. Diese Karten werden wöchentlich aktualisiert und in Ihr MultiRoute Go! integriert. Ihre Anpassungen an Gebäuden und Wegen stehen somit innerhalb weniger Tage für neue Gehfolgenberechnungen zur Verfügung. Für InHouse-Kunden ermöglicht das Zusatzmodul "[Straßenanpassungen](../zusatzmodule/#straenanpassungen)" zusätzliche Eingriffsmöglichkeiten.

Je nach Installation und Lizenzierung stehen Ihnen weitere Kartendienste zur Verfügung. Mit einem Klick auf :material-layers-triple: im Kartenfenster können Sie zwischen verschiedenen Hintergrundkartendiensten wählen, darunter:

- [BING Maps](https://www.bing.com/maps) (Luftbilder)
- [Basemap](https://basemap.de/viewer/) - amtliche Karte des Bundesamts für Kartografie und Geodäsie
- [Mapquest](https://www.mapquest.com/) (Luftbilder)
- Amtliche Luftbilder (je nach Bundesland und Verfügbarkeit, teilweise mit zusätzlichen Kosten - wir beraten Sie gerne!)

## Gebäudekoordinaten für die Gebietsplanung

Für die **[Gebietsplanung](../gebietsplanung)** benötigen Sie **[Gebäudekoordinaten](../definitionen/#koordinaten)**, die auf drei verschiedene Arten ins System gelangen können:

1. **Amtliche Koordinaten**: Wir stellen Ihnen amtliche [Koordinaten](../definitionen/#koordinaten) der Vermessungsverwaltungen (aktuell nur für Deutschland) zur Verfügung, bezogen von TomTom. Die räumliche Genauigkeit dieser Daten kann schwanken, abhängig von den Aktualisierungszyklen der Verwaltung. Die **Haushaltsdaten** werden von [infas360](https://www.infas360.de/) statistisch ermittelt und den Koordinaten zugeordnet.

2. **Geokodierung über HERE**: Wenige Adresspunkte werden beim Upload über [HERE](https://wego.here.com/) geokodiert.

3. **Eigene Geokoordinaten**: Wenn Sie bereits **Geokoordinaten** (Latitude, Longitude) besitzen, können wir diese übernehmen, inklusive Ihrer eigenen Haushaltszahlen für eine präzise Planung.

## Zusätzliche Daten und Layer

Wenn Sie weitere Daten wie **Werbeverweigerer** oder eigene Haushaltsdaten in die Planung einbeziehen möchten, sprechen Sie uns an! Diese wertvollen Informationen können nahtlos in MultiRoute Go! integriert werden.

Über den Button zur Kartenauswahl und Detaildarstellung können Sie je nach Bearbeitungsart verschiedene Karten, Informationen und Layer an- und ausschalten.

![Layerübersicht](https://github.com/gbconsite/MultiRoute-Go/assets/99329016/3090a288-8d03-44d6-99df-04edfaabd5e6 "Layerübersicht")

![Transparenzregler](https://user-images.githubusercontent.com/99329016/168080224-0fd8ed04-ad2a-4e03-a149-9ea02038412c.png "Transparenzregler"){ align=right }

Das Ein- und Ausschalten von Labels (Beschriftungen der Bezirke) oder das Einfärben kann Ihnen helfen, den Überblick zu behalten. Unten in der Karte können Sie die Transparenz der Einfärbungen über einen Schieberegler anpassen.


