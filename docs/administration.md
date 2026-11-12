---
title: Einstellungen für Power-User und Administratoren von MultiRoute Go!
description: Das Menü eröffnet die Möglichkeit, Rechte und Rollen von Anwendern zu definieren. Wer darf was sehen, wie wird welcher Verteilbezirk gerechnet? Alles einstellbar und konfigurierbar. 
---

Das Menü Administration stellt sich Nutzern je nach Zugriffsrechten in MultiRoute Go! unterschiedlich dar.

Welche Rechte die einzelnen Benutzerrollen besitzen, erfahren Sie in der [Benutzerverwaltung](user.md).

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
Die Bedeutung und Auswirkungen der einzelnen Berechnungsparameter erläutert das Kapitel [Gehfolgenberechnung](gehfolgen.md#parameter-fur-die-gehfolgenberechnung).

Einstellungen auf Kundenebene können durch abweichende Angaben in einer [Ausgabe](#ausgaben) oder einem [Verteilbezirk](#verteilbezirke) übersteuert werden. Die Rangfolge erklärt der Abschnitt [Einstellungen bei Gehfolgenberechnungen](gehfolgen.md#einstellungen-bei-gehfolgenberechnungen).

## Ausgaben ##
Hier können Sie bestehende Ausgaben ```Bearbeiten``` oder neue Ausgaben anlegen. 
Legen Sie hier die Parameter für die jeweilige Ausgabe fest für die Gehfolgenberechnungen. 
Was eine Ausgabe ist und wofür Sie diese verwenden können, erfahren Sie unter [Begriffe → Ausgabe](definitionen.md#ausgabe).

Je Ausgabe können Sie auch die Darstellungsart der automatisch erzeugten Gebietspolygone auswählen. Welche Variante für Ihre Aufgabenstellung geeignet ist, erfahren Sie unter [Darstellung: Gummiband oder Voronoi](gebietsplanung.md#gummiband-oder-voronoi).

Häufig wird eine eigene Ausgabe zu Planungszwecken erstellt. Dazu gehen Sie folgendermaßen vor:
Administration - Ausgaben - 'Neue Ausgabe'

Diese können Sie anschließend mit Informationen aus einer anderen Ausgabe befüllen. Dazu einfach auf `Verteilbezirke` gehen und die gewünschten Verteilbezirke markieren. 
Ganz unten dann auf 
"Markierte Verteilbezirke" in Ausgabe 'Neue Ausgabe' kopieren oder verschieben. Nur noch auf ```Anwenden``` drücken und schon haben Sie die gewünschten Polygone in der neuen Ausgabe.
Hinterlegte Abladestellen kopieren Sie so übrigens gleich mit!

Abonnenten können Sie unter [Administration → Upload](#upload) kopieren oder verschieben.

Wichtig: Nicht jeder User hat diese Rechte. Sollten Sie das nicht sehen, sprechen Sie Ihren MultiRoute Go! Administrator an oder melden Sie sich bei uns.

## Ausgabe auswählen und suchen ##

Über das Auswahlfeld „Aktuelle Ausgabe“ im oberen Bereich von MultiRoute Go! wechseln Sie zwischen den verfügbaren Ausgaben.

Damit Sie die gewünschte Ausgabe schneller finden, steht Ihnen in der Auswahlliste eine Suchfunktion zur Verfügung.

So funktioniert es:

Klicken Sie auf das Auswahlfeld „Aktuelle Ausgabe“.

Geben Sie im Suchfeld einen Teil der gesuchten Ausgabebezeichnung ein, beispielsweise montag.

Die Auswahlliste wird automatisch auf passende Einträge eingegrenzt.

Klicken Sie auf die gewünschte Ausgabe, um diese auszuwählen.

Tipp: Besonders bei einer großen Anzahl an Ausgaben sparen Sie mit der Suchfunktion Zeit und vermeiden langes Scrollen.

## Geschäftsstelle ##
❗ Achtung! Nicht im Standard enthalten - bitte sprechen Sie uns an!
Vielleicht möchten Sie, dass der Lesermarkt oder der Betriebsrat nur auf bestimmte Ausgaben zugreifen darf? Dann können Sie über Geschäftsstellen eingrenzen, wer welche Ausgabe sehen darf und auch hier noch, welche Rechte der einzelne Benutzer hat. Änderungen an Gebieten vornehmen ja/nein oder Gehfolgen ansehen/berechnen ja/nein.
Ein Benutzer kann dabei mehreren Geschäftsstellen zugehörig sein.


## Benutzer ##
In der [Benutzerverwaltung](user.md) verwalten Sie Benutzer, ändern Passwörter und legen Berechtigungen fest. Dort finden Sie auch die Erläuterungen zu den einzelnen Benutzerrollen.

## Transportmittel

Mit Transportmitteln hinterlegen Sie Vorgaben für die Gehfolgenberechnung.
Sie können eigene Transportmittel anlegen, beispielsweise Fahrrad, eBike,
Lastenrad, Auto oder Kastenwagen. Für jedes Transportmittel lassen sich
Standardgeschwindigkeiten, eine Stoppzeit und eine Dichtematrix hinterlegen.

### Transportmittel und Routingprofil

Jedes Transportmittel wird einem Routingprofil zugeordnet.
Zur Auswahl stehen **Fußweg**, **Fahrrad** und **Kfz**.

Das Routingprofil bestimmt, welche Straßen und Wege bei der Berechnung
berücksichtigt werden. Mehrere Transportmittel können dasselbe Routingprofil
verwenden und trotzdem unterschiedliche Geschwindigkeiten und Stoppzeiten
besitzen.

Beispielsweise können „Fahrrad“, „eBike dienstlich“ und „Lastenrad“
das Routingprofil „Fahrrad“ verwenden, aber jeweils eigene
Berechnungsvorgaben erhalten.

### Standardwerte hinterlegen

Für jedes Transportmittel können Sie folgende Angaben pflegen:

| Einstellung | Bedeutung |
|---|---|
| Name | Bezeichnung des Transportmittels |
| Routingprofil | Grundlage für die Auswahl der nutzbaren Straßen und Wege |
| Geschwindigkeit im Verteilbezirk | Standardgeschwindigkeit für die Zustellstrecke |
| Geschwindigkeit Hinweg | Geschwindigkeit für den Hinweg |
| Geschwindigkeit Zwischenstrecken | Geschwindigkeit für längere Verbindungen zwischen Zustellpunkten |
| Schwellwert Zwischenstrecken (Meter) | Entfernungsgrenze für die Behandlung einer Verbindung als Zwischenstrecke |
| Stoppzeit in Sekunden | Transportmittelspezifische Zeitvorgabe für Stopps |

### Dichtematrix hinterlegen

Mit einer Dichtematrix legen Sie fest, welche Geschwindigkeit bei einer
bestimmten Anzahl von **Gebäudestopps je Kilometer** angesetzt wird.

Wählen Sie unter `Dichte Klassen` die Anzahl der Klassen. Hinterlegen
Sie für jede Klasse:

1. die untere Grenze der Gebäudestopps je Kilometer;
2. die obere Grenze der Gebäudestopps je Kilometer;
3. die zugehörige Geschwindigkeit in km/h.

Legen Sie die Bereiche so fest, dass die Dichteklassen eindeutig
aufeinanderfolgen und sich nicht überschneiden.

Jedes Transportmittel kann eine eigene Dichtematrix erhalten. So können
beispielsweise für Fahrrad, eBike und Auto bei gleicher Stoppdichte
unterschiedliche Geschwindigkeiten angesetzt werden.

Die Dichtematrix basiert auf Geschwindigkeitswerten von **Markus Bohl**.
Die Klassen und Geschwindigkeiten können für das jeweilige Transportmittel
individuell hinterlegt werden.

Wie MultiRoute Go! die Stoppdichte ermittelt und daraus die Geschwindigkeit
für die Zustellstrecke ableitet, erläutert
[Gehfolgenberechnung → Dichteabhängige Geschwindigkeit](https://go.multiroute.de/handbuch/gehfolgen/#dichteabhangige-geschwindigkeit).

### Synchronisierung mit zusie

Die Transportmittel und ihre Berechnungsvorgaben können auch aus
**[zusie](https://zusie.cloud/)** synchronisiert werden. Dadurch kann die Disposition in zusie
erfolgen, während MultiRoute Go! die Gehfolgen auf Grundlage der
übernommenen Daten berechnet.

Weitere Informationen finden Sie unter
[Datenintegration → Synchronisierung mit zusie](https://go.multiroute.de/handbuch/upload/#synchronisierung-mit-zusie).

## Verteilbezirke ##
Für einzelne Verteilbezirke der ausgewählten Ausgabe, in der Sie sich gerade befinden, können Sie Änderungen - abweichend zu den übergeordneten Ebenen -  an den Parametern zur Gehfolgenberechnung durchführen. Verteilbezirke können auch bearbeitet (bspw. umbenannt) werden.
Die Bearbeitung von Gebietsflächen und die Zuordnung von Adressen beschreibt das Kapitel [Gebietsplanung](gebietsplanung.md).

Die Bedeutung der bezirksspezifischen Berechnungsparameter erläutert der Abschnitt [Parameter für die Gehfolgenberechnung](gehfolgen.md#parameter-fur-die-gehfolgenberechnung).

Um die hinterlegten Werte mehrerer Bezirke zu prüfen oder weiterzuverwenden, können Sie die [Eigenschaften der Verteilgebiete exportieren](exporte.md#eigenschaften-der-verteilgebiete).

## Gehfolgen ##
Hier finden Sie die bereits berechneten Gehfolgen der aktuell ausgewählten Ausgabe.

Wie Sie Ergebnisse aufrufen und prüfen, erläutert der Abschnitt [Aufruf von berechneten Gehfolgen](gehfolgen.md#aufruf-von-berechneten-gehfolgen).
Informationen zur Weiterverarbeitung finden Sie unter [Exporte → Gehfolgen](exporte.md#gehfolgen).

## Upload ##
Unter Upload können berechtigte Benutzer unter anderem folgende Daten hochladen:

* Gebäude (Koordinaten)
* Bezirkszuordnungen
* [Spezialhäuser](spezialhaeuser.md)

Beachten Sie beim Hochladen von Bezirkszuordnungen die unterschiedlichen [Upload-Modi](upload_manuell.md#upload).
Diese bestimmen, ob vorhandene Zuordnungen ergänzt, überschrieben oder ersetzt werden.

Weitere Informationen finden Sie unter:

- [Datenintegration](upload.md) für Erstbefüllung, Matching und Schnittstellen.
- [Importe](importe.md) für den Import von Gebietsgeometrien und GPX-Dateien.
- [Automatisierung](automatisierung.md) für die regelmäßige Datenübernahme.


Hier können Sie auch **Abonnenten verwalten** mit den Möglichkeiten:

* löschen
* kopieren
* verschieben
