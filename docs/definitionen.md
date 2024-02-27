---
description: Begriffe und Definitionen, die in MultiRoute Go! verwendet werden
---

# Begriffe und Definitionen


## Ausgabe ##
Verlage nutzen typischerweise die Ausgaben, um unterschiedliche Verteilschemata/Verteilschienen im Verbreitungsgebiet parallel zu verwalten (z.B. Mittwochs und Samstags oder Tageszeitung/Anzeigenblatt). Die Ausgaben können aber ebenso genutzt werden, um regionale Ausgaben voneinander getrennt zu verwalten. Außerdem können Ausgaben auch Planungszwecken dienen, d.h. man führt eine Ausgabe mit dem Ist-Zustand und eine weitere mit dem Soll-Zustand (Planungsausgabe), an dem man derzeit arbeitet. Kunden mit Schnittstellen können automatisiert je Verteiltag eine Ausgabe befüllen.
Die Module Gebietsplanung und Gehfolgenberechnung arbeiten immer innerhalb der gewählten, aktuellen Ausgabe. Sie sehen oben im Menü immer, in welcher Ausgabe Sie gerade arbeiten.

## Geschwindigkeit 
Wir geben die Strecken einzeln aus, die Sie mit verschiedenen Geschwindigkeiten belegen können:
- Hin- und Rückweg in den Bezirk
- Strecke im Bezirk
- Hauszugangsdistanz (HZD)

## Hauszugangsdistanz (HZD)
Die Strecke, die vom Straßenankerpunkt (Anbindung) zum Gebäude zurückgelegt wird, bezeichnen wir als HZD. [Hier](../gehfolgen/#hauszugangsdistanz-hzd) im Kapitel zur Gehfolgenberechnung erklärt.

## Hauszugangs-Suchradius
Ausführliche [Erläuterung](../gehfolgen/#hauszugangs-suchradius) im Kapitel zur Gehfolgenberechnung.


## Koordinaten
Wenn wir von Koordinaten sprechen, dann sind die Gebäude gemeint. Jede Adresse hat also eigene Koordinaten (Latitude, Longitude / x, y) und ist direkt in MultiRoute Go! hinterlegt. 

## Matching
Unter Matching verstehen wir das eindeutige Zuordnen von Adressen oder Gebäude-/ Straßen-IDs zu Gebäudekoordinaten.

## Rüstzeit
Eine pauschale Angabe in Minuten. Kann von Ihnen per API nach berechneter Formel (bspw. X Sekunden je Stück) übergeben werden.

## Steckzeit
Wir unterscheiden eine Erste Steckung und Folgesteckungen mit Angaben in Sekunden.
Eine Unterscheidung nach Produkten (Brief, Zeitung, Paket etc.) haben wir aktuell noch nicht umgesetzt.

## Optimierungsmethode
[Drei Möglichkeiten](https://go.multiroute.de/handbuch/gehfolgen/#einstellungen-bei-gehfolgenberechnungen):

- Einfacher Durchgang (one-way-open-end)
- Rundweg (egal wo die Abladestelle war, dorthin wieder zurück)
- Rundweg im Verteilbezirk (falls Abladestelle außerhalb des Bezirks war, dann zurück zur 1. Steckung)

## Zustellerhaus
In der Regel die "normale" Abladestelle. Der Name Zustellerhaus leitet sich von der Tatsache ab, dass gerade bei Wochenblättern die Gebinde an den Wohnort des Zustellers geliefert werden.
Das Zustellerhaus kann außerhalb des Verteilbezirkes sein und hat in diesem Fall auch keine Zuordnung zu diesem. Am Zustellerhaus wird in diesem Fall nicht gesteckt.

## Starthaus
Gebäudepunkt mit dem ersten Steckvorgang. Wird standardmäßig automatisch ermittelt, kann aber auch manuell festgelegt werden (z.B. um den Platz für den Abstellort des Zusteller-KFZ zu bestimmen)

## Endhaus
Gebäudepunkt mit dem letzten Steckvorgang. Wird standardmäßig automatisch ermittelt, kann aber auch manuell festgelegt werden.

## Depot
Zusätzliche Abladestelle(n) eines Verteilbezirkes (nur verfügbar mit dem Zusatzmodul "Nachladen").


