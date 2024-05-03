---
title: Lidmaatschappen ophalen
description: Leer hoe u abonnementen ophaalt met API's
role: Data Engineer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
source-git-commit: 84b72258789ba61016deb813e93bdca0ea142712
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# Abonnementen met API&#39;s ophalen {#retrieving-subscriptions-api}

## De profielen ophalen die zijn geabonneerd op een service

Dit is een procedure in twee stappen.

1. Haal de abonnements-URL voor de gewenste service op.
1. Voer een GET-aanvraag uit op de abonnements-URL. Het keert de lijst van abonnementen voor de dienst, met elk bijbehorend profiel terug.

>[!CAUTION]
>
>De REST-API retourneert de eigenschap &quot;href&quot;, die de te gebruiken URL bevat. <b>Gebruik altijd de URL in het antwoord om het volgende API-verzoek in te dienen</b>.

<br/>

***Voorbeeldverzoek***

Voer een verzoek van de GET uit om de dienst terug te winnen.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

De abonnements-URL voor de service wordt geretourneerd.

```
  {
    ...
    "messageType": "email",
    "name": "SVC1",
    "subscriptions": {
                "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/"
    },
    ...
  },
```

Voer een GET-aanvraag uit op de abonnements-URL.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

De lijst met abonnementen voor de service wordt weergegeven met elk gekoppeld profiel.

```
  {
    ...
    "service": ...,
    "serviceName": "SVC3",
    "subscriber": {
        "PKey": "<PKEY>",
        "email": "",
        "firstName": "John",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
        "lastName": "Doe",
    },
  }
```

## De services ophalen waarop een profiel is geabonneerd

Dit is een procedure in twee stappen.

1. Haal de abonnements-URL voor een bepaald profiel op.
1. Voer een verzoek van de GET op URL uit. Het keert de lijst van abonnementen voor het profiel, met elke bijbehorende dienst terug.

<br/>

***Voorbeeldverzoek***

Voer een verzoek van de GET uit om het profiel terug te winnen.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

De abonnements-URL voor het profiel wordt geretourneerd.

```
  {
    ...
    "postalAddress":...,
    "preferredLanguage": "none",
    "subscriptions": {
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions/"
    },
    ...
  }
```

Voer een GET-aanvraag uit op de abonnements-URL.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Het keert de lijst van de diensten terug waarop het profiel intekende.

```
  {
    ...
    "PKey": "<PKEY>",
    "created": "2017-03-03 10:54:00.363Z",
    "service": {
      "PKey": "<PKEY>",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
      "label": "Sport Newsletter",
      "name": "SVC1",
      "title": "Sport Newsletter (SVC1)"
    },
    ...
  }
```
