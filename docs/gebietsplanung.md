# **2. Gebietsplanung**

In der Gebietsplanung sehen Sie die jeweiligen Trägerbezirke einer **Ausgabe**. Sie können neue Bezirke anlegen, bestehende Bezirke verändern oder löschen. 

## Manuelle Neuanlage von Verteilbezirken
Manuelles Neuzeichnen von Bezirken kommt in der Regel nur sehr selten vor. Folgendermaßen gehen Sie vor:

```Administration - Verteilbezirk```

![grafik](https://user-images.githubusercontent.com/99329016/158329302-4aecd3de-1aa9-4b4f-9103-e87707cfca38.png "Neuen Verteilbezirk anlegen")

In der Ausgabe, in der Sie sich befinden, wird nun ein neuer Verteilbezirk angelegt. Sie geben Nummer und/oder Namen ein und bestätigen ganz unten mit ```Speichern```.
Die erfolgreiche Anlage können Sie sich unter dem Menüpunkt **Gebietsplanung** ansehen.

![grafik](https://user-images.githubusercontent.com/99329016/158330870-34693ff6-1752-4bf2-8268-18ac2bdceda5.png "Neuanlage Trägerbezirk")

:exclamation: Durch Klick auf den blauen Pfeil :arrow_down: haben Sie die Möglichkeit, **Spalten selbst zu definieren**, die Sie angezeigt bekommen möchten. Ein erneuter Klick auf :arrow_up: schließt dieses Menü wieder.

Um nun selbst zeichnen zu können, wird der neu angelegte Bezirk aktiviert, indem Sie auf die Bezirksnummer klicken. In der Karte öffnet sich das **Menü zum Zeichnen**. 
![grafik](https://user-images.githubusercontent.com/99329016/158331422-1d536767-f2c5-476a-8497-45da8d97ec7a.png "Zeichnen aktivieren")

Klicken Sie das ![grafik](https://user-images.githubusercontent.com/99329016/158331572-df45c4e7-9ba6-4495-8494-4401e01bd0ef.png "Geometrie zu Verteilbezirk zeichnen") Symbol an. Nun können Sie mit Klick (linke Maustaste) weiße Stützpunkte setzen und ein Polygon aufziehen. Mit **Doppelklick** wird das Zeichnen beendet. 

![grafik](https://user-images.githubusercontent.com/99329016/158331881-7aaed80d-00e7-4e11-aa94-873114d799f6.png "Gezeichnetes Polygon")

Ist das Polygon noch nicht so wie gewünscht, können Sie **nacharbeiten**. Einfach mit gedrückter linker Maustaste an den weißen Stützpunkten ziehen. Zwischen zwei weißen Stützpunkten erscheint automatisch ein neuer weißer Stützpunkt, so dass Sie auch sehr fein und kleinräumig das Polygon so ziehen können, wie gewünscht.
Erst der Klick auf das ![grafik](https://user-images.githubusercontent.com/99329016/158332684-fc21b309-0c96-4934-bf59-86fbf710db1a.png "Speichern") **Symbol** schließt die Bearbeitung ab.


## Zuordnungen aktualisieren
Der nachfolgende Dialog ist wichtig :exclamation:

![grafik](https://user-images.githubusercontent.com/99329016/158332914-8a0b833a-40a5-4851-9af2-e1538d129d14.png "Zuordnung aktualisieren")

Bei aneinanderliegenden Polygonen sind die Methoden **Nur speichern** und **Schnittfrei speichern** zu beachten, damit Polygone nicht übereinander liegen bzw. sich aneinander schmiegen.

Wichtig ist hier auch das Häkchen bei **Zuordnung aktualisieren**. Hier gibt es noch weitere Varianten im Dialog. Wichtig ist jedoch zu bedenken, dass sich die Zuordnung der (roten) Gebäudepunkte verändern soll. Die Gebäude erhalten nun die Informationen, welchem Bezirk sie zugeordnet werden. Möchten Sie das **nicht**, dann lassen Sie das Häkchen weg. Ansonsten setzen Sie es.

Als Ergebnis erhalten Sie nun den ersten gemalten Bezirk:
![grafik](https://user-images.githubusercontent.com/99329016/158333577-c252812f-35c6-4e9c-a61c-b5f52fc20344.png "erster gemalter Verteilbezirk")


## Bedeutung der bunten Punkte
Die Farbgebung in MultiRoute Go! zeigt Ihnen die Bedeutung eines Punktes:
| :red_circle:  | Gebäudepunkt ohne Zuordnung  |
| :green_circle:  | Gebäudepunkt mit Zuordnung |
| :black_circle:  | Abonnent/Briefempfänger |
| :magenta_circle:  | Abladestelle/Zustellerhaus |
| :yellow_circle:  | Starthaus |
| :orange_circle:  | Endhaus |
| :blue_circle:  | inaktives Gebäude |
| :darkgreen_circle:  | doppelt zugeordnetes Gebäude |


## Bezirke bearbeiten
Nur ein **aktiver Bezirk** kann bearbeitet werden. Aktiv ist ein Bezirk dann, wenn er **blau** hinterlegt ist. Die Gebäudepunkte haben einen **grünen Kringel** (statt  schwarzem Kringel). Sie aktivieren einen Bezirk entweder durch Anklicken auf der Karte oder über die Suche auf der linken Seite, in dem Sie bei Filter die Bezirksnummer (oder -name) eingeben.

![grafik](https://user-images.githubusercontent.com/99329016/158537426-a4614d34-850b-4d46-b1d2-156816d456b6.png "Bezirk aktivieren")

Zum Editieren des Bezirks drücken Sie den Button **Symbol** BEARBEITEN-BUTTON.

![grafik](https://user-images.githubusercontent.com/99329016/158537773-4bbd949b-c0c8-4e97-83ba-d85dd916dd22.png)

Sie sehen nun wieder die weißen Stützpunkte am Rande des Polygons, die Sie mit gedrückter linker Maustaste ziehen können. Wenn Sie fertig sind mit dem Bearbeiten, drücken Sie auf ![grafik](https://user-images.githubusercontent.com/99329016/158332684-fc21b309-0c96-4934-bf59-86fbf710db1a.png "Speichern") **Symbol**.

Die **Aktualisierung von Zuordnungen** verändert die Gebäudepunkte von :green_circle: nach :red_circle: oder umgekehrt.

![grafik](https://user-images.githubusercontent.com/99329016/158539008-247181ef-470a-4fa2-96a5-d81f208df699.png)

## Bezirk löschen und neu erzeugen
Einen Bezirk löschen Sie einfach durch Klick auf den **Symbol** Mülleimer.

![grafik](https://user-images.githubusercontent.com/99329016/158539630-2c35bcbd-e28b-4bf0-a21b-8dd2925b39cb.png "Bezirk löschen")

Die im Polygon befindlichen Punkte wissen weiterhin, welche Bezirk sie zugeordnet sind und sind weiterhin grün. Das Polygon dient nur als Hilfsmittel zur Visualisierung. Kontrollieren können Sie das, wenn Sie auf der linken Seite auf die Bezirksnummer klicken und den Bezirk aktivieren. Dort fehlt das Häkchen bei "Geometrie vorhanden", die Gebäudepunkte erscheinen aber auf der Karte mit grünem Kringel. Sie können nun das Polygon automatisiert neu erzeugen lassen, in dem Sie auf ```Administration - Verteilbezirk``` gehen. Dort wählen Sie den gewünschten Bezirk aus und drücken unten auf 

![grafik](https://user-images.githubusercontent.com/99329016/158540508-041f3dbc-b2ec-47c2-a916-0753fb3690fa.png)

```Markierte Verteilbezirke - Polygone erzeugen - Anwenden```

Zurück in der Gebietsplanung ist das Polygon für den Bezirk voll automatisch gemalt.

![grafik](https://user-images.githubusercontent.com/99329016/158540878-4b87d58c-d804-4fe5-8be3-70e9f7d8cbb8.png "Automatisch erzeugtes Polygon")

Bei den automatisch erzeugten Polygonen wird die Hülle wie ein Gummiband um die zugeordneten Punkte gelegt. Siehe hierzu unser Kapitel zum Arbeiten mit **Basispolygonen**.



