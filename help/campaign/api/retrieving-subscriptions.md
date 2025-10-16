---
title: Lidmaatschappen ophalen
description: Leer hoe u abonnementen ophaalt met API's
role: Developer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde Campaign Standard-gebruikers"
exl-id: 6d935074-3196-45c5-97cd-ccb7c80bbba8
source-git-commit: 11c49b273164b632bcffb7de01890c6f9d7ae9c2
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
>De REST-API retourneert de eigenschap &quot;href&quot;, die de te gebruiken URL bevat. <b> gebruikt altijd URL in de reactie om het verdere API verzoek </b> te maken.

<br/>

***verzoek van de Steekproef***

Voer een GET-verzoek uit om de service op te halen.

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
1. Voer een GET-aanvraag uit op de URL. Het keert de lijst van abonnementen voor het profiel, met elke bijbehorende dienst terug.

<br/>

***verzoek van de Steekproef***

Voer een GET-aanvraag uit om het profiel op te halen.

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
