# **5. Gehfolgenberechnung**

Die Heuristik zur Gehfolgenoptimierung in MultiRoute Go! folgt dem Prinzip der lokalen Suche. Sie beginnt mit einer zufälligen Reihenfolge der zu beliefernden Gebäude (Abonnenten oder Vollverteilung) und versucht systematisch, durch eine einfache Vertauschoperation von zwei Gebäuden eine bessere Gehfolge zu erhalten. Lässt sich auf diese Weise keine bessere Gehfolge mehr finden, wird das Ergebnis zwischengespeichert und eine willkürliche Vertauschung in der Gehfolge sorgt für eine neue Ausgangsposition um weiterzusuchen. Damit die Heuristik nicht wieder in dieselbe "Sackgasse" gerät, werden diese Kombinationen gespeichert und im Optimierungsvorgang entsprechend berücksichtigt bzw. werden gemieden.

Zusätzlich zur grundsätzlichen Optimierung der Reihenfolge ist in MultiRoute Go! eine Heuristik in der Kostenberechnungsfunktion (eine "nahe Gebäude zuerst"-Logik) eingebaut. Wir sind in der Lage zu simulieren, dass der Zusteller am Anfang seiner Tour mehr Ballast mit sich trägt als am Ende. Daher wird am Anfang der Tour auf die zurückgelegten Strecken ein Multiplikator angesetzt, der die Strecke z.B. um 5% mehr kostet. Während der Optimierung wird somit darauf hingearbeitet, dass die kleineren Strecken dem Multiplikator ausgesetzt sind, anstelle von längeren. Der Optimierungs-Algorithmus läuft im Endeffekt in einer Schleife, die Anzahl Schleifendurchläufe entspricht proportional der Anzahl an Gebäuden in der Tour. Ergebnis ist dann eine Gehfolge, in der so früh wie möglich so viel Gewicht wie möglich verloren wird.

Nutzen Sie die verschiedenen Ergebnisse (z.B. Excel-Export) der Gehfolgenberechnung, um Ausreißer eines Verteilbezirkes zu identifizieren. Sie erkennen die Ausreißer, wenn bspw. ihre Durchschnittsdistanz zu anderen Gebäuden desselben Verteilbezirkes markant hoch ist. Identifzierte Gebäude können dann eventuell besser einem anderen Bezirk zugeordnet werden oder auf inaktiv gesetzt werden.

Der MultiRoute Go! Algorithmus erlaubt Berechnungen von mehreren hundert Adresspunkten je Gehfolge.

Aus dem Hauptmenü können Sie:

- Gehfolgenberechnungen starten
- bereits berechnete Gehfolgenverwaltung aufrufen
- Details zu Gehfolgen abrufen

![grafik](https://user-images.githubusercontent.com/99329016/168812352-792d9e58-1c1c-44af-92ad-7865627dd38d.png)


## Einstellungen bei Gehfolgenberechnungen

Grundsätzlich können Gehfolgen auf drei verschiedene Arten berechnet werden:

- einfache Strecke: Von der [Abladestelle](../spezialhaeuser/#zustellerhaus-abladestelle-anlegenloschen) die kürzest mögliche Strecke durch den Bezirk, kein fester Endpunkt
- Rundweg: Start und Ende an der [Abladestelle](../spezialhaeuser/#zustellerhaus-abladestelle-anlegenloschen), auch wenn diese nicht im Bezirk selbst ist
- Rundweg im Verteilbezirk: Start an der Abladestelle und zurück zur ersten Steckung im Verteilbezirk


## Abladestelle / Zustellerhaus

Für jede Gehfolgenberechnung sollte vorab eine [Abladestelle (Zustellerhaus)](../spezialhaeuser/#zustellerhaus-abladestelle-anlegenloschen) angegeben sein, damit der Startpunkt bekannt ist. 


## Berechnen von Gehfolgen

Das Menü Gehfolgenberechnung wird über das Hauptmenü geöffnet. Das Symbol für die Gehfolgenberechnungen ist :fontawesome-solid-calculator:.
![grafik](https://user-images.githubusercontent.com/99329016/166660795-0f6367e1-7dbc-45e7-83b7-2cec9fe632b7.png)

Die Berechnung kann auch (aus der Gebietsplanung) über einen Klick auf den gewünschten Bezirk gestartet werden. Dort einfach auf den :fontawesome-solid-calculator: drücken.

![grafik](https://user-images.githubusercontent.com/99329016/166661323-4e0668fb-88f8-4ff3-a552-b2620e8d0a6d.png)

Im Menü Gehfolgenberechnung alternativ einfach die gewünschte Bezirksnummer eintippen:
![grafik](https://user-images.githubusercontent.com/99329016/166661505-c77fcf7a-0600-4955-83e7-b6008b812928.png)

Und mit ```Berechnung starten``` den Berechnungsvorgang anstoßen.


## Parameter für die Gehfolgenberechnung 

Es gibt viele Parameter, die Sie bei der Gehfolgenberechnung (selbst) einstellen können. Grundsätzlich bestimmen Sie **globale Werte** in der Kundeneinstellung, die dann für alle Bezirke gelten. Machen Sie in der [Ausgabe](https://gbconsite.github.io/MultiRoute-Go/definitionen/#ausgabe) andere Angaben, können Ausgabenwerte die globalen Werte übersteuern. Gibt es für einen einzelnen **Bezirk** abweichende Werte zur Ausgabe, kann auch der Bezirk die Ausgabe (und die globalen Werte) übersteuern.

Nicht jeder User sollte das Recht bekommen, in der Administration Einstellungen vornehmen zu können. Aber grundsätzlich können Sie die Angaben selbst administrieren. Wir geben Ihnen hier gerne weitere Erläuterungen, falls nötig.

Grundsätzlich wird voreingestellt, ob es sich bei deiner Ausgabe um eine  **Aboverteilung** oder **Resthaushaltsverteilung** oder **Vollverteilung** handelt.


## Hauszugangsdistanz (HZD) und Hauszugangs-Suchradius

MultiRoute Go! nutzt für die Berechnungen der Gehfolgen die Kartengrundlagen von Open Street Map (OSM). In OSM sind alle notwendigen Informationen enthalten für die optimale Gehfolge. Zur Zustellung gehört auch der Weg von der Straße (Straßenankerpunkt in rosa) bis zum Gebäude (blau). Diese Informationen zur Distanz oder zum physikalischen Weg von der Straße bis zum Gebäude/Briefkasten sind nirgendwo hinterlegt.

MultiRoute Go! zeichnet eine direkte Linie zwischen dem Straßenankerpunkt und der Lage der Hauskoordinate. Im System selber kann vor der Berechnung ein Schwellenwert in Metern angegeben werden, ab welcher Entfernung der Wert in die Berechnung einbezogen wird. Ist zum Beispiel ein Wert von 10 Metern angegeben, so wird erst berechnet, wenn die Distanz größer 10 Meter ist. Diese 10 Meter werden dann von der Entfernung Straßenankerpunkt bis zur Hauskoordinate abgezogen.

In der Darstellung wird zwischen blauen und gelben Linien unterschieden. Eine blaue Linie bedeutet, dass die Hauszugangsdistanz unter dem Schwellenwert liegt. Es kommen in der Summierung der Strecke keine extra Meter dazu. Die gelbe Linie beschreibt Hauszugangsdistanzen über dem Schwellenwert.

![grafik](https://user-images.githubusercontent.com/99329016/168802809-ba4c96c0-451d-487b-9053-a69ff0789806.png)

Diese über dem Schwellenwert befindlichen Meter können Sie in der Gehfolgenkonfiguration HIN und ZURÜCK zur Gesamtstrecke addieren. Die Summe wird separat ausgegeben. 

Neben der HDZ hilft Ihnen der **Hauszugangssuchradius**, den richtigen Zugang von einer Straße zum Haus zu finden. Es kann passieren, dass eine Straße mit einem anderen Straßennamen sich in der Nähe befindet. Falls es dort einen Gehweg gibt, kann dieser günstiger liegen.

Ein Beispiel:

Links: HZD Grenzwert 15 m, Suchradius 0 m              
Rechts: HZD Grenzwert 15 m, Suchradius 20 m
![grafik](https://user-images.githubusercontent.com/99329016/168803038-8df73c96-ce06-400f-b35f-a109390c5193.png)

In der Summe wird Ihnen das rechte Beispiel ein realistischeres Ergebnis geben.


## Geschwindigkeiten und Steckzeiten

![grafik](https://user-images.githubusercontent.com/99329016/168796891-3674ae8e-650d-4ad9-916d-407193944ec0.png)

Mit den vorliegenden Zahlen decken Sie alle Möglichkeiten der Berechnung in MultiRoute Go! ab. 

## Gehfolgenberechnung manuell anstoßen

Beim manuellen Anstoßen gibt es noch die folgenden Möglichkeiten, für diesen einen gewählten Bezirk oder sogar für alle Bezirke der aktuellen Ausgabe, die die globalen Kundeneinstellungen übersteuern:

![grafik](https://user-images.githubusercontent.com/99329016/168778910-a3738773-2c01-4228-9d8b-540d2c9b482d.png)




## Aufruf von berechneten Gehfolgen
Der Aufruf der berechneten Gehfolgen **(weißes Ordnersymbol)** können Sie mit Hilfe des "Filers" gezielt nach Gehfolgen eines Verteilbezirks filtern oder nach einer bestimmten Gehfolgennummer. 
Über den **blauen Pfeil** können Sie die Spalten selbst festlegen, die angezeigt werden sollen.

![grafik](https://user-images.githubusercontent.com/99329016/170687969-7475d998-8da4-4cf0-b0af-cb08a5af17be.png)

Bei den Aktionen stehen in der Kurzübersicht die Ergebnisse der Gehfolgen zur Verfügung und sie können gelöscht (Mülleimer) werden.

Unter der Ergebnisliste sind Exportmöglichkeiten (als CSV) verfügbar.

## Das Höhenprofil

Mit jeder Gehfolgenberechnung wird automatisch ein Höhenprofil erzeugt.

Dieses Höhenprofil ermöglicht es Ihnen, die sog. (Reliefenergie)[https://de.wikipedia.org/wiki/Reliefenergie] des jeweiligen Verteilbezirkes einzuschätzen.

Das Höhenprofil wird als interaktive Grafik auf der Karte oben rechts ausgegeben. Dort haben Sie die Möglichkeit, die Gehfolge mit der Maus virtuell abzufahren und für jeden Wegpunkt der Gehfolge die Höhe abzufragen. Zusätzlich finden Sie die Informationen zu höchstem und niedrigstem Punkt der Gehfolge sowie Aufstieg gesamt auch in den Detailinformationen zur Gehfolge auf der linken Seitenleiste:

![grafik](https://user-images.githubusercontent.com/99329016/170688820-3f3079d4-b464-48cb-b0e6-4bc2e275092c.png)

Diese Informationen zur Geländehöhe sind ebenfalls im Excel-Export und im GPX-Export enthalten.

Die Daten für das Höhenprofil stammen aus der (Shuttle Radar Topography Mission (SRTM))[https://de.wikipedia.org/wiki/SRTM-Daten], einer NASA Mission im Jahr 2000. Die Höhendaten haben eine Auflösung von ca. 30 Metern und werden bei jeder Gehfolgenberechnung automatisch mit der Route der Gehfolge verknüpft.

Mit SRTM wurden innerhalb von 11 Tagen selbst unwegsame Regionen der Erde erfasst und vermessen


## Trägerdokumente
