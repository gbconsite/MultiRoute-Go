---
description: Verschiedene Exportmöglichkeiten, die es dem Zusteller/Springer leichter machen die Zustellung so einfach wie möglich zu erledigen
---

# **7. Trägerdokumente**

Zu jeder berechneten Gehfolge gibt es einen Ergebnisbericht mit den Informationen zur Gehfolge.
- Die Dauer der Strecke ist abhängig von der Gehgeschwindigkeit. Diese kann manuell für jeden Bezirk angepasst werden mit zwei Nachkommastellen.
- Die Steckzeiten für die erste Steckung und die Folgesteckungen werden vorab definiert und hier berechnet. Die Steckzeiten werden extra ausgegeben und als Gesamtsumme mit der Streckenzeit. Je Ausgabe/Bezirk können die Steckzeiten angepasst werden.
- Die Summe der Strecke für die Hauszugangsdistanzen wird separat angegeben. Diese kann durch Aktivierung der Gesamtdauer hinzugefügt werden. Die entsprechenden Werte verändern sich dann.

![grafik](https://user-images.githubusercontent.com/99329016/170692371-21ce7637-7197-4305-a5d7-b946af9b7923.png "Details der Gehfolgenberechnung")

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
Zwei mögliche Varianten als PDF:
- rot umrandet der Trägerbezirk mit allen Gebäuden, in denen gesteckt wird als schwarzer Punkt ohne berechnete Route
- wie oben nur mit Route und Markierung für jedes 10. Gebäude

## Gehfolge
PDF der optimierten Gehfolge inkl. der an den Gebäuden vermerkten Bemerkungen.

## Straßenliste
Alle Straßen des Verteilbezirks alphabetisch und mit aufsteigenden Hausnummern sortiert.

## Excel
Eine Datei inklusive aller berechneter Faktoren und Zahlen. Wunderbar geeignet für die Dokumentation.
Aufgeteilt auf zwei Reiter:

1. Metainformationen
2. Gehfolge mit allen Parametern

## GPX 
Datei zur Übertragung in Navigationsgeräte oder andere Applikationen.

## QR Code
Liste zur schnellen Orientierung und direktem Aufruf in Google oder Apple Maps.
