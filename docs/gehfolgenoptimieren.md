---
titel: Digitales Zustellbuch wird in der Gangfolge berücksichtigt
description: MultiRoute Go! bietet von Anfang an viele Hilfestellungen, um die bestmögliche Reihenfolge der Zustellungen zu berechnen. Dazu gehören eigene Geschwindigkeiten bei Gebäudestrecken und Steckstrecken, manuelle Anbindungsmöglichkeit von Gebäuden an Straßen
---

# **6. Optimierungen in der Gehfolgenberechnung**


Nach der Berechnung der Gehfolgen besteht in MultiRoute Go! die Möglichkeit die Gehfolgen zu optimieren. Ergänzend zu der Kartengrundlage OSM kann ein Blick auf die Luftbilder geworfen werden, um bspw. den besten Weg zu einem Gebäude zu finden.

## Tracks, Touren, Routen abbilden
Vielleicht haben Sie schon getrackte Touren oder Routen, die Sie mit der berechneten Gehfolge vergleichen möchten?
Oder Sie wollen einmal sehen, wo die Fahrer auf Ihrer Abladestellen-Tour vorbeikommen? Vielleicht kann ein entlegender Abonnenten vom Fahrer mitbeliefert werden.
Mit dem :material-folder-open: können Sie vorhandene *.kml, *.gpx oder *.geojson Dateien laden.

Zur besseren Orientierung haben wir die Track-Linie mit einem Richtungspfeil versehen, sodass die Lauf-/Fahrrichtung erkennbar ist.
Geladene Tracks (mehrere gleichzeitig möglich) können einfach über die Layersteuerung ein- und ausgeschaltet werden, mit einem Klick auf die Linie erscheint ein PopUp, über das die Tracks auch wieder entfernt werden können.

Dies ist nicht nur in der "Gehfolgenberechnung", sondern auch in der "Gebietsplanung" einsetzbar.

❗Hilft besonders, wenn Sie sich mit "Perlenketten" beschäftigen und Ihre Fahrtouren mit Zustelltouren kombinieren möchten.


## Optimierungen

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

Der Straßenankerpunkt legt fest, an welcher Stelle des Wegenetzes ein
Gebäude angebunden ist. Liegt dieser Punkt ungünstig, können Sie ihn
manuell verschieben, um den tatsächlichen Zugang zum Gebäude besser
abzubilden.

Die Verbindung zwischen Straßenankerpunkt und Gebäude wird als
[Hauszugangsdistanz](https://go.multiroute.de/handbuch/gehfolgen/#hauszugangsdistanz-hzd-grenzwert)
berücksichtigt.

Für die Wahl eines geeigneten Straßenankerpunkts können Sie folgende
Informationen nutzen:

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

Wenn ein Gebäude nicht mehr in der Gehfolgenberechnung berücksichtigt
werden soll, können Sie es auf **inaktiv** setzen. Das Gebäude bleibt
gespeichert; auch seine Verteilbezirkszuordnung bleibt bestehen.

**Wichtig:** Die Einstellung gilt für **alle Ausgaben**. Auch Abonnenten
in diesem Gebäude werden anschließend nicht mehr in der Gehfolge
berücksichtigt.

So gehen Sie vor:

1. Öffnen Sie die Eigenschaften des gewünschten Gebäudes.
2. Deaktivieren Sie das Feld `Haus aktiv` und speichern Sie die Änderung.
3. Berechnen Sie die betroffene Gehfolge neu.

❗ Inaktive Gebäude werden bei den Summen für Haushalte, Gewerbebetriebe
und Abonnenten in der Gebietsinformation nicht mitgezählt.

![grafik](https://user-images.githubusercontent.com/99329016/170689864-2a9f4777-fbbe-42ba-ace3-013876a50c58.png "Status des Hauses ist inaktiv")

Wie Sie inaktive Gebäude wieder in der Adressliste anzeigen, erfahren
Sie unter
[Adressverwaltung → Anzeige Adressen](https://go.multiroute.de/handbuch/adressverwaltung/#anzeige-adressen).


## Veränderungen in OSM vornehmen 

Veränderungen in OSM können prinzipiell mit verschiedenen Kartenbearbeitungsprogrammen vorgenommen werden. Besonders bequem ist dies mit JOSM, einem sog. Fat Client.

Ab einer bestimmten Zoomstufe in MultiRoute Go! wird in der rechten unteren Ecke der Karte das Wort "JOSM" eingeblendet.

![grafik](https://user-images.githubusercontent.com/99329016/170690035-093cf305-b58a-46f6-8dd3-97bd864b9a29.png "direkte Verlinkung zum JOSM Editor aus MRGo")

Wenn Sie zuvor das Programm JOSM (Kostenloser Download unter: [https://josm.openstreetmap.de/wiki/De%3ADownload](https://josm.openstreetmap.de/wiki/De%3ADownload)) gestartet haben, wird dieses nun genau mit dem Kartenausschnitt, den Sie derzeit in MultiRoute Go! sehen, geöffnet. Nun können Sie in JOSM (Voraussetzung ist ein Zugang von [https://www.openstreetmap.org/login](https://www.openstreetmap.org/login)) z.B. Straßen und Wegeverläufe korrigieren und ergänzen oder einfach nur Schreibweisen von Straßennamen verbessern.

Weitere Informationen zur Einrichtung finden Sie in diesem PDF: [https://gbconsite.de/wp-content/uploads/2022/08/Zugang_Neu_OSM_JOSM.pdf](https://gbconsite.de/wp-content/uploads/2022/08/Zugang_Neu_OSM_JOSM.pdf).

Sofern für Ihr Kundenprofil ein oder meherer OSM-Accounts vom gb consite Support eingetragen wurde, können Sie über den OSM Monitor nun sehen, ob diese in JOSM durchgeführten Änderungen bereits in MultiRoute Go! verfügbar sind (siehe hierzu OSM Monitor).

Wenn Straßenanpassungen ausschließlich für Ihre eigene Installation gelten
sollen, können Sie das Zusatzmodul
[Straßenanpassungen](https://go.multiroute.de/handbuch/zusatzmodule/#straenanpassungen)
nutzen, beispielsweise für vorübergehende Sperren oder saisonal ungeeignete
Wege. Das Modul ist für Kunden mit InHouse-Lizenz oder dediziertem Server
verfügbar.

## Manuelle Gehfolgensortierung (Zusatzmodul)
Trotz aller Optimierungen kann es Gründe geben, warum die Reihenfolge der Gehfolge verändert werden muss. Dafür haben wir das Zusatzmodul "[Manuelles Eingreifen in die Gehfolgen](zusatzmodule.md#manuelles-eingreifen-in-gehfolgen)". Ist dieses Zusatzmodul aktiviert, haben Sie in bereits berechneten Gehfolgen die Möglichkeit, manuell einzugreifen.

![grafik](https://github.com/user-attachments/assets/4b7e17fa-62cc-41fa-946e-0d85c0c21aeb "Schaltfläche um Reihenfolge per drag & drop zu verändern")

Sie können nun ganz einfach per drag & drop Gebäude an einen anderen Punkt in der Liste verschieben. Oder Sie klicken in der Karte und geben einen neuen Reihenfolgeindexwert an:

![grafik](https://github.com/user-attachments/assets/5e87e3f3-ab44-4785-910b-d98f9d986e7d "Index verändern")

Ihre veränderten Punkte erkennen Sie durch die orangene Einfärbung.
Anschließend können Sie die nun aktuellen Strecken und Zeiten von MultiRoute Go! berechnen lassen. Sind Sie mit dem Ergebnis zufrieden, können Sie die "Reihenfolge speichern" für zukünftige Berechnungen.

Liegt Ihre gewünschte Zustellreihenfolge bereits als Datei vor, können Sie
diese mit dem entsprechenden Zusatzmodul importieren. Die Anleitung finden
Sie unter
[Festgelegte Reihenfolge hochladen](#festgelegte-reihenfolge-hochladen-zusatzmodul).

## Festgelegte Reihenfolge hochladen (Zusatzmodul)
Es gibt schon eine festgelegte Reihenfolge von Ihnen (vom Zusteller) und die soll unbedingt eingehalten werden? Vielleicht liegt es auch an der (Brief-)Sortierung?
Auch das kann MultiRoute Go! mit dem 🆕 Zusatzmodul "[Festgelegte Reihenfolge](zusatzmodule.md#festgelegte-reihenfolge)" nun berücksichtigen.
Sie benötigen nur einen Reihenfolge-Index und können diesen dann mit uploaden.
Upload - Weitere Optionen:

![grafik](https://github.com/user-attachments/assets/e27623f4-f085-4f1d-82db-06370cd15d03 "Upload Sortierreihenfolge")

❗Hinweis:
Die Modi bei "Zuordnung":

- **hinzufügen**: Zuordnung wird einfach hinzugefügt. (Überlappungen mit anderen Gebieten sind möglich.)

- **überschreiben**: Die gesamte alte Zuordnung des Gebietes wird als erstes gelöscht. Dann wird die neue Zuordnung geladen. (Überlappungen mit anderen Gebieten sind möglich.)
  
- **ersetzen**: Alle Zuordnungen der Adressen werden gelöscht. Dann wird die neue Zuordnung geladen. (Überlappungen mit anderen Gebieten sind nicht möglich.)
  
- **überschreiben und ersetzen**: Die gesamte alte Zuordnung des Gebietes wird als erstes gelöscht. Alle Zuordnungen der Adressen zu anderen Gebieten werden gelöscht. Dann wird die neue Zuordnung geladen. (Überlappungen mit anderen Gebieten sind nicht möglich.)
  
## Straßenseite beibehalten (Zusatzmodul)
Eine weitere Möglichkeit - und besonders beliebt bei der Briefzustellung - ist die Möglichkeit MultiRoute Go! zu "zwingen" für eine bestimmte Straße oder innerhalb eines Ortsteils die "Straßenseite beizubehalten". Also nicht die Straßenseite zu wechseln. Bei der Sortierung von Briefen hilt das, aber auch wenn es weitere logistische Gründe gibt.
Nach Aktivierung dieses Zusatzmoduls können Sie die bestimmten Gebäude/Straßen in der Adressverwaltung (Gebietsplanung) mit dem Lasso  <img width="32" height="29" alt="grafik" src="https://github.com/user-attachments/assets/c119d66b-89ab-443b-a1c5-fa79c9c2aed3" /> auswählen und in der Adressliste explizit für "Straßenseite beibehalten" auswählen:

![grafik](https://github.com/user-attachments/assets/c80f06e8-873b-460f-979e-e9f9021e274a "Anti-Zick-Zack Zustellung")

**Voraussetzung:** Für den Verteilbezirk muss mindestens ein Zustellerhaus,
ein Starthaus oder ein Endhaus festgelegt sein. Wie Sie diese Punkte
einrichten, erfahren Sie im Kapitel
[Spezialhäuser](https://go.multiroute.de/handbuch/spezialhaeuser/).

## Parameterveränderungen für Gehfolgen
Im Standard werden die Gehfolgenparameter in den Kundeneinstellungen festgelegt. Je Ausgabe und je Bezirk können diese übersteuert werden.

Dazu gehören:

- Optimierungsmethode (Rundweg, einfache Strecke, Rundweg im Verteilbezirk)
* [Geschwindigkeiten](https://go.multiroute.de/handbuch/gehfolgen/#geschwindigkeiten)
  für Hin- und Rückweg, Zustellstrecke im Verteilbezirk, Hauszugangsdistanz
  und Zwischenstrecken
* [Zwischenstreckengrenzwert](https://go.multiroute.de/handbuch/gehfolgen/#zwischenstrecken)
  zur Festlegung, ab welcher Entfernung eine Verbindung als Zwischenstrecke
  behandelt wird
- Steckzeiten
- Rüstzeiten
- Hauszugangsdistanzen
- Hauszugangssuchradius

## Parameter ändern per Import
Natürlich müssen Sie nicht jedes Gebiet einzeln durchklicken und Änderungen am jeweligen Bezirk abspeichern.
Sie können das auch elegant per Upload lösen für eine ganze Ausgabe.
Die passende Musterdatei dazu finden Sie hier:

[Import-Parameter Bezirkseigenschaften.xlsx](https://github.com/user-attachments/files/18206637/Import-Parameter.Bezirkseigenschaften.xlsx)

Ändern Sie nur für die Gebietsnummern die Werte, die abweichend von den globen Werten/Ausgabenwerten sind. Dann gehen Sie folgendermaßen vor:

1. IN DER RICHTIGEN AUSGABE auf "Upload" gehen und die Datei auswählen.
2. Auf "Weitere Optionen" gehen und "Verteilbezirk updaten" auswählen:

![grafik](https://github.com/user-attachments/assets/b82081aa-ed0a-4923-90b1-592bf41fb8c9)

3. Spalten zuweisen, Adressen ab Zeile 1 (damit Sie die Überschriften nicht importieren) und auf UPLOAD drücken.

Jetzt haben alle Gebiete/Bezirke die von Ihnen zugewiesenen Parameter in dieser Ausgabe.

So können Sie auch gut die Parameter für Bezirke für einen Montag ganz anders hinterlegen als für einen Samstag.

