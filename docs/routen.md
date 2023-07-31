# Routen & Endpunkte 

## Authentifizierung 

Die Authentifizierung findet mittels mittels Basic Auth (http://username:password@domain/) statt. 

`domain` steht dabei für die Domain unter der Sie auf MultiRoute Tour! zugreifen. Für die SaaS lautet die Domain [https://go.multiroute.de](https://go.multiroute.de). 

Sie können Ihren Account auch einer Konfigurationsdatei für einen schnelleren und sicheren Login hinterlegen.

## Gehfolgen-Steuerung

### Ausgaben

Da immer ein gültiger Benutzer benötigt wird, muss man sich entweder
mittels Basic Auth (<http://username:password@domain/>) anmelden,  
oder es wird ein Benutzer fest hinterlegt. Dieser feste Benutzer wird
dann in einer Konfiguration eintragen.

Wenn zwischen verschiedenen Ausgaben gewechselt werden soll, kann dies
per Aufruf erfolgen.  
Dieser ändert die Ausgabe des Benutzers.

<http://domain/fernsteuerung/ausgabe_wechseln?ausgabe=%3CAusgabename>\>  
Oder man kann die Ausgabe als optionalen Parameter an die anderen
Aufrufe mit übergeben.

### Gehfolgen-Status

Informationen zu allen Gehfolgen (einer Ausgabe)  
Es werden entweder alle angezeigt, oder nur die mit dem jeweiligen
Status.

<http://domain/fernsteuerung/gehfolgen>  
<http://domain/fernsteuerung/gehfolgen/error>  
<http://domain/fernsteuerung/gehfolgen/pending>  
<http://domain/fernsteuerung/gehfolgen/unknown>  
<http://domain/fernsteuerung/gehfolgen/success>

Optionale Parameter:  
limit (default 100)  
offset (default 0)  
ausgabe (default die vom User)  
verteilbezirk (Verteilbezirk-Nummer (Name))  
abonnenten (default alle) true=Abonnenten; false=Vollverteilung  
fussweg (default alle) true=Fußweg bevorzugt; false=kein Fußweg
bevorzugt

<http://domain/fernsteuerung/gehfolgen?limit=10&offset=0>

Rückgabewert ist ein JSON Array:  

    {"id":3607,"verteilbezirk":"51043501570","status":"pending"},{"id":3606,"verteilbezirk":"WSP_P193d","status":"pending"},
    {"id":3605,"verteilbezirk":"WSP_P193","status":"pending"},{"id":3604,"verteilbezirk":"WSP_P193w","status":"pending"},
    {"id":3603,"verteilbezirk":"WSP_P193c","status":"pending"},{"id":3602,"verteilbezirk":"WSP_P193f","status":"pending"},
    {"id":3601,"verteilbezirk":"test","status":"pending"},{"id":3600,"verteilbezirk":"8654","status":"success"},
    {"id":3599,"verteilbezirk":"8654","status":"success"},{"id":3598,"verteilbezirk":"8654","status":"success"}

### CSV-Export

<http://domain/fernsteuerung/gehfolgen/export/abonnenten/detail>  
<http://domain/fernsteuerung/gehfolgen/export/abonnenten/zusammenfassung>  
<http://domain/fernsteuerung/gehfolgen/export/vollbesteckung/detail>  
<http://domain/fernsteuerung/gehfolgen/export/vollbesteckung/zusammenfassung>

### Informationen zu einer Gehfolge (Ausgabe spielt keine Rolle):

<http://domain/fernsteuerung/gehfolge/3603>

Rückgabewert ist ein JSON Object:

    {"id":3603,"verteilbezirk":"WSP_P193c","status":"unknown","grenzdistanz":10,"zugang_fussweg":true,"abonnenten":true,"ignore_starthaus":true}

### Download der Trägerdokumente bzw. Info und Details zu einer Gehfolge

<http://domain/fernsteuerung/gehfolge/3603/gpx> (optional:
"/gpx?type=waypoint,route,track" - Default: track)

-   Die Waypoints sind die tatsächlichen Gebäudepunkte (rooftop) und
    enthalten die Adresse als Attribut (in der berechneten Reihenfolge)
-   Der Track hat Points und einen Path:
    -   Track Points sind die Zugangspunkte auf der Straße und enthalten
        einen Reihenfolgeindex als Attribut (in der berechneten
        Reihenfolge)
    -   Track Path ist die Streckenlinie aus dem Kartenmaterial
-   Die Route hat ebenfalls Points und einen Path:
    -   Route Points sind die Zugangspunkte auf der Straße und enthalten
        die Adresse als Attribut (in der berechneten Reihenfolge)
    -   Route Path ist die Linie der Luftlinienverbindung zwischen den
        Wegpunkten in der berechneten Reihenfolge

<http://domain/fernsteuerung/gehfolge/3603/excel>  
<http://domain/fernsteuerung/gehfolge/3603/image>  
<http://domain/fernsteuerung/gehfolge/3603/strassenliste> -\> pdf  
<http://domain/fernsteuerung/gehfolge/3603/bezirkskarte> -\> pdf  
<http://domain/fernsteuerung/gehfolge/3603/gehfolge> -\> pdf  
<http://domain/fernsteuerung/gehfolge/3603/detail> -\> csv  
<http://domain/fernsteuerung/gehfolge/3603/zusammenfassung> -\> csv  
<http://domain/fernsteuerung/gehfolge/3603/detail.json> -\> json  
<http://domain/fernsteuerung/gehfolge/3603/zusammenfassung.json> -\>
json  
<http://domain/fernsteuerung/gehfolge/3603/all.json> -\> json

JSON Objekt Beispiele:

Achtung: Die folgenden Keys sind optional:

-   nur_abonnenten
-   privathaushalte
-   gewerbebetriebe
-   werbeverweigerer
-   abonnenten

Zusammenfassung  

    {
        "verteilbezirk_nr": "B421902002",
        "verteilbezirk_name": "Landenhausen 2",
        "gehfolge_id": 2727,
        "zustellerhaus": true,
        "fussweg": false,
        "transport": "fuss",
        "zustellerhaus_kfz": false,
        "nur_abonnenten": true,
        "datenstand_osm": "OSM-Datenstand nicht verfügbar",
        "berechnet_am": "27.04.2021 18:52",
        "grenzdistanz": 36,
        "speed": 6.0,
        "ruestzeit": 15,
        "dauer": 0.8222222222222222,
        "steckzeit": 0.7777777777777778,
        "dauer_sekunden": 2960,
        "steckzeit_sekunden": 2800,
        "strecke_im_gebiet": 4934,
        "strecke_gesamt": 5328,
        "hinweg": 197,
        "rueckweg": 197,
        "dauer_hinweg": 0.002777777777777778,
        "dauer_rueckweg": 0.002777777777777778,
        "osrm_schwelldistanz": "30",
        "hauszugangsdistanzen": 0,
        "anzahl_haeuser_mit_hauszugangsdistanz": 0,
        "privathaushalte": 80,
        "gewerbebetriebe": 8,
        "werbeverweigerer": 0,
        "abonnenten": 40,
        "wv_p": 5,
        "wv_gew": 0,
        "wv_p_zeitung": 0,
        "wv_gew_zeitung": 40,
        "hauszugang_suchradius": "30",
        "abladestelle_id": null,
        "ausgabe_name": "GVS_99_Grundstruktur_Abo",
        "ausgabe_stand": null,
        "zusteller_haus": {
            "oi": "24960475",
            "street_oi": "304207",
            "hausnummer": "5",
            "hausnummer_zusatz": "" 
        },
        "hoehenprofil_min": 274,
        "hoehenprofil_max": 306,
        "hoehenprofil_aufstieg": 113,
        "image_path": "/gehfolgens/2727/image_bezirkskarte",
        "bezirkskarte_path": "/gehfolgens/2727/pdf_bezirkskarte.pdf",
        "strassenliste_path": "/gehfolgens/2727/pdf_strassenliste.pdf",
        "haeuserliste_path": "/gehfolgens/2727/pdf_strassenliste_kompakt.pdf" 
    }

Detail  

    [{
        "geb_id": "abc1",
        "gehfolge_id": 4607,
        "nr": 1,
        "strasse": "Gendarmenmarkt",
        "hausnummer": "2",
        "plz": "10117",
        "ort": "Berlin",
        "verteilbezirk_nr": "Bezirk 10",
        "hauszugangs_distanz": null,
        "dauer": null,
        "strecke": null,
        "privathaushalte": 0,
        "gewerbebetriebe": 0,
        "werbeverweigerer": 0,
        "abonnenten": 0
    }, {
        "geb_id": "abc2",
        "gehfolge_id": 4607,
        "nr": 2,
        "strasse": "Wilhelmstraße",
        "hausnummer": "96",
        "plz": "10117",
        "ort": "Berlin",
        "verteilbezirk_nr": "Bezirk 10",
        "hauszugangs_distanz": 8,
        "dauer": 664,
        "strecke": 917,
        "privathaushalte": 0,
        "gewerbebetriebe": 0,
        "werbeverweigerer": 0,
        "abonnenten": 0
    }, {
        "geb_id": "abc3",
        "gehfolge_id": 4607,
        "nr": 3,
        "strasse": "Voßstraße",
        "hausnummer": "35",
        "plz": "10117",
        "ort": "Berlin",
        "verteilbezirk_nr": "Bezirk 10",
        "hauszugangs_distanz": 4,
        "dauer": 129,
        "strecke": 179,
        "privathaushalte": 3,
        "gewerbebetriebe": 0,
        "werbeverweigerer": 0,
        "abonnenten": 2
    }, {
        "geb_id": "abc4",
        "gehfolge_id": 4607,
        "nr": 4,
        "strasse": "Voßstraße",
        "hausnummer": "34",
        "plz": "10117",
        "ort": "Berlin",
        "verteilbezirk_nr": "Bezirk 10",
        "hauszugangs_distanz": 3,
        "dauer": 22,
        "strecke": 31,
        "privathaushalte": 4,
        "gewerbebetriebe": 0,
        "werbeverweigerer": 0,
        "abonnenten": 3
    }, {
        "geb_id": "abc5",
        "gehfolge_id": 4607,
        "nr": 5,
        "strasse": "Voßstraße",
        "hausnummer": "33",
        "plz": "10117",
        "ort": "Berlin",
        "verteilbezirk_nr": "Bezirk 10",
        "hauszugangs_distanz": 3,
        "dauer": 27,
        "strecke": 38,
        "privathaushalte": 4,
        "gewerbebetriebe": 0,
        "werbeverweigerer": 0,
        "abonnenten": 2
    }, {
        "geb_id": "abc6",
        "gehfolge_id": 4607,
        "nr": 6,
        "strasse": "Voßstraße",
        "hausnummer": "27",
        "plz": "10117",
        "ort": "Berlin",
        "verteilbezirk_nr": "Bezirk 10",
        "hauszugangs_distanz": 4,
        "dauer": 58,
        "strecke": 81,
        "privathaushalte": 6,
        "gewerbebetriebe": 0,
        "werbeverweigerer": 0,
        "abonnenten": 4
    }]

all.json  

    {
        "verteilbezirk_nr": "B421902002",
        "verteilbezirk_name": "Landenhausen 2",
        "gehfolge_id": 2730,
        "zustellerhaus": false,
        "fussweg": false,
        "transport": "fuss",
        "nur_abonnenten": true,
        "datenstand_osm": "OSM-Datenstand nicht verfügbar",
        "berechnet_am": "29.04.2021 13:03",
        "grenzdistanz": 36,
        "speed": 6.0,
        "ruestzeit": 15,
        "dauer": 1.44,
        "steckzeit": 0.7,
        "dauer_sekunden": 5184,
        "steckzeit_sekunden": 2520,
        "strecke_im_gebiet": 8640,
        "strecke_gesamt": 8640,
        "hinweg": 0,
        "rueckweg": 0,
        "dauer_hinweg": 0,
        "dauer_rueckweg": 0,
        "osrm_schwelldistanz": "30",
        "hauszugangsdistanzen": 8,
        "anzahl_haeuser_mit_hauszugangsdistanz": 1,
        "privathaushalte": 215,
        "gewerbebetriebe": 32,
        "werbeverweigerer": 12,
        "abonnenten": 36,
        "hoehenprofil_min": 274,
        "hoehenprofil_max": 340,
        "hoehenprofil_aufstieg": 200,
        "wv_p": 5,
        "wv_gew": 0,
        "wv_p_zeitung": 0,
        "wv_gew_zeitung": 36,
        "hauszugang_suchradius": "30",
        "abladestelle_id": null,
        "ausgabe_name": "GVS_99_Grundstruktur_Abo",
        "ausgabe_stand": null,
        "image_path": "/gehfolgens/2730/image_bezirkskarte",
        "bezirkskarte_path": "/gehfolgens/2730/pdf_bezirkskarte.pdf",
        "strassenliste_path": "/gehfolgens/2730/pdf_strassenliste.pdf",
        "haeuserliste_path": "/gehfolgens/2730/pdf_strassenliste_kompakt.pdf",
        "route": [{
            "geb_id": "29577122",
            "gehfolge_id": 2730,
            "nr": 1,
            "strasse": "Am Sportzentrum",
            "hausnummer": "7",
            "plz": "36367",
            "ort": "Wartenberg",
            "verteilbezirk_nr": "B421902002",
            "hauszugangs_distanz": null,
            "dauer": null,
            "strecke": null,
            "privathaushalte": 0,
            "gewerbebetriebe": 0,
            "werbeverweigerer": 0,
            "abonnenten": 0,
            "abonnenten_detail": [
                []
            ],
            "bemerkung": "",
            "wv_p": 0,
            "wv_gew": 0,
            "wv_p_zeitung": 0,
            "wv_gew_zeitung": 0,
            "haustyp": null
        },
        ...
        ]
    }

### Gehfolgenberechung starten

#### Für alle Verteilbezirke der (Ausgabe)

<http://domain/fernsteuerung/gehfolgen/berechnen>

Optionale Parameter:

|                    |                                                                                                                                   |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| use_save_settings  | Verwende nur die gespeicherten Einstellungen von Verteilbezirk/Ausgabe/Kunde                                                      |
| grenzdistanz       | Hauszugangsdistanz (HZD) Grenzwert (default Kundeneinstellung)                                                                    |
| abonnenten         | Gehfolge nur für Abonnenten berechnen (default false)                                                                             |
| ignore_starthaus   | Starthaus automatisch optimieren (default false) Starhaus des Beziks wird verwendet                                               |
| transport          | fuss oder kfz (default fuss)                                                                                                      |
| zugang_fussweg     | Zum Haus nächstgelegene Fußwege als Zugang bevorzugen (default false) Funktioniert nur bei transport=fuss                         |
| ignore_street_name | Straßennamen ignorieren (default false) Bei Problemen wenn in OSM ein anderer Straßennamen enthalten ist wie in den Adresse-Daten |
| steckzeit_erste    | (default Kundeneinstellung)                                                                                                       |
| steckzeit_folgende | (default Kundeneinstellung)                                                                                                       |
| speed              | Geschwindigkeit (default Kundeneinstellung oder 5)                                                                                |
| ruestzeit          | Rüstzeit (default Kundeneinstellung oder 0)                                                                                       |
| ausgabe            | Name der Ausgabe (default die vom User)                                                                                           |
| option             | Optionen Parameter (Verteilbezirk und Ausgabe) Objekt (optional)                                                                  |

Parameter für Depot-Optimierung:

|                  |                                                                     |
|------------------|---------------------------------------------------------------------|
| kapazitaet       | Anzahl der Zeitungen                                                |
| start_kapazitaet | Anzahl der Zeitungen die der Zusteller schon dabei hat. (default 0) |

bzw.

|                     |                                                                                                                       |
|---------------------|-----------------------------------------------------------------------------------------------------------------------|
| kapazitaet_kg       | Tragekapazität des Zustellers in kg)                                                                                  |
| start_kapazitaet_kg | Tragekapazität des Zustellers in kg beim Start (\~ Anzahl der Zeitungen die der Zusteller schon dabei hat)(default 0) |
| mediengewicht       | Gewicht eines Mediums in Gramm                                                                                        |

Optionen Parameter: (null setzte den Wert auf Standard)

|                                |                                                                                |                  |
|--------------------------------|--------------------------------------------------------------------------------|------------------|
| hauszugangsdistanz             | Hauszugangsdistanz Grenzwert (als Vorgabewert, in Meter)                       | float            |
| osrm_schwelldistanz            | Hauszugangs-Suchradius                                                         | float            |
| ruestzeit                      | Standardeinstellung Rüstzeit (in ganzen Minuten)                               | float            |
| steckzeit_erste                | Erste Steckung (an Adresse, in Sekunden)                                       | float            |
| steckzeit_folgende             | Folgende Steckungen (an Adresse, in Sekunden)                                  | float            |
| optimierung                    | Optimierungsmethode                                                            | siehe Auflistung |
| geschwindigkeit                | Geschwindigkeit (in km/h )                                                     | float            |
| car_profile_fuer_zustellerhaus | Hin-/Rückweg zum Zustellerhaus mit Kfz.                                        | true,false,null  |
| starthaus                      | Starthaus automatisch optimieren                                               | true,false,null  |
| strassen_name                  | Straßennamen ignorieren (Zum Haus nächstgelegenen Punkt als Zugang bevorzugen) |                  |
| nullhaushalte                  | Adressen ohne Haushalte oder Gewerbebetriebe ignorieren                        | true,false,null  |
| osrm_overview                  | Routengeometrie (nur Anzeige): exakt oder vereinfacht (default vereinfacht)    | true,false,null  |

Nur wenn die Option verfügbar ist.

|                  |                                                                                     |                 |
|------------------|-------------------------------------------------------------------------------------|-----------------|
| kfz              | Kfz-Fahrprofil                                                                      | true,false,null |
| geschwindigkeit2 | Alternative Geschwindigkeit (in km/h ) für Hin- und Rückweg (nur bei Zustellerhaus) | float           |
| geschwindigkeit3 | Alternative Geschwindigkeit (in km/h ) für Hauszugangsdistanz                       | float           |

Nur wenn Option Depots freigeschaltet ist.

|                              |                                                |                 |
|------------------------------|------------------------------------------------|-----------------|
| depot                        | Depot Einstellungen überschreiben              | true,false,null |
| austraeger_kg                | Verwende Gewicht statt Anzahl                  | float           |
| austraeger_start_capacity    | Tragekapazität des Zustellers beim Start       | float           |
| austraeger_capacity          | Tragekapazität des Zustellers                  | float           |
| austraeger_start_capacity_kg | Tragekapazität des Zustellers in kg beim Start | float           |
| austraeger_capacity_kg       | Tragekapazität des Zustellers in kg            | float           |
| mediengewicht                | Gewicht eines Mediums in Gramm                 | float           |

Einstellung für Ausgabe verändern:

|            |                                             |                        |
|------------|---------------------------------------------|------------------------|
| p          | Privathaushalte                             | true,false             |
| gew        | Gewerbebetriebe                             | true,false             |
| wv_mit_abo | Resthaushaltsverteilung mit/ohne Abonnenten | true,false             |
| wv_p       | Sperrung Werbung Privathaushalte            | Ausprägung siehe unten |
| wv_gew     | Sperrung Werbung Gewerbebetriebe            | Ausprägung siehe unten |

|               |                                             |
|---------------|---------------------------------------------|
| wv_p          | Sperrung Werbung Privathaushalte            |
| wv_p\_zeitung | Sperrung kostenlose Zeitung Privathaushalte |
| false         | keine Sperrung                              |

|                |                                             |
|----------------|---------------------------------------------|
| wv_gew         | Sperrung Werbung Gewerbebetriebe            |
| wv_gew_zeitung | Sperrung kostenlose Zeitung Gewerbebetriebe |
| false          | keine Sperrung                              |

Optimierungsmethode

|                          |                  |
|--------------------------|------------------|
| roundtrip                | Rundweg          |
| roundtrip_intern         |                  |
| oneway                   | Einfache Strecke |
| '' bzw. jeder ander Wert | Default          |

Beispiel Aufruf:

    {
      "verteilbezirk": "B421902002",
      "option": {
        "kfz": true,
        "hauszugangsdistanz": 36,
        "strassen_name": "",
        "starthaus": null,
        "steckzeit_erste": 70,
        "steckzeit_folgende": 20,
        "optimierung": "oneway",
        "geschwindigkeit": 6,
        "geschwindigkeit2": 70,
        "car_profile_fuer_zustellerhaus": false,
        "ruestzeit": 15,
        "nullhaushalte": false,
        "osrm_schwelldistanz": 30,
        "modus": "rest",
        "p": true,
        "gew": true
      }
    }

METHODE \[POST oder GET\]

Rückgabewert ist ein JSON Object:

    {"status":200,"gehfolgen_ids":[3601,3602,3603,3604,3605,3606,3607,3608,3609]}
    {"status":500,"error":{"text":"kein Verteilbezirk gefunden","data":null}}

#### Für einen Verteilbezirk

<http://domain/fernsteuerung/gehfolge/berechnen?verteilbezirk=123>

Parameter: \|verteilbezirk\| Nr. des Verteilbezirks\|  
Optionale Parameter:  
siehe: Für alle Verteilbezirke der (Ausgabe)

METHODE \[POST oder GET\]

Rückgabewert ist ein JSON Object:

    {"status":200,"gehfolgen_ids":[1]}
    {"status":500,"error":{"text":"kein Verteilbezirk gefunden","data":null}}

#### Abbrechen der Gehfolgenberechung (nur die von User)

<http://domain/fernsteuerung/gehfolgen/abbrechen>

### Beispiele

[PHP-Beispiel letzte berechnete Gehfolge für bestimmen
Verteilbezirk](PHP-Beispiel_letzte_berechnete_Gehfolge_für_bestimmen_Verteilbezirk.html)

## Datenaustausch (JSON)

Der Datenaustausch ist auf JSON Objekte ausgelegt.  
Beim Übermitteln von JSON Objekten(POST) muss man den  
Header: "Content-Type: application/json" mit angeben.

Es ist aber auch möglich die Abfrage über GET bzw. normale POST Request
zu machen.  
Dies ist dann sinnvoll, wenn ich Daten vom Server hole.

### Adressen

#### Adressen abrufen

<http://domain/fernsteuerung/adresse>

Parameter (optional):

|               |                                                                                                                                                                     |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| limit         | Limit                                                                                                                                                               |
| offset        | Offset                                                                                                                                                              |
| koordinaten   | Gibt Koordinaten mit aus (optional default false)                                                                                                                   |
| kommentar     | Gibt Kommentar mit aus (optional default false)                                                                                                                     |
| alle_ausgaben | Gibt nur zugeordnete Adressen aus (Bezirk und Ausgabe werden als Array ausgegeben (Adresse kann in verschiedenen Ausgaben sein) (optional default false)            |
| starthaus     | Gibt nur Adressen die Starthaus sind aus (Bezirk und Ausgabe werden als Array ausgegeben (Adresse kann in verschiedenen Ausgaben sein) (optional default false)     |
| zustellerhaus | Gibt nur Adressen die Zustellerhaus sind aus (Bezirk und Ausgabe werden als Array ausgegeben (Adresse kann in verschiedenen Ausgaben sein) (optional default false) |
| endhaus       | Gibt nur Adressen die Endhaus sind aus (Bezirk und Ausgabe werden als Array ausgegeben (Adresse kann in verschiedenen Ausgaben sein) (optional default false)       |
| depot         | Gibt nur Adressen die Depot sind aus (Bezirk und Ausgabe werden als Array ausgegeben (Adresse kann in verschiedenen Ausgaben sein) (optional default false)         |
| ausgabe       | Name der Ausgabe (funktioniert nur mit \[alle_ausgaben,starthaus,zustellerhaus,endhaus,depot\])                                                                     |

Optionale Filter Parameter:

|                   |                                                                      |
|-------------------|----------------------------------------------------------------------|
| oi                | Gebäude ids                                                          |
| plz               | Postleitzahl                                                         |
| ort               | Ort                                                                  |
| ort_zusatz        | Ortsteil                                                             |
| strasse           | Strasse                                                              |
| hausnummer        | Hausnummer                                                           |
| hausnummer_zusatz | Hausnummer Zusatz                                                    |
| street_oi         | Straßenabschnitts-ID                                                 |
| street_alt_oi     | Alternative Straßenabschnitts-ID                                     |
| manuell           | true (Gibt nur durch Kartenklick erfasste Adressen aus (GBC Nummer)) |

Rückgabe:  

    [{
        "oi": "OOI1411",
        "plz": "10115",
        "ort": "Berlin",
        "ort_zusatz": null,
        "strasse": "Ackerstraße",
        "hausnummer": "172",
        "hausnummer_zusatz": "",
        "is_active": true,
        "privathaushalte": 1,
        "gewerbebetriebe": 2
    }, {
        "oi": "OOI1412",
        "plz": "10115",
        "ort": "Berlin",
        "ort_zusatz": null,
        "strasse": "Ackerstraße",
        "hausnummer": "173",
        "hausnummer_zusatz": "",
        "is_active": true,
        "privathaushalte": null,
        "gewerbebetriebe": null
    }, {
        "oi": "OOI1413",
        "plz": "10115",
        "ort": "Berlin",
        "ort_zusatz": null,
        "strasse": "Ackerstraße",
        "hausnummer": "174",
        "hausnummer_zusatz": "",
        "is_active": true,
        "privathaushalte": null,
        "gewerbebetriebe": null
    }]

Rückgabe mit alle_ausgaben:  

    [{
        "oi": "12760120275582",
        "plz": "35075",
        "ort": "Gladenbach",
        "ortsteil": "",
        "ort_zusatz": null,
        "strasse": "Adolf-Theis-Straße",
        "hausnummer": "12",
        "hausnummer_zusatz": "",
        "is_active": true,
        "notice": null,
        "street_oi": "0000386499",
        "privathaushalte": 2,
        "gewerbebetriebe": 0,
        "werbeverweigerer": null,
        "ausgabe_bezirk": [{
            "nr": "B201015Z",
            "ausgabe": "Freitag" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Montag" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Dienstag" 
        }, {
            "nr": "B201015V",
            "ausgabe": "Vollverteilung" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Vollverteilung" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Donnerstag" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Test Meier Abo 24.03.17" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Samstag" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Sonntag" 
        }, {
            "nr": "T201055",
            "ausgabe": "Test Meier Abo 24.03.17" 
        }, {
            "nr": "T201055",
            "ausgabe": "Test" 
        }]
    }, {
        "oi": "12760120388646",
        "plz": "35075",
        "ort": "Gladenbach",
        "ortsteil": "",
        "ort_zusatz": null,
        "strasse": "Adolf-Theis-Straße",
        "hausnummer": "13",
        "hausnummer_zusatz": "",
        "is_active": true,
        "notice": null,
        "street_oi": "0000386499",
        "privathaushalte": 2,
        "gewerbebetriebe": 0,
        "werbeverweigerer": null,
        "ausgabe_bezirk": [{
            "nr": "T201055",
            "ausgabe": "Test" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Montag" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Dienstag" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Donnerstag" 
        }, {
            "nr": "B201015V",
            "ausgabe": "Vollverteilung" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Vollverteilung" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Freitag" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Test Meier Abo 24.03.17" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Samstag" 
        }, {
            "nr": "T201055",
            "ausgabe": "Test Meier Abo 24.03.17" 
        }]
    }, {
        "oi": "12760120264124",
        "plz": "35075",
        "ort": "Gladenbach",
        "ortsteil": "",
        "ort_zusatz": null,
        "strasse": "Adolf-Theis-Straße",
        "hausnummer": "14",
        "hausnummer_zusatz": "",
        "is_active": true,
        "notice": null,
        "street_oi": "0000386499",
        "privathaushalte": 1,
        "gewerbebetriebe": 0,
        "werbeverweigerer": null,
        "ausgabe_bezirk": [{
            "nr": "T201055",
            "ausgabe": "Test" 
        }, {
            "nr": "B201015V",
            "ausgabe": "Vollverteilung" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Sonntag" 
        }, {
            "nr": "T201055",
            "ausgabe": "Test Meier Abo 24.03.17" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Donnerstag" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Vollverteilung" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Test Meier Abo 24.03.17" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Freitag" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Dienstag" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Montag" 
        }, {
            "nr": "B201015Z",
            "ausgabe": "Samstag" 
        }]
    }]

#### Adressen Hinzufügen/Updaten

<http://domain/fernsteuerung/add_and_update_adresse>

Parameter:

|         |                                                                |
|---------|----------------------------------------------------------------|
| adresse | Adresse Parameter                                              |
| insert  | true(default) oder false. Nur neue Adressen werden hinzugefügt |
| update  | true(default) oder false. Bestehende Adressen werden geupdated |

Adresse Parameter:

|                   |                                   |
|-------------------|-----------------------------------|
| oi                | Gebäude ID (required)             |
| street_oi         | Straßen ID                        |
| longitude         | Längengrad (required)             |
| latitude          | Breitengrad (required)            |
| plz               | Postleitzahl                      |
| ort               | Ort                               |
| ort_zusatz        | Ort Zusatz                        |
| ortsteil          | Ortsteil                          |
| strasse           | Strasse                           |
| hausnummer        | Hausnummer                        |
| hausnummer_zusatz | Hausnummer Zusatz                 |
| is_active         | Haus ist aktiv (required)         |
| privathaushalte   | Anzahl Werbeverweigerer (integer) |
| gewerbebetriebe   | Anzahl Werbeverweigerer (integer) |
| werbeverweigerer  | Anzahl Werbeverweigerer (integer) |

    {
    "update": true,
    "insert": true, 
    "adresse": [{
        "oi": "GBC93385",
        "plz": "10119",
        "ort": "Berlin",
        "ort_zusatz": null,
        "strasse": "Schwedter Straße",
        "hausnummer": "22",
        "hausnummer_zusatz": "",
        "is_active": true,
        "notice": null,
        "privathaushalte": 0,
        "gewerbebetriebe": 0,
        "werbeverweigerer": 0,
        "longitude": 52.5347133208835,
        "latitude": 13.4075689315796
    }, {
        "oi": "GBC360693",
        "plz": "84030",
        "ort": "Ergolding",
        "ort_zusatz": null,
        "strasse": "Schinderstraßl",
        "hausnummer": "5",
        "hausnummer_zusatz": "D",
        "is_active": true,
        "notice": null,
        "privathaushalte": 0,
        "gewerbebetriebe": 0,
        "werbeverweigerer": null,
        "longitude": 12.1660333871841,
        "latitude": 48.5649005287186
    }]
     }

#### Adressen löschen

<http://domain/fernsteuerung/delete_adresse>

|     |            |
|-----|------------|
| oi  | Adresse ID |

    {
    "oi": ["3353880","2739684","DEBYv00099005586","DEBYv00099000331","DEBYv00099029356","DEBYv00099001121","DEBYv00099000328"]
    }

### Abonnenten

#### Abonnenten abrufen

<http://domain/fernsteuerung/gebiet/abonnent> (Gebiets Ausgabe)  
<http://domain/fernsteuerung/bezirk/abonnent> (Bezirks Ausgabe)

Parameter (optional):

|         |                                                           |
|---------|-----------------------------------------------------------|
| limit   | Limit                                                     |
| offset  | Offset                                                    |
| ausgabe | Name der Ausgabe (default=Aktuelle Ausgabe des Benutzers) |

Rückgabe:  

    [{"oi":"GBC372190","abonnenten":0},{"oi":"GBC372192","abonnenten":7},{"oi":"DEBYv00099001290","abonnenten":1}]

#### Abonnenten Hinzufügen/Updaten

<http://domain/fernsteuerung/gebiet/add_and_update_abonnent> (Gebiets
Ausgabe)  
<http://domain/fernsteuerung/bezirk/add_and_update_abonnent> (Bezirks
Ausgabe)

Parameters

|          |                                                                    |
|----------|--------------------------------------------------------------------|
| abonnent | Abonnent Parameters                                                |
| insert   | true(default) oder false. Nur neue Gebiete werden hinzugefügt      |
| update   | true(default) oder false. Bestehende Gebiete werden geupdated      |
| ausgabe  | Name der Ausgabe (optional: defaul=Aktuelle Ausgabe des Benutzers) |

Abonnent Parameter

|                |                                               |          |
|----------------|-----------------------------------------------|----------|
| oi             | Gebäude ID                                    |          |
| abonnenten     | Anzahl Abonnent                               | integer  |
| title          | Abo Titel                                     | optional |
| abo_name       | Abonnent Name, Nr ... (darf kein ; enthalten) | optional |
| abo_vorname    | Abonnent Vorname (darf kein ; enthalten)      | optional |
| abo_nachname   | Abonnent Nachname (darf kein ; enthalten)     | optional |
| abo_hint       | Hinweis Zustellbesonderheit                   | optional |
| abo_nr         | Abo Nummer (Zusie)                            | optional |
| abo_pva        | Planvertriebsausgabe (Zusie)                  | optional |
| abo_bper       | Bezugsperiode (Zusie)                         | optional |
| abo_ub         | Unterbrechung (Zusie)                         | optional |
| abo_valid_from | gültig von (Zusie)                            | optional |
| abo_valid_to   | gültig bis (Zusie)                            | optional |

Abonnent Parameter mit Straßen ID

|                   |                                               |                                                                     |
|-------------------|-----------------------------------------------|---------------------------------------------------------------------|
| street_oi         | Straßen ID                                    |                                                                     |
| hausnummer        | Hausnummer                                    |                                                                     |
| hausnummer_zusatz | Hausnummer Zusatz                             | (optional, der Zusatz kann auch bei der Hausnummer mit dabei sein.) |
| abonnenten        | Anzahl Abonnent                               | integer                                                             |
| title             | Abo Titel                                     | optional                                                            |
| abo_name          | Abonnent Name, Nr ... (darf kein ; enthalten) | optional                                                            |
| abo_vorname       | Abonnent Vorname (darf kein ; enthalten)      | optional                                                            |
| abo_nachname      | Abonnent Nachname (darf kein ; enthalten)     | optional                                                            |
| abo_hint          | Hinweis Zustellbesonderheit                   | optional                                                            |
| abo_nr            | Abo Nummer (Zusie)                            | optional                                                            |
| abo_pva           | Planvertriebsausgabe (Zusie)                  | optional                                                            |
| abo_bper          | Bezugsperiode (Zusie)                         | optional                                                            |
| abo_ub            | Unterbrechung (Zusie)                         | optional                                                            |
| abo_valid_from    | gültig von (Zusie)                            | optional                                                            |
| abo_valid_to      | gültig bis (Zusie)                            | optional                                                            |

    {
    "update": true,
    "insert": true, 
    "abonnent": [{"oi":"3353880","abonnenten":3},{"oi":"2739684","abonnenten":3}]
     }

    {
    "update": true,
    "insert": true, 
    "abonnent": [
    {"street_oi":"1234", "hausnummer": "2","abonnenten":3},
    {"street_oi":"4567", "hausnummer": "12","abonnenten":3},
    {"street_oi":"4567", "hausnummer": "21","abonnenten":3}]
     }

Abonnent-Parameter wie z.B. abo_name oder title an einer oder mehreren
Adressen übergeben:  
Die Anzahl der Paramter müssen für jeden Datensatz gleich sein. Es ist
wie, wenn man eine Tabelle hochlädt, da sind auch für jede Spalte Daten
vorhanden.

    {
    "update": true,
    "insert": true, 
    "abonnent": [
    {"street_oi":"1234", "hausnummer": "2","abonnenten":1,"title": "SZ", "abo_name": "Fritz Huber"},
    {"street_oi":"1234", "hausnummer": "2","abonnenten":1,"title": "SZ", "abo_name": "Hans Meier"},
    {"street_oi":"1234", "hausnummer": "2","abonnenten":1,"title": "TZ", "abo_name": "Hans Meier"},
    {"street_oi":"4567", "hausnummer": "12","abonnenten":1,"title": "TZ", "abo_name": "Hansi Maier"},
    {"street_oi":"4567", "hausnummer": "21","abonnenten":3,"title": "TZ", "abo_name": "Altenheim"}
    ]
     }

#### Abonnenten löschen

<http://domain/fernsteuerung/gebiet/delete_abonnent> (Gebiets Ausgabe)  
<http://domain/fernsteuerung/bezirk/delete_abonnent> (Bezirks Ausgabe)

|         |                                                                |
|---------|----------------------------------------------------------------|
| oi      | Adresse ID                                                     |
| ausgabe | Name der Ausgabe (defaul=Aktuelle Ausgabe des Benutzers)       |
| all     | (optional) true , alle Abonnenten der Ausgabe werden gelöscht. |

    {
    "oi": ["3353880","2739684","DEBYv00099005586","DEBYv00099000331","DEBYv00099029356","DEBYv00099001121","DEBYv00099000328"]
    }

### Gebiet

Das Gebiet (= Zelle) ist die untergeordnete Ebene, wenn zwei Ebenen
verfügbar sind. Auf dieser Ebene werden die Zuordnungen zu den Gebäuden
(Adressen) vorgenommen. Aus einem oder mehreren Gebieten werden durch
die Zuordnung Gebiet=\>Bezirk Bezirke (= Trägerbezirke) gebildet.  
Ist nur eine Ebene vorhanden, so bildet ein Gebiet den Trägerbezirk
(Regelfall).

#### Gebiete abrufen

<http://domain/fernsteuerung/gebiet/>

Parameter (optional):

|         |                                                           |
|---------|-----------------------------------------------------------|
| nr      | Nummer(n) der Gebiete                                     |
| limit   | Limit                                                     |
| offset  | Offset                                                    |
| ausgabe | Name der Ausgabe (default=Aktuelle Ausgabe des Benutzers) |
| option  | Optionen Parameter                                        |
| geojson | Geojson Feature                                           |

Beispiel Rückgabe:
<http://domain/fernsteuerung/gebiet/?nr=1200,1300,1400&ausgabe=default>

    [{
        "nr": "1200",
        "name": "",
        "privathaushalte": 1,
        "gewerbebetriebe": 2,
        "abonnenten": 10,
        "limit_plz": "",
        "starthaus": "1",
        "zustellerhaus": "2",
        "endhaus": "3" 
    }, {
        "nr": "1300",
        "name": "",
        "privathaushalte": 0,
        "gewerbebetriebe": 0,
        "abonnenten": 0,
        "limit_plz": "",
        "starthaus": null,
        "zustellerhaus": null,
        "endhaus": null
    }, {
        "nr": "1400",
        "name": "",
        "privathaushalte": 0,
        "gewerbebetriebe": 0,
        "abonnenten": 0,
        "limit_plz": "",
        "starthaus": null,
        "zustellerhaus": null,
        "endhaus": null
    }]
    
Optionale Ausgabe wenn in Kundenverwaltung ausgewählt:  
privathaushalte, gewerbebetriebe, werbeverweigerer, abonnenten  
limit_plz  
starthaus, zustellerhaus, endhaus (Gebäude ID (oi))

Beispiel mit option:
<http://domain/fernsteuerung/gebiet/?nr=test2&ausgabe=default&option=true>

    [{
        "nr": "test2",
        "name": "",
        "privathaushalte": 0,
        "gewerbebetriebe": 0,
        "abonnenten": 0,
        "starthaus": "2464801",
        "zustellerhaus": "24079601",
        "endhaus": null,
        "wegnetz_laenge": "",
        "option": {
            "kfz": null,
            "hauszugangsdistanz": null,
            "strassen_name": null,
            "starthaus": null,
            "steckzeit_erste": null,
            "steckzeit_folgende": null,
            "optimierung": "",
            "geschwindigkeit": 70,
            "car_profile_fuer_zustellerhaus": true,
            "ruestzeit": null,
            "nullhaushalte": null,
            "osrm_schwelldistanz": null,
            "depot": false,
            "austraeger_kg": false,
            "austraeger_start_capacity": 50,
            "austraeger_capacity": 50,
            "austraeger_start_capacity_kg": null,
            "austraeger_capacity_kg": null,
            "mediengewicht": null
        }
    }]

Beispiel mit geojson:
<http://domain/fernsteuerung/gebiet/?nr=test2&ausgabe=default&geojson=true>

    [{
        "nr": "test2",
        "name": "",
        "privathaushalte": 0,
        "gewerbebetriebe": 0,
        "abonnenten": 0,
        "starthaus": "2464801",
        "zustellerhaus": "24079601",
        "endhaus": null,
        "wegnetz_laenge": "",
        "geojson": {
            "type": "Feature",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [8.173963, 52.231681],
                        [8.17392353099216, 52.23171560874612],
                        [8.173319231411217, 52.23177219638712],
                        [8.173292809392441, 52.23174228707541],
                        [8.172802044818699, 52.23184869266271],
                        [8.172249231411216, 52.23184419638712],
                        [8.172202196387119, 52.23181276858879],
                        [8.171935284271246, 52.23188771572875],
                        [8.171293955181302, 52.231996692662705],
                        [8.1702830448187, 52.23208469266271],
                        [8.169846715728752, 52.232168715728754],
                        [8.169695777190679, 52.232313741215506],
                        [8.169285222809322, 52.23221974121551],
                        [8.1692260448187, 52.23223769266271],
                        [8.169023777190679, 52.23241074121551],
                        [8.168438, 52.23237],
                        [8.16776615831024, 52.23244770503202],
                        [8.166211715728753, 52.232728715728754],
                        [8.165591304129428, 52.23260324064874],
                        [8.165559876331093, 52.232634668447076],
                        [8.165583800405015, 52.23267942724126],
                        [8.165513196387119, 52.233156768588785],
                        [8.165481768588783, 52.23320380361288],
                        [8.165669741215508, 52.23343477719068],
                        [8.165674715728754, 52.23348528427125],
                        [8.165725222809321, 52.23349025878449],
                        [8.166131741215507, 52.23393077719068],
                        [8.166131741215507, 52.23397522280932],
                        [8.166312307337295, 52.2340879551813],
                        [8.166672741215507, 52.23454177719068],
                        [8.166683777190679, 52.23459725878449],
                        [8.166734284271246, 52.234592284271244],
                        [8.167082692662705, 52.2348539551813],
                        [8.167388715728753, 52.234834284271244],
                        [8.168430803612882, 52.235379231411216],
                        [8.168698196387119, 52.23511923141122],
                        [8.168972307337295, 52.2351679551813],
                        [8.16936, 52.23478],
                        [8.169762371209346, 52.23466496343907],
                        [8.170116307337295, 52.2344569551813],
                        [8.170751369206673, 52.23424438760029],
                        [8.171241715728753, 52.23403028427124],
                        [8.171285307337294, 52.2340389551813],
                        [8.17142822280932, 52.23384325878449],
                        [8.171960715728753, 52.233674284271245],
                        [8.172004307337295, 52.2336829551813],
                        [8.172203974045564, 52.233565876364345],
                        [8.172358590196875, 52.233326779416835],
                        [8.172638777190679, 52.23327525878449],
                        [8.17326070939186, 52.232912203143435],
                        [8.173622222809321, 52.23276325878449],
                        [8.173783598950585, 52.23260618511437],
                        [8.173779258784492, 52.23257077719068],
                        [8.174297777190679, 52.23209325878449],
                        [8.1745309551813, 52.23194230733729],
                        [8.174509307337294, 52.2318900448187],
                        [8.174307, 52.231992],
                        [8.173963, 52.231681]
                    ]
                ]
            },
            "properties": {},
            "id": "test2"
        }
    }]

#### Gebiet Hinzufügen/Updaten

<http://domain/fernsteuerung/gebiet/add_and_update>

Parameter:

|         |                                                                     |
|---------|---------------------------------------------------------------------|
| gebiet  | Gebiet Parameter                                                    |
| insert  | true(default) oder false. Nur neue Gebiete werden hinzugefügt       |
| update  | true(default) oder false. Bestehende Gebiete werden geupdated       |
| ausgabe | Name der Ausgabe (optional: default=Aktuelle Ausgabe des Benutzers) |
| option  | Optionen Parameter (optional)                                       |

Gebiet Parameter (Achtung: beim Einfügen von mehreren Gebieten muss
immer die gleiche Anzahl der Parameter angegeben werden):

|               |                                                    |
|---------------|----------------------------------------------------|
| nr            | Gebietsnummer                                      |
| name          | Gebietsname (optional)                             |
| limit_plz     | Adressen limitiert auf Postleitzahl(en) (optional) |
| starthaus     | oi Starthaus oder Objekt (optional)                |
| zustellerhaus | oi Zustellerhaus oder Objekt (optional)            |
| endhaus       | oi Endhaus oder Objekt (optional)                  |

Start- Zusteller- Endhaus als Objekt
([r2417](/redmine/projects/multiroute-go/repository/revisions/2417 "CS: #4871 API Gehfolge erweitert. API Zusteller-, Start- und Endhaus mit street_oi möglich."))

|                   |                                 |
|-------------------|---------------------------------|
| street_oi         | Straßenabschnitts-ID (required) |
| hausnummer        | Hausnummer (required)           |
| hausnummer_zusatz | Hausnummer Zusatz (required)    |

Optionen Parameter: (null setzte den Wert auf Standard)

|                                |                                                                                |                  |
|--------------------------------|--------------------------------------------------------------------------------|------------------|
| hauszugangsdistanz             | Hauszugangsdistanz Grenzwert (als Vorgabewert, in Meter)                       | float            |
| osrm_schwelldistanz            | Hauszugangs-Suchradius                                                         | float            |
| ruestzeit                      | Standardeinstellung Rüstzeit (in ganzen Minuten)                               | float            |
| steckzeit_erste                | Erste Steckung (an Adresse, in Sekunden)                                       | float            |
| steckzeit_folgende             | Folgende Steckungen (an Adresse, in Sekunden)                                  | float            |
| optimierung                    | Optimierungsmethode                                                            | siehe Auflistung |
| geschwindigkeit                | Geschwindigkeit (in km/h )                                                     | float            |
| car_profile_fuer_zustellerhaus | Hin-/Rückweg zum Zustellerhaus mit Kfz.                                        | true,false,null  |
| starthaus                      | Starthaus automatisch optimieren                                               | true,false,null  |
| strassen_name                  | Straßennamen ignorieren (Zum Haus nächstgelegenen Punkt als Zugang bevorzugen) | true,false,null  |
| nullhaushalte                  | Adressen ohne Haushalte oder Gewerbebetriebe ignorieren                        | true,false,null  |
| osrm_overview                  | Routengeometrie (nur Anzeige): exakt oder vereinfacht (default vereinfacht)    | true,false,null  |

Nur wenn die Option verfügbar ist.

|                  |                                                                                     |                 |
|------------------|-------------------------------------------------------------------------------------|-----------------|
| kfz              | Kfz-Fahrprofil                                                                      | true,false,null |
| geschwindigkeit2 | Alternative Geschwindigkeit (in km/h ) für Hin- und Rückweg (nur bei Zustellerhaus) | float           |
| geschwindigkeit3 | Alternative Geschwindigkeit (in km/h ) für Hauszugangsdistanz                       | float           |

Nur wenn Option Depots freigeschaltet ist.

|                              |                                                |                 |
|------------------------------|------------------------------------------------|-----------------|
| depot                        | Depot Einstellungen überschreiben              | true,false,null |
| austraeger_kg                | Verwende Gewicht statt Anzahl                  | float           |
| austraeger_start_capacity    | Tragekapazität des Zustellers beim Start       | float           |
| austraeger_capacity          | Tragekapazität des Zustellers                  | float           |
| austraeger_start_capacity_kg | Tragekapazität des Zustellers in kg beim Start | float           |
| austraeger_capacity_kg       | Tragekapazität des Zustellers in kg            | float           |
| mediengewicht                | Gewicht eines Mediums in Gramm                 | float           |

Optimierungsmethode

|                          |                          |
|--------------------------|--------------------------|
| roundtrip                | Rundweg                  |
| roundtrip_intern         | Rundweg im Verteilbezirk |
| oneway                   | Einfache Strecke         |
| '' bzw. jeder ander Wert | Default                  |

Beispiel:

    {
    "update": true,
    "insert": true, 
    "gebiet": [{
        "nr": "1200",
        "name": "Gebiet 1",
        "limit_plz": "12345,23456",
        "starthaus": "1",
        "zustellerhaus": "2",
        "endhaus": "3" 
    }, {
        "nr": "1300",
        "name": "Gebiet 2",
        "limit_plz": "",
        "starthaus": null,
        "zustellerhaus": null,
        "endhaus": null
    }]
     }

Beispiel Optionen Updaten  

    {
      "ausgabe": "Name der Ausgabe",
      "gebiet": [
        {
          "nr": "B421902002",
          "option": {
            "kfz": false,
            "hauszugangsdistanz": 10,
            "strassen_name": null,
            "starthaus": null,
            "steckzeit_erste": 70,
            "steckzeit_folgende": 25,
            "optimierung": "roundtrip",
            "geschwindigkeit": 12,
            "geschwindigkeit2": 50,
            "car_profile_fuer_zustellerhaus": true,
            "ruestzeit": 5,
            "nullhaushalte": true,
            "osrm_schwelldistanz": "20" 
          }
        }
      ]
    }

Beispiel Zustellerhaus mit Straßenabschnitts-ID  

    {
      "gebiet": [
        {
          "nr": "B421902002",
          "zustellerhaus": {
            "street_oi": "304207",
            "hausnummer": "7",
            "hausnummer_zusatz": "" 
          }
        }
      ]
    }

#### Gebiet löschen

<http://domain/fernsteuerung/gebiet/delete>

Parameter:

|         |                                                                     |
|---------|---------------------------------------------------------------------|
| nr      | Nummer des Gebietes/Nummern der Gebiete                             |
| ausgabe | Name der Ausgabe (optional: default=Aktuelle Ausgabe des Benutzers) |

    {
      nr: ["1","2"]
    }

#### Gebietsdefinition

<http://domain/fernsteuerung/gebiet/definition>

Parameter (optional):

|         |                                                           |
|---------|-----------------------------------------------------------|
| gebiet  | Nummer(n) der Gebiete                                     |
| limit   | Limit                                                     |
| offset  | Offset                                                    |
| ausgabe | Name der Ausgabe (default=Aktuelle Ausgabe des Benutzers) |

Rückgabe:

    [{"gebiet":"1234","oi":["1","2","3","4"],"ausgabe":"1234"},{"gebiet":"2345","oi":["5","6","7","8"],"ausgabe":"1234"}]

#### Gebietsdefinition hinzufügen bzw. löschen

<http://domain/fernsteuerung/gebiet/add_definition>  
<http://domain/fernsteuerung/gebiet/delete_definition>

Parameter:

[TABLE]

    {
      "oi": ["1","2","3"],
      "gebiet": "11",
      "ausgabe": "1234" 
    }

bzw.

<http://domain/fernsteuerung/gebiet/add_definition?ausgabe=1234&gebiet=11&oi=1,2,3>  
<http://domain/fernsteuerung/gebiet/delete_definition?ausgabe=1234&gebiet=11&oi=1,2,3>

Bekannte Fehlermeldungen:

    {"text":"Ausgabe nicht gefunden","status":500}
    {"text":"Kein Gebiet übergeben","status":500}
    {"text":"Keine Adresse übergeben","status":500}
    {"text":"Daten wurden nicht übernommen","status":500}

#### Gebietsdefinition hinzufügen (Mit Street-ID)

<http://domain/fernsteuerung/gebiet/add_definition_with_street_oi>

Parameter:

[TABLE]

Adresse Params:

|           |                |
|-----------|----------------|
| street_oi | Straßen ID     |
| nr_von    | von Hausnummer |
| nr_bis    | Bis Hausnummer |

Optionale Adresse Params:

|              |                       |
|--------------|-----------------------|
| nrzusatz_von | von Hausnummer Zusatz |
| nrzusatz_bis | Bis Hausnummer Zusatz |

|       |                                                                                              |
|-------|----------------------------------------------------------------------------------------------|
| kennz | Kennzahl A: Alle, G:Nur gerade Hausnummern, U: Nur ungerade Hausnummern. optional(default A) |

    {
      "adresse": [{"street_oi":"1234", "nr_von": "2","nr_bis":"998","kennz":"G"},{"street_oi":"4567", "nr_von": "1","nr_bis":"999","kennz":"A"}],
      "gebiet": "8765",
      "ausgabe": "default" 
    }

    gegeben Hausnummer 20, 20A, 20B, 21, 21A, 21B, 22, 22A,22B

    Bisher:
    {  "adresse": [{"street_oi": "x11", "nr_von": "20",  "nr_bis": "20" }]} => 20, 20A, 20B
    {  "adresse": [{"street_oi": "x11", "nr_von": "20",  "nr_bis": "22" }]} => 20, 20A, 20B, 21, 21A, 21B, 22, 22A,22B

    Neu:
    {  "adresse": [{"street_oi": "x11", "nr_von": "20",  "nr_bis": "20", "nrzusatz_von": "", "nrzusatz_bis": "" }]} => 20
    {  "adresse": [{"street_oi": "x11", "nr_von": "20",  "nr_bis": "20", "nrzusatz_von": "A", "nrzusatz_bis": "B" }]} => 20A, 20B
    {  "adresse": [{"street_oi": "x11", "nr_von": "20",  "nr_bis": "20", "nrzusatz_von": "", "nrzusatz_bis": "A" }]} => 20, 20A
    {  "adresse": [{"street_oi": "x11", "nr_von": "20",  "nr_bis": "20", "nrzusatz_bis": "" }]} => 20 (wenn nrzusatz_von leerer String ist kann man ihn auch weglassen.)
    {  "adresse": [{"street_oi": "x11", "nr_von": "20",  "nr_bis": "22", "nrzusatz_von": "B", "nrzusatz_bis": "" }]} => 20B, 21, 21A, 21B, 22
    {  "adresse": [{"street_oi": "x11", "nr_von": "20",  "nr_bis": "22", "nrzusatz_von": "B", "nrzusatz_bis": "A" }]} => 20B, 21, 21A, 21B, 22, 22A
    {  "adresse": [{"street_oi": "x11", "nr_von": "20",  "nr_bis": "22", "nrzusatz_von": "B" }]} => 20B, 21, 21A, 21B, 22, 22A,22B
    Reihenfolge wenn nr_von = nr_bis
    {  "adresse": [{"street_oi": "x11", "nr_von": "20",  "nr_bis": "20", "nrzusatz_von": "B", "nrzusatz_bis": "" }]} => x (keine Zuordnung)

#### Gebiete als Bild exportieren (Gebietskarten)

<http://domain/fernsteuerung/gebiet/image?nr=B421902002&ausgabe=default>

Gebiets-Nr. und Name der der Ausgabe müssen URL-encoded übergeben werden.

Es wird eine Karte mit den Umrissen eines Trägerbezirkes als Bilddatei erzeugt (JPG-Format).
Die Auswahl der Hintergrundkarte in den Kundeneinstellungen (z.B. basemap.de) wird berücksichtigt.

Bekannte Fehlermeldungen:

    {"text":"Ausgabe nicht gefunden","status":500}
    {"text":"Bezirk nicht gefunden","status":404}

### Bezirke

Der Bezirk (= Trägerbezirk) ist die übergeordnete Ebene, wenn zwei
Ebenen verfügbar sind. Aus einem oder mehreren Gebieten (= Zellen)
werden durch die Zuordnung Gebiet=\>Bezirk Bezirke gebildet. Auf dieser
Ebene werden keine Zuordnungen zu Gebäuden (Adressen) vorgenommen.

#### Bezirke abrufen

<http://domain/fernsteuerung/bezirk/>

Parameter (optional):

|         |                                                           |
|---------|-----------------------------------------------------------|
| nr      | Nummer(n) der Bezirke                                     |
| limit   | Limit                                                     |
| offset  | Offset                                                    |
| ausgabe | Name der Ausgabe (default=Aktuelle Ausgabe des Benutzers) |

Rückgabe:

    [{"nr":"12","name":"","privathaushalte":1,"gewerbebetriebe":2,"abonnenten":10,"starthaus":"1","zustellerhaus":"2","endhaus":"3"},{"nr":"13","name":"","privathaushalte":0,"gewerbebetriebe":0,"abonnenten":0,"starthaus":null,"zustellerhaus":null,"endhaus":null},{"nr":"14","name":"","privathaushalte":0,"gewerbebetriebe":0,"abonnenten":0,"starthaus":null,"zustellerhaus":null,"endhaus":null}]

Optionale Ausgabe wenn in Kundenverwaltung ausgewählt:

privathaushalte, gewerbebetriebe, werbeverweigerer, abonnenten  
starthaus, zustellerhaus, endhaus (Gebäude ID (oi))

#### Bezirke Hinzufügen/Updaten

<http://domain/fernsteuerung/bezirk/add_and_update>

Parameter:

|         |                                                                     |
|---------|---------------------------------------------------------------------|
| bezirk  | Bezirk Parameter                                                    |
| insert  | true(default) oder false. Nur neue Bezirk werden hinzugefügt        |
| update  | true(default) oder false. Bestehende Bezirke werden geupdated       |
| ausgabe | Name der Ausgabe (optional: default=Aktuelle Ausgabe des Benutzers) |
| option  | Optionen Parameter (optional) siehe unter Gebiet Updaten            |

Bezirk Parameter (Achtung: beim Einfügen von mehreren Bezirken muss
immer die gleiche Anzahl der Parameter angegeben werden):

|               |                                         |
|---------------|-----------------------------------------|
| nr            | Bezirknummer                            |
| name          | Bezirkname (optional)                   |
| starthaus     | oi Starthaus oder Objekt (optional)     |
| zustellerhaus | oi Zustellerhaus oder Objekt (optional) |
| endhaus       | oi Endhaus oder Objekt (optional)       |

Start- Zusteller- Endhaus als Objekt
([r2417](/redmine/projects/multiroute-go/repository/revisions/2417 "CS: #4871 API Gehfolge erweitert. API Zusteller-, Start- und Endhaus mit street_oi möglich."))
\|street_oi\|Straßenabschnitts-ID (required)\| \|hausnummer\|Hausnummer
(required)\| \|hausnummer_zusatz\|Hausnummer Zusatz (required)\|  
Beispiel:

    {
    "update": true,
    "insert": true, 
    "bezirk": [{"nr":"1200","name":"Bezirk 1","starthaus":"1","zustellerhaus":"2","endhaus":"3"},{"nr":"1300","name":"Bezirk 2","starthaus":null,"zustellerhaus":null,"endhaus":null}]
     }

#### Bezirke löschen

<http://domain/fernsteuerung/bezirk/delete>

Parameter

|         |                                                                    |
|---------|--------------------------------------------------------------------|
| nr      | Nummer des Bezirks/Nummern der Bezirke                             |
| ausgabe | Name der Ausgabe (optional: defaul=Aktuelle Ausgabe des Benutzers) |

    {
      nr: ["1","2"]
    }

#### Bezirksdefinition

<http://domain/fernsteuerung/bezirk/definition>

Parameter (optional)

|         |                                                           |
|---------|-----------------------------------------------------------|
| bezirk  | Nummer(n) der Bezirke                                     |
| limit   | Limit                                                     |
| offset  | Offset                                                    |
| ausgabe | Name der Ausgabe (default=Aktuelle Ausgabe des Benutzers) |

Rückgabe:

    [{"bezirk":"12","gebiet":["1","2","3","4"],"ausgabe":"1234"},{"bezirk":"13","gebiet":["5","6","7","8"],"ausgabe":"1234"}]

#### Bezirksdefinition Hinzufügen bzw. löschen

<http://domain/fernsteuerung/bezirk/add_definition>  
<http://domain/fernsteuerung/bezirk/delete_definition>

Parameter:

|         |                                                                                        |
|---------|----------------------------------------------------------------------------------------|
| gebiet  | Nummern der Gebiete                                                                    |
| bezirk  | Nummer des Bezirks                                                                     |
| ausgabe | Name der Ausgabe (optional default=Aktuelle Ausgabe des Benutzers)                     |
| append  | Modus beim Hinzufügen (optional default=true) ; mit false wird die Zuordnung ersetzt   |
| all     | Modus beim Löschen (optional default=false); mit true wird die Zuordnung wird gelöscht |

    {
      "gebiet": ["1","2","3"],
      "bezirk": "11",
      "ausgabe": "1234" 
    }

Bekannte Fehlermeldungen:

    {"text":"Ausgabe nicht gefunden","status":500}
    {"text":"Kein Gebiet übergeben","status":500}
    {"text":"Kein Bezirk übergeben","status":500}
    {"text":"Daten wurden nicht übernommen","status":500}

#### Bezirke als Bild exportieren (Bezirkskarten)

<http://domain/fernsteuerung/bezirk/image?nr=Bezirk%2011&ausgabe=2.%20Bezirk>

Bezirks-Nr. und Name der der Ausgabe müssen URL-encoded übergeben werden.

Es wird eine Karte mit den Umrissen eines Trägerbezirkes der übergeordneten Ebene als Bilddatei erzeugt (JPG-Format).
Die Auswahl der Hintergrundkarte in den Kundeneinstellungen (z.B. basemap.de) wird berücksichtigt.

Bekannte Fehlermeldungen:

    {"text":"Ausgabe nicht gefunden","status":500}
    {"text":"Bezirk nicht gefunden","status":404}

### Datenübernahme (individuell konfiguriert)

Nur neue Adressen  
<http://domain/fernsteuerung/adressen>

Alle Verteilbezirke und Zuordnungen  
<http://domain/fernsteuerung/definition>

Neue Adressen und Alle Verteilbezirke sowie Zuordnung  
<http://domain/fernsteuerung/adressen_definition>

### Zähllisten

<http://domain/fernsteuerung/zaehlliste/%3Cverteilbezirk_nummer%3E.pdf>
oder xlsx

Parameter (optional)

\|ausgabe\| Name der Ausgabe (default=Aktuelle Ausgabe des
Benutzers)\|  


    http://127.0.0.1:3000/fernsteuerung/zaehlliste/12.pdf

### ClickMap

<http://domain/fernsteuerung/click_map/>

Parameter:

|                  |                                                                    |
|------------------|--------------------------------------------------------------------|
| click_map        | Nummern der Gebiete                                                |
| verteilbezirk_nr | Nummern der Verteilbezirke                                         |
| ausgabe          | Name der Ausgabe (optional: defaul=Aktuelle Ausgabe des Benutzers) |

click_map Objekt:

|               |                             |                                                                                                                                  |
|---------------|-----------------------------|----------------------------------------------------------------------------------------------------------------------------------|
| one_bezirk    | true/false (default: false) |                                                                                                                                  |
| one_bezirk    | true                        | für einen Verteilbezirk mit/ohne Adresspunkte (Es wird für jeden angegebenen Verteilbezirk eine eigene Clickable Map angelegt)   |
| one_bezirk    | false                       | für mehrere Verteilbezirk ohne Adresspunkte (Es wird für alle angegebenen Verteilbezirke eine gemeinsame Clickable Map angelegt) |
| show_adressen | true/false (default: false) | Adressen werden auch angezeigt (funktioniert nur bei one_bezirk: true)                                                           |
| show_gehfolge | true/false (default: false) | Aktuellste Gehfolge wird auch angezeigt (funktioniert nur bei one_bezirk: true)                                                  |
| use_once      | true/false (default: false) | Einweg-Link (Link kann nur einmal aufgerufen werden)                                                                             |

    {
    "click_map": {"show_adressen": true, "one_bezirk": true, "use_once": false}, 
    "verteilbezirk_nr": ["B001056", "B001070"]
    }

one_bezirk:true Rückgabewert ist ein JSON Array:  

    [
    {"url":"http://domain/klick_karte/20/3d7ca9bc7996ea8e94690170a32820b2","verteilbezirk_nr":"B001056"},
    {"url":"http://domain/klick_karte/21/ce8927a1d7ba8ed49f520306e92d112b","verteilbezirk_nr":"B001070"}
    ]

one_bezirk:false Rückgabewert ist ein JSON Object:  

    {"url":"http://domain/klick_karte/23/d6aad99591c06d6e242f19ea44933f78"}

## Zusie

### Zusie Sync

Synchronisation mit Zusie  
Es werden die aktuellsten Gehfolgen einer Ausgabe zu Zusie übermittelt,
bzw. in Zusie gelöscht.

<http://domain/fernsteuerung/zusie/sync/>  
<http://domain/fernsteuerung/zusie/delete/>

Optionale Parameter:

|         |                                            |
|---------|--------------------------------------------|
| ausgabe | (default die vom User)                     |
| nr      | Nummern der Verteilbezirke, (default alle) |

    {"nr": ["B430501004"]}
