---
titel: Digitales Zustellbuch wird in der Gangfolge berücksichtigt
description: MultiRoute Go! bietet von Anfang an viele Hilfestellungen, um die bestmögliche Reihenfolge der Zustellungen zu berechnen. Dazu gehören eigene Geschwindigkeiten bei Gebäudestrecken und Steckstrecken, manuelle Anbindungsmöglichkeit von Gebäuden an Straßen
---

# **6. Optimierungen in der Gehfolgenberechnung**


Nach der Berechnung der Gehfolgen besteht in MultiRoute Go! die Möglichkeit die Gehfolgen zu optimieren. Ergänzend zu der Kartengrundlage OSM kann ein Blick auf die Luftbilder geworfen werden, um bspw. den besten Weg zu einem Gebäude zu finden.

Vielleicht haben Sie auch einen GPS Track, den Sie einlesen möchten?
Mit dem :material-folder-open: können Sie GPS Tracks laden.
Zur besseren Orientierung haben wir die Track-Linie mit einem Richtungspfeil versehen, sodass die Laufrichtung erkennbar ist.
Geladene Tracks (mehrere gleichzeitig möglich) können einfach über die Layersteuerung ein- und ausgeschaltet werden, mit einem Klick auf die Linie erscheint ein PopUp, über das die Tracks auch wieder entfernt werden können.



Folgende Optimierungen können in der MultiRoute Go! Gangfolge direkt vorgenommen werden:

- Veränderung der Straßenankerpunkte (Anbindung, Hauszugang)
- Passivschaltung (inaktiv) oder Löschen von Gebäudekoordinaten
- Veränderungen in OSM vornehmen
- Parameterveränderungen für Gehfolgen

Zustellbesonderheiten wie "*Briefkasten rechts um die Ecke*". Oder "*Achtung, bissiger Hund!*", die für Zusteller in einem Botenbuch gesammelt werden, können Sie direkt am jeweiligen Haus im Feld "Bemerkungen" hinterlegen.
Diese Bemerkungen tauchen dann auch in der Gehfolgenliste auf, so dass Springer/Aushilfsträger oder neue Zusteller es viel einfacher haben, sich zurecht zu finden. Mit Klick auf ```Speichern``` werden diese Informationen direkt an das Haus gehängt.

Auf der Karte erkennbar mit einem kleinen Dreieck. Das Dreieck nimmt die passende Farbe an, die es auch als Kreis hätte. Ein :material-triangle: bspw. ist ein Abonnent, bei dem Bemerkungen hinterlegt werden. Ein :material-triangle:{style="color:magenta"} entspricht einem Zustellerhaus mit Bemerkungen.

![grafik](https://user-images.githubusercontent.com/99329016/170690319-edbe0da8-19fb-4e1d-aca6-1b2a5cdcb5fa.png "Bemerkungen gespeichert am jeweiligen Gebäude")

![grafik](https://user-images.githubusercontent.com/99329016/170690311-f82f6c82-a274-443b-a651-81dde62c5d5f.png "Dreicke als Symbole weisen auf Bemerkungen hin")


Einstellungen für die Gehfolgenberechnung werden global für alle Bezirke standardmäßig eingestellt. Über die API können die Parameter jedoch abweichend übergeben werden. Oder Sie stellen manuell je Ausgabe oder sogar je Bezirk eigene Parameter ein.

## Veränderung der Straßenankerpunkte

Mittels Manipulation der berechneten Straßenankerpunkte kann die Gehfolge zusätzlich optimiert werden. Die Grundlagen der Informationen für die Veränderungen können vielfältig sein:

- Erfahrungen oder Tracking der Zusteller
- Begehungen durch Inspektoren
- Aus der Sicht auf das Luftbild
- Aus der Sicht auf die OSM Karten

Um Veränderungen durchführen zu können, muss die Gehfolge aufgerufen sein und auf der Karte erscheinen. Dann startet man den Vorgang über den im Schaubild markierten Button **Hauszugänge editieren**. Mit der Maus schiebt man den entsprechenden Straßenankerpunkt an die gewünschte Stelle (= neuer Straßenankerpunkt). Nach dem Speichern muss die Gehfolge neu berechnet werden.
![grafik](https://user-images.githubusercontent.com/99329016/170689694-55cd35fa-9054-429e-8313-1e5b74266165.png "Ankerpunkte bzw. Hauszugänge verschieben")

Die Gebäudekoordinaten, an denn der Straßenankerpunkt verschoben wurde, haben nun einen gelben Kringel. 

![grafik](https://github.com/gbconsite/MultiRoute-Go/assets/99329016/295d3db0-bee8-40f9-b3c8-94c44e993a34 "gelber Kringel als Hinweis auf verschobenen Hauszugang")

Die Straßenpunkte sind gelb markiert, so dass sofort ersichtlich ist, dass hier manuell eingegriffen wurde. Mit Klick auf einen gelben Punkt können Sie die Änderungen auch wieder zurücksetzen.

![grafik](https://user-images.githubusercontent.com/99329016/170689703-9c87dddd-0423-4d55-9286-d11946acb0b0.png "gelb hinterlegte Straßenpunkte als Hinweis auf verschobene Anbindung")

In unserem Beispiel müssen auch noch die Straßen in OSM angepasst werden, da diese noch nicht digitalisiert wurden. 


## Passivschaltung (inaktiv) oder Löschen von Gebäudekoordinaten

Ein Gebäude auf inaktiv <span style="color: blue;">&#x1f534;&#xfe0e;</span> zu setzen bedeutet nicht, dass das Gebäude aus der Verteilbezirkszuordnung entfernt wird. Es wird lediglich nicht in die Berechnung einbezogen. Es gibt verschiedene Gründe dies zu tun. Beispielsweise wenn aus der Betrachtung der Gehfolge absehbar ist, dass sich durch die Passivschaltung eine signifikant kürzere Gehfolge ergibt. Dabei ist es dann abzuwägen, ob eine Nichtbelieferung sinnvoll ist.

Da grundsätzlich alle Gebäude zunächst aktiv geschaltet sind muss zur Passivschaltung das "Haus aktiv" Feld ausgeschaltet werden. Danach muss die Gehfolge neu berechnet werden. Das Gebäude ist nicht mehr Bestandteil der Zustellung. Das "inaktiv" Schalten wirkt sich auf ALLE Ausgaben aus.

![grafik](https://user-images.githubusercontent.com/99329016/170689864-2a9f4777-fbbe-42ba-ace3-013876a50c58.png "Status des Hauses ist inaktiv")

Abonennten, die sich in passiven Gebäuden befinden werden NICHT in der Gehfolge berücksichtigt! Bei der Aufsummierung bei Klick auf den Trägerbezirk werden inaktive Gebäude sowohl mit Anzahl Haushalte, Gewerbebetriebe und Abonnenten NICHT mitgezählt.

## Veränderungen in OSM vornehmen 

Veränderungen in OSM können prinzipiell mit verschiedenen Kartenbearbeitungsprogrammen vorgenommen werden. Besonders bequem ist dies mit JOSM, einem sog. Fat Client.

Ab einer bestimmten Zoomstufe in MultiRoute Go! wird in der rechten unteren Ecke der Karte das Wort "JOSM" eingeblendet.
![grafik](https://user-images.githubusercontent.com/99329016/170690035-093cf305-b58a-46f6-8dd3-97bd864b9a29.png "direkte Verlinkung zum JOSM Editor aus MRGo")

Wenn Sie zuvor das Programm JOSM (Kostenloser Download unter: [https://josm.openstreetmap.de/wiki/De%3ADownload](https://josm.openstreetmap.de/wiki/De%3ADownload)) gestartet haben, wird dieses nun genau mit dem Kartenausschnitt, den Sie derzeit in MultiRoute Go! sehen, geöffnet. Nun können Sie in JOSM (Voraussetzung ist ein Zugang von [https://www.openstreetmap.org/login](https://www.openstreetmap.org/login)) z.B. Straßen und Wegeverläufe korrigieren und ergänzen oder einfach nur Schreibweisen von Straßennamen verbessern.

Weitere Informationen zur Einrichtung finden Sie in diesem PDF: [https://gbconsite.de/wp-content/uploads/2022/08/Zugang_Neu_OSM_JOSM.pdf](https://gbconsite.de/wp-content/uploads/2022/08/Zugang_Neu_OSM_JOSM.pdf).

Sofern für Ihr Kundenprofil ein oder meherer OSM-Accounts vom gb consite Support eingetragen wurde, können Sie über den OSM Monitor nun sehen, ob diese in JOSM durchgeführten Änderungen bereits in MultiRoute Go! verfügbar sind (siehe hierzu OSM Monitor).


## Parameterveränderungen für Gehfolgen
Im Standard werden die Gehfolgenparameter in den Kundeneinstellungen festgelegt. Je Ausgabe und je Bezirk können diese übersteuert werden.

Dazu gehören:

- Optimierungsmethode (Rundweg, einfache Strecke, Rundweg im Verteilbezirk)
- Geschwindigkeiten (separat für Hin-/Rückweg, im Bezirk, für Hauszugangsdistanz)
- Steckzeiten
- Hauszugangsdistanzen
- Hauszugangssuchradius
