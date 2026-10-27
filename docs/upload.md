---
title: Wie kommen die Daten in MultiRoute Go! ? Die verschiedenen Uploadmöglichkeiten
description: Manuelles Zeichnen und Planen in MultiRoute Go! und tägliche Übernahme von Abonnenteninformationen und Briefzustellungen zur gemeinsamen Gehfolgenberechnung 
---

# **1. Datenintegration**

Ihre Bezirkseinheiten sind noch nicht digital vorhanden? Dann lesen Sie weiter unter "[Bezirke manuell anlegen](gebietsplanung.md#manuelle-neuanlage-von-verteilbezirken)".

Ansonsten erfolgt grundsätzlich  die Erstbefüllung der MultiRoute Go! Datenbank durch die gb consite. Gibt es die Bezirkseinheiten schon digital, gibt es die folgenden Wege: 

## Übernahme aus einem anderen GIS

Egal bei welchem GIS-Anbieter Sie vorher schon Ihre Bezirksstrukturen abgebildet hatten, wir übernehmen Sie gerne direkt in MultiRoute Go!. Senden Sie uns gerne Beispiele Ihrer Exportmöglichkeiten oder sprechen Sie uns an.


## Import aus (Verlags-)Software

Der Import erfolgt in der Regel über das Excel-Format. Aus Ihrer Software heraus benötigt MultiRoute Go! die Informationen: 

   * Strasse
   * Hausnummer
   * (Straßenabschnitt von-bis; gerade/ungerade)
   * PLZ
   * Ortsteil
   * Ort
   * Verteilgebiet/Verteilbezirk

  * Abonnenten
  * Abladestellen

💾 [Musterliste](assets/downloads/Import-Datenformat_MRGo.xlsx)

Optional auch: 

   * Eigene Haushaltsdaten
   * Eigene Werbeverweigerer Daten
   * eindeutige Straßen-ID / Gebäude-ID

## Manueller Upload

Möchten Sie selbst den manuellen Upload in MultiRoute Go! durchführen benötigen Sie Ihre Gebäudedaten mit angereichteren Koordinaten. Hier ist standardmäßig kein Geokodierservice angeschlossen.
In allen anderen Fällen benötigen wir ein eindeutiges Merkmal zum [Matchen](definitionen.md#matching). Üblicherweise matchen wir initial Ihren Straßen-/Gebäudestamm gegen unsere amtlichen Koordinaten. Dabei übernehmen wir Ihre Straßen-/Gebäude-ID.
Sprechen Sie uns gerne an, wenn Sie weitere Informationen benötigen.

## Schnittstelle (automatisierter Import)

Natürlich kann der Import auch automatisiert über eine Schnittstelle erfolgen. Zuvor ist das [Matching](definitionen.md#matching) nötig.
Wir besprechen mit Ihnen die automatisierte tägliche Datenübernahme. 

Alternativ: Datenimport wird manuell angestoßen


## Was passiert im Hintergrund?

Im Hintergrund werden Ihren Adressen (Straßenabschnitten) Geokoordinaten zugeordnet. Durch die Zuordnung zu (Verteil-)Bezirken werden diese auf der Karte visualisiert. Wir legen die Polygone drumherum. Jeder Adresspunkt, der über den Straßenabschnitt definiert wurde, weiß nun, in welchen Bezirk er gehört/zu welchem Bezirk er zugeordnet ist. Auf der Karte wird dieser nun <span style="color: green;">&#x1f534;&#xfe0e;</span>  (oder <span style="color: black;">&#x1f534;&#xfe0e;</span> ) dargestellt. Wenn Sie auf der Karte <span style="color: red;">&#x1f534;&#xfe0e;</span> Punkte entdecken, dann wurden diese entweder nicht gefunden oder von Ihnen nicht definiert. Hier lohnt sich nochmal ein zweiter Blick in die Ursprungsdaten. Häufige Fehler treten auf bei unterschiedlichen Schreibeweisen bei Straßen mit Bindestrichen.

