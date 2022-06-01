# ** 8. Zusatzmodule**

Der modulare Aufbau von MultiRoute Go! ermöglicht das Anpassen an verlagseigene Prozesse. Derzeit sind als Zusatzmodule verfügbar:

- [Abo-/Titeldifferenzierung](#abo-titeldifferenzierung)
- [Bezirksplanung](#bezirksplanung)
- [Nachladen an „Depots“](#nachladen-an-depots)
- [Resthaushalte](#resthaushalte)
- [Tracking](##tracking)
- [Wegnetzlängen](#wegnetzlangen)
- [Gebiets-Adressliste für die Briefverteilung](#gebiets-adressliste-fur-die-briefverteilung)
- [Klickbare Karte](#klickbare-karte)
- [Straßenanpassungen](#straenanpassungen)

    
##Abo-Titeldifferenzierung##

Wichtig für jede Tageszeitung, damit die Zusteller genau wissen, welchen Titel Sie in welchen Briefkasten zustellen müssen. 

Info für Zusteller OHNE Zusatzmodul: 2 Abonnenten = 2 Steckvorgänge.
Was und bei wem ist unklar.

![grafik](https://user-images.githubusercontent.com/99329016/167622701-d5e9c356-2f1c-44c7-9bcb-5d6082243aa7.png)


Info für Zusteller MIT Zusatzmodul: Frau Mustermann erhält eine Zeitung und ein Brief (Name steht drauf) wird im gleichen Gebäude zugestellt.

![grafik](https://user-images.githubusercontent.com/99329016/167623220-48f5dec6-5d71-409d-ad18-5bde2256427a.png)

:exclamation: Nur verfügbar bei InHouse-Kunden oder bei dediziertem Server auf Grund der DSGVO.


##Bezirksplanung##

Der Trend geht bei vielen Verlagen dazu, kleinere Untereinheiten von Trägerbezirken zu erstellen und diese dann je nach Trägerverfügbarkeit zusammen zu stellen. Wir unterstützen das flexible Zusammensetzen und sprechen von kleinen Gebieten (Waben, Zellen, Segmenten etc.), die zu einem Trägerbezirk (Bezirk, Cluster o.a.) zusammengefasst werden. 

![grafik](https://user-images.githubusercontent.com/99329016/166670122-780d45a7-e1d7-4db6-ba07-d0add5704588.png)

Zeichenlösung:

Eine neue Gebietsausgabe anlegen, die Gebiete in kleine Zellen/Waben anlegen und in einer Liste festlegen, welche Gebiete in einen Bezirk zugeordnet werden sollen. Dies kann dann per Upload in die Bezirksebene gespielt werden.


##Nachladen an „Depots“##

Träger von Wochenblättern haben fast immer das Problem, dass sie nicht mit einem Durchgang durch den Trägerbezirk alle Zeitungen stecken können. Aber genau dafür wird die normale Gehfolge berechnet. Muss man Nachladen, stimmt die berechnete Gehfolge nicht mehr.
Mit diesem Zusatzumodul wird berücksichtigt wie viel Gewicht (oder Stück) der Zusteller mitnehmen kann und wie viel wo und was gesteckt wird. So errechnet MultiRoute Go! automatisch "Mini-Rundwege" um die Abladestelle oder weitere Nachlade-Depots, um die kürzeste Strecke trotz und mit Nachladen zu finden. 
Ein realistischer Weg, der das Nachladen abbildet.
Mehrere Abladestellen (Depots) möglich.


##Resthaushalte##

Für die Resthaushaltsverteilung ist es wichtig, dass möglichst alle Gebäude, die sich innerhalb eines Trägerbezirks befinden, auch zugeordnet <span style="color: green;">&#x1f534;&#xfe0e;</span>  sind. Die Resthaushaltsverteilung ist gemäß unserer Definition:

Vollverteilung minus Abos minus Werbeverweigerer = Resthaushalte 

Bei besonders gut gepflegten Haushaltshaltszahlen wird auch berücksichtigt, dass bspw. in einem Mehrfamilienhaus, in dem es 6 Haushalte und davon 4 Werbeverweiger gibt, noch 2x gesteckt wird.


##Tracking##

Auf der Karte können Sie entweder live oder historisch verfolgen, wie sich ein Tracker bewegt hat. Das Tracking läuft entweder mit Hilfe eines mobilen Endgeräts (Traccar App) oder eines Trackers, den wir Ihnen zur Verfügung stellen. Bitte sprechen Sie den Vertrieb an!

Die App ist geeignet für die Verwendung in Fahrzeugen, aber auch Zusteller, die zu Fuß unterwegs sind, können darüber getrackt werden.


##Wegnetzlängen##

Alle innerhalb eines Polygons befindlichen Streckenlängen werden addiert. Besonders gut bei Neuplanungen und Optimierungen von Bezirken.


##Gebiets-Adressliste für die Briefverteilung##

Bei Hybrid-Zustellung mit wenig Briefen innerhalb eines Bezirks ohne automatische Schnittstelle. Manuell werden die Briefe im MultiRoute Go! Trägerbezirk erfasst und mit in der Gehfolgenberechnung berücksichtigt.


##Klickbare Karte##

Ein Link zur direkten Verwendung in App, Portal oder direkt an die Träger. Zum Rein- und Rauszoomen. Einmalig gültiger Link oder permanter Link. 


##Straßenanpassungen##

Nur für Kunden mit InHouse-Lizenz oder dediziertem Server. Machen Sie Anpassungen in den OpenStreetMap (OSM) Daten, die nur für Sie gelten. Also bspw. Straßen, die vorübergehend gesperrt sind markieren oder Fußwege, die im Winter zu matschig werden, rausnehmen. 
