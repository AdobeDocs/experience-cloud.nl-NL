---
title: Lidmaatschappen verwijderen
description: Leer hoe u abonnementen met API's kunt verwijderen
role: Data Engineer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
source-git-commit: 84b72258789ba61016deb813e93bdca0ea142712
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# Abonnementen met API&#39;s verwijderen {#mdeleting-subscriptions-api}

<!--NOTE TO WRITER: There are two duplicate headings that seem to have the same content. Delete one? Rename if different?-->

## Een serviceabonnement voor een specifiek profiel verwijderen {#deleting-service-subscription}

Dit is een procedure in drie stappen.

1. Haal de abonnements-URL voor het gewenste profiel op.
1. Voer een GET-aanvraag uit op de abonnements-URL.
1. Voer een verzoek van de DELETE op de gewenste dienst URL uit.

Als het verwijderingsverzoek is gelukt, is de status van het antwoord 204 Geen inhoud.

<br/>

***Voorbeeldverzoek***

In de onderstaande voorbeeldladingen ziet u hoe u een profiel van een service kunt afmelden. Voer eerst een GET-aanvraag uit om het profiel op te halen.

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

Het keert de lijst van abonnementen voor het geselecteerde profiel, met een URL voor elke geabonneerde dienst terug.

```
...
"service": {
  "PKey": "<PKEY>",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
  "label": "Sport Newsletter",
  "name": "SVC1",
  "title": "Sport Newsletter (SVC1)"
},
...
```

Voer een verzoek van de DELETE op de gewenste dienst URL uit.

```
-X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!-- + réponse -->

## Een serviceabonnement voor een specifiek profiel verwijderen

Dit is een procedure in drie stappen.

1. Haal de gewenste service en de abonnements-URL op.
1. Voer op de abonnements-URL een aanvraag voor GET uit om alle abonnementen op profielen op te halen.
1. Voer een DELETE-aanvraag uit op de gewenste profielabonnements-URL.

Als het verwijderingsverzoek is gelukt, is de status van het antwoord 204 Geen inhoud.

<br/>

***Voorbeeldverzoek***

Haal het servicerecord op.

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
  "mode": "newsletter",
  "name": "SVC3",
  "subScenarioEventType": "subscriptionEvent",
  "subscriptions": {
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/"
  },
  "targetResource": "profile",
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

De lijst met abonnementen voor de geselecteerde service wordt geretourneerd, met een URL (href) voor elk profielabonnement.

```
{
  "PKey": "<PKEY>",
  "created": "2019-03-26 08:58:04.764Z",
  "email": "",
  "expirationDate": "",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/<PKEY>",
  "metadata": "subscriptionRcp",
  "service": ...,
  "serviceName": "SVC3",
  "subscriber": ...,
  ...
}
```

Voer een DELETE-aanvraag uit op de gewenste profielabonnements-URL.

```
-X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!-- + réponse -->
