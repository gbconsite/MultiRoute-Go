# Begriffe und Definitionen


## Ausgabe ##
Verlage nutzen typischerweise die Ausgaben, um unterschiedliche Verteilschemata im Verbreitungsgebiet parallel zu verwalten (z.B. Mittwochs und Samstags oder Tageszeitung/Anzeigenblatt). Die Ausgaben können aber ebenso genutzt werden, um regionale Ausgaben voneinander getrennt zu verwalten. Außerdem können Ausgaben auch Planungszwecken dienen, d.h. man führt eine Ausgabe mit dem Ist-Zustand und eine weitere mit dem Soll-Zustand, an dem man derzeit arbeitet. Kunden mit Schnittstellen können automatisiert je Verteiltag eine Ausgabe befüllen.
Die Module Gebietsplanung und Gehfolgenberechnung arbeiten immer innerhalb der gewählten Ausgabe. Sie sehen oben im Menü immer, in welcher Ausgabe Sie gerade arbeiten.

## Geschwindigkeit 
Wir geben die Strecken einzeln aus, die Sie mit verschiedenen Geschwindigkeiten belegen können:
- Hin- und Rückweg in den Bezirk
- Strecke im Bezirk
- Hauszugangsdistanz (HZD)

## Hauszugangsdistanz (HZD)
Die Strecke, die vom Straßenankerpunkt zum Gebäude zurückgelegt wird, bezeichnen wir als HZD.

## Hauszugangs-Suchradius

## Koordinaten
Wenn wir von Koordinaten sprechen, dann sind die Gebäude gemeint. Jede Adresse hat also eigene Koordinaten (Latitude, Longitude / x, y) und ist direkt in MultiRoute Go! hinterlegt. 

## Matching
Unter Matching verstehen wir das eindeutige Zuordnen von Adressen zu Gebäudekoordinaten.

## Rüstzeit
Eine pauschale Angabe in Minuten. Kann von Ihnen per API nach berechneter Formel übergeben werden.

## Steckzeit
Wir unterscheiden eine Erste Steckung und Folgesteckungen mit Angaben in Sekunden.

## Optimierungsmethode
Drei Möglichkeiten:
- Einfacher Durchgang (one-way-open-end)
- Rundweg (egal wo die Abladestelle war, dorthin wieder zurück)
- Rundweg im Verteilbezirk (falls Abladestelle außerhalb des Bezirks war, dann zurück zur 1. Steckung)




