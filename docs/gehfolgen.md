---
title: Die optimale Gangfolge ist das Herzstück von MultiRoute Go! Reihenfolge zu Fuß oder mit einem Fahrzeug
description: Wie ist die optimale Laufreihenfolge für den Zusteller? MultiRoute Go! rechnet täglich neu und spart damit viele unnötige Meter und Zeit. Gangfolgen werden innerhalb weniger Sekunden gerechnet. Für ein ganzes Verbreitungsgebiet problemlos über Nacht.
---

# **5. Gehfolgenberechnung**

Die Heuristik zur Gehfolgenoptimierung in MultiRoute Go! folgt dem Prinzip der lokalen Suche. Sie beginnt mit einer zufälligen Reihenfolge der zu beliefernden Gebäude (Abonnenten oder Vollverteilung) und versucht systematisch, durch eine einfache Vertauschoperation von zwei Gebäuden eine bessere Gehfolge zu erhalten. Lässt sich auf diese Weise keine bessere Gehfolge mehr finden, wird das Ergebnis zwischengespeichert und eine willkürliche Vertauschung in der Gehfolge sorgt für eine neue Ausgangsposition um weiterzusuchen. Damit die Heuristik nicht wieder in dieselbe "Sackgasse" gerät, werden diese Kombinationen gespeichert und im Optimierungsvorgang entsprechend berücksichtigt bzw. werden gemieden.

Zusätzlich zur grundsätzlichen Optimierung der Reihenfolge ist in MultiRoute Go! eine Heuristik in der Kostenberechnungsfunktion (eine "nahe Gebäude zuerst"-Logik) eingebaut. Wir sind in der Lage zu simulieren, dass der Zusteller am Anfang seiner Tour mehr Ballast mit sich trägt als am Ende. Daher wird am Anfang der Tour auf die zurückgelegten Strecken ein Multiplikator angesetzt, der die Strecke z.B. um 5% mehr kostet. Während der Optimierung wird somit darauf hingearbeitet, dass die kleineren Strecken dem Multiplikator ausgesetzt sind, anstelle von längeren. Der Optimierungs-Algorithmus läuft im Endeffekt in einer Schleife, die Anzahl Schleifendurchläufe entspricht proportional der Anzahl an Gebäuden in der Tour. Ergebnis ist dann eine Gehfolge, in der so früh wie möglich so viel Gewicht wie möglich verloren wird.

Nutzen Sie die verschiedenen Ergebnisse (z.B. Excel-Export) der Gehfolgenberechnung, um Ausreißer eines Verteilbezirkes zu identifizieren. Sie erkennen die Ausreißer, wenn bspw. ihre Durchschnittsdistanz zu anderen Gebäuden desselben Verteilbezirkes markant hoch ist. Identifzierte Gebäude können dann eventuell besser einem anderen Bezirk zugeordnet werden oder auf inaktiv gesetzt werden.

Der MultiRoute Go! Algorithmus erlaubt Berechnungen von mehreren hundert Adresspunkten je Gehfolge.

Aus dem Hauptmenü können Sie:

- Gehfolgenberechnungen starten
- bereits berechnete Gehfolgenverwaltung aufrufen
- Details zu Gehfolgen abrufen

![grafik](https://user-images.githubusercontent.com/99329016/168812352-792d9e58-1c1c-44af-92ad-7865627dd38d.png "Übersicht Gehfolgen")


## Einstellungen bei Gehfolgenberechnungen

Grundsätzlich kann als Optimierungsmethode für die Gehfolgenberechnung zwischen **drei verschiedene Arten** (mit Varianten) gewählt werden:

- **einfache Strecke**: Von der Abladestelle/Starthaus <span style="color: magenta;">&#x1f534;&#xfe0e;</span> die kürzest mögliche Strecke durch den Bezirk, kein fester Endpunkt:

![Einfache Strecke](https://github.com/gbconsite/MultiRoute-Go/assets/99329016/7f235bc3-e0dd-4b0f-8350-51a25bde64a3 "One Way open End"){ width="200" }

oder mit festem Endpunkt:

![Einfache Strecke mit festem Endhaus](https://github.com/gbconsite/MultiRoute-Go/assets/99329016/ac3f7227-6744-44d8-b036-752a1731df53 "fester Endpunkt"){ width="200" }


- **Rundweg**: Start und Ende an der Abladestelle <span style="color: magenta;">&#x1f534;&#xfe0e;</span> , auch wenn diese nicht im Bezirk selbst ist

![Rundweg](https://github.com/gbconsite/MultiRoute-Go/assets/99329016/0d83ffea-92e4-42a0-8086-7d94d4ab4e95 "Rundweg"){ width="200" }

- **Rundweg im Verteilbezirk**: Start an der Abladestelle <span style="color: magenta;">&#x1f534;&#xfe0e;</span> und zurück zur ersten Steckung (Starthaus) im Verteilbezirk

![Rundweg im Verteilbezirk](https://github.com/gbconsite/MultiRoute-Go/assets/99329016/14101711-3993-42ba-8826-7528adfc4220 "Rundweg nur im Verteilbezirk am ersten Punkt im Bezirk wieder ankommen"){ width="200" }



## Abladestelle / Zustellerhaus

Für jede Gehfolgenberechnung sollte vorab eine [Abladestelle (Zustellerhaus)](../spezialhaeuser/#zustellerhaus-abladestelle-anlegenloschen) angegeben sein, damit der Startpunkt bekannt ist. Die Abladestelle kann sich im Bezirk befinden oder außerhalb sein. Grundsätzlich wird an der ersten Abladestelle nicht automatisch gestectk. Soll diese auch passieren an einer Abladestelle im Bezirk, können Sie diese auch als Starthaus eingeben.

## Start- /Endhaus

Manchmal ist es nötig, dass Sie in die Gehfolge eingreifen. Sie können ein Starthaus definieren, bei dem die erste Steckung im Bezirk vorgenommen wird. Und genau so ein Endhaus, bei dem zuletzt gesteckt wird.

## Berechnen von Gehfolgen

Das Menü Gehfolgenberechnung wird über das Hauptmenü geöffnet. Das Symbol für die Gehfolgenberechnungen ist :fontawesome-solid-calculator:. Auch hier kann wieder mit einem zweiten Klick auf das Symbol das Menü ein-/ausgeklappt werden.

![grafik](https://user-images.githubusercontent.com/99329016/166660795-0f6367e1-7dbc-45e7-83b7-2cec9fe632b7.png "zwei Wege führen in die Gehfolgenberechnung")

Die Berechnung kann auch (aus der Gebietsplanung) über einen Klick auf den gewünschten Bezirk gestartet werden. Dort einfach auf den :fontawesome-solid-calculator: drücken.

![grafik](https://user-images.githubusercontent.com/99329016/166661323-4e0668fb-88f8-4ff3-a552-b2620e8d0a6d.png "Gehfolge berechnen mit Taschenrechner starten")

Im Menü Gehfolgenberechnung alternativ einfach die gewünschte Bezirksnummer eintippen:
![grafik](https://user-images.githubusercontent.com/99329016/166661505-c77fcf7a-0600-4955-83e7-b6008b812928.png "Bezirksnummer eingeben um Gehfolgenberechnung zu starten")

Und mit ```Berechnung starten``` den Berechnungsvorgang anstoßen.


## Parameter für die Gehfolgenberechnung 

Es gibt viele Parameter, die Sie bei der Gehfolgenberechnung (selbst) einstellen können. Grundsätzlich bestimmen Sie **globale Werte** in der Kundeneinstellung, die dann für alle Bezirke gelten. Machen Sie in der [Ausgabe](https://gbconsite.github.io/MultiRoute-Go/definitionen/#ausgabe) andere Angaben, können Ausgabenwerte die globalen Werte übersteuern. Gibt es für einen einzelnen **Bezirk** abweichende Werte zur Ausgabe, kann auch der Bezirk die Ausgabe (und die globalen Werte) übersteuern.

Nicht jeder User sollte das Recht bekommen, in der Administration Einstellungen vornehmen zu können. Aber grundsätzlich können Sie die Angaben selbst administrieren. Wir geben Ihnen hier gerne weitere Erläuterungen, falls nötig.

Die Einstellung, ob es sich bei einer [Ausgabe](../definitionen/#ausgabe) um eine  **Aboverteilung** oder **Resthaushaltsverteilung** oder **Vollverteilung** handelt wird von uns für Sie eingestellt.

Haben Sie die Parameter für die Gehfolgenberechnung schon in Excel/CSV vorliegen, können diese auch importiert werden (falls Sie über die entsprechenden Rechte verfüggen). Dazu **in der entsprechenden Ausgabe** auf Administration - Upload gehen und die Datei mit Bezirkseigenschaften auswählen:

<img width="1477" height="592" alt="grafik" src="https://github.com/user-attachments/assets/8b6da97a-3454-4c5c-aa83-6829e4a0abd0" />

Zum Exportieren von Parametern siehe [Export](../exporte/#eigenschaften-der-verteilgebiete).

## Hauszugangsdistanz (HZD) 

MultiRoute Go! nutzt für die Berechnungen der Gehfolgen die Kartengrundlagen von Open Street Map (OSM). In OSM sind alle notwendigen Informationen enthalten für die optimale Gehfolge. Zur Zustellung gehört auch der Weg von der Straße (Straßenankerpunkt in rosa) bis zum Gebäude (blau). Diese Informationen zur Distanz oder zum physikalischen Weg von der Straße bis zum Gebäude/Briefkasten sind nirgendwo hinterlegt.

MultiRoute Go! zeichnet eine direkte Linie zwischen dem Straßenankerpunkt und der Lage der Hauskoordinate (auch Gebäudestrecke oder Steckstrecke genannt). Im System selber kann vor der Berechnung ein Schwellenwert in Metern angegeben werden, ab welcher Entfernung der Wert in die Berechnung einbezogen wird. Ist zum Beispiel ein Wert von 10 Metern angegeben, so wird erst berechnet, wenn die Distanz größer 10 Meter ist. Diese 10 Meter werden dann von der Entfernung Straßenankerpunkt bis zur Hauskoordinate abgezogen.

In der Darstellung wird zwischen blauen und gelben Linien unterschieden. Eine blaue Linie bedeutet, dass die Hauszugangsdistanz unter dem Schwellenwert liegt. Es kommen in der Summierung der Strecke keine extra Meter dazu. Die gelbe Linie beschreibt Hauszugangsdistanzen über dem Schwellenwert.

![grafik](https://user-images.githubusercontent.com/99329016/168802809-ba4c96c0-451d-487b-9053-a69ff0789806.png "Beispiel HZD")

Diese über dem Schwellenwert befindlichen Meter können Sie in der Gehfolgenkonfiguration HIN und ZURÜCK zur Gesamtstrecke addieren. Die Summe wird separat ausgegeben. 


## Hauszugangs-Suchradius

Neben der HZD hilft Ihnen der **Hauszugangs-Suchradius**, den richtigen Zugang (Ankerpunkt) von einer Straße zum Haus zu finden. Es kann passieren, dass eine Straße mit einem anderen Straßennamen sich in der Nähe befindet. Falls es dort einen Gehweg gibt, kann dieser günstiger liegen.

Ein Beispiel:

Links: HZD Grenzwert 15 m, Suchradius 0 m              
Rechts: HZD Grenzwert 15 m, Suchradius 20 m
![grafik](https://user-images.githubusercontent.com/99329016/168803038-8df73c96-ce06-400f-b35f-a109390c5193.png "Anbindung für den Haussuchradius mit unterschiedlichen Grenzwerten")

In der Summe wird Ihnen das rechte Beispiel ein realistischeres Ergebnis geben.


## Geschwindigkeiten und Steckzeiten

![grafik](https://user-images.githubusercontent.com/99329016/168796891-3674ae8e-650d-4ad9-916d-407193944ec0.png "Einstellmöglichkeiten für Geschwindigkeiten und Steckzeiten")

Mit den vorliegenden Zahlen decken Sie alle Möglichkeiten der Berechnung in MultiRoute Go! ab.
Geschwindigkeiten lassen sich für jede Ausgabe und jeden Verteilbezirk anpassen.
Hier wird bspw. bei einem Mehrfamilienhaus für die erste Steckung mit 6,3 Sekunden gerechnet. Die nachfolgenden Steckungen sind etwas schneller mit 4,2 Sekunden.


## Gehfolgenberechnung manuell anstoßen

Beim manuellen Anstoßen gibt es noch die folgenden Möglichkeiten, für diesen einen gewählten Bezirk oder sogar für alle Bezirke der aktuellen Ausgabe, die die globalen Kundeneinstellungen übersteuern:

![grafik](https://user-images.githubusercontent.com/99329016/168778910-a3738773-2c01-4228-9d8b-540d2c9b482d.png "Gehfolgen manuell berechnen")




## Aufruf von berechneten Gehfolgen

Der Aufruf der berechneten Gehfolgen :material-folder-open-outline: können Sie mit Hilfe des "Filters" gezielt nach Gehfolgen eines Verteilbezirks filtern oder nach einer bestimmten Gehfolgennummer. 
Über den :material-arrow-up:{style="color:#0078A8"} können Sie die Spalten selbst festlegen, die angezeigt werden sollen.

![grafik](https://user-images.githubusercontent.com/99329016/170687969-7475d998-8da4-4cf0-b0af-cb08a5af17be.png "Spalten definieren beim Aufruf von berechneten Gehfolgen")

Bei den Aktionen stehen in der Kurzübersicht die Ergebnisse der Gehfolgen zur Verfügung und sie können gelöscht (Mülleimer) werden.

Unter der Ergebnisliste sind Exportmöglichkeiten (als CSV) verfügbar.


## Das Höhenprofil

Mit jeder Gehfolgenberechnung wird automatisch ein Höhenprofil erzeugt.

Dieses Höhenprofil ermöglicht es Ihnen, die sog. [Reliefenergie](https://de.wikipedia.org/wiki/Reliefenergie) des jeweiligen Verteilbezirkes einzuschätzen.

Das Höhenprofil wird als interaktive Grafik auf der Karte oben rechts ausgegeben. Dort haben Sie die Möglichkeit, die Gehfolge mit der Maus virtuell abzufahren und für jeden Wegpunkt der Gehfolge die Höhe abzufragen. Zusätzlich finden Sie die Informationen zu höchstem und niedrigstem Punkt der Gehfolge sowie Aufstieg gesamt auch in den Detailinformationen zur Gehfolge auf der linken Seitenleiste:

![grafik](https://user-images.githubusercontent.com/99329016/170688820-3f3079d4-b464-48cb-b0e6-4bc2e275092c.png "Detailinformationen zum Höhenprofil eines Zeitungsbezirks")

Diese Informationen zur Geländehöhe sind ebenfalls im Excel-Export und im GPX-Export enthalten.

Die Daten für das Höhenprofil stammen aus der [Shuttle Radar Topography Mission (SRTM)](https://de.wikipedia.org/wiki/SRTM-Daten), einer NASA Mission im Jahr 2000. Die Höhendaten haben eine Auflösung von ca. 30 Metern und werden bei jeder Gehfolgenberechnung automatisch mit der Route der Gehfolge verknüpft.


## Fehler bei der Gehfolgenberechnung

**Die häufigsten Fehler:**

- Es sind **keine Abos** vorhanden, Sie haben aber die **Aboberechnung** aktiviert.
- Ihr Verteilbezirk enthält nur **eine** Adresse, sodass keine Route berechnet werden kann.

Noch häufiger hängen die Probleme nicht mit MultiRoute Go! selbst zusammen, sondern mit den zugrunde liegenden OSM-Daten (OpenStreetMap). Beispiele:

- **Falsch gesetzte Sperren** – es wird eine Straße blockiert, die eigentlich befahrbar oder begehbar ist.  
- **Fehlerhafte Einbahnstraßen-Attribute** – eine Straße ist nur in eine Richtung freigegeben, obwohl das in der Realität nicht stimmt oder vielleicht ist auch nur die falsche Richtung angegeben.
- **Fehlende Anbindungen ans Straßennetz** – einzelne Straßenabschnitte sind nicht mit dem restlichen Netzwerk verbunden. Dadurch entstehen kleine „Inseln“, die von außen nicht erreichbar sind.  

Um diese Fehler zu erkennen können (berechtige User) rechts im Menü zwei Layer aktivieren:

<img width="304" height="456" alt="grafik" src="https://github.com/user-attachments/assets/f7a8f770-1a6d-4c6d-9ceb-695fa31168cd" />


Diese zusätzlichen Ebenen geben einen Hinweis, wo es aufgrund fehlerhafter OSM-Daten zu Routingproblemen kommt.

Die Farben:

**Zu Fuß**

| Farbe | Bedeutung |
|-------|-----------|
| **<span style="color:#FF37EF">PINK</span>** | "Insel" |
| **<span style="color:#ff0000">ROT</span>** | Geschwindigkeit 0 km/h |
| **BLASSES <span style="color:#dcffdc">GRÜN</span>** | Geschwindigkeit > 0 km/h |
| **<span style="color:#90ee90">HELLGRÜN</span>** | Geschwindigkeit > 2 km/h |
| **<span style="color:#3cb371">GRÜN</span>** | Geschwindigkeit > 4 km/h |
| **<span style="color:#006400">DUNKELGRÜN</span>** | Geschwindigkeit > 6 km/h |

**Kfz**

| Farbe | Bedeutung |
|-------|-----------|
| **<span style="color:#FF37EF">PINK</span>** | "Insel" |
| **<span style="color:#ff0000">ROT</span>** | Geschwindigkeit 0 km/h |
| **<span style="color:#66c2a5">HELLGRÜN</span>** | Geschwindigkeit > 0 km/h |
| **<span style="color:#47dda4">GRÜN</span>** | Geschwindigkeit > 25 km/h |
| **<span style="color:#f46d43">ORANGE</span>** | Geschwindigkeit > 50 km/h |
| **<span style="color:#9e0142">DUNKELROT</span>** | Geschwindigkeit > 100 km/h |

