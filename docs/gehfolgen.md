# **5. Gehfolgenberechnung**

Die Heuristik zur Gehfolgenoptimierung in MultiRoute Go! folgt dem Prinzip der lokalen Suche. Sie beginnt mit einer zufälligen Reihenfolge der zu beliefernden Gebäude (Abonnenten oder Vollverteilung) und versucht systematisch, durch eine einfache Vertauschoperation von zwei Gebäuden eine bessere Gehfolge zu erhalten. Lässt sich auf diese Weise keine bessere Gehfolge mehr finden, wird das Ergebnis zwischengespeichert und eine willkürliche Vertauschung in der Gehfolge sorgt für eine neue Ausgangsposition um weiterzusuchen. Damit die Heuristik nicht wieder in dieselbe "Sackgasse" gerät, werden diese Kombinationen gespeichert und im Optimierungsvorgang entsprechend berücksichtigt bzw. werden gemieden.

Zusätzlich zur grundsätzlichen Optimierung der Reihenfolge ist in MultiRoute Go! eine Heuristik in der Kostenberechnungsfunktion (eine "nahe Gebäude zuerst"-Logik) eingebaut. Wir sind in der Lage zu simulieren, dass der Zusteller am Anfang seiner Tour mehr Ballast mit sich trägt als am Ende. Daher wird am Anfang der Tour auf die zurückgelegten Strecken ein Multiplikator angesetzt, der die Strecke z.B. um 5% mehr kostet. Während der Optimierung wird somit darauf hingearbeitet, dass die kleineren Strecken dem Multiplikator ausgesetzt sind, anstelle von längeren. Der Optimierungs-Algorithmus läuft im Endeffekt in einer Schleife, die Anzahl Schleifendurchläufe entspricht proportional der Anzahl an Gebäuden in der Tour. Ergebnis ist dann eine Gehfolge, in der so früh wie möglich so viel Gewicht wie möglich verloren wird.

Die Ausreißer-Suche ist eine Erweiterung für die Routenberechnungs-Engine von MultiRoute Go!. Ausreißer eines Verteilbezirkes lassen sich identifizieren, wenn ihre Durchschnittsdistanz zu anderen Gebäuden desselben Verteilbezirkes markant hoch sind. Da hier aber die reine Durchschnittsdistanz zu den Gebäuden nicht als souveränes Maß verwendet werden kann (aufgrund der variablen Größe der Verteilbezirke), muss diese Angabe durch die Gesamtdurchschnittsdistanz aller Strecken der Distanzmatrix normiert werden. Auf diese Weise erhalten wir einen repräsentativen Wert um den Wert 1.0 für jedes Gebäude, der als "Durchschnitt-Zentralitätsmaß" interpretiert werden kann. Ausreißer erzielen dabei Werte größer 1.0. Gebäude, die sich eher im Zentrum befinden, besitzen dann einen Zentralitätswert kleiner 1.0. Mit Hilfe der Ausreißer-Suche können dann Gebäude identifiziert werden, die besser anderen Verteilbezirken zugeordnet werden oder deaktiviert werden sollten.

Der MultiRoute Go! Algorithmus erlaubt Berechnungen von mehreren hundert Adresspunkten je Gehfolge.

## Einstellungen bei Gehfolgenberechnungen

Grundsätzlich können Gehfolgen auf drei verschiedene Arten berechnet werden:
- einfache Strecke: Von der [Abladestelle](../spezialhaeuser/#zustellerhaus-abladestelle-anlegenloschen) die kürzest mögliche Strecke durch den Bezirk, kein fester Endpunkt
- Rundweg: Start und Ende an der [Abladestelle](../spezialhaeuser/#zustellerhaus-abladestelle-anlegenloschen), auch wenn diese nicht im Bezirk selbst ist
- Rundweg im Verteilbezirk: Start an der Abladestelle und w


## Abladestelle / Zustellerhaus

Für jede Gehfolgenberechnung sollte vorab eine Abladestelle (Zustellerhaus) angegeben sein, damit der Start bekannt ist. 

## Berechnen von Gehfolgen

Das Menü Gehfolgenberechnung wird über das Hauptmenü geöffnet. Das Symbol für die Gehfolgenberechnungen ist :fontawesome-solid-calculator:.
![grafik](https://user-images.githubusercontent.com/99329016/166660795-0f6367e1-7dbc-45e7-83b7-2cec9fe632b7.png)

Die Berechnung kann auch (aus der Gebietsplanung) über einen Klick auf den gewünschten Bezirk gestartet werden. Dort einfach auf den :fontawesome-solid-calculator: drücken.

![grafik](https://user-images.githubusercontent.com/99329016/166661323-4e0668fb-88f8-4ff3-a552-b2620e8d0a6d.png)

Im Menü Gehfolgenberechnung alternativ einfach die gewünschte Bezirksnummer eintippen:
![grafik](https://user-images.githubusercontent.com/99329016/166661505-c77fcf7a-0600-4955-83e7-b6008b812928.png)

Und mit ```Berechnung starten``` den Berechnungsvorgang anstoßen.


## Parameter für die Gehfolgenberechnung 

Es gibt viele Parameter, die Sie bei der Gehfolgenberechnung (selbst) einstellen können. Grundsätzlich bestimmen Sie *globale Werte* in der Kundeneinstellung, die dann für alle Bezirke gelten. Machen Sie in der *Ausgabe* andere Angaben, können Ausgabenwerte die globalen Werte übersteuern. Gibt es für einen einzelnen *Bezirk* abweichende Werte zur Ausgabe, kann auch der Bezirk die Ausgabe (und die globalen Werte) übersteuern.

## Globale Einstellungen

Grundsätzlich ist eine Ausgabe vorab eingestellt als *Aboverteilung* oder *Resthaushaltsverteilung* oder *Vollverteilung*.
In unserem Beispiel möchten wir eine Vollverteilung rechnen und lassen deswegen das Kästchen leer:

![grafik](https://user-images.githubusercontent.com/99329016/168780491-6cb7a8ee-45fb-4e44-a8b9-23407b9786dc.png)

###### Geschwindigkeiten und Steckzeiten

![grafik](https://user-images.githubusercontent.com/99329016/168796891-3674ae8e-650d-4ad9-916d-407193944ec0.png)


Beim manuellen Anstoßen gibt es noch die folgenden Möglichkeiten, für diesen einen gewählten Bezirk oder sogar für alle Bezirke der aktuellen Ausgabe, die die globalen Kundeneinstellungen übersteuern:

![grafik](https://user-images.githubusercontent.com/99329016/168778910-a3738773-2c01-4228-9d8b-540d2c9b482d.png)




## Aufruf von berechneten Gehfolgen

## Trägerdokumente
