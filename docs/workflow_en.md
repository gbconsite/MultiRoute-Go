---
title: Basic workflow for MultiRoute Go!
description: How to get started the API in 6 steps
---

# Getting Started with the MultiRoute Go! API: From Addresses to Optimization

This guide outlines the steps required to obtain optimized routes using the MultiRoute Go! API, starting with an empty account.

## 1. Authentication

Authenticate using Basic Auth: `http://username:password@domain/`, replacing `username`, `password`, and `domain` with your credentials. For SaaS, the domain is `https://go.multiroute.de`.

## 2. Adding Addresses:

Add address data using the following endpoint:

```
http://domain/fernsteuerung/add_and_update_adresse
```

Submit a POST request with a JSON payload like this:

```json
{
  "update": true,
  "insert": true, 
  "adresse": [
    {
      "oi": "UNIQUE_BUILDING_ID_1",
      "longitude": 13.40123,
      "latitude": 52.52001,
      "plz": "10115",
      "ort": "Berlin",
      "strasse": "Example Street",
      "hausnummer": "1",
      "is_active": true,
      "privathaushalte": 1,
      "gewerbebetriebe": 0
    },
    // ... more addresses
  ]
}
```

Each address requires a unique `oi`, `longitude`, `latitude`, and `is_active` set to `true`. Include other relevant fields as needed.

## 3. Defining Territories

Define your delivery territories:

```
http://domain/fernsteuerung/gebiet/add_and_update
```

Use a POST request with a JSON payload:

```json
{
  "update": true,
  "insert": true, 
  "gebiet": [
    {
      "nr": "TERRITORY_NUMBER_1",
      "name": "Territory Name 1"
    },
    // ... more territories
  ]
}
```

## 4. Assigning Addresses to Territories

Assign addresses to territories using their unique `oi` identifier:

```
http://domain/fernsteuerung/gebiet/add_definition
```

Example:  Assigning addresses with `oi` values "BUILDING_ID_1" and "BUILDING_ID_2" to territory "TERRITORY_1" within the distribution "MY_DISTRIBUTION":

```json
{
  "oi": ["BUILDING_ID_1", "BUILDING_ID_2"],
  "gebiet": "TERRITORY_1",
  "ausgabe": "MY_DISTRIBUTION" 
}
```

## 5. Initiating Route Optimization

Start route calculation for a specific territory:

```
http://domain/fernsteuerung/gehfolge/berechnen?verteilbezirk=TERRITORY_NUMBER_1
```

Or for all territories within a distribution:

```
http://domain/fernsteuerung/gehfolgen/berechnen?ausgabe=MY_DISTRIBUTION
```


## 6. Retrieving Optimization Results

After the calculation completes, retrieve results (GPX, Excel, etc.) using the `gehfolge_id` returned from the previous step:

```
http://domain/fernsteuerung/gehfolge/{gehfolge_id}/gpx
http://domain/fernsteuerung/gehfolge/{gehfolge_id}/excel
// ... other formats
```

This workflow provides a clear path to managing address data, defining delivery territories, and generating optimized routes using the MultiRoute Go! API. Consult the full documentation for advanced options and parameters.
