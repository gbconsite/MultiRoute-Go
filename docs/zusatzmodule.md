---
title: Zusatzmodule unterstreichen den modularen Aufbau von MultiRoute Go! zur Abbildung Ihrer Prozesse
description: Durch den modularen Aufbau von MultiRoute Go! können die Bedürfnisse und Aufgabenstellungen der Verlage und Zustellorganisationen abgebildet werden. Die Zusatzmodule sind optional und jederzeit zubuchbar. Egal, ob Anzeigenblatt oder Hybrid-Zustellung. Mit MultiRoute Go! lässt sich alles abbilden - täglich aktualisiert.
---

# **8. Zusatzmodule**

Der modulare Aufbau von MultiRoute Go! ermöglicht das Anpassen an verlagseigene Prozesse. Derzeit sind als Zusatzmodule verfügbar:

- [Abo-/Titeldifferenzierung](#abo-titeldifferenzierung)
- [Abo-Optimierungsbooster](#abo-optimierungsbooster)
- [Bezirksplanung](#bezirksplanung)
- [Nachladen an „Depots“](#nachladen-an-depots)
- [Resthaushalte](#resthaushalte)
- [Tracking](#tracking)
- [Wegnetzlängen](#wegnetzlangen)
- [Gebiets-Adressliste für die Briefverteilung](#gebiets-adressliste-fur-die-briefverteilung)
- [Klickbare Karte](#klickbare-karte)
- [Straßenanpassungen](#straenanpassungen)
- [Manuelle Gehfolgensortierung](#manuelles-eingreifen-in-gehfolgen)
- [Festgelegte Reihenfolge](#festgelegte-reihenfolge)

    
##Abo-Titeldifferenzierung##

:fontawesome-solid-file-pdf: [Abo-/Titeldifferenzierung](https://gbconsite.de/wp-content/uploads/2019/10/Abo-Titeldifferenzierung-MRGo-Zusatzmodul.pdf)

Wichtig für jede Tageszeitung, damit die Zusteller genau wissen, welchen Titel sie in welchen Briefkasten zustellen müssen. 

Info für Zusteller OHNE Zusatzmodul: 2 Abonnenten = 2 Steckvorgänge.
Was und bei wem ist unklar.

![grafik](https://user-images.githubusercontent.com/99329016/167622701-d5e9c356-2f1c-44c7-9bcb-5d6082243aa7.png "Anzahl der Abos")


Info für Zusteller MIT Zusatzmodul: Frau Mustermann erhält eine Zeitung und ein Brief (Name steht drauf) wird im gleichen Gebäude zugestellt.

![grafik](https://user-images.githubusercontent.com/99329016/167623220-48f5dec6-5d71-409d-ad18-5bde2256427a.png "differenziert nach Produkten und Info der Anzahl")

:exclamation: Nur verfügbar bei InHouse-Kunden oder bei dediziertem Server auf Grund der DSGVO.



##Abo-Optimierungsbooster##

🆕 :fontawesome-solid-file-pdf: [Abo-Optimierungsbooster](https://gbconsite.de/wp-content/uploads/2024/11/Abo-Optimierungsbooster.pdf)

Über einen zusätzlichen Schieberegler kann der Abo-Booster für relevante User an-/ausgeschaltet werden.

![grafik](https://github.com/user-attachments/assets/0b76d629-2aa7-4932-bd95-726e4fc8653e "Abo-Booster per Schieberegler aktivieren")

Unsere Heuristik liefert für Sie mit Hilfe eines kartografischen Dashboards die Möglichkeit schnelle, faktenbasierte Entscheidungen zu Ihren Abonnenten zu treffen. 

Wo sind besonders "teure Abos"? Wie gehe ich damit um?
Wo sollten Abos in einen Nachbarbezirk gelegt werden?

Dabei berechnen wir für Sie analog demSchulnoten-System von 1-5 und entsprechend eingefärbt (grün=sehr gut bis hin zu rot=mangelhaft):

- Wegzeit-Score (Betrachtung einer Aboadresse nur aufgrund der Erreichbarkeit mit dem für den Bezirk festgelegten Verkehrsmittel und den dazu passenden Wege-Verbindungen)
- Wegzeit-Umsatz-Score (zusätzlich Einbeziehung der von Ihnen festgelegten Umsätze je Druckerzeugnis)
- Verdacht falscher Bezirk (eigener Layer mit blauen Punkt-Umrandungen bei größerer Nähe zu Punkten anderer Verteilbezirke)
- Sehr schlechter Wegzeit-Score (eigener Layer mit roten Punkt-Umrandungen bei Werten von 4 und 5)
- Lange Verbindungen im Bezirk (rote Umrandung der Polygone bei Zwischenstrecken größer 10 Minuten mit dem für den Bezirk festgelegten Verkehrsmittel und der dafür festgelegten Geschwindigkeit)


Für die Berechnungen ist einiges an Informationen nötig, das wir nicht in MultiRoute Go! vorhalten. Bitte sprechen Sie uns an, wir können Musterlisten liefern, die alle Informationen beinhalten, die wir für die Berechnungen benötigen.




##Bezirksplanung##

:fontawesome-solid-file-pdf:  [Bezirksplanung](https://gbconsite.de/wp-content/uploads/2019/10/Bezirksplanung-MRGo-Zusatzmodul.pdf)

Der Trend geht bei vielen Verlagen dazu, kleinere Untereinheiten von Trägerbezirken zu erstellen und diese dann je nach Trägerverfügbarkeit zusammen zu stellen. Wir unterstützen das flexible Zusammensetzen und sprechen von kleinen Gebieten (Waben, Zellen, Segmenten etc.), die zu einem Trägerbezirk (Bezirk, Cluster o.a.) zusammengefasst werden. 

![grafik](https://user-images.githubusercontent.com/99329016/166670122-780d45a7-e1d7-4db6-ba07-d0add5704588.png "gleichfarbige kleine Einheiten gehören zu einer gemeinsamen größeren Einheit und werden gemeinsam und/oder einzeln berechnet")

So geht es:

Eine neue BEZIRKsausgabe anlegen, die Gebiete in kleine Zellen/Waben anlegen und in einer Liste festlegen, welche Gebiete in einen Bezirk zugeordnet werden sollen. Dies kann dann per Upload in die Bezirksebene gespielt werden. Die Liste muss nur zwei Spalten enthalten: Bezirksnummern und die dazugehörigen Gebietsnummern.


Genau so können Sie auch vorgehen, wenn Sie den aktuellen **Besetzungsstatus** Ihrer Trägerezirke darstellen möchten:
offen / besetzt / Warteschlange

Beispiel:
Sie legen eine "neue Ausgabe/Planung" an und nennen diese "Zusteller".
![grafik](https://github.com/gbconsite/MultiRoute-Go/assets/99329016/762c293e-5a11-4964-baa7-5c3724fb8456)

Als "Gebiet" geben Sie die Ausgabe an, in der sich die einzelnen (kleinen Einheiten) Trägerbezirke befinden (hier: Testausgabe).

Nun legen Sie einfach Verteilbezirke an, die den Status widergeben:
offen / besetzt / Warteschlange

Per Upload (*.csv, *.xlsx etc.) mit nur zwei Spalten 

![grafik](https://github.com/gbconsite/MultiRoute-Go/assets/99329016/a838b84d-ebcc-4d9e-ab5b-012829d3698d)

![grafik](https://github.com/gbconsite/MultiRoute-Go/assets/99329016/e7f18028-1a33-488c-a4f8-e62bd6133f6d)

werden die Trägerbezirke mit ihrem jeweiligen Status abgebildet. 

![grafik](https://github.com/gbconsite/MultiRoute-Go/assets/99329016/0fc0268e-b47a-4f78-893a-10d08d1d8dd6)

Einzelne Trägerbezirke können Sie per "Zuordnung entfernen" aus einem der Verteilbezirke "offen", "besetzt", "Warteschlange" entfernen oder hinzufügen. Der Status (und die Farbe) passt sich entsprechend an.

Die manuelle Arbeit mit Bezirken funktioniert ansonsten sehr ähnlich mit Gebieten, siehe [Gebietsplanung](https://go.multiroute.de/handbuch/gebietsplanung/).


##Nachladen an „Depots“##

:fontawesome-solid-file-pdf: [Nachladen an „Depots“](https://gbconsite.de/wp-content/uploads/2019/10/Abladeoptimierung-MRGo-Zusatzmodul.pdf)

Träger von Wochenblättern haben fast immer das Problem, dass sie nicht mit einem Durchgang durch den Trägerbezirk alle Zeitungen stecken können. Aber genau dafür wird die normale Gehfolge berechnet. Muss man Nachladen, stimmt die berechnete Gehfolge nicht mehr.
Mit diesem Zusatzumodul wird berücksichtigt wie viel Gewicht (oder Stück) der Zusteller mitnehmen kann und wie viel wo und was gesteckt wird. So errechnet MultiRoute Go! automatisch "Mini-Rundwege" um die Abladestelle oder weitere Nachlade-Depots, um die kürzeste Strecke trotz und mit Nachladen zu finden. 
Ein realistischer Weg, der das Nachladen abbildet.
Mehrere Abladestellen (Depots) möglich.

So funktioniert es (manuell):
In der Bezirkseinstellung (Ausgabe) einstellen, wie viel Stück/Gewicht ein Träger auf einmal mitnehmen kann. Bsp. 30 kg Gewicht in Taschen. Bei Gewicht auch noch definieren, wie schwer 1 Stück ist. 
In der Gebietsplanung auch ein (oder mehrere) Depot(s) anlegen (zusätzlich zur Abladestelle, gleiche Vorgehensweise). Bei der Berechnung Häkchen nicht vergessen!
![grafik](https://user-images.githubusercontent.com/99329016/181526036-eda10285-0c0e-4be1-a2aa-face92a8eee0.png)



##Resthaushalte##

:fontawesome-solid-file-pdf: [Resthaushalte](https://gbconsite.de/wp-content/uploads/2019/10/Resthaushalte-MRGo-Zusatzmodul.pdf)

Für die Resthaushaltsverteilung ist es wichtig, dass möglichst alle Gebäude, die sich innerhalb eines Trägerbezirks befinden, auch zugeordnet <span style="color: green;">&#x1f534;&#xfe0e;</span>  sind. Die Resthaushaltsverteilung ist gemäß unserer Definition:

Vollverteilung minus Abos minus Werbeverweigerer = Resthaushalte 

Bei besonders gut gepflegten Haushaltshaltszahlen wird auch berücksichtigt, dass bspw. in einem Mehrfamilienhaus, in dem es 6 Haushalte und davon 4 Werbeverweiger gibt, noch 2x gesteckt wird.


##Tracking##

:fontawesome-solid-file-pdf: [Tracking](https://gbconsite.de/wp-content/uploads/2024/02/Tracking-MRGo-Zusatzmodul.pdf)

Auf der Karte können Sie entweder live oder historisch verfolgen, wie sich ein Tracker bewegt hat. Das Tracking läuft entweder mit Hilfe eines mobilen Endgeräts (Traccar App) oder eines Trackers, den wir Ihnen zur Verfügung stellen. Bitte sprechen Sie den Vertrieb an!

Die App ist geeignet für die Verwendung in Fahrzeugen, aber auch Zusteller, die zu Fuß unterwegs sind, können darüber getrackt werden.

Mehr Tipps zur Einrichtung der App finden Sie auch direkt im Handbuch von MultiRoute Tour! zum Zusatzmodul [Tracking](https://tour.multiroute.de/handbuch/zusatzmodule/#tracking).


##Wegnetzlängen##

:fontawesome-solid-file-pdf: [Wegnetzlängen](https://gbconsite.de/wp-content/uploads/2019/10/Wegnetzl%C3%A4nge-MRGo-Zusatzmodul.pdf)

Alle innerhalb eines Polygons befindlichen Streckenlängen werden addiert. Besonders gut bei Neuplanungen und Optimierungen von Bezirken.


##Gebiets-Adressliste für die Briefverteilung##

:fontawesome-solid-file-pdf: [Gebiets-Adressliste für die Briefverteilung](https://gbconsite.de/wp-content/uploads/2019/10/Gebiets-Adressliste-MRGo-Zusatzmodul.pdf)

Bei Hybrid-Zustellung mit wenig Briefen innerhalb eines Bezirks ohne automatische Schnittstelle. Manuell werden die Briefe im MultiRoute Go! Trägerbezirk erfasst und mit in der Gehfolgenberechnung berücksichtigt.


##Klickbare Karte##

:fontawesome-solid-file-pdf: [Klickbare Karte](https://gbconsite.de/wp-content/uploads/2019/10/Klickbare-Karte-MultiRouteGo-Zusatzmodul.pdf)

Ein Link zur direkten Verwendung in App, Portal oder direkt an die Träger. Zum Rein- und Rauszoomen. Einmalig gültiger Link oder permanter Link. 
Unser beliebtestes Zusatzmodul!


##Straßenanpassungen##

:fontawesome-solid-file-pdf: [Straßenanpassungen](https://gbconsite.de/wp-content/uploads/2021/11/Strassenanpassungen-MRGo-Zusatzmodul.pdf)

Nur für Kunden mit InHouse-Lizenz oder dediziertem Server. Machen Sie Anpassungen in den OpenStreetMap (OSM) Daten, die nur für Sie gelten. Also bspw. Straßen, die vorübergehend gesperrt sind markieren oder Fußwege, die im Winter zu matschig werden, rausnehmen. 


##Manuelles Eingreifen in Gehfolgen##

 🆕 MultiRoute Go! hat die kürzeste Route gefunden, es gibt aber Gründe, die diese optimale Route verhindern? Auch kein Problem mehr!  Mit diesem Zusatzmodul können Sie manuell in die optimierte Gehfolge eingreifen. Wenn beispielsweise die optimierte Gehfolge Ihre Straßenabschnitte zerteilt, Sie aber aus Gründen der Sortierung unbedingt den kompletten Straßenabschnitt am Stück abgehen möchten. Oder wenn der Zusteller darauf besteht, dass seine Route besser ist. Einfach mal "nachbauen" und dann auch den Zusteller überzeugen, dass es anders kürzer geht.
 [Und so geht es](https://go.multiroute.de/handbuch/gehfolgenoptimieren/#manuelle-gehfolgensortierung).

##Festgelegte Reihenfolge##

 🆕 Haben Sie sich aus Ihren logistischen Gründen selbst zusammengebastelte Route überlegt und möchten diese nun weiterhin nutzen? Mit dem neuen Zusatzmoodul "Festgelegte Reihenfolge" verwenden wir IHRE Reihenfolge und optimieren gar nicht mehr. Einfach per [Upload](https://go.multiroute.de/handbuch/gehfolgenoptimieren/#festgelegte-reihenfolge-hochladen).
