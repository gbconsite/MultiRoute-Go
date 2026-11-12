---
title: Begriffe und Definitionen, die in MultiRoute Go! verwendet werden
description: Manche Begriffe kennen Sie schon in anderem Zusammenhang. Was genau meint Gehfolge, Gangfolge, Route? Oder Steckstrecke, Gebäudestrecke, Anbindung? Hier erhalten Sie Klarheit.
---

# Begriffe und Definitionen


## Ausgabe ##
Verlage nutzen typischerweise die Ausgaben, um unterschiedliche Verteilschemata/Verteilschienen im Verbreitungsgebiet parallel zu verwalten (z.B. Mittwochs und Samstags oder Tageszeitung/Anzeigenblatt). Die Ausgaben können aber ebenso genutzt werden, um regionale Ausgaben voneinander getrennt zu verwalten. Außerdem können Ausgaben auch Planungszwecken dienen, d.h. man führt eine Ausgabe mit dem Ist-Zustand und eine weitere mit dem Soll-Zustand (Planungsausgabe), an dem man derzeit arbeitet. Kunden mit Schnittstellen können automatisiert je Verteiltag eine Ausgabe befüllen.
Die Module Gebietsplanung und Gehfolgenberechnung arbeiten immer innerhalb der gewählten, aktuellen Ausgabe. Sie sehen oben im Menü immer oben rechts, in welcher Ausgabe Sie gerade arbeiten.
Wie Sie die gewünschte Ausgabe über das Suchfeld finden und zu ihr wechseln,
erfahren Sie unter
[Grundlagen → Ausgabe suchen und wechseln](https://go.multiroute.de/handbuch/grundlagen/#ausgabe-suchen-und-wechseln).

## Geschwindigkeit 
Für unterschiedliche Streckenanteile können Sie eigene Geschwindigkeiten
hinterlegen:

- Hin- und Rückweg zum beziehungsweise vom Verteilbezirk
- Zustellstrecke im Verteilbezirk
- Hauszugangsdistanz (HZD)
- Zwischenstrecken

Weitere Informationen finden Sie unter
[Gehfolgenberechnung → Geschwindigkeiten](https://go.multiroute.de/handbuch/gehfolgen/#geschwindigkeiten).

Wie Zwischenstrecken bei der Dichte- und Zeitberechnung berücksichtigt
werden, erläutert der Abschnitt
[Zwischenstrecken](https://go.multiroute.de/handbuch/gehfolgen/#zwischenstrecken).

## [Hauszugangsdistanz (HZD)](gehfolgen.md#hauszugangsdistanz-hzd-grenzwert)
Die Strecke, die vom Straßenankerpunkt (Anbindung) zum Gebäude zurückgelegt wird, bezeichnen wir als HZD. [Hier](gehfolgen.md#hauszugangsdistanz-hzd-grenzwert) im Kapitel zur Gehfolgenberechnung erklärt.
Auch Gebäudestrecke oder Steckstrecke genannt.

## [Hauszugangs-Suchradius](gehfolgen.md#hauszugangs-suchradius)
Ausführliche [Erläuterung](gehfolgen.md#hauszugangs-suchradius) im Kapitel zur Gehfolgenberechnung.


## Koordinaten
Wenn wir von Koordinaten sprechen, dann sind die Gebäude gemeint. Jede Adresse hat also eigene Koordinaten (Latitude, Longitude / x, y) und ist direkt in MultiRoute Go! hinterlegt. 

## Matching
Unter Matching verstehen wir das eindeutige Zuordnen von Adressen oder Gebäude-/ Straßen-IDs zu Gebäudekoordinaten.

## Rüstzeit
Eine pauschale Angabe in Minuten. Kann von Ihnen per API nach berechneter Formel (bspw. X Sekunden je Stück) übergeben werden.

## Steckzeit
Die Steckzeit beschreibt die Zeit für das Zustellen eines Exemplars am
Gebäude. Sie wird in Sekunden angegeben. MultiRoute Go! unterscheidet
zwischen der ersten Steckung und weiteren Steckungen am selben Gebäude.

Weitere Informationen zur Berücksichtigung unterschiedlicher Produkte
finden Sie unter
[Gehfolgenberechnung → Steckzeiten](https://go.multiroute.de/handbuch/gehfolgen/#steckzeiten).

## Optimierungsmethode
Für die Gehfolgenberechnung stehen drei Optimierungsmethoden zur Verfügung:

- **Einfache Strecke:** Die Route endet ohne Rückkehr zum Ausgangspunkt.
  Ein festes Endhaus kann vorgegeben werden.
- **Rundweg:** Die Route führt zur Abladestelle zurück.
- **Rundweg im Verteilbezirk:** Die Route führt zur ersten Steckung
  im Verteilbezirk zurück.

Weitere Informationen und Beispiele finden Sie unter
[Gehfolgenberechnung → Optimierungsmethode](https://go.multiroute.de/handbuch/gehfolgen/#optimierungsmethode).

## Zustellerhaus
In der Regel die "normale" Abladestelle. Der Name Zustellerhaus leitet sich von der Tatsache ab, dass gerade bei Wochenblättern die Gebinde an den Wohnort des Zustellers geliefert werden.
Das Zustellerhaus kann außerhalb des Verteilbezirkes sein und hat in diesem Fall auch keine Zuordnung zu diesem. Am Zustellerhaus wird in diesem Fall nicht gesteckt.
Wie Sie ein Zustellerhaus beziehungsweise eine Abladestelle festlegen,
erfahren Sie im Kapitel
[Spezialhäuser](https://go.multiroute.de/handbuch/spezialhaeuser/).

## Starthaus
Gebäudepunkt mit dem ersten Steckvorgang. Wird standardmäßig automatisch ermittelt, kann aber auch manuell festgelegt werden (z.B. um den Platz für den Abstellort des Zusteller-KFZ zu bestimmen). Muss sich im zugeordneten Gebiet befinden.

## Endhaus
Gebäudepunkt mit dem letzten Steckvorgang. Wird standardmäßig automatisch ermittelt, kann aber auch manuell festgelegt werden.

## Depot
Zusätzliche Abladestelle(n) eines Verteilbezirkes (nur verfügbar mit dem Zusatzmodul "Nachladen"). Hierhin kehrt der Zusteller zum Nachladen zurück. Wir können mehrere "Depots" in einem Verteilbezirk definieren.
Wie Sie Depots anlegen und das Nachladen bei der Gehfolgenberechnung
berücksichtigen, erfahren Sie unter
[Zusatzmodule → Nachladen an Depots](https://go.multiroute.de/handbuch/zusatzmodule/#nachladen-an-depots).

