---
title: Verschiedene Exportmöglichkeiten, die es dem Zusteller/Springer leichter machen die Zustellung so einfach wie möglich zu erledigen
description: Für Freunde des Papiers werden optimierte Gangfolgen als PDF ausgegeben. Kann dem Packzettel beigefügt werden. Springern erleichtert die berechnete Gehfolge die Arbeit. Per API auch Weitergabe an Zusteller-App möglich.
---

# **7. Trägerdokumente**

Zu jeder berechneten Gehfolge erhalten Sie einen Ergebnisbericht
mit Angaben zu Strecken und Zeiten.

Die Zeitberechnung berücksichtigt die hinterlegten Einstellungen:

- **Wegezeiten:** Sie ergeben sich aus den Streckenlängen und den
  jeweils angesetzten Geschwindigkeiten.
- **Steckzeiten:** Die Zeiten für die erste Steckung und weitere
  Steckungen werden separat ausgewiesen und bei der Gesamtzeit berücksichtigt.
- **Hauszugangsdistanzen:** Die Wege zwischen Straßenankerpunkt und
  Gebäude werden separat ausgewiesen. Ihre Berücksichtigung in der
  Strecken- und Zeitberechnung hängt von den gewählten Einstellungen ab.

Die einzelnen Einstellungen erläutert das Kapitel
[Gehfolgenberechnung](https://go.multiroute.de/handbuch/gehfolgen/#parameter-fur-die-gehfolgenberechnung).


Parallel zur Berechnung der Gehfolgen werden PDF Dokumente und Daten erzeugt:

- Bezirkskarte
- Gehfolge
- Straßenliste
- Excel (Datei mit Metadaten und Einzeldaten)
- GPX 
- QR Codes für Google Maps/Apple Maps

![grafik](https://user-images.githubusercontent.com/99329016/170691421-7769c0df-8c51-4de1-94e9-ca69e1352f6f.png "Übersicht der zur Laufzeit erzeugten Gangfolgendokumente")


Diese Dokumente können aus dem Gehfolgenmenü heraus abgerufen und lokal gespeichert werden.
Die Übertragung per API ist natürlich ebenfalls möglich.

Bei *Bezirkskarte* und *Gehfolgen* können wir Veränderungen in der Legende unwaufwändig vornehmen. Wir bieten verschiedene Varianten, die wir gerne besprechen können. 


## Bezirkskarte

Die Bezirkskarte unterstützt Zusteller bei der Orientierung im
Verteilbezirk. Die neue Darstellung umfasst eine **Routenkarte**
und einen **Übersichtsplan**.

### Routenkarte

Die Routenkarte zeigt die berechnete Gehfolge mit Zustellreihenfolge,
Hausnummern und Richtungspfeilen.

<img width="381" height="324" alt="route" src="https://github.com/user-attachments/assets/40910407-6dfb-47eb-a5fa-cb013fe3433e" />


| Darstellung | Bedeutung |
|---|---|
| Zahl im blauen Kreis | Position des Gebäudes in der Gehfolge |
| Zahl im Haussymbol | Hausnummer des Gebäudes |
| Blaue Linie mit Richtungspfeilen | Verlauf und Richtung der Route |
| Rote Umrandung | Grenze des Verteilbezirks |

Die Position in der Gehfolge und die zugehörige Hausnummer stehen
direkt nebeneinander.

**Beispiel:** Ein blauer Kreis mit der Zahl **1** neben einem
Haussymbol mit der Zahl **12** bedeutet: Hausnummer 12 steht
an erster Position in der Gehfolge.

### Übersichtsplan

Der Übersichtsplan zeigt die Grenze des Verteilbezirks sowie die Lage
der Gebäude und Straßen. Die Gebäude sind mit kleinen Kreisen markiert.

Die zusätzliche blaue Routenlinie, die Richtungspfeile und die
Reihenfolgenmarkierungen der Routenkarte werden hier ausgeblendet.
So dient der Übersichtsplan der räumlichen Orientierung im Bezirk.

### Angaben zum Bezirk

Das Beschriftungsfeld unten rechts enthält die Bezirkskennung und
ergänzende Angaben wie den Ortsnamen und das Unternehmen.


## Gehfolge
PDF der optimierten Gehfolge inkl. der an den Gebäuden vermerkten Bemerkungen.

## Straßenliste
Die Straßenliste führt die Straßen des Verteilbezirks alphabetisch auf.
Innerhalb jeder Straße sind die Hausnummern aufsteigend sortiert.

Die Sortierung entspricht nicht der berechneten Zustellreihenfolge.
Wenn Sie die Gebäude in der Reihenfolge der Zustellung benötigen,
verwenden Sie die [Gehfolgenliste](#gehfolge).

## Excel
Die Excel-Datei enthält die Ergebnisse der berechneten Gehfolge
in zwei Tabellenblättern:

1. **Metainformationen:** Zusammenfassende Angaben zur Gehfolge.
2. **Gehfolge mit allen Parametern:** Einzelangaben zur berechneten
   Zustellreihenfolge. Sämtliche Teilstrecken werden hier einzeln ausgewiesen.

Die Datei eignet sich zur Dokumentation und für eigene Auswertungen.

Werden Zeitwerte als Dezimalstunden ausgegeben, hilft die Erklärung unter
[Exporte → Industriezeit](https://go.multiroute.de/handbuch/exporte/#industriezeit)
bei der Umrechnung in Stunden und Minuten.

## GPX 
Die GPX-Datei enthält den berechneten Routenverlauf. Sie können diese
in kompatible Navigationsgeräte oder andere Anwendungen zur
Darstellung und Weiterverarbeitung von Routen übernehmen.

Wenn Sie eine tatsächlich aufgezeichnete Tour mit der berechneten
Gehfolge vergleichen möchten, können Sie den aufgezeichneten Track
in MultiRoute Go! laden. Die Anleitung finden Sie unter
[Optimierungen → Tracks, Touren, Routen abbilden](https://go.multiroute.de/handbuch/gehfolgenoptimieren/#tracks-touren-routen-abbilden).

## QR Code
Liste zur schnellen Orientierung und direktem Aufruf in Google oder Apple Maps.
