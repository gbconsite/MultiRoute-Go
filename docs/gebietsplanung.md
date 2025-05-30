---
title: Zustellbezirke bearbeiten, vergrößern, zuschneiden, aktualisieren, umbenennen
description: Verteilbezirke optimieren um Kosten zu senken. Zeichnerisch lassen sich schnell Szenarien abbilden und umsetzen. Farbige Punkte erleichtern die Arbeit.
---

# **2. Gebietsplanung**

In der Gebietsplanung sehen Sie die jeweiligen Trägerbezirke einer [Ausgabe](https://go.multiroute.de/handbuch/definitionen/#ausgabe). Sie können neue Gebiete anlegen, bestehende Gebiete verändern oder löschen. 

## Informationen Trägerbezirk
Durch Klick auf ein Polygon erhalten Sie eine Zusammenfassung des Gebiets und ggf. einen ersten Anhaltspunkt zur Optimierung. 
Die Anzahl der Haushalte + Gewerbebetriebe entspricht der Briefkästen in diesem Bezirk. Wenn gepflegt müssen Sie nur die Werbeverweigerer abziehen, um die Auflage des Gebiets herauszufinden.

![grafik](https://user-images.githubusercontent.com/99329016/168274325-2e7a9afb-1f0d-4346-ad67-4e797195ebd1.png "Überblick bei Klick auf Verteilbezirk")

## Gebiete suchen und finden
Kennen Sie die Gebietsnummer oder den Gebietsnamen, dann ist es ganz einfach: Sie geben einfach die Nummer im Feld ```Filter``` (hier: 100) ein und MultiRoute Go! filtert nach allen passenden Ergbnissen.

![grafik](https://user-images.githubusercontent.com/99329016/168274689-cc00db90-c23a-4c58-8f80-0367e496e244.png "Beispiel für Suche per Filter in der Gebietsplanung")

Alternativ suchen Sie über die Karte nach dem Gebiet oder oben rechts in der Suche nach dem jeweiligen Ort. Mit dem Klick auf die Gebietsnummer **aktivieren** Sie das Gebiet. Es ist blau hinterlegt und kann editiert werden.


## Manuelle Neuanlage von Verteilbezirken
Folgendermaßen gehen Sie vor:

```Administration - Verteilbezirk```

![grafik](https://user-images.githubusercontent.com/99329016/158329302-4aecd3de-1aa9-4b4f-9103-e87707cfca38.png "Neuen Verteilbezirk anlegen")

In der Ausgabe, in der Sie sich befinden, wird nun ein neuer Verteilbezirk angelegt. Sie geben Nummer und/oder Namen ein und bestätigen ganz unten mit ```Speichern```.
Die erfolgreiche Anlage können Sie sich unter dem Menüpunkt **Gebietsplanung** ansehen.

![grafik](https://user-images.githubusercontent.com/99329016/158330870-34693ff6-1752-4bf2-8268-18ac2bdceda5.png "Neuanlage Trägerbezirk")

:exclamation: Durch Klick auf den blauen Pfeil :material-arrow-down:{style="color:#0078A8"} haben Sie die Möglichkeit, **Spalten selbst zu definieren**, die Sie angezeigt bekommen möchten. Ein erneuter Klick auf :material-arrow-up:{style="color:#0078A8"} schließt dieses Menü wieder.

Um nun selbst zeichnen zu können, wird der neu angelegte Bezirk aktiviert, indem Sie auf die Gebietsnummer klicken. In der Karte öffnet sich das **Menü zum Zeichnen**. 
![grafik](https://user-images.githubusercontent.com/99329016/158331422-1d536767-f2c5-476a-8497-45da8d97ec7a.png "Zeichnen aktivieren")

Klicken Sie das <img src="../assets/icons/polygon.svg" style="height:16px !important" "Geometrie zu Verteilbezirk zeichnen"></img> Symbol an. Nun können Sie mit Klick (linke Maustaste) weiße Stützpunkte setzen und ein Polygon aufziehen. Mit **Doppelklick** wird das Zeichnen beendet. 

![grafik](https://user-images.githubusercontent.com/99329016/158331881-7aaed80d-00e7-4e11-aa94-873114d799f6.png "Gezeichnetes Polygon")

Ist das Polygon noch nicht so wie gewünscht, können Sie **nacharbeiten**. Einfach mit gedrückter linker Maustaste an den weißen Stützpunkten ziehen. Zwischen zwei weißen Stützpunkten erscheint automatisch ein neuer weißer Stützpunkt, so dass Sie auch sehr fein und kleinräumig das Polygon so ziehen können, wie gewünscht.

Ein Doppelklick auf einen weißen Stützpunkt entfernt diesen wieder.

Zur exakten Digitalisierung, z.B. von Straßen, die in zwei Verteilbezirke gehören, erscheint als Hilfe die Hausnummer einer Gebäudekoordinate beim Überfahren des Mauskreuzes. 
Erst der Klick auf :material-content-save:{style="color:#0078A8"} schließt die Bearbeitung ab.


## Zuordnungen aktualisieren
Der nachfolgende Dialog ist wichtig :exclamation:

![grafik](https://user-images.githubusercontent.com/99329016/158332914-8a0b833a-40a5-4851-9af2-e1538d129d14.png "Zuordnung aktualisieren")


* *Schnittfrei speichern* beeinflusst nur die Ausprägung des Polygons. Die Umrisse von Polygonen werden aneinandergelegt. Zuordnungen ändern sich nicht. Die überlappte Greneze, die man it einer neuen Polylinie überzieht, bleibt dabei bestehen.
* *Nur Speichern* bedeutet, dass die Geometrie gespeichert wurde, aber nicht die Zuordnung der Adressen/Gebäude
* *Zuordnung aktualisieren* ordnet Adressen dem Polygon und damit dem Verteilbezirk neu zu. Hauskoordinaten verfärben sich automatisch von rot nach grün (oder umgekehrt).

Bei aneinanderliegenden Polygonen sind die Methoden **Nur speichern** und **Schnittfrei speichern** zu beachten, damit Polygone nicht übereinander liegen bzw. sich aneinander schmiegen.

Wichtig ist hier auch das Häkchen bei **Zuordnung aktualisieren**. Hier gibt es noch weitere Varianten im Dialog. Wichtig ist jedoch zu bedenken, dass sich die Zuordnung der (roten) Gebäudepunkte verändern soll. Die Gebäude erhalten nun die Informationen, welchem Bezirk sie zugeordnet werden. Möchten Sie das **nicht**, dann lassen Sie das Häkchen weg. Ansonsten setzen Sie es. Es können so auch Zuordnungen gelöscht werden.

Als Ergebnis erhalten Sie nun den ersten gemalten Bezirk:
![grafik](https://user-images.githubusercontent.com/99329016/158333577-c252812f-35c6-4e9c-a61c-b5f52fc20344.png "erster gemalter Verteilbezirk")


## Bedeutung der Punkteinfärbungen
Die Farbgebung in MultiRoute Go! sagt einen Blick etwas über die Bedeutung eines Punktes:

| Farbe     | Bedeutung |
| --- | --- |
|  <span style="color: red;">&#x1f534;&#xfe0e;</span> | Gebäudepunkt ohne Zuordnung  |
|  <span style="color: lightgreen;">&#x1f534;&#xfe0e;</span>  | Gebäudepunkt mit Zuordnung |
|  <span style="color: black;">&#x1f534;&#xfe0e;</span>  | Abonnent/Briefempfänger |
|  <span style="color: grey;">&#x1f534;&#xfe0e;</span>  | Abonnent/Briefempfänger ohne Zuordnung|
| <span style="color: magenta;">&#x1f534;&#xfe0e;</span> | Abladestelle/Zustellerhaus |
|  <span style="color: yellow;">&#x1f534;&#xfe0e;</span>  | Starthaus |
|  <span style="color: orange;">&#x1f534;&#xfe0e;</span> | Endhaus |
|  <span style="color: blue;">&#x1f534;&#xfe0e;</span>  | inaktives Gebäude |
| <span style="color: darkgreen;">&#x1f534;&#xfe0e;</span>  | doppelt zugeordnetes Gebäude |


![grafik](https://user-images.githubusercontent.com/99329016/161265829-4d7e3cc2-28f8-43e2-ab77-0fda8391596c.png "Beispiele für Punkteinfärbungen in MultiRoute Go!")

## Gebiete bearbeiten
Nur ein **aktives Gebiet** kann bearbeitet werden. Aktiv ist ein Gebiet dann, wenn es **blau** hinterlegt ist. Die Gebäudepunkte haben einen **grünen Kringel** (statt  schwarzem Kringel). Sie aktivieren ein Gebiet entweder durch Anklicken auf der Karte oder über die Suche auf der linken Seite, in dem Sie bei Filter die Gebietsnummer (oder -name) eingeben.

![grafik](https://user-images.githubusercontent.com/99329016/158537426-a4614d34-850b-4d46-b1d2-156816d456b6.png "Bezirk aktivieren")

Zum Editieren des Gebiets drücken Sie :material-file-edit:{style="color:#0078A8"}.

![grafik](https://user-images.githubusercontent.com/99329016/158537773-4bbd949b-c0c8-4e97-83ba-d85dd916dd22.png "Verteilgebiets-Geometrie bearbeiten")

Sie sehen nun wieder die weißen Stützpunkte am Rande des Polygons, die Sie mit gedrückter linker Maustaste ziehen können. Wenn Sie fertig sind mit dem Bearbeiten, drücken Sie auf :material-content-save:{style="color:#0078A8"}.

![grafik](https://user-images.githubusercontent.com/99329016/168273860-a1724188-2dda-4919-ae00-e4d2d3d40568.png "weiße Stützpunkte zum Verschieben")

## Gebiete teilen
Um ein Gebiet teilen zu können, aktivieren Sie ihn einfach. Mit der Maus an eine beliebige Stelle im zu teilenden Gebiet klicken.. Das Gebietsbearbeitungsfenster erscheint. Im Fenster klickt man mit der Maus auf :fontawesome-solid-scissors:{style="color:#0078A8"}. 

Außerhalb des Gebiets setzen Sie den ersten weißen Stützpunkt und klicken mit der linken Maustaste auf weitere Punkte bis Sie außerhalb des Gebiets ankommen und mit Doppelklick abschließen. 

Sie erhalten zwei Gebiete, die Sie nun neu benennen können:

![grafik](https://user-images.githubusercontent.com/99329016/168276772-b400f9bc-c0f7-41cf-b5be-12f90ae7da09.png "Teilen von Trägerbezirken")

Im Kartenmenü auf der linken Seite können Sie (von unten nach oben) ```Speichern```, ```Aktion rückgängig machen``` und die ```Infobox an-/ausschalten```.

![grafik](https://user-images.githubusercontent.com/99329016/168276826-c5a5233a-37b5-439c-aaac-c8422ed4f0b8.png "Menü zum Editieren")

Die "neuen" Gebiete können nun separat voneinander berechnet werden. Möglicherweise möchte Sie einen 

## Gebiet umbenennen

Gehen Sie auf ```Administration - Verteilberzirke``` und drücken Sie hier beim umzubenennenden Gebiet einfach auf ```Bearbeiten```. Sie können alle Anpassungen für diesen ein Gebiet nun machen und mit ```Speichern``` bestätigen.


Die **Aktualisierung von Zuordnungen** verändert die Gebäudepunkte von :green_circle: nach :red_circle: oder umgekehrt.

![grafik](https://user-images.githubusercontent.com/99329016/158539008-247181ef-470a-4fa2-96a5-d81f208df699.png "Zuordnungen aktualisieren beim Zeichnen")

## Gebiet löschen und neu erzeugen
Ein Gebiet löschen Sie einfach durch Klick auf den :fontawesome-regular-trash-can:{style="color:#0078A8"}.

![grafik](https://user-images.githubusercontent.com/99329016/158539630-2c35bcbd-e28b-4bf0-a21b-8dd2925b39cb.png "Bezirk löschen")

Die im Polygon befindlichen Punkte wissen weiterhin, welchem Gebiet sie zugeordnet sind und sind weiterhin grün. Das Polygon dient nur als Hilfsmittel zur Visualisierung. Kontrollieren können Sie das, wenn Sie auf der linken Seite auf die Gebietsnummer klicken und den Gebiet aktivieren. Dort fehlt das Häkchen bei "Geometrie vorhanden", die Gebäudepunkte erscheinen aber auf der Karte mit grünem Kringel. 

Sie können nun das Polygon automatisiert neu erzeugen lassen, in dem Sie auf ```Administration - Verteilbezirke``` gehen. Dort wählen Sie das gewünschte Gebiet aus und drücken unten auf 

![grafik](https://user-images.githubusercontent.com/99329016/158540508-041f3dbc-b2ec-47c2-a916-0753fb3690fa.png "Auswahl von Verteilbezirken in der Administration")

```Markierte Verteilbezirke - Polygone erzeugen - Anwenden```

Zurück in der **Gebietsplanung** ist das Polygon für das Gebiet voll automatisch gemalt.

![grafik](https://user-images.githubusercontent.com/99329016/158540878-4b87d58c-d804-4fe5-8be3-70e9f7d8cbb8.png "Automatisch erzeugtes Polygon")

Bei den automatisch erzeugten Polygonen wird die Hülle wie ein Gummiband um die zugeordneten Punkte gelegt. Siehe hierzu unser Kapitel zum Arbeiten mit **Basispolygonen**.

## Zusammenfassen von Gebieten
Gebiete können wie folgt zusammengefasst werden:

1. Das Gebiet, welches in Zukunft die Gebietsbezeichnung tragen soll wird aufgerufen und mittels des Kreuzes zentriert.

   ![grafik](https://user-images.githubusercontent.com/99329016/168277793-8290ac86-6ee0-4938-b1cf-4018ae04f052.png "Trägerbezirk aktivieren")
   

2. Nach dem Zentrieren ruft man durch Anklicken des zweiten Gebietes das Gebietsbearbeitungsmenü auf. Dort drückt man den Button "Mit Verteilgebiet ... vereinigen".
   
   ![grafik](https://user-images.githubusercontent.com/99329016/168277807-e4d8637b-ad7f-4e35-813e-75208858ed24.png "Mit anderem Verteilbezirk vereinigen")

3. Nun sind die Gebiete vereinigt. Das neue Gebiet hat den Gebietsnamen des ersten Bezirks. Das zugeordnete Gebiet ist noch vorhanden. Es beinhaltet aber keine Gebäude mehr und hat kein Polygon. Es kann unter ```Administration - Verteilbezirke``` gelöscht werden.

   ![grafik](https://user-images.githubusercontent.com/99329016/168277832-ddd9b339-4dde-4291-838c-41c9f8e26538.png "Aus zwei Trägerbezirken ist ein neuer Bezirk entstanden")



## Multipolygone, Teilflächen und Sonderformen
Mit MultiRoute Go! ist es auch möglich, sog. Multipolygone als Geometrien der Verteilbezirke anzulegen. Man versteht darunter Flächen, die aus mehreren Teilen bestehen. Am Beispiel von Bauernschaften kann man sich die Situation besonders gut vorstellen:

![grafik](https://user-images.githubusercontent.com/99329016/168278059-6d96d792-5fac-4ae3-a641-5fbd6765f39a.png "Multipolygone")

Anstelle eines, alle Bauernschaften überspannenden Polygons, können auch mehrere einzelne Polygone als ein Verteilbezirk gezeichnet werden. Hierzu verwendet man einfach die  [bekannte Funktion zum Zeichnen](/#manuelle-neuanlage-von-verteilbezirken). Das fertig gestellte Polygon **nicht** sofort speichern, sondern nach dem Fertigstellen per Doppelklick einfach die Zeichnungsfunktion erneut auswählen und ein weiteres Polygon erstellen usw. Mit ```Speichern``` erzeugen Sie ein Multipolygon.

Als eine Sonderform der Polygone gibt es noch das "**Donut**" Polygon. Dazu im Bearbeitungsmenü den Kreis mit Punkt in der Mitte auswählen. Einfach in das bestehende Polygon klicken und Stützpunkte setzen mit der linken Maustaste. Für den nächsten Punkt erneut klicken, wie beim Polygone zeichnen. Am Ende per Doppelklick abschließen und ```Speichern```.

![grafik](https://user-images.githubusercontent.com/99329016/168278374-af023d8b-967c-49ba-a272-f4ff6658ebef.png "Donut Polygon")

## Einzelne Adressen einem Gebiet hinzufügen oder entfernen
Sollen mehrere Koordinaten auf einmal zugeordnet werden, muss das [Polygon für die Bearbeitung aktiviert (blau hinterlegt)](../#gebiete-bearbeiten) werden.

Alle Koordinaten, die sich nun innerhalb des blau gewordenen Polyongs befinden, können gleichzeitig zugeordnet werden. Deshalb sollte man nun die Polygonstützpunkte entsprechend verschieben, so dass es nicht zu Überlappungen und doppelten Zuordnungen kommt. Mit ```Speichern``` abschließen und entsprechende Option wählen.

Einzelne Koordinaten lassen sich **zuordnen**, in dem im aktivieren Polygon die entsprechenden Koordinaten angeklickt werden und die Koordinate mit dem Polygon verknüpft wird.
![grafik](https://user-images.githubusercontent.com/99329016/168282417-dd028266-582a-4c60-a7fa-58a171f5f0ae.png "Manuelles Zuordnen")

Zum **Entfernen einer einzelnen Koordinate** drücken Sie einfach die "kaputte Büroklammer" und die Zuordnung des Gebäudes verschwindet. Im Bsp. hier wird das Gebäude also anschließend rot.
![grafik](https://user-images.githubusercontent.com/99329016/168282544-d87c7d8c-36b3-448e-bd4f-e7453f1eb8ce.png "Manuell Zuordnung löschen")



## Weitere Funktionen
Alle weiteren Funktionen finden Sie unter der Auflistung Ihrer Verteilbezirke:
![grafik](https://user-images.githubusercontent.com/99329016/168077138-e3775e43-b597-4518-af6c-879c23d1a02e.png "Weitere Funktionen in der Adminstration von Verteilgebieten")

Achten Sie immer darauf, dass Sie die richtige Ausgabe gewählt haben:exclamation:


