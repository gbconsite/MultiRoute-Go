---
title: Einstellungen für Power-User und Administratoren von MultiRoute Go!
description: Das Menü eröffnet die Möglichkeit, Rechte und Rollen von Anwendern zu definieren. Wer darf was sehen, wie wird welcher Verteilbezirk gerechnet? Alles einstellbar und konfigurierbar. 
---

Das Menü Administration stellt sich Nutzern je nach Zugriffsrechten in MultiRoute Go! unterschiedlich dar.

Welche Rechte die einzelnen Benutzerrollen besitzen, erfahren Sie in der [Benutzerverwaltung](https://go.multiroute.de/handbuch/user/).

Grundsätzlich stehen folgende Menüpunkte zur Verfügung:

* *Kunden (nicht in der SaaS-Version von MultiRoute Go! verfügbar)*
* Ausgaben
* Geschäftsstellen (nicht für alle im Standard sichtbar)
* Benutzer
* Verteilbezirke
* Gehfolgen
* Upload


## Kunden ##
Hier können berechtigte Nutzer verschiedene Optionen einstellen. Dazu gehören vor allem die grundlegenden Einstellungen für die Gehfolgenberechnung (Einfache Strecke, Rundweg, Rundweg im Verteilbezirk), die Einstellungen für die Trägerdokumente und Steckzeiten. Hier führen Sie auch die Voreinstellungen für Geschwindigkeiten und Hauszugangsdistanzen durch.
Die Bedeutung und Auswirkungen der einzelnen Berechnungsparameter erläutert das Kapitel [Gehfolgenberechnung](https://go.multiroute.de/handbuch/gehfolgen/#parameter-fur-die-gehfolgenberechnung).

Einstellungen auf Kundenebene können durch abweichende Angaben in einer [Ausgabe](#ausgaben) oder einem [Verteilbezirk](#verteilbezirke) übersteuert werden. Die Rangfolge erklärt der Abschnitt [Einstellungen bei Gehfolgenberechnungen](https://go.multiroute.de/handbuch/gehfolgen/#einstellungen-bei-gehfolgenberechnungen).

## Ausgaben ##
Hier können Sie bestehende Ausgaben ```Bearbeiten``` oder neue Ausgaben anlegen. 
Legen Sie hier die Parameter für die jeweilige Ausgabe fest für die Gehfolgenberechnungen. 
Was eine Ausgabe ist und wofür Sie diese verwenden können, erfahren Sie unter [Begriffe → Ausgabe](https://go.multiroute.de/handbuch/definitionen/#ausgabe).

Je Ausgabe können Sie auch die Darstellungsart der automatisch erzeugten Gebietspolygone auswählen. Welche Variante für Ihre Aufgabenstellung geeignet ist, erfahren Sie unter [Darstellung: Gummiband oder Voronoi](https://go.multiroute.de/handbuch/gebietsplanung/#darstellung-gummiband-oder-voronoi).

Häufig wird eine eigene Ausgabe zu Planungszwecken erstellt. Dazu gehen Sie folgendermaßen vor:
Administration - Ausgaben - 'Neue Ausgabe'

Diese können Sie anschließend mit Informationen aus einer anderen Ausgabe befüllen. Dazu einfach auf `Verteilbezirke` gehen und die gewünschten Verteilbezirke markieren. 
Ganz unten dann auf 
"Markierte Verteilbezirke" in Ausgabe 'Neue Ausgabe' kopieren oder verschieben. Nur noch auf ```Anwenden``` drücken und schon haben Sie die gewünschten Polygone in der neuen Ausgabe.
Hinterlegte Abladestellen kopieren Sie so übrigens gleich mit!

Abonnenten können Sie unter [Administration → Upload](#upload) kopieren oder verschieben.

Wichtig: Nicht jeder User hat diese Rechte. Sollten Sie das nicht sehen, sprechen Sie Ihren MultiRoute Go! Administrator an oder melden Sie sich bei uns.

## Geschäftsstelle ##
❗ Achtung! Nicht im Standard enthalten - bitte sprechen Sie uns an!
Vielleicht möchten Sie, dass der Lesermarkt oder der Betriebsrat nur auf bestimmte Ausgaben zugreifen darf? Dann können Sie über Geschäftsstellen eingrenzen, wer welche Ausgabe sehen darf und auch hier noch, welche Rechte der einzelne Benutzer hat. Änderungen an Gebieten vornehmen ja/nein oder Gehfolgen ansehen/berechnen ja/nein.
Ein Benutzer kann dabei mehreren Geschäftsstellen zugehörig sein.


## Benutzer ##
In der [Benutzerverwaltung](https://go.multiroute.de/handbuch/user/) verwalten Sie Benutzer, ändern Passwörter und legen Berechtigungen fest. Dort finden Sie auch die Erläuterungen zu den einzelnen Benutzerrollen.

## Verteilbezirke ##
Für einzelne Verteilbezirke der ausgewählten Ausgabe, in der Sie sich gerade befinden, können Sie Änderungen - abweichend zu den übergeordneten Ebenen -  an den Parametern zur Gehfolgenberechnung durchführen. Verteilbezirke können auch bearbeitet (bspw. umbenannt) werden.
Die Bearbeitung von Gebietsflächen und die Zuordnung von Adressen beschreibt das Kapitel [Gebietsplanung](https://go.multiroute.de/handbuch/gebietsplanung/).

Die Bedeutung der bezirksspezifischen Berechnungsparameter erläutert der Abschnitt [Parameter für die Gehfolgenberechnung](https://go.multiroute.de/handbuch/gehfolgen/#parameter-fur-die-gehfolgenberechnung).

Um die hinterlegten Werte mehrerer Bezirke zu prüfen oder weiterzuverwenden, können Sie die [Eigenschaften der Verteilgebiete exportieren](https://go.multiroute.de/handbuch/exporte/#eigenschaften-der-verteilgebiete).

## Gehfolgen ##
Hier finden Sie die bereits berechneten Gehfolgen der aktuell ausgewählten Ausgabe.

Wie Sie Ergebnisse aufrufen und prüfen, erläutert der Abschnitt [Aufruf von berechneten Gehfolgen](https://go.multiroute.de/handbuch/gehfolgen/#aufruf-von-berechneten-gehfolgen).
Informationen zur Weiterverarbeitung finden Sie unter [Exporte → Gehfolgen](https://go.multiroute.de/handbuch/exporte/#gehfolgen).

## Upload ##
Unter Upload können berechtigte Benutzer unter anderem folgende Daten hochladen:

* Gebäude (Koordinaten)
* Bezirkszuordnungen
* [Spezialhäuser](https://go.multiroute.de/handbuch/spezialhaeuser/)

Beachten Sie beim Hochladen von Bezirkszuordnungen die unterschiedlichen [Upload-Modi](https://go.multiroute.de/handbuch/upload_manuell/#upload).
Diese bestimmen, ob vorhandene Zuordnungen ergänzt, überschrieben oder ersetzt werden.

Weitere Informationen finden Sie unter:

- [Datenintegration](https://go.multiroute.de/handbuch/upload/) für Erstbefüllung, Matching und Schnittstellen.
- [Importe](https://go.multiroute.de/handbuch/importe/) für den Import von Gebietsgeometrien und GPX-Dateien.
- [Automatisierung](https://go.multiroute.de/handbuch/automatisierung/) für die regelmäßige Datenübernahme.


Hier können Sie auch **Abonnenten verwalten** mit den Möglichkeiten:

* löschen
* kopieren
* verschieben
