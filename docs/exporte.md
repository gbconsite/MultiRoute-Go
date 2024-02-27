---
description: Exportmöglichkeiten für Auswertungen in Reports
---

# 9. Exporte

Manuelle Exportmöglichkeiten bietet MultiRoute Go! an den verschiedensten Stellen. 

## Adressverwaltung 

Aus der Adressverwaltung heraus besteht die Möglichkeit Gebäude zu filtern und mit/ohne Zuordnungen zu exportieren.

![grafik](https://user-images.githubusercontent.com/99329016/167629229-2027f10c-694c-4c7e-9b66-4c94b316c7a9.png "Exportmöglichkeiten mit Hilfe von Filtern")

Auch die Zustellerhäuser (Abladestellen),  Start-/Endhäuser oder Depots können Sie hier exportieren. 

## Gehfolgen

In Ihrer aktuellen, aktiven Ausgabe können Sie auch jederzeit die Gehfolgen exportieren:
![grafik](https://user-images.githubusercontent.com/99329016/167630490-932c3daf-6822-4843-a81a-10da0d9c0640.png "Export der aktuellen Verteilschiene in MRGo")


## Arbeiten mit Gehfolgenexport
Sie erhalten zwei Dateien. 

![grafik](https://github.com/gbconsite/MultiRoute-Go/assets/99329016/7e10ce7d-0407-40b0-892e-f6966c1d6282 "zwei Export Dateien der Gangfolgenberechnung)

In "gehfolgen" erhalten Sie ALLE Informationen inklusive aller Steckpunkte zu ALLEN Gehfolgen der anzeigten Ausgabe.
In "gehfolgen-zusammenfassung" nur die Summierung der Zeiten/Strecken. 

Für Auswertungen des ZIP-Files in Excel gehen Sie am Besten folgendermaßen vor:

1. Entzippen der Datei.
2. Öffnen mit dem Editor, alles markieren [STRG+A], dann alles kopieren [STRG+C].
3. Öffnen Sie ein leeres Excel und nutzen Sie den Textkonvertierungsassistenten:
   
![grafik](https://github.com/gbconsite/MultiRoute-Go/assets/99329016/b6360eac-1c04-4fe0-8b77-82248113e2f6 "Excel Textkonvertierungs-Assistent")

Und navigieren Sie sich durch den Assistenten:

![grafik](https://github.com/gbconsite/MultiRoute-Go/assets/99329016/8aa885e8-7330-4946-9bd1-2d5e620627e3 "Excel Textkonvertierungs-Assistent")


![grafik](https://github.com/gbconsite/MultiRoute-Go/assets/99329016/294f66a2-9b96-47b9-9d8b-47cdf7c4a146 "Excel Textkonvertierungs-Assistent")

PIPE als Trennzeichen eingeben!

![grafik](https://github.com/gbconsite/MultiRoute-Go/assets/99329016/5071fdf3-52a5-491e-9646-2f8a44e5add7 "Pipe im Excel Textkonvertierungs-Assistent")
Unter ERWEITERT noch Punkt und Komma tauschen.

4. Fertig stellen.
5. Nun können Sie alle Auswertungen in Excel mit korrekter Formatierung durchführen.



## Industriezeit

In vielen Exporten gibt MultiRoute Go! die berechnete Zeit in Industriestunden aus. Wie Sie das wieder in "normale Zeit" umrechnen können oder wie genau das zu lesen ist, finden Sie auch hier: [https://de.wikipedia.org/wiki/Industrieminute](https://de.wikipedia.org/wiki/Industrieminute)

